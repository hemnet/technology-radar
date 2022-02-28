# Platforms

# <span style="color:green"> ✅ **ADOPT** </span>

---

### ✅ AWS ECS

Amazon's Elastic Container Service is a product that adds bare-bones orchestration of Docker on top of EC2-nodes. It's essentially a programmable interface to the plain docker command, but on top of clusters of machines. It's been working well, but there's limitation to what you can build on top of this and it requires a lot of tooling in order to get some features that are expected of an orchestration layer. Until Hemnet finds a better alternative, or dismisses all alternatives as worse, it will remain as a "Trial".

### ✅ AWS Lambda

Amazon's Lambda is a serverless "Functions-as-a-service", that allows deployment of functions to an environment where they can be executed with very high parallelization without requiring explicit machines to be running on stand-by. It seems to be a really good platform for features that have very variable but unpredictable loads over time, but it has other tradeoffs that prevents it from being a clear choice right now. Hemnet will need to run more production loads on this platform in order to learn about the limits and opportunities presented.

### ✅ CircleCI

CircleCI is a managed CI platform which Hemnet switch to during 2020 in favour of Jenkins. It provides a great developer (documentation) experience which allows developers to set it up with minimal involvement from platform team.

### ✅ Cloudflare CDN

Cloudflare has a large CDN that has excellent performance and pricing. This service is one of the core components in Hemnets infrastructure and have proven itself to be very reliable.

### ✅ Cloudflare Rate Limiting

Cloudflare has a rate limiting platform that allows us to add rate-limiting on the "network layer", which in this case means that we can protect ourselves without having offenders even reach our applications. This is really powerful for stopping bad actors, but it's also unclear how it could be used when application-level logic is needed to determine how to scope clients or to identify to certain behavior to limit. It's also something that cannot be configured in the applications directly as it must be set on the Cloudflare web UI rather than live in a codebase.

### ✅ Elasticsearch

Elasticsearch is a capable, modern, and cloud-native full-text search engine.

### ✅ Google Analytics

Google Analytics is a tool for web analytics. It is used to track user interactions and analyse user behaviour.

### ✅ Google Tag Manager

Manage JavaScript-tags without editing code. Google Tag Manager delivers simple, reliable, easily integrated tag management solutions.

### ✅ Memcached

Memcached is a network attached cache placed in RAM. It is very fast and simple for the most common cache loads. Adopt this if you just want a simple Key-Value store for non-persistent cache of String-like values.

### ✅ PostgreSQL

PostgreSQL is a powerful relational database system that has proven itself again and again at Hemnet. It's one of the surest picks on this entire Tech Radar.

### ✅ Redis

Redis is a powerful Key-Value database that has support for several value types, including Sets, Hashes, and Lists. While the cases where a simple key-value database clearly wins over a full relational or document-oriented database are few, when you do need a fast key-value database Redis is very hard to beat.

### ✅ Snowplow

Snowplow is a data collection platform that tracks real time events. We use their stream based platform to track interactions on our site. We have tracked interactions with this system for a couple of months now and we're tracking its progress.

### ✅ Cloudflare Workers

Cloudflare Workers is Cloudflare's Lambda compute offering running on their edges. It provides 0ms cold starts and runs in V8 isolates. It includes a distributted KV store.

### ✅ Google Maps

Hemnet uses Google Maps for map services (except iOS-app which uses the native Apple Maps). We are however open for exploring other options if the use case is there.

### ✅ AWS DynamoDB for time series data

DynamoDB is a managed key-value database with some extra features. We have used the range index feature to store time series data. With this feature it's possible to fetch a range of values for a given key. We're levering this to store aggregated metrics as time series for our listings. It works well if the quires is well defined but it's harder to support a wide range of queries since DynamoDB is stil just a key-value database.

### ✅ AWS Kinesis

Kinesis is a managed data stream which can be used to collect and process any kind of real time data. We use it to transfer events between components in our event tracking setup and to store searches to S3.

### ✅ AWS Redshift

Redshift is column based database designed for warehousing large amount of data. Redshift has proven itself to be capable to store and transform large amount of data. We use this database to store tracking data and we're evaluating its capabilities.

# <span style="color:green">🧪 **TRIAL**</span>

---

### 🧪 Contentful

Headless CMS. Flexible, build in environment support. Easy to use admin UI(Robin likes it). Easy to integrate with Gatsby or Next.js. Hemnet has trialed it with Hemnet Utland. Good replacement for Wordpress
Serverless (framework)	

### 🧪 Serverless framework

A framework for building serverless applications. It takes care of infrastructure provisioning, packaging and deployment of the application as well as tools for running your serverless services locally. It is widely used with around 35k stars on Github and a rich eco system with plugins to extend the functionality. It is vendor agnostic with support for all major cloud providers. AWS' equivalent is Serverless Application Model (AWS SAM).

# <span style="color:orange"> 🔬️ **ASSESS** </span>

---

### 🔬️ ️Kubernetes

Kubernetes is a Docker orchestration platform that has a lot of features. Hemnet will be assessing this stack as an alternative to AWS ECS. Kubernetes seems to becoming the most popular stack for running Docker in the cloud, but the backside of it is that the stack is designed for 1000-node magnitudes of large corporations which is counteracted with extra complexity that might be too much for us. Hemnet must evaluate if the extra complexity makes the stack worse than our own stack and how hard it is to maintain.

### 🔬️ Cloudflare Pages

Cloudflare Workers Sites is a product for serving static assets. Hemnet runs /utland and the maintenance site on this.

### 🔬️ AWS Sagemaker

Amazon SageMaker is a fully managed service that provides every developer and data scientist with the ability to build, train, and deploy machine learning (ML) models quickly. SageMaker removes the heavy lifting from each step of the machine learning process to make it easier to develop high quality models.

# <span style="color:red"> 🛑 **HOLD**</span>

---

### 🛑 Jenkins

Jenkins is a platform in order to build runners, most popularily used for building CI/CD pipelines. Hemnet uses Jenkings as CD, and as a "cloud cron". The CI part has been replaced by CircleCI and we are looking at moving the CD parts away from Jenkins too.

### 🛑 RabbitMQ

RabbitMQ is one implementation of the AMQP protocol, which is used to build message buses for sending messages between services without the services having to know about each other and without requiring a stable connection to be opened directly to the apps. Hemnet does not have enough cases of service communication to warrant a whole message bus for now, and RabbitMQ has mostly been used to implement background job runners anyway. For this reason, background jobs are recommended to move to Sidekiq instead, and message passing to Retryable Webhooks. Hemnet will re-evaluate these choices in the future if message buses becomes more fitting.
