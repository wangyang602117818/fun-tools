# sso-util

## install
``` 
npm install sso-util
```
## usage
```
import ssoutil from 'sso-util'
```
## function list
** 前缀 ssoutil. 省略
```
sso验证方法(window.token_jwt_data)
    authorize(baseUrl, cookieName)
cookie相关
    var value = getCookie(cname)
    setCookie(cname, cvalue, exdays)
解析参数相关
    var result = getQueryString(name)  //获取url上面的参数
    var result = base64SecureURLDecode(str) //把base64安全的编码解析成源吗
    var result = base64SecureURLEncode(base64) //把base64字符串转成url安全的编码
    var result = base64EnCode(str)  //base64编码
    var result = base64DeCode(base64_str)  //base64解码
    var result = parseBsonTime(str) //解析从mongo中传出来的 date.$date
    var result = parseIsoDateTime(str) //解析Newtonsoft.Json格式化的日期(IsoDateFormat)
    var result = formatMonth(month) //格式化成2位的时间格式
    var result = getReturnUrl(name) //获取url上面name参数之后所有部分,这和getQueryString有所不同,因为returnUrl后面可能还有参数
    var result = convertFileSize(val) //把字节格式转成用户可识别的文件大小
    var result = getFileExtension(val)  //获取文件扩展名(小写)
    var result = removeHTML(val)  //移除字符串中的html标签
    var result = convertTime(val)  //把秒转换成 00:00:00格式
    var result = getCurrentDateTime()  //获取当前的日期
 随机数相关
    var result = randomWord(min,max)  //min:最小位数,max:最大位数
    var result = randomNumber(min,max) //min:最小值,max:最大值
设备相关
    var device = getDeviceType(userAgent) //根据userAgent获取设备类型 mobile|pc
字符串相关
    var result = trimChar(str,char)    //去除字符串首尾char字符串
    var result = trimEndChar(str,char)  //去除字符串尾char字符串
    var result = trimStartChar(str,char)  //去除字符串首char字符串
    var result = getFileName(fileName,length) //获取长文件名的前几个字符串
html 字符串相关
    var dom = htmlToDom(html) //把html字符串转换成dom对象
    var html = getOuterHtml(html,tag) //获取一段html中指定的某个tag的内部html(包括他本身)
数组相关
    var arr = reMapArray(array, len) //将一个一维数组转换成二维数组每一项有len个元素,不足填充null
    removeArrayItem(array, val)  //移除数组[a,b,c,d]中某一项c,不包含数组对象
时间相关
    var result = dateAddDays(date,-13,"yyyy-MM-dd");  //日期添加或减少几天date可以为字符串或者Date对象
```
## vue 组件列表
```
import ssocomponent from "sso-util/plugins/index"
Vue.use(ssocomponent)
```
```
<vue-server-select 
    :datas="datas"
    :selected="selected"
    @select="selectItem"
    @search="searchItem"
    @nextPage="nextPage"
    :loading="loading"
    :pageEnd="pageEnd"
    label="UserName"
    value="UserId"
    multiple
/>
//label:select的text(默认name)
//value:select的value(默认id)
```