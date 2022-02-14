## 常用bat脚本
---

```
@echo off
		DOs在运行批处理命令时候，会依次处理批处理中每条命令，并在显示器上显示，
		echo off，可以取消这些显示
		echo on ，打开这些显示
		"echo off"也是条命令 也会显示，在前面加个“@”，这个也不显示
	::    
		注释，当echo on 时，也不会回显
	REM 
		注释，命令后的内容不被执行，但能回显。
	pause
		使显示器停下，并显示“请按任意键继续_ _ _”
 
	&   commane1 &  command2
	Cmd.exe 运行第一个命令，然后运行第二个命令

	&&  commane1 &&  command2
	md.exe 运行第一个命令，然后仅在第一个命令成功完成时运行第二个命令。
	
	||  commane1 ||  command2
	md.exe 运行第一个命令，然后仅在第一个命令失败时运行第二个命令。（接收大于0的错误代码）
	
	()  (command1 & command2)
	用于分组或嵌套多个命令。
	
	;    command1 parameter1;parameter2
	用于分隔命令参数。
	
  
  字符串替换
	  将路径中的反斜杠替换成斜杠：echo repalce AppData is %AppData:\=//%
```
	
