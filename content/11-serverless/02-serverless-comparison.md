---
title: 'Top 13 serverless computing and database providers'
metaTitle: 'Comparing the top serverless platform options'
metaDescription: 'Comparing popular serverless platforms: AWS Lambda, Microsoft Azure Functions, Google Cloud Functions, Cloudflare Workers, Netlify Functions, and Vercel Functions'
metaImage: '/content/serverless/serverless-comparison/header.png'
---

## Introduction

![Article header](/content/serverless/serverless-comparison/header.png)

Serverless computing is a fairly recent evolution in the cloud computing space.  Serverless providers allow developers to focus on the functionality that their applications require without worrying about the execution environment or any of the other lower level layers.

In this article, we'll take a look at some of the most popular serverless providers and break down how they compare across different categories.  After learning about your options, you'll be in a better position to evaluate your choices and choose the service that best matches your needs.

We will discuss what each service has in common, their points of departure, and what criteria might make you choose one over another.  While no single serverless provider is appropriate for every user, this breakdown is intended to highlight criteria to make it easier to evaluate candidates against your priorities.

<PrismaOutlinks>

Registrations are now open for the Prisma Serverless Conference on November 18, 2021.  [Sign up now for free!](https://www.prisma.io/serverless)

</PrismaOutlinks>

## Overview of providers and evaluation criteria

While other options _do_ exist, in this article, we'll take a look at some of the most common commercial serverless providers.  We will evaluate the following options:

* AWS Lambda
* Microsoft Azure Functions
* Google Cloud Functions
* Cloudflare Workers
* Netlify Functions
* Vercel Functions

Each of these these offerings represents an implementation of serverless computing.  To get a better sense of what serverless computing is and what benefits it can provide, check out our ["What is serverless?" article](https://www.prisma.io/dataguide/serverless/what-is-serverless).

As we describe the services offered by various providers, it's helpful to be able to compare each option using the same general categories.  For this guide, we'll take a look at how each of these serverless platforms compare across:

* **focus:** What is the provider's primary goal for the service?  Are they a general offering or focused on a specific aspect of the market?
* **features:** Does the platform offer any unique selling points that set it apart?
* **language support:** What languages are supported for functions?
* **maturity:** How well-tested is the service and how long has it proven itself reliable?
* **price:** How much does it cost to use the service?  Are there free and paid tier?  What ways are usage accounted for?
* **limitations:** What are the limits and caps on workload execution? What are the thresholds for execution time, request and response sizes, executions per day or month, etc.?

We'll also briefly cover some serverless database options that can be useful to improve your serverless strategy.  We'll mention the following providers and services:

* Amazon DynamoDB and Aurora Serverless
* Microsoft Cosmos DB Serverless and Azure SQL Serverless
* Google Firestore
* PlanetScale
* MongoDB Atlas Serverless
* CockroachDB Serverless
* Fauna

With those categories in mind, we can start to look at the available services.

## AWS Lambda

### Overview

* **Released:** 2014
* **Focus:** General serverless computing.  AWS service integration.
* **Language support:** Broad
* **Maturity:** Mature
* **Pricing:** By invocation and resource consumption.  Additional costs for edge deployment or provisioned warm instances.

### General description

Perhaps the best known provider in the serverless space is [AWS Lambda](https://aws.amazon.com/lambda/).  Introduced in 2014, Amazon's Lambda service was one of the first providers to capture major market interest, in a large part due to the builtin customer base from other service offerings.

AWS Lambda remains the main service that other offerings are compared against due to its stability, range of features, and general familiarity.

### Focus

AWS Lambda is a general serverless platform.  It does not focus heavily on solving specific problems, but rather providing a platform to use for whatever event-driven workflows you might have.

Because of Amazon's extensive service catalog, Lambda does have heavy emphasis on compatibility and integration with other AWS services.

### Features

AWS Lambda offers features beyond the basics that can be expected from every serverless provider.  The service has become more flexible and powerful as time passes, allowing it to remain competitive and fresh.

Here are some of the features it boasts:

* Arbitrary executables: You can configure the Lambda service to run arbitrary executables to process events rather than working with language-specific functions.
* Custom runtimes: Users can implement their own language runtimes beyond those provided natively by Amazon.
* Provisioned concurrency: The ability to keep event handlers spun up and on standby to help mitigate the cold start problem of allocating resources at the time of the event.
* Easy access to persistence: Users can use [Amazon's RDS Proxy](https://aws.amazon.com/rds/proxy/) to connect to database instances securely from their functions and use Elastic File System to store file-based data.

### Language support

At the time of writing, AWS Lambda offers the following native language runtimes:

* Node.js: 10, 12, 14
* Python: 2.7, 3.6, 3.7, 3.8, 3.9
* Ruby: 2.5, 2.7
* Java: 8, 11
* Go: 1.x
* .Net Core: 2.1, 3.1

Additionally, as mentioned above, you can provide your own custom runtimes, which lets you arbitrarily expand the available runtime support.

### Maturity

AWS Lambda is probably the most mature serverless platform available today due to the amount of time it has been operating.  It has proven to be reliable and is capable of handling workloads of various sizes.

### Price

AWS Lambda charges based on resource usage tracked at the millisecond level.  Unfortunately, the total cost of running AWS Lambda is often difficult to calculate up front because so many different factors affect the overall price.

The total price is based on a number of factors:

* The architecture executing the functions: x86 or Arm.  This is charged based on the number of requests and the duration of each request.
* The amount of memory allocated to the function: From 128 MB to 10,240 MB, allocated in 1 MB increments
* Provisioned concurrency usage: If you choose to provision concurrency to help with performance, the extra concurrency will cost more
* Amount of data transferred in and out of the functions
* Lambda@Edge usage: If you deploy your functions closer to clients, you will be charged for that extra service.

### Limitations

Serverless providers often have limits or quotas of what resources your functions and account are allowed to consume.  Some of AWS Lambda's more significant ceilings are:

* Function memory: configurable in 1 MB increments, from 128 MB to 10240 MB
* Function timeout: 900 seconds (15 minutes)
* Function layers: 5
* Function burst concurrency: 500-3000, depending on region
* Request and response sizes: 6 MB for synchronous, 256 KB for asynchronous
* Deployment size: 50 MB zipped, 250 MB unzipped

### Summary

AWS Lambda is a robust, mature platform for building serverless applications.  It has the benefit of experience over many other providers and still leads the way in many features and evolutions in the serverless space.

Its integration with other AWS services makes it an obvious choice for those already living in Amazon's ecosystem.  Unfortunately, it also inherits the cost prediction difficulties that AWS services are often criticized for.

Overall, however, AWS Lambda is a strong, general choice for serverless functions.  It is likely to continue its trajectory of adding features and integrations to remain competitive.

## Microsoft Azure Functions

### Overview

* **Released:** 2016
* **Focus:** General serverless computing.  Azure service integration.
* **Language support:** Broad
* **Maturity:** Mature
* **Pricing:** By invocation and resource consumption.  Tiered bundles available.

### General description

[Microsoft Azure Functions](https://azure.microsoft.com/en-us/services/functions/) is the serverless offering of the Azure cloud ecosystem, released in 2016.  While AWS Lambda had a head start, Microsoft was able to use their example as a starting point for developing their own pricing strategy, positioning, and features.

Because Azure Functions aims to fill the same niche in its service catalog as AWS Lambda it is, in many ways, a similar product.  Even so, there are some important distinctions that distinguish Microsoft's offering.

### Focus

Microsoft Azure Functions is a general purpose serverless platformed aimed running at event-driven applications.  While it was developed to be a flexible, general purpose tool, Azure Functions were also designed with the rest of the Azure ecosystem in mind.

### Features

Azure Functions offer all of the standard functionality that you'd expect from a serverless platform.  In addition, some interesting features it offers include:

* Various deployment options: Azure offers various plans for serverless functions that bundle features according to your need.
* Extensible bindings: You can add extensions to the platform to support different workflows and integrations.
* Integrated HTTP endpoint: Azure functions come complete with HTTP endpoint management out of the box.

### Language support

Azure Functions support the following language runtimes natively:

* C#: .Net Framework 4.8, .Net Core 2.1 and 3.1, .Net 5.0 and 6.0
* JavaScript: Node.js 6, 8, 10, 12, 14
* F#: .Net Framework 4.8, .Net Core 2.1 and 3.1, .Net 6.0
* Java: 8, 11
* PowerShell: PowerShell Core 6, PowerShell 7.0
* Python: 3.6, 3.7, 3.8, 3.9
* TypeScript: (transpiled to JavaScript)

Additional languages and runtimes can be supported by running a lightweight web server as a custom handler.

### Maturity

Azure Functions have been around awhile now and had some time to mature.  The Azure Functions product has iterated on its initial offering and now represents a fairly stable product with good performance for most use cases.  Even so, Microsoft's product often feels like it is still playing catch up with Amazon's offering, which may be important for some.

### Price

In terms of cost, Microsoft's Azure Functions come out to be fairly identical to Amazon Lambda's pricing.  Following the same pattern, Azure Functions are billed based on the number of executions and by the resources allocated to processing the functions.

Some places where Azure Functions differ include:

* charging only for used memory instead of allocated memory
* charging only once for resources used when executing multiple functions in the same execution instance

Additionally, Azure Functions offer a tiered pricing model to offer plans for different types of usage:

* Consumption plan: the classic serverless offering with an event driven, automatically scaled execution with a pay-for-use model
* Premium plan: adds additional reserved capacity and resource allocation for a higher price to avoid cold starts.
* Dedicated plan: the functions host does not spin down, so no cold starts are possible.

### Limitations

Microsoft Azure Functions limitations depend on what type of plan you are using.  Some of the resource allocations for functions include:

* Scale: Maximum of 200 instances for the consumption plan, 100 instances for premium, and 10-20 instances for the dedicated plan
* Function maximum execution time: 10 minutes on the consumption plan, and unlimited for premium and dedicated plans
* Max request size: 100 MB
* Max memory: 1.5 GB on the consumption plan, 3.5-14 GB on the premium plan, 1.75-14 GB on the dedicated plan

### Summary

Overall, Microsoft Azure Functions are a great option for general serverless applications.  Microsoft has a whole ecosystem of services and tools that you can glue together with Functions.  Additionally, it offers a bit more flexibility in allocating your resources and predicting your costs.

In the end, your choice of Microsoft Azure Functions is probably similar to other choices about your cloud environments.  It's not only about the service itself, but whether you are interested in the entire ecosystem.  For developers who use Windows-focused development technologies or rely on Azure-based services, Azure Functions offers a great option that should work well with your other tools.

## Google Cloud Functions

### Overview

* **Released:** 2016
* **Focus:** General serverless computing.  GCP service integration.
* **Language support:** Broad
* **Maturity:** Mature
* **Pricing:** By invocation and resource consumption.  Additional charge for function storage.

### General description

[Google Cloud Functions](https://cloud.google.com/functions) is a general serverless solution available on the Google Cloud Platform.  Released in 2016, Google Cloud Functions served to bridge the gap created by AWS Lambda a few years prior.

Google Cloud Functions follows the general product model offered by competing cloud platforms by offering a high performance, stable platform for deploying functionality without management.  As with other providers, care has been taken to integrate it with other services in Google's catalog to complement users already invested in the ecosystem.

### Focus

Google Cloud Functions focuses on providing a platform for general serverless applications.  It is not heavily specialized and mainly seeks to provide a reliable target and platform for application developers to deploy serverless functions in Google's cloud.

### Features

Beyond standard serverless functionality, Google Cloud Functions offer a few differentiating features:

* Distributed tracing and debugging: Designed to work well with Google's Cloud Trace and Cloud Debugger tools.
* Integrated HTTP endpoint: Google Cloud Functions come complete with HTTP endpoint management out of the box.

### Language support

At the time of writing, Google Cloud Functions supports the following native language runtimes:

* Node.js: 8, 10, 12, 14, 16
* Python: 3.7, 3.8, 3.9
* Go: 1.11, 1.13, 1.16
* Java: 11
* .Net Core: 3.1
* Ruby: 2.6, 2.7
* PHP: 7.4

As with other providers, Google Cloud Functions allow you to also specify custom runtimes to access broader language support.

### Maturity

Google Cloud Functions has had time to mature and stabilize since its introduction.  In general, you can expect it to offer a level of stability comparable to that of other GCP services.  Google's offering seems to lag somewhat behind the solutions given by other cloud providers, but still represents a solid implementation and a reliable place to deploy serverless code.

### Price

The costs associated with running Google Cloud Functions are calculated similarly as with other providers: both by resource usage and number of executions.  Overall, this ends up coming out to roughly the same price as Amazon and Microsoft's offerings.

One thing to keep in mind with Google Cloud Functions is that the functions themselves are stored in the Google Container Registry, which customers must pay for.  So in addition to the execution costs, there is a cost to uploading and storing your functions within Google's ecosystem.

### Limitations

Google Cloud Functions has the following limits and quotas on actions executing on the platform:

* Number of functions per region: 1000
* Deployment size: 100 MB compressed for sources, 500 MB uncompressed for sources plus modules
* HTTP request size: 10 MB
* HTTP response size: 10 MB
* Function memory: 8192 MB
* Function timeout: 540 seconds
* Function concurrency: 3000
* Function invocation rate: 1000 per second

### Summary

Google Cloud Functions is a capable contender in the serverless market that is well-suited for general workloads, especially if you are already leveraging GCP's other offerings.  Like the other large cloud providers, it is heavily integrated with their other services so that configuring functions to respond to other product events or calling out to other services in functions is straightforward.

Like Microsoft, Google seems to still be following Amazon's lead in the serverless space.  At 8 GBs, the quota for memory available to functions is quite a bit lower than the other major clouds we've looked at thus far, which can be a factor for certain workloads.  Overall, however, Google Cloud Functions is a great platform for general serverless deployment.

## Cloudflare Workers

### Overview

* **Released:** 2018
* **Focus:** Edge and performance computing.
* **Language support:** JavaScript-compilable and WASM compatible languages.
* **Maturity:** Newer
* **Pricing:** By invocation and duration.  Different plans available.

### General description

[Cloudflare Workers](https://workers.cloudflare.com/) is a serverless option provided by Cloudflare that combines the functions-as-a-service model with edge computing.  Released in 2018, Cloudflare Workers decided to approach the problem from a different angle given that they are a more of a web tooling company than a general cloud provider.

Cloudflare Workers are capable of delivering high performance at a lower cost to developers due to their implementation details and some self-imposed limitations.  If your applications fit the Cloudflare Workers paradigm, it is a great choice for delivering low latency responses to your clients.

### Focus

Unlike the serverless solutions offered by general cloud providers, Cloudflare Workers is a much more narrowly focused offering.  Cloudflare workers are primarily concerned with high performance, low latency execution by deploying functions as close to clients as possible.

They are able to achieve their performance not only through their highly distributed deploy locations, but also because of the environment that they execute in.  Cloudflare Workers execute functions using Chrome V8 directly instead of through Node.js or on a different runtime.  This helps it deliver faster performance and avoid some common issues with serverless, like cold start problems, since code can be executed directly instead of by a runtime.

### Features

Because Cloudflare Workers offers a different approach to the serverless space, it has a different set of features than traditional cloud platforms:

* Faster execution support: Cloudflare Workers execute quickly directly on V8 instead of in a traditional JavaScript runtime environment like Node.js.
* Lower latency: Because the serverless functions are globally distributed to over 200 locations throughout the world, client latency is often noticeably lower.
* Naturally sandboxed: One of the advantages of running on V8 is that functions are automatically isolated from one another instead of having to isolate at a higher layer.
* Uses familiar API: Cloudflare Workers are modeled after JavaScript Service Workers, used in progressive web applications.  Their API uses the same patterns wherever possible.


### Language support

Because of its Chrome V8 runtime, Cloudflare Workers must be written in or compilable to a web-friendly language.  Supported languages include:

* JavaScript
* TypeScript
* WebAssembly (WASM) compilable languages like:
    * Rust
    * C
    * Cobol
* Languages compilable to JavaScript like:
    * Kotlin
    * Dart
    * Python
    * Scala
    * Reason/OCaml
    * Perl
    * PHP
    * F#

### Maturity

Cloudflare Workers are a relatively new offering that hasn't been around long enough to grow an ecosystem as large as those associated with the major cloud providers.  Its performance and execution model, however, have attracted many development teams.  Cloudflare, in turn, has responded by adding support for more and more languages and developing extensive documentation to help developers learn both about the conceptual model Cloudflare Workers employs and how to write and deploy functions with the platform.

### Price

Cloudflare Workers are charged based on both the number of requests and the duration of each request.  The amount charged depends on whether your workers are part of an "unbound" plan or a "bundled" plan.

Bundled plans include a set amount of requests per month with a limit to the duration of each request.  The unbound plan, on the other hand, does not have a limit to execution duration but charges for both the number of requests and the amount of time spent executing.

Cloudflare Workers tend to be less expensive to run than their more traditional counterparts.  The V8 execution model allows for a single machine to host more isolated functions than other runtime environments.  This increased density allows Cloudflare to handle greater capacity with the same hardware and the costs they charge are lower as a result.

### Limitations

Cloudflare workers have the following limits or quota on their usage:

* HTTP request size: depends on your overall Cloudflare plan (100 MB for Free and Pro, 200 MB for Business, and 500 MB for Enterprise)
* Function memory: 128 MB
* Function duration: 50ms CPU time for bundled plan, charged for time on unbound plan with a maximum of 30 seconds
* Function invocation rate: no limitation
* Deployment size: 1 MB compressed

As you may have noticed, the expectations for Cloudflare Workers is vastly different from the previous solutions in terms of expected execution time and resource usage.  This should provide a hint as to what types of workloads are best suited for Cloudflare's environment.

### Summary

Cloudflare Workers is a very attractive solution for many projects due to its low latency delivery and high performance execution environment.  The platform is designed specifically to allow for quick execution of small, focused functions at the edge.

While Cloudflare Workers are probably not the best solution for every type of serverless, they are an ideal solution for those working primarily in JavaScript or TypeScript who already have experience with Progressive Web App fundamentals.  The familiar developer experience, easy deployment, and scalable high performance execution environment makes it a great choice for many projects.

## Netlify Functions

### Overview

* **Released:** 2018
* **Focus:** Web application integration.
* **Language support:** Narrow
* **Maturity:** Newer
* **Pricing:** By invocation and duration.  Different tiers available.

### General description

[Netlify Functions](https://www.netlify.com/products/functions/) is a serverless offering provided by Netlify, a web application build and deployment platform.  The Functions product, released in 2018, is actually a value added service built on top of AWS Lambda focused on making it easier to integrate serverless functionality into the Netlify ecosystem.

While different from some of the other offerings because of this positioning, Netlify Functions is interesting because of the way that it integrates serverless within a coherent ecosystem focused on application delivery.

### Focus

Netlify Functions is focused squarely on helping developers deploy web applications with little friction.  Rather than positioning its serverless offering as a general tool, instead, it uses AWS Lambda as a means to an end to simplify the build and deployment process.

For projects that match Netlify's area of expertise, the Functions feature can help accelerate their workflow and iteration cycles.  For projects that fall outside of that realm, however, other solutions are likely a better idea.

### Features

Netlify Functions is primarily focused around integrating serverless capacity into your web applications.  Its feature set is centered around that use case:

* Deploy functions with your application: Netlify Functions can be developed and managed right beside the applications they integrate with.
* Preview and rollback functionality: You can preview and test functions before deploying them to your live environment and can rollback in case of any problems.
* A/B testing: You can run A/B tests that allow you to compare changes in both your frontend application code and your serverless functions.

### Language support

Netlify's language support is quite limited as Netlify further restricts the options available through AWS Lambda to a subset that it is willing to support for its application management platform.

Functions can be written in the following languages:

* JavaScript
* TypeScript
* Go

### Maturity

Netlify Functions is a relatively new offering, but benefits from the maturity that comes from building on top of AWS Lambda.  The actual serverless execution is handled by Amazon, which has proven stable and reliable.

The glue functionality and the integration with Netlify's other application build and deploy features, however, are run by Netlify itself.  Because Netlify is basically acting as an AWS Lambda customer, the reliability of its serverless offering should likely be considered as reliable as you'd consider the rest of their product catalog.

### Price

Netlify Functions are billed according to the number of request invocations that occurred as well as the execution duration.

To make the pricing simpler to understand, Netlify uses a tiered system to calculate costs and limits.  These tiers intersect with plans that Netlify offers for their platform, which makes it possible to select your general platform level and the serverless level somewhat independently.

In terms of their serverless offering, the tiers they offer are:

* Level 0: Free, but with limited functionality. Can be used with a Starter (free) or Pro ($19 per user per month) Netlify plan.
* Level 1: An additional $25 per site per month. Can be used with a Starter (free) or Pro ($19 per user per month) Netlify plan.
* Level 2: Included with the business or enterprise plan for Netlify's general platform.

### Limitations

The thresholds associated with the serverless functionality are tied directly to your Netlify plan level and your Netlify Functions tier.  The following limitations apply:

* Monthly requests: 125,000 for Level 0, 2 million for Level 1, unlimited for Level 2
* Monthly run time: 100 hours for Level 0, 1,000 hours for Level 1, unlimited for level 2
* Access to background (asynchronous) functions: available with a Netlify Pro or higher account
* Function timeout: 10 seconds for synchronous functions, 15 minutes for background (asynchronous) functions

### Summary

Netlify Functions is a great choice for leveraging serverless functionality within a larger application management platform.  While it is not available or useful outside of the Netlify platform, its tight integration with the rest of the build and deployment life cycle management makes it a valuable option.

Netlify Functions doesn't aim to be a general serverless solution.  Instead, it smooths out some of the rough edges of incorporating AWS Lambda within development workflow.  If you are interested in using serverless to augment your web projects, Netlify is a great choice that can make that intuitive and straightforward.

## Vercel Functions

### Overview

* **Released:** 2016
* **Focus:** Web application integration
* **Language support:** Broad
* **Maturity:** Newer
* **Pricing:** Bundled with platform

### General description

[Vercel Functions](https://vercel.com/docs/concepts/functions/introduction) are another entry aimed at simplifying the serverless experience for web application developers.  Like Netlify Functions, Vercel Functions are part of an overall platform focused on making web application development and delivery better a better experience.

Vercel Functions come in two flavors: Serverless Functions, which execute like regular serverless services, and Edge Functions, which are deployed to and run by Vercel's edge network.  This flexibility allows you to choose between the deployment type based on what suits each function best.

### Focus

Vercel Functions are entirely focused on improving the development, deployment, and delivery experience for modern web applications.  Its offering is tightly integrated with the rest of Vercel's features to create a good experience for these workflows.

This focus means that Vercel Functions are designed to using serverless within a web applications easier, so if your project fits in that category, it can be extremely useful.  The platform helps you implement this functionality in order to add features and increase performance.

### Features

The features associated with Vercel Functions are closely related to the rest of the Vercel product.  These include:

* Two types of functions: Serverless and edge functions allow you to choose what options are most appropriate for each of your functions.
* First class Next.js support: Vercel is responsible for Next.js development and has a vested interest in making its Next.js experience great.
* Deploy functions with your application: Vercel Functions can be developed and managed right beside the applications they integrate with.
* Fast execution: Vercel's Edge Functions use a V8 runtime for improved execution performance over heavier weight runtimes.

### Language support

Vercel Functions can execute a variety of languages.  Officially, they support the following languages:

* Node.js: 12.x, 14.x
* Go: 1.16, alternatives configurable through `go.mod` file
* Python: 3.6
* Ruby: 2.7.x, 2.5.x

The community has augmented this list by also providing:

* Bash: GNU version 4
* Deno: Any supported tag
* PHP: 8.0.3
* Rust

### Maturity

Evaluating the maturity of Vercel Functions is slightly complicated because of its split between Serverless Functions and Edge Functions.

Vercel's Serverless Functions are run on AWS Lambda, similar to the way that Netlify wraps that functionality.  For those cases, Lambda's stability is an asset to Vercel's own reliability.

Vercel's Edge Functions are a newer offering that does not appear to use Amazon Lambda's infrastructure.  Instead, it runs on the V8 runtime directly similar to Cloudflare Workers.  As Edge Functions are still in beta, they should probably be considered less stable and more likely to change than their Serverless Functions.

### Price

Unlike all other providers thus far, however, Vercel's serverless offering is completely bundled into its regular product.  It does not have a separate price for its serverless offering.

That being said, Vercel's pricing plans include:

* Hobby: Free for non-commercial sites
* Pro: $20 per month per member
* Enterprise: Plan customized per client

### Limitations

Vercel's ceilings and limitations are somewhat inherited from AWS Lambda for its Serverless Functions.  The limitations include:

* Serverless Function execution: 100 GB-hours for Hobby, 1,000 GB-hours for Pro, and custom execution levels for Enterprise
* Serverless Function execution timeout: 5 seconds for Hobby, 15 seconds for Pro, 30 seconds for Enterprise
* Serverless Function invocations: Unlimited
* Edge Function invocations per day: 100,000 for Hobby, 500,000 for Pro, 5 million for Enterprise
* Serverless Function deployment size: 50 MB zipped, 250 MB unzipped
* Serverless Function memory: 1024 MB for Hobby, 3008 MB for Pro
* Serverless Function request or response body: 5 MB

### Summary

Vercel Functions are a good solution for web application developers using the Vercel platform.  The serverless functionality is tightly integrated within the platform and is developed in tandem with the Next.js framework to ensure compatibility.

For users who need serverless for their Next.js application, Vercel is an obvious choice.  For other web application developers, Vercel Functions and the rest of the Vercel platform may be able to help you manage both your serverless needs and your application life cycle management.

## Serverless computing adjacent: serverless databases

While we've tried to cover some of the most common and interesting providers in the serverless computing space, there are other related services that are also worth mentioning.  In this section, we'll briefly introduce some serverless database offerings that may complement your serverless computing needs.

You can read more about how serverless databases work in our ["What is serverless?" article](https://www.prisma.io/dataguide/serverless/what-is-serverless).

### Amazon DynamoDB and Aurora Serverless

Amazon offers a few serverless database services depending on your needs.

Amazon's [DynamoDB](https://aws.amazon.com/dynamodb/) is a NoSQL serverless database solution that can scale up and down as needed to accommodate the level of requests its receiving.  It functions as a key-value store and is able to respond and scale very rapidly.

For SQL oriented workloads, Amazon offers [Aurora Serverless](https://aws.amazon.com/rds/aurora/serverless/), a serverless relational database solution that scales the data processing units according to demand.

### Microsoft Cosmos DB Serverless and Azure SQL Serverless

Microsoft similarly offers a few options for serverless databases.

Microsoft [Cosmos DB Serverless](https://docs.microsoft.com/en-us/azure/cosmos-db/serverless) is a serverless tier for their NoSQL Cosmos database.  It offers multi-model operation compatible with a few different NoSQL technologies.

For relational data, Microsoft also has [Azure SQL Serverless](https://docs.microsoft.com/en-us/azure/azure-sql/database/serverless-tier-overview).  This is the serverless tier for their managed SQL database service, which scales automatically to match the incoming requests.

### Google Firestore

Google's serverless database offering is [Firestore](https://cloud.google.com/firestore).  Firestore is a NoSQL document database that is designed to automatically match the processing required for the queries it receives.  It focuses on being a "set it and forget it" option for document-based storage that lets you easily hook up applications during development and production.

### PlanetScale

[PlanetScale](https://planetscale.com/) is a MySQL-compatible serverless database platform built on Vitess, a relational database implementation built for scaling in Kubernetes environments.  PlanetScale is able to provide versioned data branching, non-blocking schema changes, and other advanced features with simple to deploy tooling.

### MongoDB Atlas Serverless

MongoDB Atlas is a hosted, multi-cloud version of MongoDB.  They now are offering [MongoDB Atlas Serverless](https://www.mongodb.com/cloud/atlas/serverless) as a way of interacting MongoDB according to the serverless model.  While still in preview, the serverless version of their hosted database aims offer a seamless scaling experience to accommodate different levels of use.

### CockroachDB Serverless

[CockroachDB Serverless](https://www.cockroachlabs.com/blog/announcing-cockroachdb-serverless/) is a newly announced offering from CockroachDB that aims to augment its flexible SQL database with serverless capabilities.  The database will automatically scale up and down according to user demand.

### Fauna

[Fauna](https://fauna.com/) offers serverless transactional database instances designed to work with modern applications in diverse cloud-based contexts.  Fauna provides API based data operations that act more as a utility than a piece of infrastructure you need to manage.  This model perfectly fits with the serverless paradigm that you are already using to build your applications.

## Wrapping up

To summarize the serverless offerings we've covered, we've distilled some of the details into the following table to make it easier to compare at a glance.  We'll only include the serverless compute options to avoid confusion:

| Product                   | Focus                            | Language support                                                                                                                                            | Recommended usage                                                                                                 | Additional comments                                                                                                                                                                                                                                                       |
|---------------------------|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AWS Lambda                | General purpose functions        | Node.js, Python, Ruby, Java, Go, .Net, custom runtimes                                                                                                      | Situations where serverless is needed anywhere in your technology stack, especially if already using AWS.   | AWS Lambda is the most mature offering available.  It introduces new features regularly and has variations like Lambda@Edge focused on filling in additional niches.                                                                                                     |
| Microsoft Azure Functions | General purpose functions        | .Net, Node.js, Java, PowerShell, Python, custom runtimes                                                                                                    | Situations where serverless is needed anywhere in your technology stack, especially if already using Azure. | Microsoft Azure Functions makes sense if your technology is Microsoft-focused, but it tends to lag behind AWS Lambda in features.                                                                                                                                         |
| Google Cloud Functions    | General purpose functions        | Node.js, Python, Go, Java, .Net, Ruby, PHP, custom runtimes                                                                                                 | Situations where serverless is needed anywhere in your technology stack, especially if already using GCP.   | Google Cloud Functions is a good choice if already living in GCP, but has more limitations than some of the other general providers.                                                                                                                                      |
| Cloudflare Workers        | Performance-based edge functions | JavaScript, TypeScript, WASM compilable languages (Rust, C, COBOL), languages compilable to JavaScript (Kotlin, Dart, Python, Scala, OCaml, Perl, PHP, F#) | High performance edge computing, especially if using JavaScript or TypeScript.                                    | CloudFlare Workers offers a major difference from other general providers by focusing on edge delivery and using V8 isolates.  If your serverless workflows fit this execution model, Cloudflare Workers may be able to deliver better performance for lower costs. |
| Netlify Functions         | Web application functions        | JavaScript, TypeScript, Go                                                                                                                                  | Web applications, JAM stack sites, headless CMSs.                                                                 | Netlify adds value to AWS Lambda by integrating serverless functionality into complete application build and deployment management.  If your serverless needs match that use case, Netlify is a good choice for managing everything in one place.                   |
| Vercel Functions          | Web application functions        | Node.js, Go, Python, Ruby, Bash, Deno, PHP, Rust                                                                                                            | Web applications, JAM stack sites, headless CMSs.                                                                 | Vercel is a great choice if you need serverless to augment your web application deployment story.  This is doubly true if your application is built with Next.js since the integration is guaranteed to be excellent.                                     |

<PrismaOutlinks>

Registrations are now open for the Prisma Serverless Conference on November 18, 2021.  [Sign up now for free!](https://www.prisma.io/serverless)

</PrismaOutlinks>