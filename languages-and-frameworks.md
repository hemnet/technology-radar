# Languages and Frameworks

# ✅ **ADOPT**

---

### ✅ GraphQL

GraphQL has proven itself to be a great API design platform for Hemnet, allowing new features to be developed fast, safe fixtures to be used in clients, and for documentation to have a natural place in the APIs. GraphQL is strongly recommended for all internal API traffic.

### ✅ React

React is a framework for building reusable components for the web using a unidirectional data flow which Hemnet has decided to use

### ✅ RSpec

The de-facto BDD framework for Ruby. Hemnet recommends using RSpec for all Ruby repos to keep the tests written in a consistent style. Prefer RSpec over minitest or Test::Unit.

### ✅ Ruby

Hemnet's most used programming language. It's a language that is focused on developer happiness!

### ✅ Ruby on Rails

A DSL for building web apps in Ruby. It's built on the idea of the smart server that renders finished markup for the clients to consume, rather than having a thin server and heavy clients that render everything. Rails might be on the decline as client-side application increase in size and complexity, but the stability of the platform has proven to work well at Hemnet. Even for client-heavy apps, Rails' ability to easily create RESTful APIs and integrate testing makes it a good platform to work on when using Ruby.

### ✅ Sidekiq

Sidekiq is a popular background job runner for Ruby apps. It's using Redis for persistence and integrates very well with Ruby on Rails.

### ✅ Swift (for iOS)

This is the current default and preferred language on iOS. Apple is pushing Swift hard and it is the language that most new iOS developers learn. It provide a number of benefits compared to Objective-C in relation to security, performance, ease of use and developer happiness etc.

### ✅ Terraform

Terraform is a framework for handling infrastructure as code. It's well-used and powerful, but at the same time it has a tendency to lead to infrastructure living in independent places from the applications that it is driving. Hemnet is happy with it, but it's not obvious that one should use it over something else.

### ✅ Testing Library

A light-weight solution for testing web pages by querying and interacting with DOM nodes (whether simulated with JSDOM/Jest or in the browser)

### ✅ Android Jetpack

A suite of libraries, tools, and guidance from Google to help developers write high-quality Android apps easier.

### ✅ Dagger(Hilt)

A fully static, compile-time dependency injection framework for both Java and Android.

### ✅ Jest

A testing framework for Javascript, which integrates well with other tools and framworks we use at Hemnet.

### ✅ Kotlin (for Android)

A cross-platform, statically typed, general-purpose programming language with type inference. Kotlin is designed to interoperate fully with Java, and the JVM version of its standard library depends on the Java Class Library,[3] but type inference allows its syntax to be more concise. It's also the de facto programming language for mordan Android development

### ✅ Combine

New reactive framework released in 2019 by Apple. It is comparable to RxSwift but lack a lot of the rich features RxSwift provide. Combine is heavily used by Apple in their SwiftUI examples and it is clear that this is a technology / pattern that will be increasingly important over time.

### ✅ SwiftUI

New declarative UI framework released in 2019. It is supported from iOS 13 and forward. SwiftUI is a significant change from existing UI patterns on iOS. As of spring 2020 this should be considered as a immature technology. It is something that could be very useful in the long term since it enables new interesting workflows and a much improved way to think structure UI code and reason about different UI states etc.

### ✅ Next.js

A React framework with hybrid static & server rendering, TypeScript support, smart bundling. One of the most (seemingly) mature and stable frameworks out there. Hemnet is currenly in the transition of building our consumer facing web applications with it.

### ✅ NodeJS

A language runtime for running Javascript in the backend. It's a very popular stack and it is built on top of asynchronous I/O, which should lead to great performance in I/O-heavy applications, which is usually almost all web apps. Hemnet uses it in a few applications, e.g. image scaling, map tile generation and a few infrastructure related tools. It is however not to Adopt for general purpose web applications/APIs.

### ✅ Kotlin Flow / Kotlin coroutines

A Kotlin implementation of coroutines and cold asynchronous data stream that sequentially emits values and completes normally or with an exception.

# 🧪 **TRIAL**

---

### 🧪 Typescript

Typescript is a superset of Javascript developed by Microsoft (and others) that adds an optional static type system to Javascript, which - if the assertion is true - should help maintainability of large Javascript codebases and make it easier to develop in it.

# 🔬️ **ASSESS**

---

### 🔬 Android Jetpack Compose

Jetpack Compose is Android’s modern toolkit for building native UI. It simplifies and accelerates UI development on Android.

### 🔬 Kotlin Multiplatform Mobile

Kotlin Multiplatform Mobile allows you to use a single codebase for the business logic of iOS and Android apps. You only need to write platform-specific code

### 🔬 Inertia.js

See “Integrating React in the conventional Rails monolith” on the radar for context. Inertia allows you to create fully client-side rendered, single-page apps, without much of the complexity that comes with modern SPAs. It does this by leveraging existing server-side frameworks. InertiaJS would help us if we were to convert an whole "traditional" Rails monolith from ERB to React, but we don't see the need to do that anywhere today. For one-off embedded React-components, where using React makes sense, InertiaJS does not help us. There are a few technical issues with using InertiaJS, e g. We can only have one Rails layout, and the library does not play well with rendering other traditional pages. See #7538 in Kundportalen for more information.

### 🔬 dbt

www.getdbt.com is a framework for writing modular sql-queries with software engineering practices. Such as testing, versioning and so on. It is becoming increaseingly popular within Data Engineering and could be used for transforming data in our Data Warehouse  

# 🛑 **HOLD**

---

### 🛑 Rust

Rust is a fairly new programming language for low- to high-level development with focus on stability, performance, and maintainability. Rust is currently being assessed if it would be a good fit for Hemnet's more performance-critical parts, services that need stability, or for smaller software that shouldn't need too much active maintenance.

### 🛑 Java (for Android)

We're still running parts of the Android app in Java, but are migrating Java-code to Kotlin in a steady pace with the goal to run 100 % Kotlin on Android.

### 🛑 jQuery

jQuery was a popular Javascript framework for decorating simpler web apps with interactivity and build simpler client-side webapps at a time where browsers had wildly different levels of Javascript conformance and the Javascript APIs were less developed. As the web moved on and new JS APIs were added and old browsers fell out of use, new frameworks took its place. Hemnet does not see a place for jQuery on the modern web and recommends actively trying to remove jQuery from apps still using it.

### 🛑 Objective-C

We should avoid writing any new features in Objective-C to support the migration to Swift. The only case when Objective-C code should be considered is if it solves an specific problem that otherwise would require significant refactor to move to Swift.

### 🛑 Enzyme

Enzyme is a testing framework for React components. Was evaluated against Testing-Framework

### 🛑 IGListKit

Framework that enables a better way to work with lists in iOS. It is a data driven approach that is developed and maintained by Instagram. Apple introduced an own solution to this in 2019 (diffable datasources) that should be the preferred approach when possible. Considering this we should avoid to use IGListKit in new development unless it provide significant benefits in the short term. We currently use ListKit for most of our views where we display search result in the app.

### 🛑 Realm

Framework for storing data locally on device. We adopted this as an alternative to the Core Data framework that is provided by Apple. The dependency is quite large for our limited use of storing data locally. It might be a good idea to go back to Core Data (or sqlite, custom data types) to reduce the number of dependancies.

### 🛑 Retrofit (Android)

A type-safe HTTP client for Android and Java

### 🛑 RxJava (Android)

A Java-implementation of Reactive Programming programming paradigm that is concerned with data streams and the propagation of change.

### 🛑 Gatsby

Gatsby is React-based frontend framework that Hemnet used when building Hemnet Utland (with Contentful as CMS). This was prior to Next.js and given the adoption of Next.js at Hemnet we do not intend to continue our usage of Gatsby.
