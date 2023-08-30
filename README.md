
# CallAny: Build Speech Interaction APP with Javascript
- Realtime speech interaction for pc, mobile and pad via javascript
- Acoustic Echo Cancelling(AEC) for most devices
- Speech enhancement for any devices
- Noise suppression for any devices
- Instant interruption during AI talking
- Automatic language detection before AI repling
- Access Openai and Linkerai for chat
- Support voice tracking, automatically track your own voice for the first conversation, and automatically block other people's voices
- Access of other chat engine comming soon


[**中文简体**](https://github.com/linkerai/CallAny/blob/master/README_zh.md)
| [**视频演示**](https://www.bilibili.com/video/BV1Mu4y1i7cp/)
| [**Demo site**](https://app.4387.top)
| [**Get Key**](https://cqupt.4387.top)

## Usage
```javascript
var dclog = document.getElementById('dc_history');// chat history
function start(){
    dclog.textContent=''; //clear history
    var chat_param = {  // openai config
        "model": "gpt-3.5-turbo",
        "stream": true,
        "messages": [{"role": "system", "content": 'You are an ai assistant'}],
        "temperature": 0.7
    };
    var key_linkerai = 'sk-6Be2PgJrlmVctpLNdxow0s9i4nSW1KMjG7UfAFhH8YZRX5vu';//Multiple separated by commas
    var key_openai = '';  //Optional, if not empty use openai else use linkerai for chat
    var param_all = {
        'chat_param':chat_param,
        'key_linkerai':key_linkerai, // necessary
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

