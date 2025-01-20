+ DevOps is about bringing developers and operations team together to improve software delivery
+ Combination of Concepts + Tools + Practices
+ make the SDLC as efficient as possible by fully or mostly automatin
+ We can use Agile and DevOps together

![[Pasted image 20240904073850.png]]
![[Pasted image 20240904074206.png]]
+ key focus: **Automation** and **Monitoring**
+ Key topics:
	+ Networking and Protocols
	+ Containers: Docker
	+ Version Control (git ops)
	+ Cloud: AWS, Azure, GCP
	+ IaC (Infrastructure as Code)
	+ SDLC and CI/CD pipelines
# CI / CD
![[Pasted image 20250114190037.png]]
+ Stands for Continuos Integration / Continuos Delivery
CI/CD automates much or all of the manual human intervention traditionally needed to get new code from a commit into production, encompassing the build, test (including integration tests, unit tests, and regression tests), and deploy phases, as well as infrastructure provisioning

A CI/CD pipeline, development teams can make changes to code that are then automatically tested and pushed out for delivery and deployment.

+ **CI**: integrating all your code changes into the main branch of a shared source code repository early and often, automatically testing each change when you commit or merge them, and automatically kicking off a build. Can identify faster errors, security issues
+ **CD**: automate the infrastructure provisioning and application release process.
---
+ **Continuous testing**: Unit Testing, Integration Testing, Regression Testing

e.g
1. run linters
2. build
3. run tests (unit, integration, e2e)
4. deploy
---
CI/CD vs pre-commit hook
# Notes
+ [[Cloud Computing]]: Azure
## Tools
+ [[Azure DevOps]]