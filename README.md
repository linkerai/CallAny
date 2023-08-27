# CallAny: build your speech interaction app with javascript
- Realtime speech interaction
- Acoustic Echo Cancelling(AEC) when AI is talking
- Speech enhancement 
- Noise suppression 
- Interrupt when AI is talking
## 

```javascript
var dclog = document.getElementById('dc_history');// chat history
function start(){
    document.getElementById('start').style.display = 'none';  
    document.getElementById('stop').style.display = 'inline-block';
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
    t_start(t_onopen = onopen,t_onclose = onclose,t_onmessage = onmessage, param_all = param_all); // start calling
}
function stop(){
    document.getElementById('stop').style.display = 'none';
    document.getElementById('start').style.display = 'inline';
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

