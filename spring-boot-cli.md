Prerequisite [check vagrant file](vagrant.md):
* vagrant box with: java 11+

## Spring-boot-cli

Download and extract latest archive, follow instruction [here](https://docs.spring.io/spring-boot/docs/current/reference/html/getting-started.html#getting-started-installing-the-cli).

We can compile and run Groovy source code by using the run command. 
The Spring Boot CLI is completely self-contained, so no need any external Groovy installation.


* hello.groovy

```
@RestController
class WebApplication {
    @RequestMapping("/")
    String home() { "Hello World!" }
}
```

```
$ spring run hello.groovy
```

To pass command-line arguments to the application, use -- to separate the commands from the “spring” command arguments

```
$ spring run hello.groovy -- --server.port=9000
```

To set JVM command line arguments, you can use the JAVA_OPTS environment variable, as shown in the following example:

```
$ JAVA_OPTS=-Xmx1024m spring run hello.groovy
```
* another nice hello world

```
package org.test

@Grab("org.codehaus.groovy.modules.http-builder:http-builder:0.7.1")
import groovyx.net.http.*

@Controller
class Example implements CommandLineRunner {

	@Autowired
	ApplicationContext context;

	@RequestMapping("/")
	@ResponseBody
	public String helloWorld() {
		return "World!"
	}

	void run(String... args) {
		def port = context.webServer.port;
		def world = new RESTClient("http://localhost:" + port).get(path:"/").data.text
		print "Hello " + world
	}

}
```

For more [sample](https://github.com/spring-projects/spring-boot/tree/v2.2.2.RELEASE/spring-boot-project/spring-boot-cli/samples)
