# Microservices & Monolith

In recent years, microservices architecture has gained immense popularity in the software development world. This approach offers numerous benefits, such as scalability, agility, and ease of maintenance, making it a compelling choice for many organizations. It promotes rapid development, deployment, and scaling of services. However, there are instances where the microservices approach might not be the best fit. As an example, you can read about how and why Amazon [has been dumped microservices for video monitoring](https://thenewstack.io/return-of-the-monolith-amazon-dumps-microservices-for-video-monitoring/). But not only Amazon, the below architectural trends figure
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9ddhk2c9aa5rr8g00hgt.png) indicates, that modular monolith is already on early majority stage in 2023. Hmm, it seems to be a growing trend...
  
#Understanding Micro-Packages
Nevertheless you are transferring your microservices to monolith, designing monolith from scratch or design you system according to microservices pattern, staying agile, efficient, and adaptable is key.

> And here I'd like to introduce you **micro-packages architecture pattern definition©**.
 
This approach, inspired by microservices, offers a fresh perspective on how to structure and manage code in a modular and scalable way. Micro-packages can be thought of as the smaller building blocks within a software project. These are individual, self-contained pieces of code, each serving a specific function or solving a particular problem. While they share similarities with libraries and modules, micro-packages go a step further by emphasizing extreme modularity, minimalism, and a focus on doing one thing exceptionally well.

# Benefits of Micro-Packages Architecture

 - **modularity**: micro-packages promote a highly modular approach to code organization. Developers can easily pick and choose the specific functionalities they need, reducing code bloat and improving maintainability.

 - **scalability**: by breaking down a project into a collection of micro-packages, it becomes easier to scale and evolve individual components independently. This means faster development and deployment cycles for specific features or improvements.

 - **reusability**: micro-packages are designed to be reusable across projects. When you create a micro-package to solve a particular problem, it can be shared across different applications, saving time and effort.

 - **version control**: managing dependencies and updates becomes simpler with micro-packages. Each micro-package can have its version control, allowing for fine-grained control over updates and backward compatibility.

 - **collaboration**: teams can collaborate more efficiently as micro-packages facilitate better code isolation and clearer interfaces. This also makes it easier to onboard new team members.

 - **testing and maintenance**: smaller, focused codebases are easier to test and maintain. When issues arise, it's often easier to locate and fix them in a specific micro-package.

> Conceptually, the pattern is similar to microservices one, at least one binary package can be treated as a service but a difference is that it can be used in monolith application or reused in another service. Moreover, during package updates (keeping its API unchanged) you can transfer functionality to external services - in another words you can scale your application.

# Approach
Let's assume that we designed eShop with a four microservices that communicate with each other via Event Bus and expose API throughout gateway:

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/4ksm7dcdv1y89jgk68yh.png)
The similar effect, of course in very simplification, can be achieved with monolith which is built on four packages (_Identity_, _Catalog_, _Ordering_ and _Basket_). These packages need to expose contracts for communication with each other and approach for communication depends of our needs. If we'll decide to extract for instance, _Identity_ for separate microservice, we only need to update _Identity_ package inside an application that will order its job to new microservice, Event Bus, etc.

# Conclusion

Micro-packages architecture is a promising approach for modern software development. It offers a scalable, modular, and efficient way to build and maintain software projects. While it might not be suitable for every use case, it can enhance development speed, code quality, and collaboration in the right contexts. As the software development landscape continues to evolve, micro-packages are a valuable tool for staying agile and adaptable in the face of ever-changing requirements and technologies. It is not only about commonly used utilities, it is about start packaging your organization domain logic and later easily reuse or scale using miscroservices (or scale back to monolith).

