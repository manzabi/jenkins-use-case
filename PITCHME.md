## Deploy a SpringBoot app to GKE using Jenkins
---
@title[Tech Stack Description]

@snap[north-west]
### The Usual Suspects
@snapend

@snap[west span-55]
@ul[spaced]
- Jenkins automation server
- GitLab code repository
- Maven build system
- Springboot framework
- Docker
- Google Kubernetes Engine
@ulend
@snapend

@snap[east span-45]
@img[shadow](assets/img/tech_stack.png)
@snapend

---
@title[Into the Jenkins]

@snap[north-west]
### The Butler
@snapend

@snap[west span-55]
@ul[spaced]
- Login with GMail SSO
- Slack integration
- Shared Global Library
- Pipeline As Code
@ulend
@snapend

@snap[east span-45]
@img[shadow](assets/img/jenkinstein.png)
@snapend

---
@title[Flow]

@snap[north-west]
### Go With The Flow
@snapend

@snap[center span-45]
@img[shadow](assets/img/overview.png)
@snapend

---
@color[black](Code Presenting
Slide Templates)
@fa[arrow-down text-black]

@snap[south docslink span-50] The Template Docs @snapend

+++?code=assets/src/Jenkinsfile @title[The Jenkinsfile]

@[1,3-6](Present code found within any repository source file.) @[8-18](Without ever leaving your slideshow.) @[19-28](Using GitPitch code-presenting with (optional) annotations.)

@snap[north-east template-note text-gray] Code presenting repository source file template. @snapend

+++?color=lavender @title[Fenced Code Block]

// Include http module.
var http = require("http");

// Create the server. Function passed as parameter
// is called on every request made.
http.createServer(function (request, response) {
  // Attach listener on end event.  This event is
  // called when client sent, awaiting response.
  request.on("end", function () {
    // Write headers to the response.
    // HTTP 200 status, Content-Type text/plain.
    response.writeHead(200, {
      'Content-Type': 'text/plain'
    });
    // Send data and end response.
    response.end('Hello HTTP!');
  });

// Listen on the 8080 port.
}).listen(8080);
@[1,2](You can present code inlined within your slide markdown too.) @[9-17](Your code is displayed using code-syntax highlighting just like your IDE.) @[19-20](Again, all of this without ever leaving your slideshow.)