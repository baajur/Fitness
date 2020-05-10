Language: [English](README-EN.md) | 中文简体

## Fitness（个人项目，暂未开源）
Flutter开发的微博客户端，同时支持Android和iOS。与官方微博x9.99%相似度体验，离线模式，多语言支持，主题随心换，超乎想象的流畅度，各种惊喜的细节等待你一一发现。

### 支持功能：
查看微博动态、正文、评论  
查看热门话题、微博、热搜  
支持话题、@、表情、全文  
离线模式  
国际化  
主题色

### 分享内容

##### 1、九宫格图片控件（源码整理中，稍等···）
类似微博动态，微信朋友圈，微信群组，钉钉群组，支持单张大图预览。

#### 2、拖拽九宫格图片控件（源码整理中，稍等···）
类似微博/微信发布动态九宫格，支持按压放大效果，拖拽排序，拖拽到指定位置删除。

#### 3、获取图片尺寸 [ImageUtil](https://github.com/Sky24n/flustars)
大图功能必备工具。
```yaml
Image image = new Image(image: new CachedNetworkImageProvider("Url"));
Image imageAsset = new Image.asset("");
Image imageFile = new Image.file(File("path"));
Image imageNetwork = new Image.network("url");
Image imageMemory = new Image.memory(null);

ImageUtil imageUtil = ImageUtil();
Rect rect = await imageUtil.getImageSize(image: image);  
ImageUtil().getImageSize(image: image).then((Rect rect) {
  print("rect: " + rect.toString();
});

```

#### 4、简单加解密 [EncryptUtil](https://github.com/Sky24n/common_utils)
异或对称加解密 + Base64加解密
```yaml
const String key = '11, 22, 33, 44, 55, 66';
String value = 'Sky24n';
String encode = EncryptUtil.xorBase64Encode(value, key); // WH1YHgMs
String decode = EncryptUtil.xorBase64Decode(encode, key); // Sky24n
```
#### 5、[JsonUtil](https://github.com/Sky24n/common_utils)
简单封装json字符串转对象。
```yaml
String objStr = "{\"name\":\"成都市\"}";
City hisCity = JsonUtil.getObj(objStr, (v) => City.fromJson(v));

String listStr = "[{\"name\":\"成都市\"}, {\"name\":\"北京市\"}]";
List<City> cityList = JsonUtil.getObjList(listStr, (v) => City.fromJson(v));
```

#### 6、时间格式化 [DateUtil](https://github.com/Sky24n/common_utils)
格式化时间戳。
```yaml
/// year -> yyyy/yy   month -> MM/M    day -> dd/d
/// hour -> HH/H      minute -> mm/m   second -> ss/s

DateUtil.formatDateMs(DateTime.now().millisecondsSinceEpoch, format: DataFormats.full); // 2019-07-09 16:51:14
DateUtil.formatDateStr("2019-07-09 16:51:14", format: "yyyy/M/d HH:mm:ss"); // 2019/7/9 16:51:14
DateUtil.formatDate(DateTime.now(), format: "yyyy/MM/dd HH:mm:ss");  // 2019/07/09 16:51:14
DateUtil.formatDateMs(ms, format: "yyyy年MM月dd日 HH时mm分ss秒");  // 2019年07月09日 16时51分14秒
```
#### 7、时间轴 [TimelineUtil](https://github.com/Sky24n/common_utils)
类似微信朋友圈，微博动态时间线。
```yaml
enum DayFormat {
  ///(less than 10s->just now)、x minutes、x hours、(Yesterday)、x days.
  ///(小于10s->刚刚)、x分钟、x小时、(昨天)、x天.
  Simple,

  ///(less than 10s->just now)、x minutes、x hours、[This year:(Yesterday/a day ago)、(two days age)、MM-dd ]、[past years: yyyy-MM-dd]
  ///(小于10s->刚刚)、x分钟、x小时、[今年: (昨天/1天前)、(2天前)、MM-dd],[往年: yyyy-MM-dd].
  Common,

  ///日期 + HH:mm
  ///(less than 10s->just now)、x minutes、x hours、[This year:(Yesterday HH:mm/a day ago)、(two days age)、MM-dd HH:mm]、[past years: yyyy-MM-dd HH:mm]
  ///小于10s->刚刚)、x分钟、x小时、[今年: (昨天 HH:mm/1天前)、(2天前)、MM-dd HH:mm],[往年: yyyy-MM-dd HH:mm].
  Full,fitness_rec_list.json
}

TimelineUtil.format(timeMillis, locale: Localizations.localeOf(context).languageCode, dayFormat: DayFormat.Common);
```

#### 8、版本升级功能（仅供参考） [VersionUtil](https://github.com/Sky24n/FlutterRepos)
```yaml

```

### Screenshots

|首页|探索|我的|
|:---:|:---:|:---:|
|<img src="screenshots/home.png" width="220" height="465"/>|<img src="screenshots/discover.png" width="220" height="465"/>|<img src="screenshots/me.png" width="220" height="465"/>|
|微博发布|微博正文|个人页面|
|<img src="screenshots/wb_publish.gif" width="220" height="391"/>|<img src="screenshots/wb_content.gif" width="220" height="391"/>|<img src="screenshots/wb_user.gif" width="220" height="391"/>|
|授权|设置|图片|
|<img src="screenshots/wb_auth.png" width="220" height="465"/>|<img src="screenshots/setting.png" width="220" height="465"/>|<img src="screenshots/wb_photo.png" width="220" height="465"/>|


### 关于App
GitHub ： [Fitness](https://github.com/Sky24n/Fitness)  
Apk &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;： 微博正在审核中...

### 关于作者
GitHub : [Sky24n](https://github.com/Sky24n)  
简书 &nbsp;&nbsp;&nbsp;&nbsp;: [Sky24n](https://www.jianshu.com/u/cbf2ad25d33a)  
掘金 &nbsp;&nbsp;&nbsp;&nbsp;: [Sky24n](https://juejin.im/user/5b9e8a92e51d453df0440422)