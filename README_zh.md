# CallAny: 使用javascript构建语音交互APP
- 实时语音交互，支持 pc端、移动端、小程序
- 支持回声消除
- 支持语音增强
- 支持非平稳噪声抑制
- 支持交谈过程中的即时打断
- 自动检测回复语言
- 聊天功能接入openai、Linkerai等大模型
- 支持语音跟踪，首次对话自动跟踪本人语音，自动屏蔽其他人语音
- 其他大模型接入 comming soon


[**English**](https://github.com/linkerai/CallAny/blob/master/README.md)
| [**视频演示**](https://www.bilibili.com/video/BV1Mu4y1i7cp/)
| [**演示网站**](https://xxx.4387.top)
| [**获取KEY**](https://cqupt.4387.top)
## Usage
```javascript
var dclog = document.getElementById('dc_history');// 聊天记录
function start(){
    dclog.textContent=''; //清空聊天记录
    var chat_param = {  // openai 配置
        "model": "gpt-3.5-turbo",
        "stream": true,
        "messages": [{"role": "system", "content": 'You are an ai assistant'}],
        "temperature": 0.7
    };
    var key_linkerai = 'sk-6Be2PgJrlmVctpLNdxow0s9i4nSW1KMjG7UfAFhH8YZRX5vu';//多个以逗号隔开
    var key_openai = '';  // 可选, 多个以逗号隔开
    var param_all = {
        'chat_param':chat_param,
        'key_linkerai':key_linkerai, // 必须
        'key_openai': key_openai, 
        'speaker_id':0, 
        'language':'zh-cn',
        'use_video':false,
    };
    t_start(t_onopen = onopen,t_onclose = onclose,t_onmessage = onmessage, param_all = param_all); 
}
function stop(){
    t_stop();
}
function onopen(){
    dclog.textContent += '\n- connected\n';
}
function onclose(){
    dclog.textContent += '\n- hang up\n';
    scrollToBottom();
}
function onmessage(txt){
    dclog.textContent += txt ;
    scrollToBottom();
}
function scrollToBottom() {
    dclog.scrollTop = dclog.scrollHeight;
}
<script src="https://xxx.4387.top/lingxi.js"></script>
```

