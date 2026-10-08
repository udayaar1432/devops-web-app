# Hello World WAR — Java Web Application

A minimal Java Servlet project that builds into a **WAR** (Web Application Archive) using Maven.

---

## Project Structure

```
hello-world-war/
├── pom.xml                                        # Maven build file (packaging = war)
└── src/
    └── main/
        ├── java/
        │   └── com/example/
        │       └── HelloWorldServlet.java          # Servlet mapped to /hello hi
        └── webapp/
            ├── index.html                          # Welcome page
            └── WEB-INF/
                └── web.xml                         # Deployment descriptor
```

---

## Prerequisites

| Tool | Version |
|------|---------|
| JDK  | 11+     |
| Maven| 3.6+    |

---

## Build

```bash
# From the project root (where pom.xml is)
mvn clean package
```

The WAR file is generated at:
```
target/hello-world.war
```

---

## Deploy & Run

### Option 1 — Apache Tomcat
1. Copy `target/hello-world.war` into Tomcat's `webapps/` directory.
2. Start Tomcat: `./bin/startup.sh` (Linux/Mac) or `startup.bat` (Windows).
3. Open: [http://localhost:8080/hello-world/](http://localhost:8080/hello-world/)
4. Servlet endpoint: [http://localhost:8080/hello-world/hello](http://localhost:8080/hello-world/hello)

### Option 2 — Maven Tomcat plugin (quick test)
Add the plugin to `pom.xml` and run:
```bash
mvn tomcat7:run
# then visit http://ip:8080/hello-world/hello
```

---

## Endpoints

| URL | Description |
|-----|-------------|
| `/hello-world/` | Welcome HTML page |
| `/hello-world/hello` | Hello World Servlet response |
