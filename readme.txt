首先推荐一篇文章：http://zhuanlan.zhihu.com/kaede/20564614 ;
1. accessibilityservice 目录下
AccessibilityService  是一个辅助类，可以监听我们手机的焦点，窗口变化，按钮点击等等
2. accounts目录
 AccountAuthenticatorActivity
AccountManager
AccountManagerService
3. animation目录
Animator  AnimatorListener
AnimatorInflater 将xml动画转换为Animator
AnimatorSet
Keyframe 
LayoutTransition
做项目的时候应该碰到这种问题：根据不同条件显示或者隐藏一个控件或者布局，我们能想到的第一个方法就是 调用View.setVisibility（）方法。虽然实现了显示隐藏效果，但是总感觉这样的显示隐藏过程很僵硬，让人不是很舒服，那么有没有办法能让这种显示隐藏有个过渡的动画效果呢？答案是肯定的，不言而喻就是LayoutTransition类
android:animateLayoutChanges="true"
或者代码添加更好的动画

TimeInterpolator 时间补间

ValueAnimator  

PropertyValuesHolder

 4. annotation目录
BinderThread
MainThread UiThread
NonNull
ullable
RequiresPermission 
SdkConstant
Widget
5. app目录
    activity 目录  一些测试activity
    admin目录
        DeviceAdminInfo
        DevicePolicyManager 
    assist 目录
    backup目录
        BackupAgent
         
    job目录
        JobScheduler
        JobService
    trust目录
    usage目录
        NetworkStatsManager
        UsageStatsManager
    ActionBar 
    Activity  

6.appwidget目录
    AppWidgetManager
    AppWidgetHostView
    

content
    pm
        PackageItemInfo---ApplicationInfo
        ComponentInfo  PackageItemInfo---ComponentInfo  
        PackageItemInfo---ComponentInfo---ActivityInfo
        PackageInfo  对应于AndroidManifest.xml的所有信息  里边有个比较重要的信息：firstInstallTime  lastUpdateTime  applicationInfo 对应<application>  activities所有activity  receivers services providers  instrumentation permissions requestedPermissions signatures .......
        ApplicationInfo  应用程序信息  重要：taskAffinity processName app进程名称默认和packagename一样 className  fullBackupContent resourceDirs sharedLibraryFiles dataDir nativeLibraryDir targetSdkVersion  loadDefaultIcon() 
        ActivityInfo activity 信息  launchMode taskAffinity screenOrientation  softInputMode getThemeResource() 如果activity没有设置them，使用app的them  
        ConfigurationInfo 配置信息 reqTouchScreen 配置设备的触屏模式：TOUCHSCREEN_STYLUS TOUCHSCREEN_FINGER reqKeyboardType设置键盘模式  KEYBOARD_NOKEYS  ....   
        FeatureGroupInfo  AndroidManifest.xml's  <feature-group>     
        FeatureInfo AndroidManifest.xml's  <uses-feature>  
        InstrumentationInfo   PackageItemInfo--- InstrumentationInfo   AndroidManifest.xml's  instrumentation
        IntentFilterVerificationInfo         
        KeySet  AndroidManifest.xml 应用程序之间相互信任的值 
        Intent LabeledIntent(带有label/icon的Intent) 
        LauncherActivityInfo  可以查询activity的一些信息
        LauncherApps  startMainActivity()
        LimitedLengthInputStream 限制长度输入流
        MacAuthenticatedInputStream MAC加密授权输入流 
        ManifestDigest 配置摘要 
        PackageInfoLite 精简的pageinfo
        PackageInstaller 可以安装 删除 更新 设备上的app getAllSessions getMySessions Session SessionParams SessionInfo
        PackageManager 通过Context#getPackageManager 得到PackageManager 里边定义了2000多行(总共4000多行代码)的常量，包括各种功能feature常量 定位 NFC  温度  重力  ....   各种获取activity receiver  service 权限...的方法 
        PackageParser 解析package的 
        PathPermission 路径读写权限
        PermissionGroupInfo  PackageItemInfo ---PermissionGroupInfo  
        PermissionInfo  PackageItemInfo --- PermissionInfo  AndroidManifest.xml's  permission
        ProviderInfo   ComponentInfo---ProviderInfo   
        ResolveInfo 从intent查询的信息
        ServiceInfo ComponentInf---ServiceInfo       
        Signature 签名
        VerifierDeviceIdentity 
        VerifierInfo PackageManagerService中使用验证package的
    res
        AssetFileDescriptor  asset 文件 
        AssetManager  asset文件管理器  open 读文件  openNonAsset 打开一个非asset的文件   getResource().getAssetManager()
        BridgeResources 不能编译成二进制的资源文件
        ColorStateList item android:state_focused="true" android:color="@color/testcolor1"/  映射  color -- state
              CompatibilityInfo 兼容性信息
              Configuration 配置  Configuration config = getResources().getConfiguration()  代表应用程序  以及 设备的配置信息 such as input modes, screen size and screen orientation   
              ConstantState   A cache class that can provide new instances of a particular resource which may change depending on the current {@link Resources.Theme} or {@link Configuration}
              DrawableCache   
              ObbScanner    can Opaque Binary Blob (OBB) files 
              Resources  资源  高于 asset  ，Resources是app 除asset的资源 android.content.Context#getResources getResources()  编译器会把 Resources  编译成二进制  /res    openRawResource 
              TypedArray  Container for an array of values that were retrieved with {@link Resources.Theme#obtainStyledAttributes(AttributeSet, int[], int, int)} or {@link Resources#obtainAttributes}.  Be sure to call {@link #recycle} when done with them     

    AbstractThreadedSyncAdapter  主要用于执行Account相关内容（比如Contact）的同步操作。它是对 Account的内容（比如contact）进行同步操作的适配器   http://blog.csdn.net/hudashi/article/details/7350020
    AsyncQueryHandler 异步查询处理  继承 Handler   处理类似ContentResolver 的查询  http://blog.csdn.net/hudashi/article/details/6896356
    Loader 异步加载数据   参考  android.app.LoaderManager  
    AsyncTaskLoader  继承Loader  异步任务加载    使用AsyncTask 处理任务    例如从包管理器中加载应用程序  参考  android.app.LoaderManager  
    BroadcastReceiver    
    ClipData  粘贴板数据
    ClipDescription 描述  ClipData  
    ClipboardManager extends android.text.ClipboardManager
    http://blog.csdn.net/easy_gemini/article/details/38019351 
    ComponentName  标识一个应用程序的组件  activity  service  broadcast  ContentProvder    mPackage  mClass
    ComponentCallbacks    activity  service  ContentProvder  application  的callback
    ComponentCallbacks2 extends ComponentCallbacks  onTrimMemory 
    参考  ：http://www.cnblogs.com/xiajf/p/3993599.html 
    ContentProvider implements ComponentCallbacks2
    ContentProviderClient  ContentResolver#acquireContentProviderClient 
    ContentUris 
    ContentResolver 
    ContentValues  键值对（HashMap实现的）  被ContentResolver所使用  
    Context    应用程序全局的环境信息global information about an application environment  getAssets  getResources getPackageManager getContentResolver  getMainLooper（和Looper.getMainLooper()一样）getApplicationContext（返回应用程序全局的）  getString（getResource().getString） obtainStyledAttributes  getSharedPreferences  openFileOutput getFilesDir  getExternalFilesDir(android.os.Environment#getExternalStorageDirectory())   getCacheDir  getExternalCacheDir  openOrCreateDatabase   getDatabasePath startActivityForResult startActivity startActivities sendBroadcast registerReceiver  unregisterReceiver startService bindService  unbindService  getSystemService 
    DialogInterface 
    Entity (ContentValues) 
    IntentSender Intent IntentFilter
    ServiceConnection
    SharedPreferences Editor  
    UriMatcher  matching URIs in content providers  addURI  match      uri的链式结构 
     
         


util
    ArrayMap  ArraySet  IntArray LongArray  LongSparseArray  LongSparseLongArray  MapCollections  SparseLongArray  SparseIntArray  SparseBooleanArray SparseArray 
    AtomicFile AtomicFile首先不是用来代替File的，而是作为File的辅助类从在，AtomicFile的作用是实现事务性原子操作，即文件读写必须完整，适合多线程中的文件读写操作。用来实现多线程中的文件读写的安全操作
       Base64  Base64InputStream  Base64OutputStream
       Singleton  非常不错的工具
       ContainerHelpers 二分查找工具
       DisplayMetrics 设备分辨率 等信息
       Size  描述宽高的工具  px  SizeF 单位任意的大小工具
       DayOfMonthCursor  MonthDisplayHelper
       EventLog  /system/etc/event-log-tags 
       FastImmutableArraySet 
       FloatMath  Math   数学工具
       MathUtils  数学工具
       Property FloatProperty  IntProperty  ReflectiveProperty
       GridScenario 一个  gridview activity 类似 Android staggered grid   
       ListScenario  一个   listview  activity
       ScrollViewScenario  一个 scrollview activity 
       JsonWriter  JsonReader
       LayoutDirection  
       Log  日志工具  Slog
       LruCache  
       MutableLong  MutableInt  MutableBoolean MutableByte ........       
       Pair  非常好用的元组    数据不可以修改  类似Python的元组
       Printer PrintStreamPrinter PrintWriterPrinter PrefixPrinter  StringBuilderPrinter 
       Pools 池工具  SynchronizedPool  SimplePool
       Patterns 正则表达式模式
       PathParser  
       Range  数据范围工具   
       Rational  有理数 
       Spline  曲线  （看到惊喜了，O(∩_∩)O~）LinearSpline 线性曲线  MonotoneCubicSpline  单调立方曲线
       StateSet  View 的状态集 
       TimingLogger  记录method花费时间日志工具
        TimedRemoteCaller  一个异步调用的工具
       TimeUtils  时间工具 
        TrustedTime  
       NtpTrustedTime  NTP时间工具 
       TypedValue 资源文件值android.content.res.Resources 
        XmlPullAttributes  xml  资源属性  
        Xml  xml资源解析  ..... 
text
    format
        Formatter  
        Time  TimeFormatter   isLeap  DateFormat    DateUtils  formatDateRange 
    method  输入
        TransformationMethod 输入转换 如：passwd  换行  TransformationMethod2 extends TransformationMethod
        ReplacementTransformationMethod implements TransformationMethod 替换输入  getOriginal -->getReplacement
        HideReturnsTransformationMethod extends ReplacementTransformationMethod  隐藏回车  \r--->\uFEFF 零宽不换行空格
        SingleLineTransformationMethod extends ReplacementTransformationMethod 单行输入  '\n', '\r'  --->' ', '\uFEFF'
        MetaKeyKeyListener 封装 了一个元 key 的动作状态  如果SHIFT ALT  SYM handleKeyDown(long, int, KeyEvent)} and
 * {@link #getMetaState(long)} operate on a meta key    getMetaState
        KeyListener converting text key events into edit operations on an Editable class  处理硬件输入，软输入使用InputMethod
        BaseKeyListener extends MetaKeyKeyListener implements KeyListener   backspace 删除  forwardDelete  deleteSelection deleteLine  
        AllCapsTransformationMethod implements TransformationMethod2  所有字母大写转换
        MovementMethod  onKeyDown  onKeyUp onTouchEvent  onGenericMotionEvent onTrackballEvent 
        BaseMovementMethod implements MovementMethod  各种动作   handleMovementKey  左右上下移动处理  key的处理
        ArrowKeyMovementMethod extends BaseMovementMethod implements MovementMethod   提供光标移动和选择
        ScrollingMovementMethod extends BaseMovementMethod implements MovementMethod  滚动text
        LinkMovementMethod extends ScrollingMovementMethod  遍历 text 的links，如果需要滚动则滚动  支持links上的点击  ClickableSpan[] link
        PasswordTransformationMethod implements TransformationMethod, TextWatcher  char DOT = '\u2022'  密码  
        NumberKeyListener extends BaseKeyListener   implements InputFilter 数字输入键监听  getAcceptedChars  可以接受的输入字符
        DateKeyListener extends NumberKeyListener   日期   
        DigitsKeyListener extends NumberKeyListener    数子 isSignChar 
        DialerKeyListener extends NumberKeyListener  电话拨号  拨号器   InputType.TYPE_CLASS_PHONE   '0', '1', '2', '3', '4', '5', '6', '7', '8', '9', '#', '*',      '+', '-', '(', ')', ',', '/', 'N', '.', ' ', ';'
        MultiTapKeyListener extends BaseKeyListener  implements SpanWatcher  12键输入
        QwertyKeyListener extends BaseKeyListener  全键盘  qwerty keyboards
        TextKeyListener extends BaseKeyListener implements SpanWatcher  正常的text 输入
        
        WordIterator implements Selection.PositionIterator  以单词的方式移动光标BreakIterator#getWordInstance()}
        CharacterPickerDialog 字符选择对话框
    util 
        Linkify 使一些text可以点击  如： email  web url  电话   会自动添加 scheme 如果没有scheme的话  addLinks 对text添加动作  
        Rfc822Token  
    style
        CharacterStyle  字符样式
        UpdateAppearance 
        UpdateLayout extends UpdateAppearance
        MetricAffectingSpan extends CharacterStyle implements UpdateLayout  度量 影响  跨度
        AbsoluteSizeSpan extends MetricAffectingSpan implements ParcelableSpan  绝对大小  mSize
        ParagraphStyle 款样式
        AlignmentSpan extends ParagraphStyle   对齐  Layout.Alignment getAlignment
        BackgroundColorSpan extends CharacterStyle  implements UpdateAppearance, ParcelableSpan  getBackgroundColor
        LeadingMarginSpan extends ParagraphStyle getLeadingMargin drawLeadingMargin
        BulletSpan implements LeadingMarginSpan  子弹  mGapWidth  mColor sBulletPath 
        ClickableSpan extends CharacterStyle implements UpdateAppearance onClick 
        WrapTogetherSpan extends ParagraphStyle 
        LineHeightSpan extends ParagraphStyle, WrapTogetherSpan chooseHeight
        DrawableMarginSpan implements LeadingMarginSpan, LineHeightSpan drawLeadingMargin 
        ReplacementSpan extends MetricAffectingSpan  getSize draw 
        DynamicDrawableSpan extends ReplacementSpan getVerticalAlignment getDrawable  
        EasyEditSpan implements ParcelableSpan an easy way to edit a portion of text
        ForegroundColorSpan extends CharacterStyle implements UpdateAppearance, ParcelableSpan  getForegroundColor
        IconMarginSpan implements LeadingMarginSpan, LineHeightSpan mBitmap 
        ImageSpan extends DynamicDrawableSpan getDrawable 
        LineBackgroundSpan extends ParagraphStyle drawBackground
        MaskFilterSpan extends CharacterStyle implements UpdateAppearance 
        QuoteSpan implements LeadingMarginSpan, ParcelableSpan mColor = 0xff0000ff STRIPE_WIDTH = 2; 画一个2长度的引号
        RasterizerSpan extends CharacterStyle implements UpdateAppearance 光栅 
        ScaleXSpan extends MetricAffectingSpan implements ParcelableSpan getScaleX ds.setTextScaleX(ds.getTextScaleX() * mProportion); 
        SpellCheckSpan implements ParcelableSpan 
        StrikethroughSpan extends CharacterStyle  implements UpdateAppearance, ParcelableSpan ds.setStrikeThruText(true); 
        StyleSpan extends MetricAffectingSpan implements ParcelableSpan Describes a style in a span  getStyle  apply
        SubscriptSpan extends MetricAffectingSpan implements ParcelableSpan 
        SubscriptSpan extends MetricAffectingSpan implements ParcelableSpan  下标span  tp.baselineShift -= (int) (tp.ascent() / 2);
        SuggestionRangeSpan extends CharacterStyle implements ParcelableSpan 提示范围span  setBackgroundColor tp.bgColor = mBackgroundColor; 
        SuggestionSpan extends CharacterStyle implements ParcelableSpan  Holds suggestion candidates for the text enclosed in this span    tp.setUnderlineText    getUnderlineColor notifySelection 
        SuperscriptSpan extends MetricAffectingSpan implements ParcelableSpan  上标span tp.baselineShift += (int) (tp.ascent() / 2);
        TabStopSpan extends ParagraphStyle a single tab stop on a line getTabStop（）
        TextAppearanceSpan extends MetricAffectingSpan implements ParcelableSpan Sets the text color, size, style, and typeface to match a TextAppearance 设置text的颜色 大小.....  
        TtsSpan implements ParcelableSpan text-to-speech engines  
        TypefaceSpan extends MetricAffectingSpan implements ParcelableSpan 字体 typeface family of the text paint.setTypeface(tf)
        UnderlineSpan extends CharacterStyle  implements UpdateAppearance, ParcelableSpan 下划线ds.setUnderlineText(true);
        URLSpan extends ClickableSpan implements ParcelableSpan  getURL onClick ACTION_VIEW 
 
 AndroidCharacter  一些java.lang.Character中不易得到的字符
 Annotation implements ParcelableSpan key-value pairs 
 AutoText 自动拼写矫正 corrections to frequent misspellings. 
 BidiFormatter  
 BoringLayout 无聊的  
 ClipboardManager    粘贴板管理器  @Deprecated 使用android.content.ClipboardManger
 Layout  控制text在view的显示
 DynamicLayout extends Layout a text layout that updates itself as the text is edited 
 StaticLayout extends Layout 静态 如果一个text laid out了(铺垫) 不能再修改
 Editable extends CharSequence, GetChars, Spannable, Appendable 可编辑 replace insert delete append 
 GraphicsOperations drawText measureText 
 Html  将html转换为可视的text   ImageGetter TagHandler fromHtml HtmlToSpannedConverter
 Hyphenator 连字符
 InputFilter  filter 输入过滤
 InputType TYPE_CLASS_TEXT TYPE_TEXT_VARIATION_URI TYPE_TEXT_VARIATION_EMAIL_ADDRESS  TYPE_TEXT_VARIATION_PASSWORD TYPE_CLASS_NUMBER  
 MeasuredText obtain 
 PackedObjectVector PackedIntVector 
 Selection 选择  一个光标就是一个start 和end在一样的位置 setSelection getSelectionEnd  getSelectionStart removeSelection 
 Spanned extends CharSequence  getSpans 
 Spannable extends Spanned setSpan removeSpan 
 SpannableStringInternal 字符串 mText CharSequence 
 SpannableString extends SpannableStringInternal implements CharSequence, GetChars, Spannable 
 SpannableStringBuilder implements CharSequence, GetChars, Spannable, Editable, Appendable, GraphicsOperations 
 SpannedString extends SpannableStringInternal implements CharSequence, GetChars, Spanned
 SpanWatcher extends NoCopySpan 
 TextWatcher extends NoCopySpan 监听text变化 beforeTextChanged onTextChanged afterTextChanged 
 TextPaint extends Paint text画笔    underlineThickness默认1.0 
 TextLine Represents a line of styled text 
 TextUtils 
         ELLIPSIS_STRING \u2026 ...   ELLIPSIS_TWO_DOTS \u2025 .. 
         indexOf substring split isEmpty getReverse replace  ellipsize (TruncateAt)
        注意：
            public static CharSequence ellipsize(CharSequence text,
                                         TextPaint paint,
                                         float avail, TruncateAt where,
                                         boolean preserveLength,
                                         EllipsizeCallback callback) {
        return ellipsize(text, paint, avail, where, preserveLength, callback,
                TextDirectionHeuristics.FIRSTSTRONG_LTR,
                (where == TruncateAt.END_SMALL) ? ELLIPSIS_TWO_DOTS_STRING : ELLIPSIS_STRING);
    } 
        EllipsizeCallback  ellipsized 
        htmlEncode（string）   concat  isDigitsOnly 

os    单词  Binder： 胶 粘合剂  derive：推导出
    Binder implements IBinder 胶  remotable object  android 远程调用对象  isBinderAlive  
    IInterface   IBinder asBinder(); 
    AsyncResult 
    AsyncTask  异步任务，在UI thread 不用申请 threads and/or handlers ，适合short operations (a few seconds at the most.)，如果 长操作推荐使用Executor   
            AsyncTask<Params, Progress, Result>   在 AsyncTask内部使用handler 和thread 实现的   publishProgress  
            InternalHandler   Looper.getMainLooper()   
        BaseBundle 一个string 到各种类型的映射 ArrayMap<String, Object> mMap  putXXX  getXXX
	Bundle extends BaseBundle implements Cloneable, Parcelable 
	PersistableBundle extends Bundle 序列化到xml中的bundle
	BatteryProperties  chargerAcOnline  chargerUsbOnline  chargerWirelessOnline batteryStatus batteryHealth  batteryTemperature  batteryTechnology batteryVoltage 
	BatteryStats 电池的统计 battery usage statistics, including information on wakelocks, processes, packages, and services
	BatteryManagerInternal
	BatteryManager 提 供了一些查询电池和充电的方法 其实是从BatteryStats中查询的 isCharging 
	BrightnessLimit extends Activity implements OnClickListener  屏幕亮度 一个SCREEN_BRIGHTNESS亮度限制的activity IPowerManager  power.setTemporaryScreenBrightnessSettingOverride(0);
	Build system properties 系统属性 ID DISPLAY PRODUCT DEVICE BOARD MANUFACTURER  BRAND BOOTLOADER HARDWARE  TYPE deriveFingerprint() SystemProperties.get(property, UNKNOWN);
	Build.VERSION  BASE_OS SDK SDK_INT 
	CancellationSignal 取消在进行的操作
	CommonClock 
	CommonTimeUtils 
	CountDownTimer  非常好使的倒计时工具  使用handler完成的
	Debug 非常好用的Android 应用程序调试工具  Debug.MemoryInfo waitForDebugger isDebuggerConnected getVmFeatureList startMethodTracing getMemoryInfo 
	DropBoxManager  getSystemService Context#DROPBOX_SERVICE  addText  addData addFile 
	Environment 系统环境  Environment.UserEnvironment  getExternalDirs-->StorageManager.getVolumeList(mUserId,StorageManager.FLAG_FOR_WRITE) getStorageDirectory(/storage)  getDataDirectory（/data）getDataAppDirectory getExternalStorageDirectory 
	FileObserver  非常好用 监听文件被任何程序的改变 onEvent 
	FileUtils 
	Message 消息 描述发送handler的数据和描述信息 不要new 而要使用 Message.obtain()  或者 Handler.obtainMessage() 从池中获取回收的  what  obj when  data   Message next下一个消息指针
	MessageQueue 存储Looper分发的消息  信息是handler发送的  quit 退出消息队列，意味着没有消息了
	boolean enqueueMessage(Message msg, long when) {//把消息发送到消息队列 中
			if (msg.target == null) {
				throw new IllegalArgumentException("Message must have a target.");
			}
			if (msg.isInUse()) {
				throw new IllegalStateException(msg + " This message is already in use.");
			}

			synchronized (this) {
				if (mQuitting) {
					IllegalStateException e = new IllegalStateException(
							msg.target + " sending message to a Handler on a dead thread");
					Log.w(TAG, e.getMessage(), e);
					msg.recycle();
					return false;
				}

				msg.markInUse();
				msg.when = when;
				Message p = mMessages;
				boolean needWake;
				if (p == null || when == 0 || when < p.when) {  //添加到消息头
					// New head, wake up the event queue if blocked.
					msg.next = p;
					mMessages = msg;
					needWake = mBlocked;
				} else {
					// Inserted within the middle of the queue.  Usually we don't have to wake
					// up the event queue unless there is a barrier at the head of the queue
					// and the message is the earliest asynchronous message in the queue.
					needWake = mBlocked && p.target == null && msg.isAsynchronous();
					Message prev;
					for (;;) {
						prev = p;
						p = p.next;
						if (p == null || when < p.when) {
							break;
						}
						if (needWake && p.isAsynchronous()) {
							needWake = false;
						}
					}
					msg.next = p; // invariant: p == prev.next  //使用Message 的next 形成的消息队列
					prev.next = msg;
				}

				// We can assume mPtr != 0 because mQuitting is false.
				if (needWake) {
					nativeWake(mPtr);
				}
			}
			return true;
		}
	Messenger 用于向handler发送消息 send  Message mTarget.send(message); 
	Looper Class used to run a message loop for a thread.  Threads by default do not have a message loop associated with them; to create one, call {@link #prepare} in the thread that is to run the loop, and then {@link #loop} to have it process messages until the loop is stopped 
	ThreadLocal<Looper> sThreadLocal = new ThreadLocal<Looper>();   线程安全
        Looper sMainLooper; MessageQueue mQueue;  
        Thread mThread;   
	private static void prepare(boolean quitAllowed) {
			if (sThreadLocal.get() != null) {
				throw new RuntimeException("Only one Looper may be created per thread");
			}
			sThreadLocal.set(new Looper(quitAllowed));
		}
	public static void loop() {
			final Looper me = myLooper();
			if (me == null) {
				throw new RuntimeException("No Looper; Looper.prepare() wasn't called on this thread.");
			}
			final MessageQueue queue = me.mQueue;

			// Make sure the identity of this thread is that of the local process,
			// and keep track of what that identity token actually is.
			Binder.clearCallingIdentity();
			final long ident = Binder.clearCallingIdentity();

			for (;;) {// 这个死循环不停的去message queue中检查，如果有消息就 分发出去msg.target.dispatchMessage(msg);
				Message msg = queue.next(); // might block
				if (msg == null) {
					// No message indicates that the message queue is quitting.
					return;
				}

				// This must be in a local variable, in case a UI event sets the logger
				Printer logging = me.mLogging;
				if (logging != null) {
					logging.println(">>>>> Dispatching to " + msg.target + " " +
							msg.callback + ": " + msg.what);
				}

				msg.target.dispatchMessage(msg);

				if (logging != null) {
					logging.println("<<<<< Finished to " + msg.target + " " + msg.callback);
				}

				// Make sure that during the course of dispatching the
				// identity of the thread wasn't corrupted.
				final long newIdent = Binder.clearCallingIdentity();
				if (ident != newIdent) {
					Log.wtf(TAG, "Thread identity changed from 0x"
							+ Long.toHexString(ident) + " to 0x"
							+ Long.toHexString(newIdent) + " while dispatching to "
							+ msg.target.getClass().getName() + " "
							+ msg.callback + " what=" + msg.what);
				}

				msg.recycleUnchecked();
			}
		}
	HandlerThread  带有looper的thread mLooper = Looper.myLooper();  getLooper() 
	Handler_Delegate sendMessageAtTime 
	HandlerThread_Delegate 
	Handler  一个handler是用来处理/发送和当前线程关联的message或者runnable对象 A Handler allows you to send and process {@link Message} and Runnable objects associated with a thread's {@link MessageQueue} 一个handler和一个thread和对应thread的message queue 关联  When you create a new Handler, it is bound to the thread / message queue of the thread that is creating it -- from that point on, it will deliver messages and runnables to that message queue and execute them as they come out of the message queue
	Handler() 使用当前线程默认的looper 如果当前线程没有则异常  mLooper = Looper.myLooper(); mQueue = mLooper.mQueue;  Handler(Looper looper) 使用自定义的looper 
	MessageQueue mQueue; Looper mLooper; 
	handleMessage 接受处理消息  obtainMessage 从全局的消息池中创建一个message post 把一个runnable对象添加到消息队列中 postAtTime  sendMessage 发送一个消息到消息队列的尾 
	sendMessageAtFrontOfQueue 发送一个消息到消息队列的头  removeMessages getLooper 
	public boolean sendMessageAtTime(Message msg, long uptimeMillis) {
			MessageQueue queue = mQueue;
			if (queue == null) {
				RuntimeException e = new RuntimeException(
						this + " sendMessageAtTime() called with no mQueue");
				Log.w("Looper", e.getMessage(), e);
				Log.w("Looper", e.getMessage(), e);
				Log.w("Looper", e.getMessage(), e);
				Log.w("Looper", e.getMessage(), e);
				Log.w("Looper", e.getMessage(), e);
				return false;
			}
			return enqueueMessage(queue, msg, uptimeMillis);
		}
	private boolean enqueueMessage(MessageQueue queue, Message msg, long uptimeMillis) {
			msg.target = this;
			if (mAsynchronous) {
				msg.setAsynchronous(true);
			}
			return queue.enqueueMessage(msg, uptimeMillis);
		}

	IServiceManager  查找 发布 系统服务 getService  checkService addService listServices 
	MemoryFile Linux中共享内存的文件 如果是低内存可能被回收
	NetworkOnMainThreadException 主线程操作网络异常  看到了吧，这个杂种引起的不能在主线程操作网络
	ParcelFileDescriptor Parcel中的数据以文件的方法存储的
	Parcel 读写数据   进程通讯使用的序列化对象数据  大部分是native 方法 Parcelable.Creator 
	Parcelable 用于读写一个Parcel  Parcelable.Creator  Parcelable.ClassLoaderCreator   在 Parcel读写中洗衣机使用Creator
	PatternMatcher match 
	PerformanceCollector 性能收集器
	PowerManagerInternal Power manager local system service interface 定义了电源操作的接口setScreenBrightnessOverrideFromWindowManager setButtonBrightnessOverrideFromWindowManager
	PowerManager 控制设备的电源 Context.getSystemService(Context.POWER_SERVICE)  setBacklightBrightness reboot  shutdown  isScreenOn goToSleep wakeUp 
	Process 管理系统进程 start 启动一个进程 is64Bit myPid  setThreadPriority setCanSelfBackground  getFreeMemory getTotalMemory 
	RecoverySystem 用于系统恢复  更新系统  清除用户数据  last_    /cache/recovery   installPackage rebootWipeUserData
	RemoteCallbackList register unregister kill 
	SELinux  provides access to the centralized jni bindings for SELinux interaction  getContext 获取当前进程的context
	ServiceManager getService addService   checkService  listServices 
	StatFs  This is a wrapper for Unix statvfs()
	StrictMode  StrictMode is a developer tool which detects things you might be doing by accident and brings them to your attention so you can fix them
	DETECT_DISK_WRITE DETECT_DISK_READ DETECT_DISK_READ ThreadPolicy setThreadPolicy 
	SystemClock uptimeMillis currentThreadTimeMillis 
	SystemProperties get getInt getLong set 
	Vibrator operates the vibrator on the device hasVibrator vibrate  cancel 
	SystemVibrator extends Vibrator 震动  vibrate
	SystemService start stop  restart 
	TokenWatcher 
	Trace trace events to the system trace buffer isTagEnabled  setAppTracingAllowed  traceBegin traceEnd 
	UEventObserver 接受系统内核的事件  startObserving 
	UserHandle Representation of a user on the device  isSameApp isApp isOwner 
	UserManager Manages users and user details on a multi-user system.  (UserManager) context.getSystemService(Context.USER_SERVICE); getSerialNumberForUser  createUser  
    storage
        DiskInfo 硬盘信息      
        IMountService extends IInterface  formatVolume  decryptStorage  getVolumeList mkdirs  ........ 
        IMountShutdownObserver extends IInterface onShutDownComplete 
        IMountServiceListener extends IInterface   onStorageStateChanged 
        IObbActionListener extends IInterface  onObbResult 
        StorageEventListener 
        StorageListener extends StorageEventListener 
        VolumeInfo 卷信息 partition on a physical    DiskInfo   buildStorageVolume  
        StorageVolume  
        StorageManager   from(context) enableUsbMassStorage mountObb getDisks ........很多的方法  
graphics
	Atlas 地图集  Atlas.Entry Atlas中x,y 坐标  Atlas.Policy pack  Atlas.SlicePolicy extends Atlas.Policy 图片的绘制是以链式结构存储的以及查找空间的  Atlas.Cell next; insert 在可用的空间插入一个rect
		SlicePolicy(int width, int height, int flags, SplitDecision splitDecision) {
            mPadding = (flags & FLAG_ADD_PADDING) != 0 ? 1 : 0;  //这个地方会引起一个padding 

            // The entire atlas is empty at first, minus padding
            Cell first = new Cell();
            first.x = first.y = mPadding;
            first.width = width - 2 * mPadding;
            first.height = height - 2 * mPadding;

            mRoot.next = first;
            mSplitDecision = splitDecision;
        }
	Xfermode
	Xfermode_Delegate getComposite getDelegate 
	AvoidXfermode_Delegate extends Xfermode_Delegate 
	BidiRenderer 把文本分割scripts 可用用于测量text而不用绘制他  Can be used to measure the text without actually drawing it  deprecation 不用这种方法了
	NinePatch  mNativeChunk Bitmap mBitmap; 
	Bitmap implements Parcelable  
		byte[] mBuffer ；byte[] mNinePatchChunk; // may be null  mWidth  mHeight  Matrix sScaleMatrix; mNativePtr jni bitmap指针  mDensity 默认的密度是和当前设备一样的DisplayMetrics.DENSITY_DEVICE，当bitmap在canvas绘制时需要这个密度进行scale
		reconfigure 重新配置bitmap的大小，bitmap中的数据不变  recycle 
		Config ALPHA_8 一个像素需要1 byte内存，Each pixel is stored as a single translucency (alpha) channel No color information is stored 黑白照片
			RGB_565 produce slight visual artifacts  red is stored with 5 bits of precision (32 possible values), green is stored with 6 bits of precision (64 possible values) and blue is stored with 5 bits of precision
			ARGB_4444 一个alpha channel 3个RGB channel  ，一共占用2byte 内存  质量显示较差 建议使用ARGB_8888替代这个
			ARGB_8888  一个channel占用1 byte内存 高质量的照片显示使用这个
		copyPixelsToBuffer copyPixelsFromBuffer copy createScaledBitmap  createBitmap 
		CompressFormat  JPEG PNG WEBP 
		compress  eraseColor setPixel sameAs 检查两张图片是否一样dimensions pixel data  config 
		nativeXXXXX大部分的native方法 
	Bitmap_Delegate implementing the native methods of android.graphics.Bitmap 
	BitmapFactory Creates Bitmap objects from various sources, including files, streams, and byte-arrays 
		Options 
		decodeFile decodeResourceStream decodeByteArray  decodeStream 
	BitmapFactory_Delegate BitmapFactory中native方法的实现  nativeDecodeStream 判断是否是9patch文件
		static Bitmap nativeDecodeStream(InputStream is, byte[] storage,
            @Nullable Rect padding, @Nullable Options opts) {
			Bitmap bm = null;

			Density density = Density.MEDIUM;
			Set<BitmapCreateFlags> bitmapCreateFlags = EnumSet.of(BitmapCreateFlags.MUTABLE);
			if (opts != null) {
				density = Density.getEnum(opts.inDensity);
				if (opts.inPremultiplied) {
					bitmapCreateFlags.add(BitmapCreateFlags.PREMULTIPLIED);
				}
			}

			try {
				if (is instanceof NinePatchInputStream) {
					NinePatchInputStream npis = (NinePatchInputStream) is;
					npis.disableFakeMarkSupport();

					// load the bitmap as a nine patch
					com.android.ninepatch.NinePatch ninePatch = com.android.ninepatch.NinePatch.load(
							npis, true /*is9Patch*/, false /*convert*/);

					// get the bitmap and chunk objects.
					bm = Bitmap_Delegate.createBitmap(ninePatch.getImage(), bitmapCreateFlags,
							density);
					NinePatchChunk chunk = ninePatch.getChunk();

					// put the chunk in the bitmap
					bm.setNinePatchChunk(NinePatch_Delegate.serialize(chunk));

					if (padding != null) {
						// read the padding
						int[] paddingArray = chunk.getPadding();//这个padding就是.9.png中设置的
						padding.left = paddingArray[0];
						padding.top = paddingArray[1];
						padding.right = paddingArray[2];
						padding.bottom = paddingArray[3];
					}
				} else {
					// load the bitmap directly.
					bm = Bitmap_Delegate.createBitmap(is, bitmapCreateFlags, density);
				}
			} catch (IOException e) {
				Bridge.getLog().error(null, "Failed to load image", e, null);
			}

			return bm;
		}
	Shader return horizontal spans of colors during drawing Matrix mLocalMatrix; TileMode  CLAMP 钳夹 REPEAT MIRROR 
	Shader_Delegate
	BitmapShader extends Shader  draw a bitmap as a texture 
	BitmapShader_Delegate extends Shader_Delegate	
	
	drawable
		shapes
			Shape 定义一个一般的图形  mWidth mHeight draw(Canvas canvas, Paint paint); resize 
			RectShape extends Shape RectF mRect = new RectF(); 
			ArcShape extends RectShape mStart mSweep  canvas.drawArc 
			OvalShape extends RectShape 
			PathShape extends Shape mPath mStdWidth mStdHeight  mScaleX  mScaleY  
			RoundRectShape extends RectShape mOuterRadii 
 
view
    accessibility
        AccessibilityNodeInfo
        AccessibilityWindowInfo 
        AccessibilityManager
    animation 
        Interpolator 补间器  Interpolator extends TimeInterpolator   BaseInterpolator implements Interpolator
        AccelerateDecelerateInterpolator extends BaseInterpolator 加速减速   PathInterpolator
        AccelerateInterpolator  CycleInterpolator （周期）  DecelerateInterpolator LinearInterpolator  OvershootInterpolator(过渡)
        Transformation  转换 动画执行使用的是 Matrix mMatrix 非常重要
        Animation  可以应用于Views, Surfaces, or other objects  setFillAfter 如果fillAfter设为true，则动画执行后，控件将停留在动画结束的状态  setFillBefore(boolean fillBefore)：如果fillBefore设为true，则动画执行后，控件将回到动画开始的状态
    AnimationListener
        AlphaAnimation 
        AnimationSet extends Animation 
        AnimationUtils 
        ClipRectAnimation 剪切动画  ClipRectTBAnimation(top/bottom)  ClipRectLRAnimation（Right/left）
        RotateAnimation 旋转  ScaleAnimation 缩放 TranslateAnimation移动 TranslateXAnimation TranslateYAnimation   
        LayoutAnimationController  布局动画控制器 用来控制一个布局或者view Group的子view 产生相同的动画
        GridLayoutAnimationController extends LayoutAnimationController  
    inputmethod
        InputConnection 是InputMethod和应用程序连接channel， 从光标读取text，提交text到 text box， 发送 key events 到应用程序 getTextBeforeCursor  getTextAfterCursor  getSelectedText   commitText  setSelection sendKeyEvent 
        BaseInputConnection implements InputConnection  提供了访问当前的editable object   View mTargetView
        CorrectionInfo  一个editor 反馈给input method的正确的信息
        CompletionInfo 
        CursorAnchorInfo  cursor 描点信息 
        EditorInfo  text editing object 信息属性信息 inputType imeOptions  actionId hintText fieldName   
