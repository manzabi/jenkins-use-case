## Deploy a SpringBoot app to GKE using Jenkins Pipelines
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
@title[Go With The Flow]

@snap[north-west]
### Go With The Flow
@snapend

@snap[east span-45]
@ul[spaced]
- Push Code
- SCM Checkout & Build
- Push Docker Image
- Apply image to K8S object
@ulend
@snapend

@snap[west span-45]
@img[shadow](assets/img/overview.png)
@snapend

---
@title[Into The Jenkinsfile]

@snap[north-east template-note] The Jenkinsfile. @snapend

+++?color=lavender @title[Fenced Code Block]

```javascript
// import
@Library("fltrJenkinsLib")
import com.fluttr.fltrJenkinsGlobalLib
import groovy.transform.Field

@Field static deployMap = [
    tag: 'qas',
    gkeClusterCredentials: 'gcloud container clusters get-credentials fltr-qas-kube --zone europe-west4-a --project qa-env-225712',
    deploymentName: 'controlroom'
]

stage('Initializing Fluttr Global Library') {
    steps {
        script {
            fltr = new fltrJenkinsGlobalLib()
            buildTimestamp = fltr.buildTimestamp()
        }
    }
}

if (env.BRANCH_NAME == "deploy") {
    configMap = deployMap
} 
```

@[2,4](You can present code inlined within your slide markdown too.) 
@[7-11](Your code is displayed using code-syntax highlighting just like your IDE.) 
@[6-7](Again, all of this without ever leaving your slideshow.)