

# Open Grant Proposal: `OrbitDB 1.0 pt. 2`

**Name of Project:** [OrbitDB](https://github.com/orbitdb/orbit-db)

**Proposal Category:** `devtools-libraries`

**Proposer:** [@tabcat](https://github.com/tabcat)

**(Optional) Technical Sponsor:** Dietrich Ayala, [@autonome](https://github.com/autonome)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT, APACHE2, or GPL licenses?:** `No` - OrbitDB has an existing MIT license that predates the Apache/MIT dual license convention.

# Project Description

<!-- Please describe exactly what you are planning to build. Make sure to include the following: -->

<!-- - Start with the need or problem you are trying to solve with this project. -->

OrbitDB is a peer-to-peer database built on top of IPFS. It uses Merkle-CRDTs (think CRDTs stored in and inter-linked by a Merkle-DAG) to reference, store, and transfer operations made to the database. While blockchain systems care about consensus, systems like OrbitDB care about convergence; meaning database peers can handle network partitions and allow for fully asynchronous updates. We believe this will be extremely powerful in media and communication applications by increasing their safety and resilience to network delay.

The project has been around for several years but has not matured with IPFS primarily due to funding. We would like to continue our work with a grant *part 2* which will allow us to finish work from the last six months.

The work has been focused on:
  - staying compatible with the latest js-ipfs API
  - writing a specification for the protocol
  - cleaning up the codebase so it will be easier to maintain and improve
  - finding a stable API
  - the 1.0 release of OrbitDB

<!-- - Describe why your solution is going to adequately solve this problem. -->

<!-- This section should be 2-3 paragraphs long. -->

## Value

<!-- Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions: -->

<!-- - What are the benefits to getting this right? -->

OrbitDB provides an easy way for users to build real-time, decentralized, and collaborative applications. It can be used to build alternatives to many of the services that have collected user data into a handful of systems. These alternatives will act more like protocols and the valuable user data will be dispersed.

Building applications this way has a few nice benefits and goes hand in hand with delay-tolerant network designs like IPFS. The user has control over their data, often stored and updated locally. The updates made locally are treated as the source of truth. This property is often referred to as local-first and can give a very responsive user experience.

The flexibility that the Merkle-CRDT data structure enables is also notable. Causal links between messages in the Merkle-DAG provide ordering information and deduplication, this separates the CRDT from the underlying network properties and replication. Systems like IPFS, Filecoin, or other storage backends can be used to backup and restore replicas.

Not all applications can be built with peer-to-peer databases like OrbitDB. The types of applications that can be solved are called \*invariant confluent. These types of applications usually fall into the media or communication category, things like most of Google's suite of applications.

We think exploring this area by maintaining and upgrading OrbitDB is worthwhile. We believe it will result in more and better user-centric apps that utilize technologies like IPFS and Filecoin.

\*invariant confluence means that any two messages applied asynchronously will not invalidate an application's invariant. For example, an invariant of blockchains is that no account can have a negative balance.

#### Usage Stats

<!-- This section should be 1-3 paragraphs long. -->

??? [orbitdb/orbit-db](https://github.com/orbitdb/orbit-db) Github Stars: `7k`

???? [orbitdb/orbit-db](https://github.com/orbitdb/orbit-db) Github Forks: `~500`

??????????? [orbitdb/orbit-db](https://github.com/orbitdb/orbit-db) Github Contributors: `62`

???? [orbitdb](https://www.npmjs.com/package/orbit-db) weekly installs: `~3000`

???? lifetime weekly installs:

<img src="https://github.com/orbitdb/grant-applications/blob/main/ff-open-grant/.assets/orbitdb-npm-lifetime.png?raw=true" width="700" />

User Project Sample:

  - [Capsule.social](https://capsule.social/technology/platform) / [Blogchain](https://blogchain.app/home): Decentralized, censorship-resistant blogging
  - [Quiet](https://github.com/TryQuiet/monorepo): A private alternative to team chats like Discord / Slack
  - [Constellation](https://github.com/reseau-constellation/constellation): distributed and open system for sharing scientific data
  - [WatchIt](https://github.com/ZorrillosDev/watchit-toolkit): shared video library and streaming
  - [Berty](https://berty.tech) (indirectly, using their own go implementation): secure messaging

## Deliverables

<!-- Please describe in details what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished. -->

We will be delivering OrbitDB 1.0. This will be a full, stable release.

[OrbitDB 1.0 Release Tracker](https://github.com/orbitdb/orbit-db/issues/1008)

## Development Roadmap

<!-- Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section). -->

<!-- For each milestone, please describe: -->
<!-- - The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables. -->
<!-- - The amount of funding required for each milestone -->
<!-- - How much time this milestone will take to achieve (using real dates) -->

**(JULY 2022)** OrbitDB 1.0 Beta
  - [orbitdb/orbit-db#1002](https://github.com/orbitdb/orbit-db/issues/1002)
  - base 1.0 implementation
  - 90% test coverage
  - key value database
  - static access control
  - public API documentation

---

[Post OrbitDB 1.0 Beta Tasks](https://github.com/orbitdb/orbit-db/issues/1003)

**(AUGUST 2022)** Draft Protocol Spec Merge
  - [orbitdb/spec#1](https://github.com/orbitdb/spec/issues/1)
  - base protocol components defined
  - beta implementation kept in lockstep with spec

**(SEPTEMBER 2022)** Public API is Locked

**(SEPTEMBER 2022)** Security Audit Begins

**(SEPTEMBER 2022)** Heavier Testing
  - protocol conformance testing
  - work with the Berty team on cross-implementation testing
  - increase the robustness of replication tests

**(OCTOBER 2022)** Focus on Automation
  - fixup testing and publishing automation
  - performance regression checks
  - automate Github release and change logs
  - automate api documentation

**(OCTOBER - NOVEMBER 2022)** Features and Improvements
  - feed database
  - quicker database queries after opening via index/graph snapshots
  - typescript used where external data is received
  - generalized batch operations
  - reserve multicodec table spot for binary orbitdb address

---

**(EOY 2022)** OrbitDB 1.0 Release
  - [orbitdb/orbit-db#1008](https://github.com/orbitdb/orbit-db/issues/1008)
  - protocol spec finalized
  - updated documentation and examples
  - security audit has finished

## Total Budget Requested

$19,200.00 in USD, and an amount worth approximately $4,800.00 USD in FIL per month.

This number is based on an allocation of one full time developer and one part-time engineer for oversight / PR review / mentoring etc.

In total, we are requesting eight months of funding which amounts to $153,600 USD and the equivalent of approximately $38,400 in FIL.

In the end, any ratio of USD/FIL is acceptable for payment, provided that the value of FIL is determined by reference to the most recent close price on https://www.coinmarketcap.com on the day immediately prior to the payment.

<!--Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds. -->

## Maintenance and Upgrade Plans

<!-- Specify your team's long-term plans to maintain this software and upgrade it over time. -->

The plan for this grant is to build a foundation that will keep the project hyper-maintainable over the years. After the project reaches this level of maintainability, the key is to cultivate a thriving userbase. We believe we can do this by having a solid 1.0 release and then continuing to provide a supportive community chat, building features/dev-tools for orbitdb, and providing high-quality resources for learning.

Following the full 1.0 release there will still be room for improvement:

Nearer future:
  - ascending traversal: databases can read operations to the database in ascending order.
  - active replicator: implement an active replicator that pushes data, and may use orbitdb with just libp2p. requested by a few users.
  - write-ahead log: keep N operations unapplied to the database index, apply them on read. improves state calculation in some situations.
  - full typescript

Further Future:
  - next-gen access control: dynamic access control that doesn't affect the entire history
  - CBOR database: a CBOR CRDT, similar to Automerge's JSON CRDT. may require ascending traversal.
  - dynamic topological sort: maintain a dynamic topological sort of the DAG. likely to have significant effects in many areas.
  - async ratchet tree encryption: use something like message layer security for scalable multi-writer encryption of database operations.
  - Graphsync replicator: replication that uses Graphsync to quickly replicate operations from peers.


# Team

## Team Members

Anders, [@tabcat](https://github.com/tabcat) - role:maintainer

Mark, [@aphelionz](https://github.com/aphelionz) - role:oversight

## Team Website

https://equilibrium.co

## Relevant Experience

<!-- Please describe (in words) your team's relevant experience, and why you think you are the right team to build this project. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc. -->

Mark Henderson ([GitHub](https://github.com/aphelionz), [Twitter](https://twitter.com/aphelionz)) is the VP of Engineering at Equilibrium.
I have led the team starting with the original Rust IPFS grant in late 2019, through engagements with many of the largest names in Web3, and am now circling back to finish the critical work the team started with the original Ziggurat proposal. Core contributor to OrbitDB, Rust IPFS, and Ziggurat.

---

Anders has been involved with OrbitDB since finding it in late 2018.
In March of 2020 I started working on a collaborative filesystem on top of IPFS using OrbitDB. In July 2020 a partner and I leveraged this to build Sailplane, a p2p Dropbox-like web app that made us finalists in the first HackFS.
In February 2021 I was contracted by Equilibrium to maintain OrbitDB. In November we signed an open source grant from Protocol Labs to fund the first part of development for OrbitDB 1.0. During the 6 month grant period, I worked on keeping the current version supporting the latest js and go ipfs implementation, as well as a protocol spec and implementation for 1.0.

## Team code repositories

<!-- Please provide links to your team's prior code repos for similar or related projects. -->

Anders:
  - https://github.com/orbitdb: maintainer to orbitdb, its submodules, and resources
  - https://github.com/cypsela/sailplane-web: collaborative filesystem web app built with orbitdb and ipfs [[ref1]](https://showcase.ethglobal.com/hackfs/sailplane-web) [[ref2]](https://filecoin.io/blog/posts/meet-the-hackfs-teams-vol.3/)
  - https://github.com/tabcat/orbit-db-fsstore: a custom orbitdb database representing a filesystem

Mark:
  - https://github.com/orbitdb: core contributor to orbitdb, its submodules, and resources
  - https://github.com/tallylab/tallylab: local-first, end-to-end encrypted data diary app
  - https://github.com/orbitdb/orbit-db-powergate-io: A bridge between OrbitDB and Powergate

# Additional Information

How did you learn about the Open Grants Program?

`it was suggested by users in our community chat`

Please provide the best email address for discussing the grant agreement and general next steps.

`mark@equilibrium.co`

<!-- Please include any additional information that you think would be useful in helping us to evaluate your proposal. -->
