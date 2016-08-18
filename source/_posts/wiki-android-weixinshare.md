---
title: 安卓微信朋友圈分享功能
tags:
  - android
  - 微信
  - 朋友圈分享
categories:
  - wiki-Android
description: 实现安卓微信朋友圈分享功能记录.
date: 2016-08-12 17:22:19
---

### 准备工作 ###
阅读[微信的官方文档](https://open.weixin.qq.com/cgi-bin/showdocument?action=dir_list&t=resource/res_list&verify=1&id=1417751808&token=&lang=zh_CN) 在官方文档的内容里罗列了微信WPI开发的基本步骤.
1.申请你的AppID
2.下载微信终端开发工具包
[SDK的下载](https://open.weixin.qq.com/cgi-bin/showdocument?action=dir_list&t=resource/res_list&verify=1&id=open1419319167&lang=zh_CN)
3.搭建开发环境
4.在代码中使用开发工具包
这里有一个Demo程序蛮重要的,很简练.
<!-- more -->
### 需求 ###
点击右上角分享按钮,弹出下拉框,选择相应"微信"或者"朋友圈"
调出微信APP进行相关内容的分享.
![微信分享上拉选项](\images\wiki\wiki-android-weixinshare\1.png)

### 导入SDK包 ###
1.将开发工具包中libs目录下的libammsdk.jar复制到项目的lib目录中
![工程导入包](\images\wiki\wiki-android-weixinshare\3.png)
2.在你需要使用微信终端API的文件中导入相应的类。
```java
import com.tencent.mm.sdk.openapi.WXTextObject;
```
3.AndroidManifest.xml 设置
添加必要的权限支持:
```xml
<uses-permission android:name="android.permission.INTERNET"/> 
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/> 
<uses-permission android:name="android.permission.ACCESS_WIFI_STATE"/>
<uses-permission android:name="android.permission.READ_PHONE_STATE"/> 
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/> 
```
### 上拉菜单 ###
`PopupWindow`的实现.

```java
public class SNSSharePopupWindows extends PopupWindow {
    private ImageButton mWeiXinBtn, mWeiBoBtn, mPengYouquanBtn, mQQBtn;
    private WechatShareManager mWechatShareManager;
    private WechatShareManager.ShareContentWebpage mShareContentWebpage;
    private final Toast mToast;

    /**
     * @param mContext
     * @param parent
     */
    public SNSSharePopupWindows(final Activity mContext, View parent) {
        super(mContext);

        mWechatShareManager = WechatShareManager.getInstance(mContext);
        mToast = Toast.makeText(mContext, "", Toast.LENGTH_SHORT);

        final View view = View.inflate(mContext,
                R.layout.item_popupsharewindows, null);
        view.startAnimation(AnimationUtils.loadAnimation(mContext,
                R.anim.fade_ins));
        final LinearLayout linearLayout = (LinearLayout) view
                .findViewById(R.id.share_ll_popup);
        linearLayout.startAnimation(AnimationUtils.loadAnimation(mContext,
                R.anim.push_bottom_in));

        setWidth(ViewGroup.LayoutParams.MATCH_PARENT);
        setHeight(ViewGroup.LayoutParams.MATCH_PARENT);
        setBackgroundDrawable(new BitmapDrawable());
        setFocusable(true);
        setOutsideTouchable(true);
        setContentView(view);
        showAtLocation(parent, Gravity.BOTTOM, 0, 0);
        update();

        //触摸分享框外面的部分,分享弹出框消失.
        view.setOnTouchListener(new View.OnTouchListener() {
            public boolean onTouch(View v, MotionEvent event) {
                int height = view.findViewById(R.id.share_ll_popup).getTop();
                int y = (int) event.getY();
                if (event.getAction() == MotionEvent.ACTION_UP) {
                    if (y < height) {
                        dismiss();
                    }
                }
                return true;
            }
        });

        //四个分享按钮
        mWeiXinBtn = (ImageButton) view
                .findViewById(R.id.item_sharepopupwindows_weixin);
        mPengYouquanBtn = (ImageButton) view
                .findViewById(R.id.item_sharepopupwindows_pengyouquan);
        mWeiBoBtn = (ImageButton) view
                .findViewById(R.id.item_sharepopupwindows_weibo);
        mQQBtn = (ImageButton) view
                .findViewById(R.id.item_sharepopupwindows_qq);

        mWeiXinBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                //检测是否安装微信
                if (!checkSNSAvaliable(mWeiXinBtn))
                    return;
                if (null != mShareContentWebpage) {
                    mWechatShareManager.shareByWebchat(mShareContentWebpage,
                            WechatShareManager.WECHAT_SHARE_TYPE_SESSION);
                    //分享成功与否,都设为分享结束,对话框消失.
                    dismiss();
                }
            }
        });
        mPengYouquanBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if (!checkSNSAvaliable(mPengYouquanBtn))
                    return;
                if (null != mShareContentWebpage) {
                    mWechatShareManager.shareByWebchat(mShareContentWebpage,
                            WechatShareManager.WECHAT_SHARE_TYPE_TIMELINE);
                    //分享成功与否,都设为分享结束,对话框消失.
                    dismiss();
                }
            }
        });
    }
```

`WechatShareManager`是一个单例模式的类,负责管理所有的微信相关的内容的分享.
检测微信安装
```java
    /**
     * 检测手机上是否安装了微信
     */
    public boolean isWebchatAvaliable() {
        try {
            mContext.getPackageManager().getPackageInfo(WECHAT_PACKAGE_NAME, PackageManager.GET_ACTIVITIES);
            return true;
        } catch (Exception e) {
            return false;
        }
    }
```
布局文件 `item_popupsharewindows.xml`
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@android:drawable/screen_background_dark_transparent">

    <LinearLayout
        android:id="@+id/share_ll_popup"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:background="@color/white"
        android:orientation="vertical" >

        <TextView
            android:layout_width="match_parent"
            android:layout_height="1dp"
            android:background="@drawable/list_line" />

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="55dp"
            android:orientation="horizontal"
            android:gravity="center">

            <TextView
                android:id="@+id/share_title"
                android:background="@drawable/bg_center_selector"
                android:textColor="@color/gray"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:gravity="center"
                android:layout_centerVertical="true"
                android:layout_gravity="center"
                android:textSize="22sp"
                android:text="分享"/>
        </LinearLayout>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="0.5dp"
            android:background="@drawable/list_line" />

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="120dp"
            android:padding="@dimen/dimen_10dp"
            android:orientation="horizontal" >

            <ImageButton
                android:id="@+id/item_sharepopupwindows_weixin"
                android:layout_width="wrap_content"
                android:layout_height="100dp"
                android:layout_weight="1"
                android:background="@drawable/bg_center_selector"
                android:src="@drawable/share_weixin_btn"
                android:scaleType="center"
             />
            <ImageButton
                android:id="@+id/item_sharepopupwindows_pengyouquan"
                android:layout_width="wrap_content"
                android:layout_height="100dp"
                android:layout_weight="1"
                android:background="@drawable/bg_center_selector"
                android:src="@drawable/share_pengyouquan_btn"
                android:scaleType="center"
                />
            <ImageButton
                android:id="@+id/item_sharepopupwindows_qq"
                android:layout_width="wrap_content"
                android:layout_height="100dp"
                android:layout_weight="1"
                android:background="@drawable/bg_center_selector"
                android:src="@drawable/share_qq_btn"
                android:scaleType="center"
                />
            <ImageButton
                android:id="@+id/item_sharepopupwindows_weibo"
                android:layout_width="wrap_content"
                android:layout_height="100dp"
                android:layout_weight="1"
                android:background="@drawable/bg_center_selector"
                android:src="@drawable/share_weibo_btn"
                android:scaleType="center"
                />
        </LinearLayout>
    </LinearLayout>

</RelativeLayout>
```
### 分享流程 ###
分享过程主要是在`WeixinShareManager`里面完成的.下面来看看`WeixinShareManager` 做什么的.
```java
 ... ...
	//单例模式初始化
    private WechatShareManager(Context context) {
        this.mContext = context;
        initWechatShare(context);
    }

 ... ...

	//api注册
	private void initWechatShare(Context context) {
        if (mWXApi == null) {
            mWXApi = WXAPIFactory.createWXAPI(context, WECHAT_APP_ID, true);
        }
        mWXApi.registerApp(WECHAT_APP_ID);
    }

 ... ...

    /*
     * 分享链接
     */
    private void shareWebPage(ShareContent shareContent, int shareType) {
		// 初始化一个WXTextObject对象
        WXWebpageObject webpage = new WXWebpageObject();
        webpage.webpageUrl = shareContent.getURL();
        // 用WXTextObject对象初始化一个WXMediaMessage对象
        WXMediaMessage msg = new WXMediaMessage(webpage);

		// 发送文本类型的消息时，title字段不起作用
        msg.title = shareContent.getTitle();
        //截取最大长度的标题
        if (msg.title.length() >= TITILE_SIZE)
            msg.title = msg.title.substring(0, TITILE_SIZE - 1);

        msg.description = shareContent.getContent();
        //截取最大长度的描述
        if (msg.description.length() >= CONTENT_SIZE)
            msg.description = msg.description.substring(0, CONTENT_SIZE - 1);

        Logger.Log(WechatShareUtil.TAG, "getImageURL " + shareContent.getImageURL() +
                "\n getPictureResource " + shareContent.getPictureResource() +
                "\n getTitle" + shareContent.getTitle() +
                "\n getContent"  + shareContent.getContent() +
                "\n getURL" + shareContent.getURL());

        boolean useDefaultImage = StringUtils.StrIsNull(shareContent.getImageURL())? true:false;
        Bitmap thumb = null;
        if (!useDefaultImage) {
            thumb = QDApplicationContext.imageLoader.loadImageSync(shareContent.getImageURL(), new ImageSize(THUMB_SIZE,THUMB_SIZE));
        } else {
            thumb = BitmapFactory.decodeResource(mContext.getResources(), shareContent.getPictureResource());
        }

        if (thumb == null) {
            thumb = BitmapFactory.decodeResource(mContext.getResources(), R.drawable.hos_default_logo);
        } else {
            msg.thumbData = WechatShareUtil.bmpToByteArray(thumb, true);
        }

		// 构造一个Req
        SendMessageToWX.Req req = new SendMessageToWX.Req();
		// transaction字段用于唯一标识一个请求 img,video,text等
        req.transaction = buildTransaction("webpage");
        req.message = msg;
        req.scene = shareType;
        // 调用api接口发送数据到微信
        mWXApi.sendReq(req);
    }
```
从上面核心代码看,`WeixinShareManager`做了这样几件事情:
1.注册微信API
2.构造WXMediaMessage
3.初始化SendMessageToWX.Req,并指定分享类型(网页,图片,文本等等)
4.发送分享请求.

这样就完成了整个的分享过程.
图片,文本什么的类似.
{% label 关于缩略图 warning %}
{% alert warning %}
微信关于缩略图的大小有严格的限制的,如果超出限制会分享不成功.(`没有警告,就是分享不成功`)
我这里采用了100x100的大小做了压缩,我试过120x120不能成功.
{% endalert %}
{% textcolor info %}
腾讯官方给的Demo里面给出的图片分享的缩略图限制是150x150的.API文档里说明是不超过10M.缩略图大小不超过32KB
但是没有给出网页分享的缩略图大小.
{% endtextcolor %}
![微信SDK截图](\images\wiki\wiki-android-weixinshare\2.png)
具体的bitmap占内存大小问题,这篇文章可以收藏 [Android 开发绕不过的坑：你的 Bitmap 究竟占多大内存？](http://bugly.qq.com/bbs/forum.php?mod=viewthread&tid=498)

### 分享之后 ###
那么如何收到分享成功或者失败的通知呢.
微信接受的入口类在`packagename.wxapi`包下，它的分享结果回调也在这个类
微信会在`packagename.wxapi`找这个回调接口的类，这个类必须是集成了`Activity`的类，并且实现`IWXAPIEventHandler`接口
{% textcolor info %}
这个类的名字一定要是`WXEntryActivity.java`；
{% endtextcolor %}
这样，你就可以接受到微信回调结果了：
1.现在你的当前工程目录下新建wxapi文件夹并添加类`WXEntryActivity.java`
![微信分享上拉选项](\images\wiki\wiki-android-weixinshare\4.png)
2.这个类`WXEntryActivity.java`在`onCreate`中注册API.
3.重写`onReq`回调函数,提示成功或者失败.

`WXEntryActivity`
```java

public class WXEntryActivity extends Activity implements IWXAPIEventHandler{
	
	private static final int TIMELINE_SUPPORTED_VERSION = 0x21020001;
	
	private Button gotoBtn, regBtn, launchBtn, checkBtn;
	
	// IWXAPI 是第三方app和微信通信的openapi接口
    private IWXAPI api;
	
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.entry);
        
        // 通过WXAPIFactory工厂，获取IWXAPI的实例
    	api = WXAPIFactory.createWXAPI(this, Constants.APP_ID, false);

    	regBtn = (Button) findViewById(R.id.reg_btn);
    	regBtn.setOnClickListener(new View.OnClickListener() {
			
			@Override
			public void onClick(View v) {
				// 将该app注册到微信
			    api.registerApp(Constants.APP_ID);    	
			}
		});
    	
        gotoBtn = (Button) findViewById(R.id.goto_send_btn);
        gotoBtn.setOnClickListener(new View.OnClickListener() {
			
			@Override
			public void onClick(View v) {
		        startActivity(new Intent(WXEntryActivity.this, SendToWXActivity.class));
		        finish();
			}
		});
        
        launchBtn = (Button) findViewById(R.id.launch_wx_btn);
        launchBtn.setOnClickListener(new View.OnClickListener() {
			
			@Override
			public void onClick(View v) {
				Toast.makeText(WXEntryActivity.this, "launch result = " + api.openWXApp(), Toast.LENGTH_LONG).show();
			}
		});
        
        checkBtn = (Button) findViewById(R.id.check_timeline_supported_btn);
        checkBtn.setOnClickListener(new View.OnClickListener() {
			
			@Override
			public void onClick(View v) {
				int wxSdkVersion = api.getWXAppSupportAPI();
				if (wxSdkVersion >= TIMELINE_SUPPORTED_VERSION) {
					Toast.makeText(WXEntryActivity.this, "wxSdkVersion = " + Integer.toHexString(wxSdkVersion) + "\ntimeline supported", Toast.LENGTH_LONG).show();
				} else {
					Toast.makeText(WXEntryActivity.this, "wxSdkVersion = " + Integer.toHexString(wxSdkVersion) + "\ntimeline not supported", Toast.LENGTH_LONG).show();
				}
			}
		});
        
        api.handleIntent(getIntent(), this);
    }

	@Override
	protected void onNewIntent(Intent intent) {
		super.onNewIntent(intent);
		
		setIntent(intent);
        api.handleIntent(intent, this);
	}

	// 微信发送请求到第三方应用时，会回调到该方法
	@Override
	public void onReq(BaseReq req) {
		switch (req.getType()) {
		case ConstantsAPI.COMMAND_GETMESSAGE_FROM_WX:
			goToGetMsg();		
			break;
		case ConstantsAPI.COMMAND_SHOWMESSAGE_FROM_WX:
			goToShowMsg((ShowMessageFromWX.Req) req);
			break;
		default:
			break;
		}
	}

	// 第三方应用发送到微信的请求处理后的响应结果，会回调到该方法
	@Override
	public void onResp(BaseResp resp) {
		int result = 0;
		
		switch (resp.errCode) {
		case BaseResp.ErrCode.ERR_OK:
			result = R.string.errcode_success;
			break;
		case BaseResp.ErrCode.ERR_USER_CANCEL:
			result = R.string.errcode_cancel;
			break;
		case BaseResp.ErrCode.ERR_AUTH_DENIED:
			result = R.string.errcode_deny;
			break;
		default:
			result = R.string.errcode_unknown;
			break;
		}
		
		Toast.makeText(this, result, Toast.LENGTH_LONG).show();
	}
	
	private void goToGetMsg() {
		Intent intent = new Intent(this, GetFromWXActivity.class);
		intent.putExtras(getIntent());
		startActivity(intent);
		finish();
	}
	
	private void goToShowMsg(ShowMessageFromWX.Req showReq) {
		WXMediaMessage wxMsg = showReq.message;		
		WXAppExtendObject obj = (WXAppExtendObject) wxMsg.mediaObject;
		
		StringBuffer msg = new StringBuffer(); // 组织一个待显示的消息内容
		msg.append("description: ");
		msg.append(wxMsg.description);
		msg.append("\n");
		msg.append("extInfo: ");
		msg.append(obj.extInfo);
		msg.append("\n");
		msg.append("filePath: ");
		msg.append(obj.filePath);
		
		Intent intent = new Intent(this, ShowFromWXActivity.class);
		intent.putExtra(Constants.ShowMsgActivity.STitle, wxMsg.title);
		intent.putExtra(Constants.ShowMsgActivity.SMessage, msg.toString());
		intent.putExtra(Constants.ShowMsgActivity.BAThumbData, wxMsg.thumbData);
		startActivity(intent);
		finish();
	}
}
```
## 后话 ##
整个过程差不多就是这样.
后续再慢慢做补充.
关于完成这个功能的时候,我遇到的坑就是缩略图大小问题,后来解决掉了.
这一块儿有时间还得研究研究~.