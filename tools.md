# Tools

# ✅ **ADOPT**

---

### ✅ Bitrise

Bitrise have proven to be a good alternative to Jenkins for iOS. It removes the need for us to maintain our own OSX environments. We can choose to build and test our iOS applications on all the relevant versions of Xcode and OSX seamlessly (there is some delay when a new version of Xcode or OSX is released).

### ✅ Codeclimate

Codeclimate is a web-based tool to track code smells, style violations, and so on in a codebase over time. It can suggest places that need refactoring or where you should be extra careful when you work. It usually has useful insights and help us maintain the "Leave everything a little better than how you found it" rule when it comes to writing code.

### ✅ Datadog APM

Datadog's Application Performance Monitoring tool is a great tool to track performance of an app with some deep insights on how the platform and code behaves. Its distributed monitoring means that you get deep tracing for backend services where you are able to view the backend service's contribution to end-user response time.

### ✅ Datadog Metrics

Datadog Metrics is an excellent tool to collect custom metrics. It's using the Statsd format, which means it's easy to integrate almost everywhere and doesn't cause any vendor lock-in and is easy to toggle by injecting or not injecting a Statsd URL to the apps. It also integrates with our existing alerting functionality. If you want metrics in your apps at Hemnet, it is hard to beat Datadog Metrics.

### ✅ Dependabot

Dependabot is a tool that helps keep your dependencies up to date. It will inform you when new versions of your dependencies are released and offer up a PR where that dependency is upgraded. If all tests passes you can also make it merge them automatically, if you so wish. Dependabot has been working really well at Hemnet and has prevented a lot of manual work and drifting too far behind on important frameworks. It was also recently aquired by Github so their future and trustworthyness will most likely only improve over time.

### ✅ Docker

Docker has proven to ease deployments and running software in production. Docker also helps with development as we can package software and keep it isolated from the host OS enough to not interfere with other apps.

### ✅ Fastlane

Fastlane is a very mature and popular tool for automating common tasks in iOS projects. We currently use it to automate deploys to iTunes Connect (releases and testflight builds), certificate management, testing, generate code coverage etc.

### ✅ Flipper

Flipper is a backend feature toggle library that Hemnet uses in our main Rails applications. It allows a fine grained rollout control which has proved itself valuable.

### ✅ Prettier

Automatic code formatter for Javascript.

### ✅ Rubocop

A popular linter for Ruby that is actively developed and maintained.

### ✅ Sentry

Exception and error reporting service. Send your errors here to keep them in the same ecosystem as the other apps and make it possible to integrate with other tooling.

### ✅ Android Lint

A linter which scans Android project sources for potential bugs and problems

### ✅ eslint

A popular linter for Javascript that supports modern versions of JS. This is Hemnet's preferred linter for JS code.

### ✅ SwiftLint

A linter for Swift. Best practice.

### ✅ Webpack

A popular asset manager and compiler for the Javascript ecosystem. It builds bundles that are appropriate to load in a web browser from the source code in the repos.

### ✅ Swift Package Manager

Swift Package Manager is the native dependency management for Swift. It has as of 2020 matured to a state where it is realistic to start using in production.

### ✅ CodeClimate Code Coverage

Code Coverage reporting. Hemnet was previously using CodeCov but migrated to CodeClimate to have a single service.

### ✅ Firebase (iOS and Android)

"A mobile and development platform used both by iOS and Android.
Hemnet only uses a subset of its functionally namely: Cloud Messaging, Remote Configuration and Crashlytics.
"

### ✅ Apollo Client (Android)

Apollo Android is a GraphQL client that generates Java and Kotlin models from GraphQL queries. These models give you a type-safe API to work with GraphQL servers. Apollo helps you keep your GraphQL query statements together, organized, and easy to access.

# 🔬️ **ASSESS** 

---

### 🔬️ AWS Sagemaker notebooks

Notebooks are one-click Jupyter notebooks that can be spun up quickly. The underlying compute resources are fully elastic, so you can easily dial up or down the available resources and the changes take place automatically in the background without interrupting your work. SageMaker also enables one-click sharing of notebooks.

### 🔬️ Xcode Cloud

Apple's own CI service that will be tightly integrated with Xcode. Currently in Beta, should assess when it is released since there are some potential benefits over running CI through Bitrise.

#  🛑 **HOLD**

---

### 🛑 Kibana / ELK stack

The ELK stack is used to track logs and metrics and make them searchable via ES. We are running this with Amazon ElasticSearch Kibana, but are not entirely happy with it. Until the situation between this and Datadog Logs clear up, it is recommended to hold developing new things on top of this.

### 🛑 LeakCanary (Android)

A memory leak detection library for Android. We might replace this with built-in support of Android Studio IDE that's coming in a later version.
