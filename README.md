# xinge-api-python

[![PyPI version](https://badge.fury.io/py/xinge.svg)](https://badge.fury.io/py/xinge)

## 概述

欢迎使用信鸽 ServerSDK - Python 版本封装的开发包，具有最新版本的信鸽 API 功能。
[下载地址](http://xg.qq.com/xg/ctr_index/download)

## 兼容版本

- Python 2.7
- 需要使用到 base64 和 requests

```sbtshell
➜  ~ sudo easy_install pip
➜  ~ sudo pip install pybase64
➜  ~ sudo pip install requests
```

- 如需运行测试用例，需要安装 unittest

```sbtshell
pip install unittest2
```

## 引用 SDK

```shell
  pip install xinge
```

## 代码示例

```python
import json
import xinge_push

#create XingeApp
xinge = xinge_push.XingeApp(0, 'secret')

#build your message
msg = xinge_push.Message()
msg.type = xinge_push.MESSAGE_TYPE_ANDROID_NOTIFICATION
msg.title = 'some title'
msg.content = 'some content'

#call restful API
ret_code, error_msg = xinge.PushSingleDevice('some_token', msg)
if ret_code:
    print "push failed! retcode: {}, msg: {}".format(ret_code, error_msg)
else:
    print "push successfully!"

```
