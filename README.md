## Andrea Cosentino

Apache Software Foundation Member. I maintain [Apache Camel](https://github.com/apache/camel) and do security research across the Apache ecosystem. Based in Rome, at IBM.

[![Blog](https://img.shields.io/badge/blog-oscerd.github.io-1f6feb?style=flat-square&logo=rss&logoColor=white)](https://oscerd.github.io)
[![Apache](https://img.shields.io/badge/ASF-Member-D22128?style=flat-square&logo=apache&logoColor=white)](https://www.apache.org/foundation/members.html)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Andrea%20Cosentino-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/andrea-cosentino-439119100/)

### What I actually spend time on

Camel, mostly — the core framework, the Spring Boot and Quarkus runtimes, Kamelets, Camel K, and the website. Over the last twelve months that came to roughly **1,700 commits and 3,400 pull request reviews** across 31 repositories.

The review half is the part that matters. A framework with 350+ components stays healthy because other people's patches land well, not because I write more of them.

### Security research

**42 CVEs credited to date**, across Camel and twelve other Apache projects — Hadoop, Hive, Storm, Doris, Flink, Flink Kubernetes Operator, IoTDB, Zeppelin, Gravitino, Polaris, Fluss, and SkyWalking. The full table, with CWE classes and fixed-in versions, is in **[security-research](https://github.com/oscerd/security-research)**.

Much of it is one bug class chased across unrelated codebases: **untrusted input reaching a control plane that assumed it was trusted.** In Camel that shows up as header injection — an inbound header the framework never filtered, steering a producer into SSRF, a cross-topic write, or a redirected SOAP operation. Elsewhere it wears different clothes. Other recurring findings:

- **Fail-open authentication** — policies that skip verification entirely when no roles are configured, so any forged token passes
- **Unsafe deserialization** in registry lookups, key-lifecycle handling, and legacy migration paths
- **Information disclosure** — stack traces returned to clients where the mute setting defaults wrong or a binding ignores it

Where I can I publish a minimal runnable reproducer, each naming the release that fixed it: 27 for my own findings, plus 20 more built for issues reported by other researchers.

Adjacent work:

| Repository | What it is |
| --- | --- |
| [camel-pqc-tls](https://github.com/oscerd/camel-pqc-tls) | Post-quantum TLS 1.3 with Camel — X25519MLKEM768 hybrid key exchange, BouncyCastle on JDK 21 and native on JDK 27 |
| [kroxylicious-pqc-filter](https://github.com/oscerd/kroxylicious-pqc-filter) | A post-quantum filter for the Kroxylicious Kafka proxy |
| [camel-jbang-mcp-security-conf](https://github.com/oscerd/camel-jbang-mcp-security-conf) | Hardening the Camel JBang MCP server surface |
| [process-injection-playground](https://github.com/oscerd/process-injection-playground) | Process injection techniques, annotated |

I write most of this up on [oscerd.github.io](https://oscerd.github.io), including a weekly roundup of Java vulnerabilities.

### Stats

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-streak-stats.herokuapp.com/?user=oscerd&theme=dark&hide_border=true">
  <source media="(prefers-color-scheme: light)" srcset="https://github-readme-streak-stats.herokuapp.com/?user=oscerd&theme=default&hide_border=true">
  <img alt="Contribution streak" src="https://github-readme-streak-stats.herokuapp.com/?user=oscerd&hide_border=true">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=oscerd&theme=github-dark&hide_border=true&area=true">
  <source media="(prefers-color-scheme: light)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=oscerd&theme=github-light&hide_border=true&area=true">
  <img alt="Contribution activity over the last year" src="https://github-readme-activity-graph.vercel.app/graph?username=oscerd&hide_border=true&area=true">
</picture>
