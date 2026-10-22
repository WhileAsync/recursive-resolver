Recursive DNS setup using knot-resolver and dnsdist for encrypted DNS, DNSSEC validation, RPZ-based blocking, caching, and traffic filtering.

---

In the backend, knot-resolver handles recursive resolution on localhost, DNSSEC validation, resolver caching, root-zone prefill, predictive prefetching, and RPZ filtering. Resolver options enable QNAME minimization, strict glue checking, rebinding protection, and stale-answer serving.

In the frontend, dnsdist exposes DNS over TLS on port 853 and DNS over HTTPS on port 443 over IPv4 and IPv6. Forwards queries to knot-resolver, maintains a packet cache, applies dynamic rate-based drop rules, and refuses AXFR, IXFR, NOTIFY, and UPDATE requests.

> The current ACL allows all IPv4 and IPv6 sources, restrict access if public recursion is not intended.

---
