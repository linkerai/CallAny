# CallAny: build your speech interaction app with javascript
## 

```javascript
var dclog = document.getElementById('dc_history');// chat history
function start(){
    var chat_param = {  // openai config
        "model": "gpt-3.5-turbo",
        "stream": true,
        "messages": [{"role": "system", "content": 'You are an ai assistant'}],
        "temperature": 0.7
    };
    var key_linkerai = 'sk-6Be2PgJrlmVctpLNdxow0s9i4nSW1KMjG7UfAFhH8YZRX5vu';
    var key_openai = '';  //Optional
    var param_all = {
        'chat_param':chat_param,
        'key_linkerai':key_linkerai, 
        'key_openai': key_openai, 
        'speaker_id':0, 
    };
    var test = JSON.stringify(param_all);
    t_start(t_onopen = onopen,t_onclose = onclose,t_onmessage = onmessage, param_all = test); 
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

