---
title: Android appcompat-v7 包样式
tags: android
toc: true
description: Android appcompat-v7包 样式
categories: android
date: 2016-09-19 11:06:58
---



### 问题1 listview文字颜色变浅
今天遇到一个超级郁闷的问题
本来是在网上下载了一个Demo小程序,想研究一下RecyclerView,然后写一个简单的listview
原本下载的程序运行出来是这样的:

![RecyclerView](\images\android\device-1.png)

但是我自己编写的Demo运行出来却是这样的
<!-- more -->

![RecyclerView](\images\android\device-2.png)

很明显文字颜色变浅了啊.. ....

这个问题找了好久,一直以为是我RecyclerView写的ViewHolder或者加载的样式不对
结果发现居然是
`appcompat-v7`包的版本的问题....坑爹...
原来Demo版本是这个
```shell
    compile 'com.android.support:appcompat-v7:22.1.1'
    compile 'com.android.support:recyclerview-v7:22.2.1'
```
然后我用的版本是
```shell
    compile 'com.android.support:appcompat-v7:22.2.1'
    compile 'com.android.support:recyclerview-v7:22.2.1'
```

修正后问题解决

### 问题2 点击效果不正确
原本的Demo点击是有点击效果的,就是原生点击效果
![RecyclerView](\images\android\device-recycler.gif)

但是我写的Demo就是点上去啥效果的都没.

之后对比了代码发现一个地方
在`adapter`里面在初始化的时候会传入父`View`
```java
        RecyclerView exampleList = (RecyclerView) findViewById(R.id.example_list);
        exampleList.setHasFixedSize(true);
        exampleList.setLayoutManager(new LinearLayoutManager(this));
		//这里将Activity传入了
        exampleList.setAdapter(new ExampleAdapter(this, getExamples()));
```

然后在设置`item`的Listener的时候,这个OnClick事件,放在哪儿的问题
我之所以没有点击效果就是因为我把事件放在`ViewHolder`的`TextView`上面了.
这样点击效果当然就是`TextView`点击效果了,而且它没有设置什么点击效果自然也没有了...

```java
public class ExampleAdapter extends RecyclerView.Adapter<ExampleAdapter.ViewHolder> {

    private Context mContext;
    private List<ExampleActivityAndName> mExamples;

    public ExampleAdapter(Context context, List<ExampleActivityAndName> examples) {
        mContext = context;
        mExamples = examples;
    }

    @Override
    public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType) {
        View v = LayoutInflater
                .from(mContext)
                .inflate(R.layout.example_list_item, parent, false);
        return new ViewHolder(v);
    }

    @Override
    public void onBindViewHolder(final ViewHolder holder, final int position) {
        holder.mNameDisplay.setText(mExamples.get(position).mExampleName);
//就是这个地方的itemView设置的时候
//我之前写的是holder.mNameDisplay.setOnClickListener... ...
        holder.itemView.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent exampleIntent = new Intent(mContext, mExamples.get(position).mExampleActivityClass);
                //mContext.startActivity(exampleIntent);
            }
        });
    }

    @Override
    public int getItemCount() {
        return mExamples.size();
    }

    public static class ViewHolder extends RecyclerView.ViewHolder {

        public final TextView mNameDisplay;

        public ViewHolder(View itemView) {
            super(itemView);
            mNameDisplay = (TextView) itemView.findViewById(R.id.name_display);
        }
    }
}
```



