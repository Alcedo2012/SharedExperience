# Flask-Socketio

## 部署

> QF1987
>>
>> 1. 在服务器上部署Socketio应使用gunicorn --worker-class eventlet -w 1 flasky:app，不应该加入-b参数，然后在代码里填写地址和端口socketio.run(app, host='0.0.0.0', port=6005
