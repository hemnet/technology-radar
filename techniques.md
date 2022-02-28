# Techniques

# <span style="color:green"> ✅ **ADOPT** </span>

---

### ✅ Infrastructure as code

Infrastructure as code is a technique where infrastructure (servers, networks, storage, and so on) are provisioned automatically by tools that read plain text files from a codebase rather than have a human perform it manually. It makes it possible to perform the regular code review, CI/CD pipeline processes, rollbacks, and use version control for infrastructure changes. Hemnet finds this to be very valuable and it has increased velocity and transparency.

### ✅ Managed services

When running software in production, prefer a managed instance rather than running it ourselves. Databases, search engines, and so on. Not having to add these to the list of things we need to maintain internally means we have more time to maintain our actual apps instead. It also removes the need for experts of the software that tweak and adjust as much.

### ✅ Serverless

Serverless is an approach that tries to hide the servers entirely when designing and running apps. Serverless instead focuses on apps, containers, or functions, and talks about deploying these by themselves without mentions of filesystems, hostnames, port numbers, or other things that relate to the actual servers underlying them. On the outset this abstraction seems very useful for app developers as it's fewer things to talk about, and scaling can become a lot more dynamic when the platforms are given more freedom in placement and 
auto-scaling of the cluster. However, it also leads to less control as the platform will do a lot of things under the hood. There is also no clear "winner" when trying to choose a platform; it's still a pretty unexplored territory. Also see: AWS Lambda, WebAssembly, Docker, Serverless (framework), Cloudflare Workers

### ✅ 12-factor applications

The 12-factor Application manifesto is a good guideline on how to design apps and ship them to our environments. Some parts of it has become de-facto standard in the industry, just like how part from the Agile manifesto has been integrated almost everywhere. However, we feel that we want to acknowledge the source of this wisdom and to present a good and easy to read guide on why these decisions exist and how they relate to each other.

### ✅ Retryable Webhooks

Retryable Webhooks is a technique for safer service communication. Instead of sending a message on a message bus with an unclear recipient, send webhooks - simple HTTP GET requests with some payload. In order to increase deliverability safety of this (as you don't want messages to be lost if the receiver is having downtime), you can place a background queue on both the sender and recipient. The sender doesn't send the message directly, instead it places the message on its own queue so it can be retried if the receiver is down. The 
receiver does not process the message immediately when receiving a message, instead if places the message on its own queue and acknowledges the message to the sender. Now even if the receiver has issues, the message will remain on its own queue until it can be processed successfully and the sender can stop trying to send it. It is very important that these messages remain indempotent, so attach something to the message to allow the receiver to identify the same message again and skip it. This could be a UUID, a version number, or a timestamp depending on the message.

### ✅ Message Buses

Message buses are a technique for asynchcronous communication between services where a message broker receives messages from the sender and redirects them to the receiver with retries if the receiver is not responding. Usually message buses allows pub-sub, fan-out, and fan-in exchanges too for more advanced cases. This is a powerful and useful technique, but Hemnet does not yet have a good case for using this that isn't well-covered by simpler Retryable Webhooks. This decision is sure to change if more app-to-app communication is 
added.

### ✅ Component Library

Hemnet Component Library serves styles and React components to Hemnet’s different web applications.

# <span style="color:green">🧪 **TRIAL**</span>

---

### 🧪 Datadog Logs 
Datadog Logs looks like it could be a valuable platform for shipping logs to and make them searchable. It should also integrate well with their APM and watchdogs, which should help us debug issues even more. However, it's still untested and the costs of using this is still unknown. Hemnet should find cases where this can be tested in order to find out more.

# <span style="color:orange"> 🔬️ **ASSESS** </span>

---

### 🔬 Integrating React in the conventional Rails monolith

Not all web applications are going to be moved to Next.js. For example, kundportalen we see no benefit of moving to a API-driven web application and we will continue to server-side render props to the components. We do however need to optimize the way we write React in Rails with ease so that we utilise our React component library. This means we should investigate in techniques and tools to bridge this gap. E.g. Inertia (tracked separately on the radar)

# <span style="color:red"> 🛑 **HOLD**</span>

---

### 🛑 Microservices

We embrace a Service Oriented Architecture. We think microservices can be a good fit for certain isolated use cases but there is no driving force in turning Hemnet’s systems into a microservice oriented architecture at the moment. Microservices are designed for larger organisations - far beyond our scale.
