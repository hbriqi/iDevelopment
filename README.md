# Simplified-DDD (S3D)
a new style and methodology to develop application services 

<img src="https://github.com/hisham-elbreky/Simplified-DDD/blob/50240d77ec3fcba0e3fabda161fc2999f725e59f/diagrams/Seed-code-template-Pyramid.png" width="30%"/>

# Principles  
1. Simple & Powerful 
The design is simple to achieve the target purpose efficiently and as expected. The template is designed to develop application services (e.g. BE service) that manage a logic of a specific business domain, consume external  services, and expose its business to the external world via APIs. it is a light flavor of DDD and Clean Code Architecture. 
The template is tending to merge logic and the abstracted data into one layer, using adapters (via interfaces) to consume functions from other services.

2. Organized source code is the building block 
Code is organized in folders which are encapsulating application logic of  business domains per each main folder.
Main folders (each represent application module) can be combined in one source code project or separated as required without demanding technical break changes. Each folder consist of sub-folders for app logic, domain models, and infrastructure interfaces implementor classes.

3. Infrastructure and adapters are reusable binary packages
as source code is application business logic building block, infrastructure and adapters are not considered part of the application so they are used in its binary format as a reusable packages e.g. nuget and npm.

4. Application code is segregated from the framework runtime and hosting environment as possible
business logic which is encapsulated in the main folder is represented by a user journey classes and domain models while the infrastructure sub-folder is a set of gateway classes to the frameworks, runtime, and reusable libraries. nothing is tightly-coupled with the runtime and environment so the code is future proof for changes and updates. 

5. Living in the same plant: it is just a light version of DDD and appreciate to follow clean code principles like SOLID, DRY, KIS, etc.  





# Fundamentals

It worth to define the term "Application Service" before going with fundamentals, I am embracing the definition of Archimate: "An application service is defined as a service that exposes automated behavior.". and I can say, it is an independent technical module that group a set of technical functions within the application, bounded with business domain context. 

<img src="https://github.com/hisham-elbreky/Simplified-DDD/blob/50240d77ec3fcba0e3fabda161fc2999f725e59f/diagrams/Seed-code-template-Application%20Service%20Triangle.png" width="30%"/>

Application Service Triangle 
Any application service (in somehow) is bounded with three sides:
1. Application logic - application and data are two sides of one coin so the template is addressing application and data through the implementation of use cases and its data contracts. 
2. Interfaces - the way of interfacing with external world via APIs, and that may requires adapter components to be developed for either in-bound communication or out-bound communication. 
3. Infrastructure and Hosting Environment - Application logic at the end run over a set of runtime libraries and hosted by hosting environment like VM, container, etc.     


# Application Service Structure
service folder is consist of three sub-folders as follows:
1. Application - used for implementing use cases and exposing business APIs
2. Domain - hold business data contracts and interfaces of data access repository
3. Infrastructure - hold adapter classes requires to consume other services (either internal or external) and that could be done via framework runtime, reusable libraries or both 

The following diagram depict the application service structure based on S3D 

<img src="https://github.com/hisham-elbreky/Simplified-DDD/blob/50240d77ec3fcba0e3fabda161fc2999f725e59f/diagrams/Seed-code-template-Application%20Service%20Structure.png" width="30%" />


# What is it?
There are a lot of DDD flavors, while this one is going to break some constraints on DDD and make code more easily and practical to be developed and meet business requirements.

S3D is a compact design, tending to reduce the layers as possible, organize code via file system, and scale code "in" or "out" as required. Application logic, data access, and infrastructure code are exist in the same code project which can hold one or more application service in the same repo.

S3D is an evolutionary and cloud native, so it is agile and cloud friendly architecture. the intention is to develop application module either as independent service with its ow code repo (e.g. microservice) or as a combined module in a modular application service which sharing the same code repo, but at the end what you developed is a cloud native application service and modules can be split or combined like lego pieces. Code repo can be easily managed by merging or splitting as required. The convention of using file structure make it easy to automate tasks like code generation and reusability.      


The following diagram depict the main components of S3D

<img src="https://github.com/hisham-elbreky/Simplified-DDD/blob/50240d77ec3fcba0e3fabda161fc2999f725e59f/diagrams/Seed-code-template-Simplified%20DDD%20in%20Detail.png" width="70%" />


The following diagram depict the combination of two services in the same codebase

<img src="https://github.com/hisham-elbreky/Simplified-DDD/blob/50240d77ec3fcba0e3fabda161fc2999f725e59f/diagrams/Seed-code-template-Combined%20Services.png" width="25%" />

And, the following diagram depict two separated services with two separated codebase  
<img src="https://github.com/hisham-elbreky/Simplified-DDD/blob/50240d77ec3fcba0e3fabda161fc2999f725e59f/diagrams/Seed-code-template-Separated%20Service%20.png" width="35%" />
