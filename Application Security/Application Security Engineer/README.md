# Skills

## Table of contents

* [Architecture and working principles of modern web applications](#architecture-and-working-principles-of-modern-web-applications)
   * [Overview](#overview)
   * [Core components](#core-components)
   * [Three-tier architecture](#three-tier-architecture)
      * [Presentation layer: client-side component (front-end)](#presentation-layer-client-side-component-front-end)
      * [Application layer: web server](#application-layer-web-server)
      * [Application layer: server-side component (back-end)](#application-layer-server-side-component-back-end)
      * [Application layer: Application Programming Interface (API)](#application-layer-application-programming-interface-api)
      * [Application layer: cloud instance](#application-layer-cloud-instance)
      * [Data layer: database](#data-layer-database)
   * [Scalability](#scalability)
      * [Caching system](#caching-system)
      * [Cloud storage (Amazon S3)](#cloud-storage-amazon-s3)
      * [CDN (CloudFront)](#cdn-cloudfront)
      * [Load balancer](#load-balancer)
      * [Multiple servers](#multiple-servers)
   * [Types of web application architecture](#types-of-web-application-architecture)
      * [Monolithic architecture](#monolithic-architecture)
      * [Microservice architecture](#microservice-architecture)
      * [Containers](#containers)
      * [Serverless architecture](#serverless-architecture)
      * [API gateway](#api-gateway)
   * [Best practices](#best-practices)
      * [Scalable web server](#scalable-web-server)
      * [Elastic infrastructure](#elastic-infrastructure)
      * [Immutable infrastructure](#immutable-infrastructure)
      * [Microservice and serverless approach](#microservice-and-serverless-approach)
      * [Multi-tenant architecture](#multi-tenant-architecture)
      * [HIPAA and SOC2 guidelines](#hipaa-and-soc2-guidelines)
      * [DevOps CI/CD environment](#devops-cicd-environment)
      * [Infrastructure as a Code tools](#infrastructure-as-a-code-tools)
   * [Working principles](#working-principles)
      * [Separation of concerns](#separation-of-concerns)
      * [Encapsulation](#encapsulation)
      * [Single responsibility](#single-responsibility)
      * [Don't Repeat Yourself](#dont-repeat-yourself)
      * [Duplication is waste](#duplication-is-waste)
      * [Dependency inversion principle](#dependency-inversion-principle)
      * [Explicit dependencies principle](#explicit-dependencies-principle)
      * [Persistence Ignorance](#persistence-ignorance)
      * [Bounded context](#bounded-context)
* [Basic concepts of information security](#basic-concepts-of-information-security)
   * [Overview](#overview)
   * [Core principles](#core-principles)
      * [Confidentiality](#confidentiality)
      * [Integrity](#integrity)
      * [Availability](#availability)
      * [Identification](#identification)
      * [Authentication](#authentication)
      * [Authorization](#authorization)
      * [Accountability](#accountability)
      * [Logs](#logs)
      * [Functionality and assurance](#functionality-and-assurance)
      * [Privacy](#privacy)
      * [Non-repudiation](#non-repudiation)
   * [Information Security Policy](#information-security-policy)
   * [Threat intelligence](#threat-intelligence)
      * [Poorly secured systems](#poorly-secured-systems)
      * [Social media attacks](#social-media-attacks)
      * [Social engineering](#social-engineering)
      * [Malware on endpoints](#malware-on-endpoints)
      * [Lack of encryption](#lack-of-encryption)
      * [Security misconfiguration](#security-misconfiguration)
   * [Active and passive attacks](#active-and-passive-attacks)
      * [Active attack](#active-attack)
      * [Passive attack](#passive-attack)
* [CWE/SANS Top 25 Most Dangerous Software Errors](#cwesans-top-25-most-dangerous-software-errors)
   * [The 2022 CWE Top 25](#the-2022-cwe-top-25)
* [OWASP Top 10](#owasp-top-10)
   * [Overview](#overview)
   * [Methodology](#methodology)
   * [New vulnerability categories](#new-vulnerability-categories)
   * [Critical changes](#critical-changes)
      * [A03:2021 – Injections become more expansive](#a032021--injections-become-more-expansive)
      * [A05:2021 – Security misconfiguration rising in priority](#a052021--security-misconfiguration-rising-in-priority)
   * [OWASP Top 10 application vulnerabilities 2022](#owasp-top-10-application-vulnerabilities-2022)
      * [1. Broken access control](#1-broken-access-control)
      * [2. Cryptographic failures](#2-cryptographic-failures)
      * [3. Injections](#3-injections)
      * [4. Insecure design](#4-insecure-design)
      * [5. Security misconfigurations](#5-security-misconfigurations)
      * [6. Vulnerable and outdated components](#6-vulnerable-and-outdated-components)
      * [7. Identification and authentication failures](#7-identification-and-authentication-failures)
      * [8. Software and data integrity failures](#8-software-and-data-integrity-failures)
      * [9. Security logging and monitoring failures](#9-security-logging-and-monitoring-failures)
      * [10. Server-Side Request Forgery (SSRF)](#10-server-side-request-forgery-SSRF)

## Architecture and working principles of modern web applications

### Overview

Web application architecture presents a layout with all software components (servers, databases and middleware) and how they interact with each other. It defines how data is delivered through HTTP and ensures that client-side server and backend server can understand. Moreover, it also secures that valid data is present in all user requests. It creates and manages records while providing permission-based access and authentication. Choosing the right design defines your company growth, reliability and interoperability. Hence, it is important to understand components comprising the architecture of web applications.

### Core components

Typically, web-based application architecture comprises three core components:

1. Web browser: the key component that interacts with user, receives input and manages presentation logic while controlling user interactions with the application. User inputs are validated as well.

2. Web server: handles the business logic and processes user requests by routing the requests to the right component and managing entire application operations. It can run and oversee requests from a wide variety of clients.

3. Database server: provides required data for the application and handles data-related tasks. In a multi-tiered architecture, database servers can manage business logic with help of stored procedures.

### Three-tier architecture

In a traditional two-tier architecture, there are two components, namely the client-side system or the user interface and a backend system, which is usually a database server. Here, the business logic is incorporated into the user interface or the database server. The downside of 2-tier architecture is that with increased number of users, performance decreases. Moreover, direct interaction of the database and the user device also raises some security concerns.

There are three layers of a three-tier architecture:

1. Presentation layer
2. Application layer
3. Data layer

![alt text](https://github.com/Tecatech/job-interview-preparation/blob/main/Application%20Security/Application%20Security%20Engineer/images/standard_web_application_architecture.jpg)

In this model, intermediate servers receive client requests and process them by coordinating with subordinate servers applying the business logic. Communication between client and database is managed by the intermediate application layer, thereby enabling clients to access data from different DBMS solutions.

The three-tier architecture is more secure as the client does not directly access data. The ability to deploy application servers on multiple machines provides higher scalability, better performance and better re-use. You can scale it horizontally by scaling each item independently. You can abstract the core business from the database server to efficiently perform load balancing. Data integrity is improved as all data goes through the application server, which decides how data should be accessed and by whom. For that reason, a change of management is easy and cost-effective. The client layer can be a thin-client, which means hardware costs are reduced. This modular model allows you to modify a single tier without affecting remaining components.

#### Presentation layer: client-side component (front-end)

The client-side component of a web application architecture enables users to interact with a server and a backend service via a browser. Server code resides in the browser, receives requests, and presents the user with required information. This is where UX/UI design, dashboards, notifications, configuration settings, layout and interactive elements come into the picture.

Here are some of the commonly used front-end languages and technologies:

* HTML
* CSS
* JavaScript
* React
* Angular.js
* Vue.js

#### Application layer: web server

Web server runs one or more websites or web apps. It uses HyperText Transfer Protocol (HTTP) along with other protocols to listen for user requests via a browser. It processes them by applying business logic and delivering requested content to the end-user.

Web server can be a hardware device or a software program:

* Hardware web server: a computer device that is connected to the Internet and contains web server software and web app components such as images, HTML documents, JS files and CSS stylesheets.
* Software web server: software that understands URLs and HTTP protocols. Users can access it via domain names to receive requested content.

While a static web server delivers the content as it is to the browser, a dynamic web server updates data before delivering it to the browser.

Apache is a popular open-source web server from Apache Software Foundation. It is based on a process-driven model, wherein every request results in creation of a new thread. The modular design of Apache allows you to easily scale individual resources. With minimal configuration, you can manage even large traffic. It works on macOS, Windows and Linux environments. However, Linux is the most preferred environment for Apache.

While it uses a file-system to process static content, dynamic content is processed within the server. Using .htaccess files, you can perform additional configurations to the server settings.

NGINX is another popular web server that operates on an event-driven model wherein thousands of requests are processed within a single thread, delivering more with minimal resources. It uses PHP to serve static resources and serves static content two times faster than Apache. Dynamic content is served via external processes. When it comes to interpreting requests, Apache passes the file system location while NGINX passes the URI. This feature extends NGINX capability as a load balancer, HTTP cache and a proxy server.

While it supports Unix-based OS, Windows compatibility is limited. You can not make additional configurations. Smaller codebase offers better security. Dynamic modules are not supported. Along with mailing lists and IRC, Forum is available too.

NGINX has an edge over Apache as it serves as a web server as well as a proxy server. The event-driven approach that processes thousands of requests in a single thread offers greater performance, speed and cost-effectiveness.

#### Application layer: server-side component (back-end)

The server-side component is a key component of the web application architecture that receives user requests, performs business logic and delivers required data to front-end systems. It contains servers, databases, web services.

Here are some of the commonly used back-end technologies:

* Go
* Java
* NodeJS
* PHP
* Python
* Ruby

#### Application layer: Application Programming Interface (API)

Application Programming Interface (API) is not a technology – it is a concept that enables developers to access certain data and functions of a software. Simply put, it is a mediator that allows apps to communicate with each other. It comprises protocols, tools and subroutine definitions required to build apps.

For instance, when you sign in to an application, the app calls an API to retrieve your account details and credentials. The application will contact corresponding servers to receive this information and return this data to the user app. A web API is an API available over the web via HTTP protocol. It can be built using technologies such as .NET and Java.

With APIs, developers do not have to create everything from scratch but use existing functions exposed as an API to increase productivity and gain faster time to market. By reducing development efforts, APIs significantly reduce development costs. It also improves collaboration and connectivity across the ecosystem while enhancing customer experience.

There are different types of APIs:

* RESTful API: Representational State Transfer API in lightweight JSON format. It is highly scalable, dependable and delivers fast performance, making it the most popular API.
* SOAP: Simple Object Access Protocol uses XML for data transmission. It requires more bandwidth and advanced security.
* XML-RPC: Extensible Markup Language – Remote Procedure Calls uses specific XML format for data transmission.
* JSON-RPC: uses JSON format for data transmission.

#### Application layer: cloud instance

Servers or cloud instances are an important part of a web application architecture. A cloud instance is a virtual server instance that is built, delivered and hosted using a public or a private cloud and accessible over the Internet. It works as a physical server that can seamlessly move across multiple devices or deploy multiple instances on a single server. Hence, it is highly dynamic, scalable and cost-effective. You can automatically replace servers without application downtime. Using cloud instances, you can easily deploy and manage web applications in any environment.

#### Data layer: database

A database is a key component of a web application that stores and manages information for a web app. Using a function, you can search, filter and sort information based on user request and present required information to the end user. They allow role-based access to maintain data integrity.

While choosing a database for your architecture of web app, size, speed, scalability and structure are four aspects that require your consideration. For structured data, SQL-based databases are a good choice. It suits financial apps wherein data integrity is a key requirement.

To handle unstructured data, NoSQL is a good option. It suits apps wherein the nature of incoming data is not predictable. Key-value databases associate each value with a key and suit databases that store user profiles, reviews, blog comments. For analytics, Wide Column databases are a good choice.

### Scalability

#### Caching system

A caching system is a local data store that facilitates quick access to data for an application server instead of contacting a database every time. In a traditional setup, data is stored in a database. When a user makes a request, the app server requests that data from the database and presents it to the user. When the same data is requested again, the server should perform the same process again that is repetitive and time-consuming. By storing this information in a temporary cache memory, apps can quickly present data to users.

Caching system can be designed in four models:

* Application server cache: in-memory cache alongside the application server (for apps that have a single node).
* Global cache: all nodes access a single cache space.
* Distributed cache: cache is distributed across nodes, wherein a consistent hashing function is used to route the request to the required data.
* Content Delivery Network (CDN): used to deliver large amounts of static data.

Redis and Memcached are two most popular caching systems with similar features. However, Redis offers a rich set of tools, making it applicable for performing a variety of tasks. On the other hand, Memcached is simple and easy to use.

The caching system from AWS is called AWS ElastiCache. This web service enables administrators to scale and manage in-memory data store service in the cloud. AWS also offers a fully-managed Redis-compatible in-memory data store called Amazon ElastiCache for Redis and a fully-managed Memcached-compatible in-memory data store service called Amazon ElastiCache for Memcached.

#### Cloud storage (Amazon S3)

In a web application architecture, cloud storage is an obvious requirement. Cloud storage is about storing data in the cloud and accessing it over the Internet. A cloud service provider provides storage infrastructure on a pay-per-use subscription model.

As AWS is the most popular cloud service provider, Amazon S3 is the popularly used cloud storage solution in web application architecture across the globe. Amazon Simple Storage Service (S3) is a cloud storage service that is flexible, cost-effective, durable, secure and offers high availability and high scalability.

![alt text](https://github.com/Tecatech/job-interview-preparation/blob/main/Application%20Security/Application%20Security%20Engineer/images/cloud_storage_amazon_s3.jpg)

In AWS, a cloud storage unit is called a bucket. When a bucket is created, it is deployed in the region specified by the user. Once deployment is done and objects are added to the bucket, the user can choose the storage class type along with features such as versioning control, lifecycle policies, bucket policy etc. AWS takes care of lifecycle management for a group of objects, including IAM policy and data protection.

#### CDN (CloudFront)

A Content Delivery Network (CDN) is a server network that is installed in various geolocations to deliver content faster and better to users. Instead of contacting a central server, the user request is routed to a CDN server that stores a cached version of content. Hence, site speed and performance is increased, and packet loss is decreased. The server load is decreased. It also enables segmentation of the audience and advanced web security.

CloudFront is a popular CDN service for web application architecture AWS. It acts as a distributed cache to deliver higher speed, low latency and better customer experience. Considering global presence of AWS, CloudFront gives a wider range of geolocations for users. CloudFront integrates well with other AWS services such as Amazon EC2, AWS Lambda, Amazon CloudWatch, Amazon S3 to make your job easier. It is flexible, easy to set up and offers high scalability. It also features elastic services and analytics. You can control access to the content as well.

Azure CDN is a popular content delivery network from Microsoft Azure cloud platform that is easy to configure and use and offers low latency.

Google content delivery network is called Cloud CDN. It leverages globally distributed edge servers to cache content at the usage location to deliver content at high speeds.

CloudFlare is another popular CDN service. Though CloudFlare primarily offers robust DNS services and is not a traditional content delivery network, it acts as a reverse proxy to route traffic through its global network of data centers.

#### Load balancer

As the name says, a load balancer is a service that balances traffic loads by distributing them across different servers based on availability or predefined policies. When a user request is received in the load balancer, it retrieves the health of the server in terms of availability and scalability and routes the request to the best server. A load balancer can be a hardware component or a software program.

Load balancing can be done in two ways:

1. TCP/IP level load balancing: load balancing based on the DNS.

2. App-level load balancing: load balancing based on application load.

#### Multiple servers

In a traditional web architecture, you will see a web server and a database. Web server listens to client requests and contacts database to provide required information or process business logic. When concurrent users increase, the web server will run out of resources. Even though upgrading the server configuration helps for a while, it provides limited capabilities while causing a single point of failure too. Deploying multiple servers is a good choice to create a highly scalable web architecture.

While designing multiserver architecture, organizations can either connect multiple OS deployment servers to a single database or multiple databases. However, it is important to keep them replicated with appropriate content. Replication can be scheduled at specified times.

### Types of web application architecture

#### Monolithic architecture

A monolithic architecture is a traditional software development model – also known as web development architecture – wherein the entire software is developed as a single piece of code going through a traditional waterfall model. It means all components are interdependent and interconnected, and every component is required to run the application. To change or update a specific feature, you need to change the entire code to be rewritten and compiled.

As monolithic architecture treats the entire code as a single program, building a new project, applying frameworks, scripts and templates and testing it becomes simple and easy. Deployment is easy as well. However, as the code grows bigger, it becomes difficult to manage or make updates; for even a small change, you need to go through the entire process of your web development architecture. As each element is interdependent, it is not easy to scale the application. Moreover, it is not reliable, as a single point of failure can bring down the application.

When you want to build a lightweight application and when you are on a tight budget, monolithic architecture will serve the purpose. However, it makes sense to use a monolithic model when your development team is working from a single location and not spread remotely.

#### Microservice architecture

Microservice architecture solves several challenges that are encountered in a monolithic environment. In a microservice architecture, the code is developed as loosely-coupled, independent services that communicate via RESTful APIs. Each microservice contains its own database and operates a specific business logic, which means you can develop and deploy independent services with ease.

Since it is loosely coupled, microservice architecture provides flexibility to update and scale independent services. Development becomes easy and efficient, and continuous delivery is enabled. Developers can quickly adapt to innovation. For highly scalable and complex applications, microservices is a good choice.

However, deploying multiple services with runtime instances is a challenge. When the number of services grows, the complexity in managing them grows too. Moreover, microservice apps share partition databases. It means that you should ensure consistency across multiple databases that are affected by the transaction.

#### Containers

Container technology is the best option when it comes to deploying microservices. A container is an encapsulation of a lightweight runtime environment for an application that can run on a physical or a virtual machine. Hence, applications run in a consistent environment right from the developer device to the production environment. By abstracting execution at the OS-level, containerization allows you to run multiple containers inside a single OS instance. While it reduces overhead and processing power, it increases efficiency as well.

Containerization enables developers to add multiple app components in a single VM environment instead of segregating code into different VMs, and thereby gain more application processing power. With its lightweight nature, containers run quicker. They are flexible, reliable and best suit policy-based microservice environments.

Docker is the most popular containerization technology that offers a comprehensive ecosystem for containerization technologies. It offers greater performance, easy-to-use technology and large community support.

#### Serverless architecture

Serverless architecture is a model of developing software applications. In this structure, provisioning of underlying infrastructure is managed by an infrastructure service provider. It means you only pay for the infrastructure when it is in use, and not for idle CPU time or unused space. Serverless computing lowers costs as resources are only used when the application is in execution. Scaling tasks are handled by the cloud provider. Moreover, backend code gets simplified. It reduces development efforts, costs and brings faster time to market.

Multimedia processing, live-streaming, chatbots CI pipelines, IoT sensor messages are some of the use cases for serverless computing.

In a microservice architecture, you can perform serverless computing using AWS Lambda, API gateway and API step functions.

![alt text](https://github.com/Tecatech/job-interview-preparation/blob/main/Application%20Security/Application%20Security%20Engineer/images/serverless_architecture.jpg)

#### API gateway

An API gateway is an API management tool that enables you to create, publish, secure and manage HTTP, WebSocket and REST APIs. Acting as a reverse proxy, an API gateway receives various API calls, performs service aggregation to fulfill those calls and delivers the result. API gateways help you to protect your APIs, run analytics tools on APIs, connect a billing service or manage older and deleted APIs etc. In a serverless environment, resources are provisioned based on the API calls. API gateway helps you to deploy and manage serverless functions.

### Best practices

#### Scalable web server

A scalable web server is critical to delivering consistent app performance regardless of concurrent user number, location and time. There are three types of scaling options namely horizontal scaling, vertical scaling and diagonal scaling. While vertical scaling is about upgrading or downgrading device configuration, horizontal scaling is about increasing or decreasing number of devices. Diagonal scaling is about combining both models. Choosing a horizontal scaling model is recommended as you will not be limited by configuration or number of servers. Moreover, you can mix vertical scaling as and where applicable.

#### Elastic infrastructure

With hybrid and multi-cloud environments increasingly becoming popular, adapting to the cloud and proactively provisioning resources is key to delivering high-performing web apps. Elastic infrastructure comes with preconfigured network systems, VM servers, storage and compute resources, allowing to easily manage the environment with self-service portals. It gives flexibility to quickly adapt to changing market needs and customer expectations.

#### Immutable infrastructure

Simply put, immutable infrastructure is something that can not be changed once deployed. It enables administrators to automatically provision resources using code. When servers are to be updated or modified, they are automatically replaced by newer ones.

Configuration drift is a big challenge in mutable infrastructure. Scaling and debugging issues while replicating the production environment adds up to this challenge. Immutable infrastructure uses a validated and version-controlled image to provision new servers for every deployment. So, previous state of the server is not a concern. You can test servers before deploying them. It eliminates configuration drifts, allows horizontal scaling while offering simple rollback and recovery with consistent staging environments.

#### Microservice and serverless approach

Microservice and serverless computing are both critical to web application development. However, the difference is that microservice architecture offers a long-term solution with high scalability while serverless computing offers code efficiency. Serverless functions run only when they are triggered.

By combining both models, you can gain the best of both worlds. You can use AWS step functions to assign triggers to combine several functions into a service and assign triggers to them. With event-triggered microservices, you can build a combined system to gain code efficiency, long-term stability, cost-effectiveness and scalability.

#### Multi-tenant architecture

Web applications are now being delivered as SaaS applications. There are two models to deploy SaaS apps, single-tenant vs multi-tenant architecture.

* Single-tenant architecture: a single standalone environment is created for each organization, comprising the infrastructure, software and hardware ecosystem.
* Multi-tenant architecture: a single cloud environment with fully centralized services and logically isolated is shared by multiple organizations.

For web apps, using a multi-tenant architecture offers multiple benefits. Organizations can manage a single code base for all users, reducing overhead and code conflict issues. It also reduces server infrastructure costs through economies of scale. Along with reduced development efforts, it brings faster time to market as well.

#### HIPAA and SOC2 guidelines

Building a secure architecture is a minimal requirement for any organization. Applying security protocols and policies not only secures your data and environment, but it also helps you easily manage audit tasks and comply with government regulations.

* HIPAA: Health Insurance Portability and Accountability Act (HIPAA) is an important requirement that health organizations are required to comply with. It helps in reducing healthcare frauds while securing private health information.
* SOC2: a key aspect in ensuring that your data is securely managed by the cloud service provider. While organizations do not have to comply with SOC2 guidelines, it is good to follow them to secure customer data. SOC2 guidelines define five trust service principles that customer data management is based upon.

#### DevOps CI/CD environment

Deployment automation is about automating the process of code movement between testing and production environments with ease. It enables developers to quickly and frequently deploy code to production without human intervention. AWS offers a fully managed deployment service in the form of AWS CodeDeploy. It enables you to automatically deploy code to a variety of environments such as AWS Lambda, AWS Fargate, Amazon EC2 or on-premise.

Deployment automation is a part of DevOps continuous deployment pipeline. It consists of three important phases: build, test and deploy. When the code is written, it is automatically tested and added to the central repository. These changes are validated and added to the application. Automating testing runs a variety of tests at different levels to ensure that the code is error-free. Then the code is automatically deployed to production.

#### Infrastructure as a Code tools

Infrastructure as a Code (IaaC) is a method of automatically provisioning the infrastructure using code. It helps you to treat servers, network, database and other IT resources as software and manage them using config files. Hence, you can spin up resources instantly on-demand, manage configuration consistency, eliminate configuration drifts while increasing software development efficiency. It reduces software development costs as well. Terraform and AWS CloudFormation are two most popular IaaC tools.

### Working principles

#### Separation of concerns

A key principle of software design – this principle encompasses creation of a system architecture with layered components, each addressing a separate concern. Software architecture design created using this principle can be maintained easily, and it is less tightly coupled.

An architecture designed by deploying this principle keeps business logic and rules in a discreet location, while infrastructure and user interface reside in a separate project. This principle ensures that iterations in software design do not affect the core business model, at the same time the model can be tested easily for its efficacy.

#### Encapsulation

Encapsulation is defined as casing up of data inside a single discrete unit. This principle holds together code and data it manages. In other words, encapsulation protects the data from being accessed by entities outside the unit.

Software architects utilize this key principle of encapsulation or Object-Oriented Programming using a programming language like Java, which lends their code security, flexibility and easy maintainability. This allows a developer to design constructs (objects, functions and classes) that can be declared as a public interface where clients can interact without internal implementation being tampered or dependent client code getting affected. Most software developers are comfortable using encapsulation to hide (instance variables) of a class from illegal direct access.

This hidden data can be accessed only through any member function of its own class in which they are declared. This is popularly known as data hiding. Encapsulation provides a great deal of flexibility to enterprise systems. The entire business process can be overhauled without significant changes in the delivery process. Systems that are open to change as your business undergoes transformation. A single module of the entire system can undergo changes independently without any impact on any other module of the system.

#### Single responsibility

This is one of the most widely applied principles by developers to build robust, scalable and easy to maintain applications. This can be applied not just to classes or microservices, but also to software components. Its simplicity is its key feature, making the application easier to implement and open to changes in the future.

One of the key considerations is that application requirements change over a period and if your class component has been assigned multiple responsibilities, the more frequently you may need to change it, and they cease to be independent of each other.

#### Don't Repeat Yourself

Changes effected in one class may necessitate updates or recompilation of the dependent classes. Depending on your change, you might need to update the dependencies or recompile the dependent classes, even though they are not directly affected by your change.

Consequently, you may have to update your class more often, each change getting more complex. Hence, the principle ensures that each class is assigned only one responsibility. Classes, software components and microservices that have only one responsibility are easy to maintain, test or debug and lead to faster deployment.

The principle states that duplication in logic should be eliminated via abstraction, and duplication in process should be eliminated via automation.

#### Duplication is waste

Adding unnecessary code to a codebase increases the amount of work required to extend and maintain software in the future. Duplicate code adds to technical debt. Whether the duplication stems from Copy and Paste Programming or poor understanding of how to apply abstraction, it decreases the quality of the code. Duplication in process is also waste if it can be automated. Manual testing, manual build and integration processes should all be eliminated whenever possible through the use of automation.

#### Dependency inversion principle

This principle of architecture design deals with high-level modules of application, which generally involve complex logic. This means they are easily reusable and are unaffected by changes in low-level modules, which basically deal with utility features of the application. An abstraction needs to be introduced to that can decouple high-level and low-level modules from each other.

An introduction of a simple interface abstraction between the higher-level and the lower-level software components eliminates dependencies between them. The principle enables architects to modify the higher-level as well as the lower-level components without affecting any other classes if interface abstractions remain the same.

However, it must be noted that the principle is not something that can be used to resolve dependencies, instead it enables developers to design an architecture that allows to test various modules of the application in isolation.

#### Explicit dependencies principle

Strong inter-module dependencies are regarded as an indicator of poor software design. Tightly coupled systems, in which modules have excessive dependencies, are difficult to work with as different modules can not be studied easily in isolation, and revisions or extensions to functionality can not be added. Identifying architectural dependencies proactively in the development life cycle along with metrics leads to better communication of architecture quality.

If a component or class relies on other components to accomplish its operations, then other components are known as the dependencies for this class. Classes or components can have both implicit or explicit dependencies.

This principle of architectural design explicitly declares class-level dependencies at the time of class construction. Most of the time as explicit dependency is an interface which can be exchanged with other implementations at any point in the design life cycle, whether in production or during testing or debugging. This principle makes architecture design loosely coupled, easier to test and accepting of change or enhancement.

#### Persistence Ignorance

The principle of Persistence Ignorance (PI) holds that classes modeling the business domain in a software application should not be impacted by how they might be persisted. Thus, their design should reflect as closely as possible the ideal design needed to solve the business problem at hand and should not be tainted by concerns related to how object state is saved and later retrieved. Some common violations of Persistence Ignorance include domain objects that must inherit from a particular base class, or which must expose certain properties. Sometimes, the persistence knowledge takes the form of attributes that must be applied to class, or support for only certain types of collections or property visibility levels. There are degrees of persistence ignorance, with the highest degree being described as Plain Old CLR Objects in .NET, and Plain Old Java Objects in Java world.

#### Bounded context

Bounded context is a central pattern in Domain-Driven Design. It is the focus of DDD-strategic design section, which is all about dealing with large models and teams. Domain-Driven Design deals with large models by dividing them into different bounded contexts and being explicit about their interrelationships.

## Basic concepts of information security

### Overview

Information security covers tools and processes that organizations use to protect information. This includes policy settings that prevent unauthorized people from accessing business or personal information. InfoSec is a growing and evolving field that covers a wide range of fields, from network and infrastructure security to testing and auditing.

Information security protects sensitive information from unauthorized activities, including inspection, modification, recording, and any disruption or destruction. The goal is to ensure safety and privacy of critical data such as customer account details, financial data or intellectual property.

The consequences of security incidents include theft of private information, data tampering, and data deletion. Attacks can disrupt work processes and damage a company reputation, and also have a tangible cost.

Organizations must allocate funds for security and ensure that they are ready to detect, respond to, and proactively prevent, attacks such as phishing, malware, viruses, malicious insiders, and ransomware.

### Core principles

Basic tenets of information security are confidentiality, integrity and availability. Every element of an information security program must be designed to implement one or more of these principles. Together they are called the CIA triad.

#### Confidentiality

In the context of information security, confidentiality means information to stay secret stays secret, and only those persons authorized to access it may receive access. From ancient times, mankind has known that information is power, and in our information age, access to information is more important than ever. Unauthorized access to confidential information may have devastating consequences, not only in national security applications, but also in commerce and industry. Main mechanisms of confidentiality protection in information systems are cryptography and access controls. Examples of threats to confidentiality are malware, intruders, social engineering, insecure networks, and poorly administered systems.

#### Integrity

Integrity is concerned with trustworthiness, origin, completeness, and correctness of information as well as prevention of improper or unauthorized data modification. In the information security context it refers not only to integrity of information itself, but also to the origin integrity – that is, integrity of the information source. Integrity protection mechanisms may be grouped into two broad types: preventive mechanisms, such as access controls that prevent unauthorized modification of information, and detective mechanisms, which are intended to detect unauthorized modifications when preventive mechanisms have failed. Controls that protect integrity include principles of least privilege, separation, and rotation of duties.

#### Availability

Availability is protection of a system ability to make software systems and data fully available when a user needs it (or at a specified time). The purpose of availability is to make technology infrastructure, applications and data available when they are needed for organizational process or for organization customers. Although it is usually mentioned last, availability is not the least important pillar of information security. Therefore, despite being mentioned last in the CIA triad, availability is just as important and as necessary a component of information security as confidentiality and integrity. Attacks against availability are known as denial of service (DoS) attacks and are discussed below. Natural and man-made disasters obviously may also affect availability as well as confidentiality and integrity of information, though their frequency and severity greatly differ – natural disasters are infrequent but severe, whereas human errors are frequent but usually not as severe as natural disasters. In both cases, business continuity and disaster recovery planning (which at the very least includes regular and reliable backups) is intended to minimize losses.

#### Identification

Identification is the first step in the identify-authenticate-authorize sequence that is performed every day countless times by humans and computers alike when access to information or information processing resources is required. While particulars of identification systems differ depending on who or what is being identified, some intrinsic properties of identification apply regardless of these particulars – just three of these properties are scope, locality, and uniqueness of IDs.

Identification name spaces can be local or global in scope. This is one of the reasons why two user accounts should never use the same name on the same system – not only because you would not be able to enforce access controls based on non-unique and ambiguous usernames, but also because you would not be able to establish accountability for user actions.

To summarize, for information security purposes, unique names are required and, depending on their scope, they must be locally unique and possibly globally unique so that access control may be enforced and accountability established.

#### Authentication

Authentication, which happens just after identification and before authorization, verifies the authenticity of the identity declared at the identification stage. In other words, it is at the authentication stage when you prove that you are indeed the person or the system you claim to be. Regardless of the particular authentication method used, the aim is to obtain reasonable assurance that the identity declared at the identification stage belongs to the party in communication. It is important to note that reasonable assurance may mean different degrees of assurance, depending on the particular environment and application, and therefore may require different approaches to authentication: authentication requirements of a national security – critical system naturally differ from authentication requirements of a small company. Because different authentication methods have different costs and properties as well as different returns on investment, the choice of authentication method for a particular system or organization should be made after these factors have been carefully considered.

#### Authorization

After declaring identity at the identification stage and proving it at the authentication stage, users are assigned a set of authorizations (also referred to as rights, privileges, or permissions) that define what they can do on the system. These authorizations are most commonly set by the security or system administrator. These privileges may range from the extremes of «permit nothing» to «permit everything» and include anything in between. As you can see, the second and third stages of the identify-authenticate-authorize process depend on the first stage, and the final goal of the whole process is to enforce access control and accountability, which is described next.

#### Accountability

Accountability is another important principle of information security that refers to the possibility of tracing actions and events back in time to users, systems, or processes that performed them, to establish responsibility for actions or omissions. Authorization is the process of ensuring that a user has sufficient rights to perform the requested operation and preventing those without sufficient rights from doing the same. At the same time, authorization is also the process which gives rights depending on user identity – human or another system. A system may not be considered secure if it does not provide accountability, because it would be impossible to ascertain who is responsible and what did or did not happen in the system without that safeguard. Accountability in the context of information systems is mainly provided by logs.

#### Logs

System and application logs are ordered lists of events and actions and are the primary means of establishing accountability on most systems. However, logs may be considered trustworthy only if their integrity is reasonably assured. In other words, if anyone can write to erase logs or the audit trail, they would not be considered dependable enough to serve as the basis for accountability. Additionally, in case of networked or communication systems, logs should be correctly timestamped and time should be synchronized across the network so events that affect more than one system may be correctly correlated and attributed.

#### Functionality and assurance

Having introduced the concept of accountability and how it is implemented on most systems, it is time to look at perhaps one of the most challenging issues of information security: it is the difference between our expectations (as well as vendor advertising of product features) and what happens in fact that is referred to as functionality versus assurance.

A particular system may claim to implement a dozen smart security features, but this is very different from being able to say with a high degree of confidence that it indeed implements them, implements them correctly, and will not behave in an unexpected manner. Another way of looking at the functionality versus assurance issue is that functionality is about what a system can do and assurance is about what a system will not do.

#### Privacy

Privacy in the information security context usually refers to expectation and rights of individuals to privacy of their personal information and adequate, secure handling of this information by its users. Personal information here usually refers to information that directly identifies a human being, such as a name and address, although details may differ in different countries.

In many countries, privacy of personal information is protected by laws that impose requirements on organizations processing personal data and set penalties for noncompliance. The European Union (EU) in particular has strict personal data protection legislation in place, which limits how organizations may process personal information and what they can do with it. The US Constitution also guarantees certain privacy rights, although the approach to privacy issues differs between the United States and Europe.

Since privacy is not only a basic human need but also a legally protected right in most countries, organizations should take necessary precautions to protect the confidentiality and integrity of personal information they collect, store, and process. Because of these requirements, although not in the CIA triad, privacy is also an inseparable part of information security and must be addressed in all information security policies as part of information security requirements.

#### Non-repudiation

Non-repudiation in the information security context refers to the property of cryptographic digital signatures that offers the possibility of proving whether a particular message has been digitally signed by the holder of a particular digital signature private key. Non-repudiation is a somewhat controversial subject, partly because it is an important one in this day and age of electronic commerce, and because it does not provide an absolute guarantee: a digital signature owner, who may like to repudiate a transaction maliciously, may always claim that his digital signature key was stolen by someone and that someone actually signed digital transaction in question, thus repudiating the transaction.

### Information Security Policy

An Information Security Policy (ISP) is a set of rules that guide individuals when using IT assets. Companies can create information security policies to ensure that employees and other users follow security protocols and procedures. Security policies are intended to ensure that only authorized users can access sensitive systems and information.

Creating an effective security policy and taking steps to ensure compliance is an important step towards preventing and mitigating security threats. To make your policy truly effective, update it frequently based on company changes, new threats, conclusions drawn from previous breaches, and changes to security systems and tools.

Make your information security strategy practical and reasonable. To meet the needs and urgency of different departments within the organization, it is necessary to deploy a system of exceptions, with an approval process, enabling departments or individuals to deviate from rules in specific circumstances.

### Threat intelligence

There are hundreds of security threat categories and millions of known threat vectors. Below, we cover some of the key threats that are a priority for security teams at modern enterprises.

#### Poorly secured systems

The speed and technological development often leads to compromises in security measures. In other cases, systems are developed without security in mind, and remain in operation at an organization as legacy systems. Organizations must identify these poorly secured systems, and mitigate the threat by securing or patching them, decommissioning them, or isolating them.

#### Social media attacks

Many people have social media accounts, where they often unintentionally share a lot of information about themselves. Attackers can launch attacks directly via social media, for example by spreading malware via social media messages, or indirectly, by using information obtained from these sites to analyze user and organizational vulnerabilities, and use them to design an attack.

#### Social engineering

Social engineering involves attackers sending emails and messages that trick users into performing actions that may compromise their security or divulge private information. Attackers manipulate users using psychological triggers like curiosity, urgency or fear.

Because the source of a social engineering message appears to be trusted, people are more likely to comply, for example by clicking a link that installs malware on their device, or by providing personal information, credentials, or financial details.

Organizations can mitigate social engineering by making users aware of its dangers and training them to identify and avoid suspected social engineering messages. In addition, technological systems can be used to block social engineering at its source, or prevent users from performing dangerous actions such as clicking on unknown links or downloading unknown attachments.

#### Malware on endpoints

Organizational users work with a large variety of endpoint devices, including desktop computers, laptops, tablets, and mobile phones, many of which are privately owned and not under the organization control, and all of which connect regularly to the Internet.

A primary threat on all these endpoints is malware, which can be transmitted by a variety of means, can result in compromise of the endpoint itself, and can also lead to privilege escalation to other organizational systems.

Traditional antivirus software is insufficient to block all modern forms of malware, and more advanced approaches are developing to securing endpoints, such as Endpoint Detection and Response (EDR).

#### Lack of encryption

Encryption processes encrypts data so that it can only be decrypted by users with secret keys. It is very effective in preventing data loss or corruption in case of equipment loss or theft, or in case organizational systems are compromised by attackers.

Unfortunately, this measure is often overlooked due to its complexity and lack of legal obligations associated with proper implementation. Organizations are increasingly adopting encryption, by purchasing storage devices or using cloud services that support encryption, or using dedicated security tools.

#### Security misconfiguration

Modern organizations use a huge number of technological platforms and tools, in particular web applications, databases, and Software as a Service (SaaS) applications, or Infrastructure as a Service (IaaS) from providers like Amazon Web Services.

Enterprise grade platforms and cloud services have security features, but these must be configured by the organization. Security misconfiguration due to negligence or human error can result in a security breach. Another problem is «configuration drift», where correct security configuration can quickly become out of date and make a system vulnerable, unbeknownst to IT or security staff.

Organizations can mitigate security misconfiguration using technological platforms that continuously monitor systems, identify configuration gaps, and alert or even automatically remediate configuration issues that make systems vulnerable.

### Active and passive attacks

Information security is intended to protect organizations against malicious attacks. There are two primary types of attacks: active and passive. Active attacks are considered more difficult to prevent, and the focus is on detecting, mitigating and recovering from them. Passive attacks are easier to prevent with strong security measures.

#### Active attack

An active attack involves intercepting a communication or message and altering it for malicious effect. There are three common variants of an active attacks:

1. Interruption – attacker interrupts original communication and creates new, malicious messages, pretending to be one of the communicating parties.
2. Modification – attacker uses existing communications, and either replays them to fool one of the communicating parties, or modifies them to gain an advantage.
3. Fabrication – creates fake, or synthetic, communications, typically with the aim of achieving Denial of Service (DoS). This prevents users from accessing systems or performing normal operations.

#### Passive attack

In a passive attack, an attacker monitors a system and illicitly copies information without altering it. They then use this information to disrupt networks or compromise target systems.

The attackers do not make any change to the communication or target systems. This makes it more difficult to detect. However, encryption can help prevent passive attacks because it obfuscates data, making it more difficult to for attackers to make use of it.

## [CWE/SANS Top 25 Most Dangerous Software Errors](https://cwe.mitre.org/top25/archive/2022/2022_cwe_top25.html)

### [The 2022 CWE Top 25](https://cwe.mitre.org/top25/archive/2022/2022_cwe_top25.html#cwe_top_25)

| Rank     | ID        | Name                                                                                                                                         |
| :---:    | :---:     | :---                                                                                                                                         |
| **1**    | [CWE-787](https://cwe.mitre.org/data/definitions/787.html) | Out-of-Bounds Write                                                                         |
| **2**    | [CWE-79](https://cwe.mitre.org/data/definitions/79.html)   | Improper Neutralization of Input During Web Page Generation («Cross-Site Scripting»)        |
| **3**    | [CWE-89](https://cwe.mitre.org/data/definitions/89.html)   | Improper Neutralization of Special Elements used in an SQL Command («SQL Injection»)        |
| **4**    | [CWE-20](https://cwe.mitre.org/data/definitions/20.html)   | Improper Input Validation                                                                   |
| **5**    | [CWE-125](https://cwe.mitre.org/data/definitions/125.html) | Out-of-Bounds Read                                                                          |
| **6**    | [CWE-78](https://cwe.mitre.org/data/definitions/78.html)   | Improper Neutralization of Special Elements used in an OS Command («OS Command Injection»)  |
| **7**    | [CWE-416](https://cwe.mitre.org/data/definitions/416.html) | Use-After-Free                                                                              |
| **8**    | [CWE-22](https://cwe.mitre.org/data/definitions/22.html)   | Improper Limitation of a Pathname to a Restricted Directory («Path Traversal»)              |
| **9**    | [CWE-352](https://cwe.mitre.org/data/definitions/352.html) | Cross-Site Request Forgery (CSRF)                                                           |
| **10**   | [CWE-434](https://cwe.mitre.org/data/definitions/434.html) | Unrestricted Upload of File with Dangerous Type                                             |
| **11**   | [CWE-476](https://cwe.mitre.org/data/definitions/476.html) | NULL Pointer Dereference                                                                    |
| **12**   | [CWE-502](https://cwe.mitre.org/data/definitions/502.html) | Deserialization of Untrusted Data                                                           |
| **13**   | [CWE-190](https://cwe.mitre.org/data/definitions/190.html) | Integer Overflow or Wraparound                                                              |
| **14**   | [CWE-287](https://cwe.mitre.org/data/definitions/287.html) | Improper Authentication                                                                     |
| **15**   | [CWE-798](https://cwe.mitre.org/data/definitions/798.html) | Use of Hard-Coded Credentials                                                               |
| **16**   | [CWE-862](https://cwe.mitre.org/data/definitions/862.html) | Missing Authorization                                                                       |
| **17**   | [CWE-77](https://cwe.mitre.org/data/definitions/77.html)   | Improper Neutralization of Special Elements used in a Command («Command Injection»)         |
| **18**   | [CWE-306](https://cwe.mitre.org/data/definitions/306.html) | Missing Authentication for Critical Function                                                |
| **19**   | [CWE-119](https://cwe.mitre.org/data/definitions/119.html) | Improper Restriction of Operations within the Bounds of a Memory Buffer                     |
| **20**   | [CWE-276](https://cwe.mitre.org/data/definitions/276.html) | Incorrect Default Permissions                                                               |
| **21**   | [CWE-918](https://cwe.mitre.org/data/definitions/918.html) | Server-Side Request Forgery (SSRF)                                                          |
| **22**   | [CWE-362](https://cwe.mitre.org/data/definitions/362.html) | Concurrent Execution using Shared Resource with Improper Synchronization («Race Condition») |
| **23**   | [CWE-400](https://cwe.mitre.org/data/definitions/400.html) | Uncontrolled Resource Consumption                                                           |
| **24**   | [CWE-611](https://cwe.mitre.org/data/definitions/611.html) | Improper Restriction of XML External Entity Reference                                       |
| **25**   | [CWE-94](https://cwe.mitre.org/data/definitions/94.html)   | Improper Control of Generation of Code («Code Injection»)                                   |

## [OWASP Top 10](https://owasp.org/www-project-top-ten/)

### Overview

The OWASP Top 10 is put out by the Open Web Application Security Project (OWASP) Foundation. OWASP is a non-profit organization with a mission to bolster software security across industries. To further that mission, OWASP maintains and publicly shares the OWASP Top 10, an awareness document for web application security vulnerabilities.

For each ranking period, OWASP collects application data from a variety of sources and conducts a survey to gather important information about the top vulnerabilities developers encounter, but that may not be expressed in the application data received. These are usually trends developers observe that may have potential to cause damage. Submitted web application data and survey results are used together to rank the top ten security vulnerabilities.

### Methodology

Vulnerabilities are ranked based on a range of factors, which include analysis of actual web application data submitted by individuals and organizations. Contributed data can be attributed to companies or kept pseudo-anonymous. Data sources also include bug bounty programs, security consultancies, and vendors. Contributors provide details of the time period for data, total number of web applications, and list of Common Weakness Enumerations (CWEs) as defined by MITRE. Contributors must also provide a number of applications containing each core CWE.

During analysis, OWASP finds the number of applications with one or more instances of a CWE. Incidence rate is calculated by totaling all the applications that were tested and then comparing that number to the total number of applications where a CWE occurred. The top ten results are then ranked based on additional input from the accompanying survey of application and security experts. Analysis focuses on the root cause of vulnerabilities above the symptom whenever possible.

The OWASP Top 10 for 2021 contained more application data than any previous report the foundation had put out. A record 500 000 applications were submitted. The 2021 list was also the most data-driven version. Data volume required a shift in how the project categorized vulnerabilities.

### New vulnerability categories

These new categories were created to highlight trends in application data and to provide additional training benefits for companies that focus on specific CWEs related to the programming languages or frameworks they actively use.

* Insecure design: this category contains risks related to design and infrastructure flaws. Differentiated from other vulnerabilities, insecure design cannot be fixed through proper implementation.
* Software and data entry failures: this category includes risks related to accepting software updates without verifying integrity. This vulnerability focuses on the assumption these updates can always be trusted.
* Server-Side Request Forgery (SSRF): risks related to URL fetching from one application to another, at the user request, without verifying URL integrity are grouped under this category. This server-side vulnerability is considered risky because forged requests can bypass security measures such as firewalls, VPNs, or other access controls.

### Critical changes

#### A03:2021 – Injections become more expansive

The first modification involves injections. Injection attacks happen when a hacker tries to send data to a web application, such that the web application performs an unintended action. These may include SQL, operating system, and Lightweight Directory Access Protocol (LDAP) injection flaws. Since this flaw is also an injectable, the current update to the OWASP Top 10 adds A07:2017 Cross-Site Scripting (XSS).

#### A05:2021 – Security misconfiguration rising in priority

Given the rising number of configuration options, this category has risen in the OWASP Top 10. In addition, it includes A04: 2017 XML External Entities beginning in 2021 (XXE). The XXE attack targets a client-side program that processes XML input. An XML-External-Entities Attack happens when unsafe XML input references to external entities are interpreted and processed. However, this attack is only successful with a flawed or improperly configured XML parser. Therefore, A04:2017 XML External Entities (XXE) has been integrated into A05:2021 Security Misconfiguration as a particular sort of misconfiguration.

### [OWASP Top 10 application vulnerabilities 2022](https://owasp.org/www-project-top-ten/)

#### 1. Broken access control

Access control implements strategies to prevent users from operating beyond the scope of their specified permissions. Due to access vulnerabilities, unauthenticated or unwanted users may access classified data and processes and user privilege settings.

Metadata manipulation, including tampering or replaying with a JSON Web Token (JWT) access control token, or modifying cookies or hidden fields to boost privileges or exploit JWT invalidation, is an example of an access control vulnerability. A second example is a breach of the denial principle by default. Access must be granted only to specific roles, capabilities, or users but is accessible to everyone. Such errors may make it simple for attackers to get access to everything they want.

However, one may avoid inadequate access security mechanisms and identity or password management issues by applying secure coding approaches and taking precautions such as disabling administrator accounts and restrictions and installing multifactor authentication.

Additional prevention techniques include:

* Enforce access control mechanisms only once and reuse them for the duration of the application to reduce Cross-Origin Resource Sharing (CORS).
* Domain models should impose distinct application business limit constraints.
* Limit access to Application Programming Interfaces (API) and controllers to mitigate the effects of automated attack tools.
* Log failures in access control and alert administrators as required.
* Instead of granting user permission to create, view, modify or erase any information, model access controls must enforce record ownership.

#### 2. Cryptographic failures

Cryptographic failures, formerly known as sensitive data exposure, rose one spot to position two. This is more of a symptom than a primary cause – emphasis here lies on cryptographic errors or lack thereof, which frequently expose sensitive data. The following are typical examples of sensitive information exposure:

* Session tokens
* Login IDs and passwords
* Online transactions
* Personal information (switched service network or SSN, health records)

For instance, an application may securely encrypt credit card data with automated database encryption. Unfortunately, it is immediately unencrypted when this information is accessed, enabling a SQL injection fault to extract credit card information in clear text, which an intruder may exploit. These failures can be avoided using the following prevention techniques:

* You should use robust, salted and adaptive hashing algorithms with a delay factor to store passwords, like scrypt, Argon2, PBKDF2 or bcrypt.
* Older protocols such as File Transfer Protocol (FTP) and Simple Mail Transfer Protocol (SMTP) should be avoided when transferring sensitive data.
* Instead of merely using encryption, it is advisable to implement authenticated encryption.
* Cryptographically random keys must be produced and stored as byte arrays. If passwords are employed, it has to be changed into something like a key using an algorithm for password-based key creation.

#### 3. Injections

Injection (or SQL injections) is a database attack against a website that uses Structured Query Language (SQL) to obtain information or perform activities that would ordinarily need an authenticated user account. These codes are difficult for a program to interpret from its own code, allowing attackers to conduct injection attacks to gain access to protected areas and sensitive data masquerading as trusted users. Injections include SQL injections, command injections, CRLF injections, and LDAP injections.

With a maximum estimated incidence of 19 percent, an average rate of incidence of 3 percent, and 274 000 instances, 94 percent of the applications were screened for injections. As a result, Injection fell to the third position in the revised list.

Some prevention techniques include:

* A preferable alternative is to employ an API that completely eschews the interpreter, offers a parameterized API, or translocates to Object-Relational Mapping (ORM) instruments.
* Utilizing positive server-side validation input is recommended. Numerous applications, including text fields and APIs for mobile apps, necessitate special characters.
* Utilizing LIMIT and other SQL constraints inside queries is a great way to avoid massive data exposure in case of an SQL injection.

#### 4. Insecure design

This is a brand-new category for 2021 that focuses on design and architectural flaws, with a need for greater use of threat modeling, design safety recommendations, and reference architectures. Insecure design is a wide category that contains a variety of problems, such as «missing or inadequate control design». That does not imply that insecure design is the root of all other top 10 risk categories.

Insecure design is not the same as insecure implementation. Implementation flaws can lead to vulnerabilities, even when the design is secure. On the other hand, a flawed design cannot be compensated for by a flawless implementation, as necessary security safeguards do not exist to defend against specific threats.

One can avert these threats by employing the following prevention techniques:

* Set up and use a secure development lifecycle with assistance of Application Security specialists to evaluate and build security and privacy safeguards.
* Threat modeling is advised for crucial verification, access control, application logic, and essential flows.
* Include security terminology and controls inside user stories.
* Tenant segregation by design across all tiers is also seen as a practical preventative approach.

#### 5. Security misconfigurations

General security setup issues, quite like misconfigured access controls, pose significant hazards by providing attackers with quick and easy access to critical data and site regions.

With an average rate of incidence of 4 percent and over 208 000 occurrences of a common weakness enumeration (CWE) in this category, OWASP checked 90 percent of applications for misconfiguration. «CWE-16 configuration» and «CWE-611 improper restriction of XML external entity reference» are two notable CWEs included. To avoid configuration complications, secure installation techniques must be used, which include:

* A systematic reinforcement process allows for quick and easy deployment of a secure environment. Configuration of developmental, quality control and operational environments should be similar, with distinct user privileges.
* It is ideal for automating processes for establishing a new safe environment to save time and effort necessary. Unused features and frameworks should be removed or not installed. A primary platform with no unessential features, components, documentation, or demonstrations decreases the likelihood of configuration vulnerabilities.

#### 6. Vulnerable and outdated components

The majority of online apps are created with help of third-party frameworks. Unknown application codes may result in undesirable outcomes and unwanted situations such as accent control violations, SQL injections.

If the program is insecure, unsupported, or outdated, there may be vulnerability-related hazards. The package includes web server, operating system, applications, database management system (DBMS), APIs, other elements, libraries, and runtime environments.

Automated approaches are available to aid attackers in finding improperly configured or unpatched machines. For instance, Shodan IoT search engine may aid users in discovering devices that are susceptible to Heartbleed threat, which was fixed in April 2014. Certain prevention techniques include:

* It is best to purchase components from official sources through secure channels.
* Keep a lookout for modules and elements that are not functional or do not provide security updates for older versions. If patching cannot be carried out, consider developing virtual patches to observe, identify, or safeguard against the observed vulnerability.
* Remove any excessive requirements, functionalities, elements, folders, or documentation.

#### 7. Identification and authentication failures

This category, formerly known as broken authentication, dropped from second place and now contains CWEs linked to identification problems. When an attacker obtains user information, password recovery, ID sessions, and other login credentials, it poses security issues. As the name implies, an identity and authentication failure includes hackers exploiting such vulnerabilities to take advantage of inadequate authentication.

If the application permits automated assaults like credential stuffing – when the attacker has access to lists of real users and passwords – or predefined, weaker, and common passwords such as «password» or «admin», these could be signs of authentication flaws.

To avoid such defects, one must consider the following preventive measures:

* Multifactor authentication must be used wherever feasible to avoid automated credential stuffing, brute-force attacks, and reuse of stolen credentials.
* By checking new or modified passwords against a database of the 10 000 worst passwords, it is possible to boost password security.
* Using the same messages for every outcome helps prevent account enumeration attacks on password recovery, registrations, and API paths.
* Do not install any default credentials, especially for administrative users.

#### 8. Software and data integrity failures

As more sensitive information is stored in databases, vulnerable to security breaches, data integrity concerns become essential for software.

This is a new category, and it focuses on assuming the integrity of software updates, vital data, and CI/CD procedures without verifying them. One example is when applications use extensions, modules, or repositories from content delivery networks (CDNs) or unauthorized sources. CI/CD process that is not protected might raise risk of malicious code, system compromise or unauthorized access.

Prevention techniques include:

* One might use measures such as digital signatures to confirm that data or software comes from expected sources without any tampering.
* A security tool for software supply chains, like OWASP CycloneDX or OWASP Dependency-Check, may be used to guarantee that components do not include design flaws.
* It is necessary to guarantee that CI/CD workflow has required segmentation, access control, and parameterization to safeguard code integrity throughout set-up and deploy operations.
* Compilation data that is unsigned or unencrypted should not be sent to untrusted clients unless integrity testing or a digital signature is in place to identify data alteration or duplication.

#### 9. Security logging and monitoring failures

A lack of tracking in the presence of suspicious actions and occurrences can expand gaps in time that go unmonitored, allowing security breaches to go unnoticed for longer than they would with better logging. This OWASP Top 10 2021 section is meant to aid in identification, escalation, and resolution of recent breaches. Detection of a security breach is unlikely without recording and monitoring.

A major European airline had a notifiable General Data Protection Regulation (GDPR) incident to illustrate this failure. Intruders presumably exploited payment application security flaws to gain data of over 400,000 consumer payments. In response, privacy authorities fined the airline 20 million pounds for misplaced data. To avoid such attacks, it is wise for users to:

* Verify that all authentication, access security systems, and server-side data validation problems are recorded with sufficient user information to detect suspicious or fraudulent accounts and stored for an adequate period to a delayed comprehensive investigation.
* Make sure that logs are created in formats consumable by log management systems.
* Create or apply a strategy for incident recovery and response efforts, like NIST 800-61r2 or a later version.
* Ensure that log data is encoded appropriately to avoid intrusions or cyber threats to monitoring systems.

#### 10. Server-Side Request Forgery (SSRF)

The results for this category reveal an above-average testing coverage, reasonably low incidence rate, and above-average Impact and Exploit ratings. SSRF develops when server-side queries are conducted without verifying the URL given by the user. This allows an attacker to induce an application to transmit a forged request to an undesired location, even if it is protected by virtual private networks (VPN), firewalls, or network access control list (ACL).

Fetching a URL has become a typical occurrence as new online applications give end-users convenient functionalities. Consequently, SSRF prevalence is increasing. In addition, intensity of SSRF is growing due to cloud services and design complexity. With that in mind, one can avoid such attacks by employing the following prevention techniques:

* To limit effects of SSRF, one should separate remote resource access functions into distinct networks.
* Install «deny by default» firewall settings or network access control rules for blocking all web traffic except for required internal traffic.
* To protect against attacks like DNS remapping and «time of check, time of usage», in (TOCTOU) situations, it is good to be conscious of URL accuracy.