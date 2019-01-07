**Title:** Avoiding the many pitfalls of using public cloud FaaS / managed services

**Presenters:** Orestis Gorgas, Arnot Triesler

**About the presenters:** Orestis Gorgas is a software developer from Norway. Arnot Triesler is a library disenthusiast from Norway.

**Intended audience:** Programmers, IT managers

**Abstract:** We endeavour to present a coherent view of how to develop and deploy applications using function-as-a-service frameworks and generic managed services, showing how they add value at the same time as helping others avoid the pitfalls inherent in using these technologies in public cloud offerings.

While public cloud offerings are popular, it is interesting to note that the common migration strategies[1] currently include:

  1. Rehosting/Lift and shift — moving existing software from local to remote hosting
  2. Replatforming — moving existing software to remote hosting and adapting it to some extent to work better in the cloud
  3. Repurchasing — buying new, cloud-based software
  4. Refactoring/Re-architecting — adapting software to be a cloud-native application
  5. Retire — removing IT portfolio that is no longer useful
  6. Retain — not doing anything, for now

The strategies that involve migration largely align to named *aaS strategies, 1:IaaS, 2:PaaS, 3:SaaS/ASP, 4:PaaS/FaaS/Managed services.

In this presentation, we argue that FaaS / Managed services strategies are useful in a number of contexts and should be evaluated when (re-)architecting cloud-based solutions. Further, we present real-world use cases and a number of pointers that will help avoid common pitfalls that misunderstanding what FaaS[2] is can lead to, including vendor lock-in, elevated costs and spaghetti code. We also talk about the unavoidable technical debt involved in choosing cloud-based approaches.


**Terminology**

| ASP | Application service provider |   
| FaaS | Function as a service |
| IaaS | Infrastructure as a service |
| PaaS | Platform as a service |
| SaaS | Software as a service |
| Managed services | Basic functions (network, databases, etc.) are run in a managed environment |


**References**

[1] Orban, Stephen. 2016. *6 strategies for migrating applications to the cloud.* Accessed 2019-01-04 from https://medium.com/aws-enterprise-collection/6-strategies-for-migrating-applications-to-the-cloud-eb4e85c412b4
[2] 
