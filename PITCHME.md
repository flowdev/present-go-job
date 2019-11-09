## How to Land a Good Go Job
### or what to watch out for so your new team member won't break the service

Note:
- Who is looking for job?
- Who is hiring?
- Leaning more towards looking for a job

---

## What is Go used for?

- Advertisement bidding |
- Cloud technologies |
- Fintech |
- Blockchain technology |
- Diverse companies building services |

Note:
- Roughly in chronological order
- What segment do hiring engineers come from?

---

## Advertisement bidding

- Low latency (ca. 50ms) request handling |
- High concurrency |
- Scalability matters |
- Knowledge about the world held in RAM |
- Web API |
- Performance critical stuff behind interfaces |
- Many engineers love high performance stuff |
- Enough rooms for juniors |
- Few, small companies |

Note:
- Only somewhat interesting for juniors

---

## Cloud technologies

- Command line tools |
- Low level programming |
- Low latency services |
- Highly skilled engineers |
- Few, small companies |

Note:
- Don't try to go here

---

## Fintech

- Mistakes can cost a lot of money |
- Web APIs |
- Rooms for junior devs who test carefully |
- Quite some companies from small to medium |

Note:
- Can be good start

---

## Blockchain technologiy

- Distributed services |
- Highly skilled engineers |
- Few, small companies |

Note:
- Don't try to go here

---

## Diverse companies building services

- Web APIs |
- Lots of room for junior devs |
- Many companies from small to huge |

Note:
- Easiest start

---

## Job market take away

- Web APIs |
- Business software |
- Growing with more adoption of Go |

---

## Typical job interviews

- Coding test |
- Brain teasers |
- Algorithms and data structures |
- Only the top x% of engineers work for us |

Note:
- over-engineering
- old, shitty code base

---

## What do I need to know for Web APIs???

---

## HTTP (aka "Web")

- HTTP is stateless (!) |
- REST (REpresentational State Transfer) (!) |
- Interesting HTTP methods: GET, POST, DELETE, PUT, PATCH |
- Request can come multiple times: Idempotent (!) |
- Nice to know: GraphQL |

Note:
- No Web without HTTP

---

## Authentication & authorization

- Authentication: Who is it? |
- Authorization: What is allowed? |
- Role based authorization (!) |
- Cookie (from middleware or framework) + server side session |

Note:
- Gateway / bouncer

---

## Authentication & authorization 2

- JWT (JSON Web Token) can be used with or without server side session (!) |
- Offer only 1 good cipher for JWT |
- Nice to know: OAuth 2.0 |
- Security is important here |

---

## Database

- Types: relational, document-oriented, key-value, graph |
- Use cases: business data, archiving, caching, ... |
- RDBMS (Relational DataBase Management System) (!) |
- DB schema: design, evolution |
- DB transactions: how do they work, why and when to use them, locking & lock levels |
- How to prevent SQL injection (!) |

Note:
- Heart of every business software
- Long term storage -> hard to change

---

## 3rd party API

- Error handling |
- Resilience (!) against down-times |
- Call to 3rd party in the context of a transaction |

Note:
- No direct influence on third party!
- Can stop the whole system

---

## Testing / code quality

- Test pyramid (!): |
- Surviving Software Dependencies (!) |
- Clean code (!) |

Note:
- Maintainability
- Test pyramid: unit tests >> integration tests > end-to-end tests
