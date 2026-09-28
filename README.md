# Tomcat Configuration and Logs

Apache Tomcat 11.0.25 configuration files, startup scripts, and deployment logs.

## Overview

This repository contains:
- **bin/**: Startup and shutdown scripts for Windows (`.bat`) and Unix-like systems (`.sh`)
- **logs/**: Server logs and access logs from various deployment dates

## Structure

```
.
├── bin/
│   ��── catalina.bat          - Main Catalina start/stop script (Windows)
│   ├── catalina.sh           - Main Catalina start/stop script (Unix/Linux)
│   ├── catalina-tasks.xml    - Ant tasks configuration
│   ├── startup.bat           - Quick startup script (Windows)
│   ├── startup.sh            - Quick startup script (Unix/Linux)
│   ├── shutdown.bat          - Quick shutdown script (Windows)
│   └── shutdown.sh           - Quick shutdown script (Unix/Linux)
├── logs/
│   ├── catalina.YYYY-MM-DD.log      - Catalina server logs
│   ├── localhost.YYYY-MM-DD.log     - Application context logs
│   └── localhost_access_log.YYYY-MM-DD.txt - HTTP access logs
└── README.md
```

## Key Configuration Details

- **Server Version**: Apache Tomcat/11.0.25
- **Java**: JDK 26.0.1
- **OS**: Windows 11 (10.0 amd64)
- **Default Port**: 8080
- **CATALINA_HOME**: Points to the Tomcat installation directory
- **CATALINA_TMPDIR**: Temp directory for Tomcat operations

## Environment Variables

Key environment variables used:
- `CATALINA_HOME`: Tomcat installation directory
- `CATALINA_BASE`: Base directory for Tomcat instance
- `JAVA_HOME`: Java Development Kit location
- `JRE_HOME`: Java Runtime Environment location
- `CATALINA_OPTS`: Java options for Tomcat runtime

## Startup Configuration

The server is configured with module opens for Java 9+ compatibility:
```
--add-opens=java.base/java.lang=ALL-UNNAMED
--add-opens=java.base/java.lang.reflect=ALL-UNNAMED
--add-opens=java.base/java.io=ALL-UNNAMED
--add-opens=java.base/java.util=ALL-UNNAMED
--add-opens=java.base/java.util.concurrent=ALL-UNNAMED
--add-opens=java.rmi/sun.rmi.transport=ALL-UNNAMED
--enable-native-access=ALL-UNNAMED
```

## Logs

### Server Logs
- **catalina.*.log**: Main Tomcat server startup and operation logs
- Contains version info, initialization details, and deployment information

### Application Context Logs
- **localhost.*.log**: Application-specific context initialization logs
- Includes listener events and attribute changes

### Access Logs
- **localhost_access_log.*.txt**: HTTP request/response logs
- Records all incoming requests with response codes

## Usage

### Starting Tomcat (Windows)
```bash
bin\startup.bat
```

### Starting Tomcat (Unix/Linux)
```bash
bin/startup.sh
```

### Stopping Tomcat (Windows)
```bash
bin\shutdown.bat
```

### Stopping Tomcat (Unix/Linux)
```bash
bin/shutdown.sh
```

## License

Apache Tomcat is licensed under the Apache License 2.0. See individual files for license headers.
