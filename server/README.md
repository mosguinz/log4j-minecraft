Minecraft Log4j Vulnerable Server
========================================

Setup Instructions
--------------------

1. Get a Vulnerable Java Version & Minecrafter server

- Download Java 8u181 (vulnerable version) from this link:

    https://repo.huaweicloud.com/java/jdk/8u181-b13/

- Download vulnerable Minecrafter server.jar (i.e 1.16.4): 

    https://www.minecraft.net/en-us/article/minecraft-java-edition-1-16-4

- Move server.jar to this directory

    mv ~/Downloads/server.jar .

2. Setup the Minecraft Server

- Run this java command once to generate the default files:

    java -jar server.jar

- Accept the EULA by modifying this line in the eula.txt:

    eula=true

- There should already be a preconfigured server.properties, but if there isn't modify/add these lines in your server.properties

    online-mode=false
    rcon.password=supersecurerconpassword

- Run the server with the same command:

    java -jar server.jar


Notes
--------------------

- Minecraft versions 1.18.1+ are not affected
- Minecraft version 1.7 and below are not affected
- All exploits were tested and confirmed with:
    - Java 8u181
    - Minecrafter version 1.16.4
