# Open Grant Proposal: `Web3 Product Analytics`

**Name of Project:** Web3 Analytics

**Proposal Category:** `app-dev`

**Proposer:** `@andyjagoe`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT, APACHE2, or GPL licenses?:** Yes

# Project Description

<!-- Please describe exactly what you are planning to build. Make sure to include the following: -->
<!-- - Start with the need or problem you are trying to solve with this project. -->
<!-- - Describe why your solution is going to adequately solve this problem. -->

<!-- This section should be 2-3 paragraphs long. -->


The project is a decentralized analytics platform for web3. Like Google Analytics for web3. Or Dune Analytics for off-chain data.

### Why is this needed?

[80% of the top 10,000 web sites on the internet](https://www.rootandbranchgroup.com/google-analytics-in-2022/) use Google Analytics. In fact, the majority of web3 projects [do too](https://docs.google.com/spreadsheets/d/1P1yWqr1-r1xv2nUSPgT5pXtUx3IvPyYw0ZUAdpkUHjI/edit#gid=0). But, as a web3 project, giving all your data to Google breaks your brand promise to users and goes against the ethos of decentralization. Big Tech sells this data to the highest bidder for ad targeting and users have no control over their data and no visibility into what is collected. 

But a web3 project without analytics is flying blind. Without analytics, you have no data driven product insights. Only guesses. Trying to build a consumer product without analytics is like trying to fly a 747 jet airplane without instruments or a dashboard. It’s very difficult, and often ends in a bad outcome. A competitor who has analytics will fly circles around you if you don’t.

On-chain analytics are great. But they’re the very bottom of the funnel. A tiny fraction of the user journey. Transaction data misses everything that leads up to the transaction. And everything that happens afterwards. Alone, it’s not enough.

Web3 Analytics is an attempt to provide projects another option. A decentralized analytics solution that can't be shut down or censored. A public good that is default open and enables complete transparency into how a product is being used, without compromising privacy or web3 values.

### How is it different?

All the analytics solutions today are centralized and default closed. This means that only the app owner can see the dashboards and what data is being collected. Users do not own their data and may not delete it unless the app owner allows them to. Also, because data is centralized, it can be censored and shut down. One of the most forward looking new analytics products is Plausible Analytics (https://plausible.io/). They are open source and allow you to host your own service--but they don't solve the problem of centralization and they don't make analytics data a public good. The majority of web3 projects are using some sort of centralized service, with at [least half using Google Analytics](https://docs.google.com/spreadsheets/d/1P1yWqr1-r1xv2nUSPgT5pXtUx3IvPyYw0ZUAdpkUHjI/edit?usp=sharing).

By contrast, the solution I'm proposing is a decentralized public good, where all data is readable by anyone and difficult to censor or shut it down. Projects can get critical product insights to improve their user experience without breaking a user's trust or compromising web3 values. The analytics service is default open, so it actually increases transparency into how a project is being used. It does for off-chain data what Dune Analytics has done for on-chain data.

### Current Status

I've built a proof-of-concept (alpha) of the system, which consists of 5 components:

* Front-End Instrumentation Tooling
* Decentralized Data Network
* Smart Contract Registry
* Indexer
* Dashboard Builder / UI

[Here is how the system works, with links to source code and the prototype.](https://docs.google.com/document/d/1fCYnOMHetbfH4MvWoPs-e0KHHTIzgwF1IrWBAqSmU08/edit?usp=sharing)

The purpose of this grant is to allow me to finish the project and deploy it to mainnet.

## Value

<!-- Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions: -->
<!-- - What are the benefits to getting this right? -->
<!-- - What are the risks if you don't get it right? -->
<!-- - What are the risks that will make executing on this project difficult? -->

<!-- This section should be 1-3 paragraphs long. -->

The benefit to the IPFS ecosystem if this projects works is a significant increase in IPFS usage. Each application that instruments with Web3 Analytics generates a continuous river of data into the IPFS ecosystem. This data is pinned by default, so more data also means more fee income for IPFS pinning services. And more fee income enables more investment by participants into the IPFS ecosystem. The risk of not having an application like this on IPFS is that one if created for a competing ecosystem and that ecosystem is the beneficiary of the increased usage and fee income. 

The primary execution risk in this project is not technical. A proof-of-concept exists and the path to mainnet and scalability is pretty clear. The primary challenge for the project will be getting traction with the community. This is normal for a project like this.

The good news is that the project has a straight-forward distribution motion and clear value proposition. A project doesn't need to choose between Web3 Analytics and a competing analytics product. The front-end instrumentation package we use allows sending data to both Web3 Analytics and most other major analytics packages in parallel. This dramatically reduces switching costs of changing analytics platforms and allows someone to easily try Web3 Analytics while still using their existing analytics platform. And because web3 projects are open source, we can identify projects who would most benefit and do the integration/migration ourselves and issue a PR for inclusion. This approach won't scale, but is a great way to get adoption/trial in the early days.

As projects web3 projects like [Farcaster](https://www.farcaster.xyz/) (and other like it) mature, they will realize their protocols need decentralized, privacy preserving analytics built into the protocol or provided by a third party decentralized network. Farcaster needs to aggregate impressions, clicks, expands, profile visits, etc and this can't be done separately in each Farcaster client or each client's data will be incomplete/fragemented.

I don't think it will make sense for every web3 project to roll their own decentralized analytics solution from first principles, and this is why I think there's a great opportunity for Web3 Analytics and IPFS to provide the solution.

## Deliverables

<!-- Please describe in details what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished. -->

The goal of the grant proposal is to deliver a usable first version to mainnet. Specifically, this means taking the existing project and completing the below deliverables.

*Front-End Instrumentation*:
* Upgrade OpenGSN client to v3 (which uses ethers instead of web3) to reduce the size of our tracking package
* Migrate from Ceramic testnet to mainnet
* Migrate from Rinkeby testnet to layer 2 mainnet (most likely Polygon)

*Decentralized Data Network*:
* Update Ceramic data models to use new GraphQL interface so indexing is extensible and system scales. 
* Bring up Ceramic mainnet node and migrate from Ceramic testnet to mainnet

*Smart Contract Registry*:
* Update smart contracts to collect a fee from apps that would like to use the service to cover gas station network fees.
* Create self-service UI to authorize fee collection 
* Upgrade OpenGSN smart contracts to v3
* Migrate from Rinkeby testnet to layer 2 mainnet (most likely Polygon)

*Indexer*:
* Update indexer source interface to use Ceramic's new GraphQL interface and data model so indexing is extensible and system scales. 
* Migrate from Ceramic testnet to mainnet

*Dashboard Builder*:
* Expose database schema in the UI to make query generation easier
* Create documentation and example SQL queries/dashboards to support a range of analytics questions so an app wanting to use the service can easily create their own queries/dashboards.

## Development Roadmap

<!-- Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section). -->

<!-- For each milestone, please describe: -->
<!-- - The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables. -->
<!-- - How many people will be working on each milestone and their roles -->
<!-- - The amount of funding required for each milestone -->
<!-- - How much time this milestone will take to achieve (using real dates) -->

I will work full time on the project for three months, and the grant will subsidize my personal costs so I can complete the project and make it generally available on mainnet. Please see the section on Total Budget requested for cost and time estimates for each component.

### Front-End Instrumentation
To use Web3 Analytics, you instrument your app using [Analytics](https://github.com/DavidWells/analytics) (a lightweight open-source frontend analytics abstraction layer) and use the [web3 analytics plugin](https://www.npmjs.com/package/analytics-plugin-web3analytics) I wrote for a decentralized data back-end. Analytics has plugins for most major analytics systems and they can be run in parallel, so taking this approach removes vendor lock-in and reduces risk.

You can see Web3 Analytics working on this [demo site](https://celadon-pothos-120129.netlify.app/) ([source code](https://github.com/andyjagoe/web3-analytics-demo)). Click the buttons to generate events. You'll see confirmation toasts appear in the browser. Open the browser console to see the interactions with the decentralized back-end.

*Deliverables*:
* Upgrade OpenGSN client to v3 (which uses ethers instead of web3) to reduce the size of our tracking package
* Migrate from Ceramic testnet to mainnet
* Migrate from Rinkeby testnet to layer 2 mainnet (most likely Polygon)

 
### Decentralized Data Network
Web3 Analytics uses [Ceramic](https://ceramic.network/) for decentralized data storage. Ceramic is a decentralized and permissionless data streaming network built on top of IPFS. It provides DID authentication, immutable naming, and mutable streams in a decentralized manner.

When a new user arrives at your app, we auto-generate a secp256k1 keypair for the user we store in the browser. This keypair is used for DID authentication to Ceramic for writing analytics data. We store the entire analytics payload of every event in Ceramic and the data is cryptographically secured and belongs to the user. While anyone can read this anonymous data, only the user may delete or modify it using the keypair. 

I created a [secp256k1 adapter](https://www.npmjs.com/package/key-did-provider-secp256k1) for Ceramic because it is the same curve used in Ethereum and Bitcoin. This is important because of the next component. Since our data is decentralized, we need a smart contract to keep track of it so we can find it again.

*Deliverables*:
* Update Ceramic data models to use new GraphQL interface so indexing is extensible and system scales. 
* Bring up Ceramic mainnet node and migrate from Ceramic testnet to mainnet


### Smart Contract Registry
Web3 Analytics has a smart contract that tracks apps and the addresses of the users that belong to them. An app that would like to use Web3 Analytics must first call the registerApp function on the Web3 Analytics smart contract. Once done, the app can register users and allow users to record data in Ceramic.

The DID generated to securely write to Ceramic can be converted to an Ethereum keypair because they both use secp256k1. Web3 Analytics checks to see if the user is registered with this app in the smart contract. If not, it silently processes a registration transaction in the background using Gas Station Network v2 ([OpenGSN](https://opengsn.org/)).

The contracts are currently running on Rinkeby but will deploy to an EVM compatible Layer 2 (e.g. Polygon) for production so each user registration only costs a fraction of a cent.

* [Web3Analytics.sol](https://rinkeby.etherscan.io/address/0xAbff8ea6b55A80B18d57b8c4AD36DC55583cA2cb#code)
* [Web3AnalyticsPaymaster.sol](https://rinkeby.etherscan.io/address/0xfabB9AA1532fC563b7ccB040E9943D4396B2D100#code)

*Deliverables*:
* Update smart contracts to collect a fee from apps that would like to use the service to cover gas station network fees.
* Create self-service UI to authorize fee collection 
* Upgrade OpenGSN smart contracts to v3
* Migrate from Rinkeby testnet to layer 2 mainnet (most likely Polygon)


### Indexer
Having the raw analytics data in a decentralized data store is great. It’s an open, permissionless, user owned, community asset available to everyone. Like blockchain data. 

But, like blockchain data, it’s difficult to get insights from and build dashboards with a raw data format. You need a way to load it into traditional datastores for processing.

To address this, I’ve created an [indexer](https://github.com/andyjagoe/airbyte-connectors-esm/tree/main/sources/web3analytics-source) for the data. It's an automated pipeline that uses the [Airbyte](https://airbyte.com/) open source ELT platform and pushes normalized data directly into Postgres and S3. Our source connector continuously monitors the blockchain and Ceramic for new apps, users and data for indexing.

For now, data is stored in an S3 data lake in [Apache Parquet](https://databricks.com/glossary/what-is-parquet) format and accessed via [AWS Athena](https://aws.amazon.com/athena/). [Apache Spark](https://spark.apache.org/) also supports S3 data lakes in parquet format and is another option for us as we scale. Once Ceramic's GraphQL interface has robust indexing and sufficient performance to support analytics queries, we will pull data directly from Ceramic instead of using S3.

*Deliverables*:
* Update indexer source interface to use Ceramic's new GraphQL interface and data model so indexing is extensible and system scales. 
* Migrate from Ceramic testnet to mainnet


### Dashboard Builder
The dashboard builder is a free tool that allows anyone to build a dashboard using SQL. Similar to Dune Analytics, queries and dashboards are default public and designed to be easily forked and shared. 

I expect we will create many of the first dashboards as templates to make getting started easier for users. The hope is we hand this off to the community over time the same way Dune has.

An alpha version of the dashboard is [here](https://web3analytics.network/) and you can view a [sample dashboard](https://web3analytics.network/users/99281713380d8efc77348ef00b1f02ec/dashboard/andyjagoecom-key-metrics) I’ve created for one of the sites I’ve instrumented. Source code is [here](https://github.com/andyjagoe/web3-analytics-app).

*Deliverables*:
* Expose database schema in the UI to make query generation easier
* Create documentation and example SQL queries/dashboards to support a range of analytics questions so an app wanting to use the service can easily create their own queries/dashboards.


## Total Budget Requested

<!--Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds. -->

Total budget requested is $30,000:

* 12 months of hosting cost for Ceramic node and indexers: $250/mo * 12 = $3,000

* Month 1: $9000
    * Update smart contracts to collect a fee from apps that would like to use the service to cover gas station network fees.
    * Expose database schema in the UI to make query generation easier
    * Upgrade OpenGSN to v3 (which uses ethers instead of web3) so we can reduce the size of our tracking package 

* Month 2: $9000
    * Update Ceramic indexer to use new GraphQL interface so indexing is extensible and scales
    * Begin moving the service from testnet to mainnet and cover the costs of running a mainnet Ceramic node (required for mainnet usage of Ceramic) and production indexers.

* Month 3: $9000
    * Complete moving the service from testnet to mainnet and cover the costs of running a mainnet Ceramic node (required for mainnet usage of Ceramic) and production indexers. 
    * Testing
    * Create documentation and example SQL queries to support a range of analytics questions so an app wanting to use the service can easily create their own queries/dashboards.


## Maintenance and Upgrade Plans

<!-- Specify your team's long-term plans to maintain this software and upgrade it over time. -->

Applications that use the service will need to pay a small fee for registration and usage to cover gas station network expenditures. These fees could also fund maintenance and upgrades of the service.

# Team

## Team Members

<!-- - Team Member 1 -->
<!-- - Team Member 2 -->
<!-- - Team Member 3 -->

Andy Jagoe

## Team Member LinkedIn Profiles

<!-- - Team Member 1 LinkedIn profile -->
<!-- - Team Member 2 LinkedIn profile -->
<!-- - Team Member 3 LinkedIn profile -->

[https://www.linkedin.com/in/andyjagoe/](https://www.linkedin.com/in/andyjagoe/)

## Team Website

<!-- Please link to your team's website here (make sure it's `https`) -->

[https://web3analytics.network/](https://web3analytics.network/) (prototype)

[https://web3analytics.network/users/99281713380d8efc77348ef00b1f02ec/dashboard/andyjagoecom-key-metrics](https://web3analytics.network/users/99281713380d8efc77348ef00b1f02ec/dashboard/andyjagoecom-key-metrics) (sample dashboard)

## Relevant Experience

<!-- Please describe (in words) your team's relevant experience, and why you think you are the right team to build this project. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc. -->

I've started and exited a few software companies, including a messaging company I grew to millions of users and was sold to Skype and a search company that I turned around and sold to eBay. I've built multiple Internet scale products and have managed several large-scale analytics deployments, including for a site that serviced 75 million annual uniques.

My core expertise is product and engineering, and for the last several years I've been focused on web3. I believe public blockchains collapse the cost of large-scale network coordination, and I'd like to see a more fair and equitable distribution of value creation in future platforms (especially for users). For the last year, I've been doing web3 consulting for AngelList.

https://andyjagoe.com/about/

https://www.linkedin.com/in/andyjagoe/


## Team code repositories

<!-- Please provide links to your team's prior code repos for similar or related projects. -->

[https://github.com/andyjagoe](https://github.com/andyjagoe)

# Additional Information
<!-- How did you learn about the Open Grants Program? -->
<!-- Please provide the best email address for discussing the grant agreement and general next steps. -->
<!-- Please include any additional information that you think would be useful in helping us to evaluate your proposal. -->

Karola Kirsanow from Protocol Labs told me about the Open Grants program and thought this project might be a fit. More details on how the Web3 Analytics system works, including links to source code and a prototype can be found [here](https://docs.google.com/document/d/1fCYnOMHetbfH4MvWoPs-e0KHHTIzgwF1IrWBAqSmU08/edit?usp=sharing).
