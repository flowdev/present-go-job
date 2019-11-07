## How to Land a Good Go Job
### or what to watch out for so your new team member won't break the service

---

## What is Go used for?

- Advertisement bidding |
- Cloud technologies |
- Fintech |
- Blockchain technology |
- Diverse companies building services |

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

---

## Cloud technologies

- Command line tools |
- Low level programming |
- Low latency services |
- Highly skilled engineers |
- Few, small companies |

---

## Fintech

- Mistakes can cost a lot of money |
- Web APIs |
- Rooms for junior devs who test carefully |
- Quite some companies from small to medium |

---

## Blockchain technologiy

- Distributed services |
- Highly skilled engineers |
- Few, small companies |

---

## Diverse companies building services

- Web APIs |
- Lots of room for junior devs |
- Many companies from small to huge |

---

## Job market take away

- By far most Go jobs are about Web APIs |
- Growing with more adoption of Go |

---

## What do I need to know for Web APIs???

---

## HTTP (aka "Web")

- HTTP is stateless:
  - simple |
  - scaleable |
  - allows caching |
- REST (REpresentational State Transfer) (!) |
- Interesting HTTP methods: GET, POST, DELETE, PUT, PATCH |
- Idempotent methods can be done multiple times |
- Nice to know: GraphQL |

---

## Authentication & authorization

- Authentication: Who is it? |
- Authorization: What is allowed? |
- Role based authorization (!) |
- Cookie (from middleware or framework) + server side session |

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

---

## 3rd party API

- Error handling |
- Resilience against down-times (!) |
- Call to 3rd party in the context of a transaction |

---

## Testing / code quality

- Test pyramid (!): |
  - unit tests (~70%) |
  - integration tests (~20%) |
  - end-to-end tests (~10%) |
- Surviving Software Dependencies (!) |
- Clean code (!) |

---

## REST...


![Rune Stone](assets/runeStone.jpg)

This is a very fundamental and long term decision!

Note:
- Python is still strugling to get version 3 fully adopted (since 2008).
- 'contracts' is still the official proposal. All criticism so far didn't change that.

---

## Go Community Changes

![Logo](assets/adoption-curve.jpg)

The Go community is changing as the majority enters it.

---

## The Majority Is Pragmatic

- They use Go to get a job done |
- They aren't interested so much in technical details |
- They use their tools in simple pragmatic ways |

Note:
- Pragmatic programmers can very well be better programmers.
- They often know the problem domain very well and it is better to solve
  the right problem in a simple, straight forward way than elegantly solving the wrong problem.
- Or even solving the (right or wrong) problem in an overengineered way.

---

## Let's Solve A Small Problem

- Articles should be assembled into a news page |
- Short articles with title and text |
- Long articles with additional abstract |
- All articles know how to render themself |

---?code=go/news1/news1.go&lang=Go&title=Assembling The News

@[5](the expected signature)
@[11](the article is really used)
@[5-14](all together)

---

## Writing The Contract

- We need a usage of the article type |
- The most successful, used and pragmatic pattern in programming is: copy & paste |
- Usually we would google such a usage and copy it from the internet |
- But this is an internal type so no usage available... |
- ...except the one we just wrote! |

---?code=go/news1/news1.go&lang=Go&title=Consequently The Contract Looks Like This

@[16](the expected contract signature)
@[17](convert the simple type into a slice)
@[25](replace return statements with '_ = ')
@[16-26](all together)

---

## Evaluation Of This Solution

- I don't have to understand what a contract really is or how it works |
- I just have to follow a small set of simple and formal rules |
- I exactly know that my real usage is supported |
- Only downside is readability |
- But not for me since I know about Render |
- I only feel the immediate upsides and don't feel the long term downside at all |

---

## Adding Highlight Articles And Dimensions

- Our solution is accepted by the PO |
- But marketing rejects it |
- They want highlight articles with an image |
- And better layout |
- Articles support a 'Dimensions' method |

---?code=go/news2/news2.go&lang=Go&title=Assemble With Dimensions

@[7-13](search first highlight article)
@[14-17](if found, render highlight article)
@[19-21](don't forget separator after highlight article)
@[22-34](render articles in rows)
@[5-37](all together)

---?code=go/news2/news2.go&lang=Go&title=Contract With Dimensions

@[39-40](the start is the same)
@[71-72](the end too)
@[41-70](the rest is just copied over)

---

## Supporting Newsletters

- Our solution is a success in the market |
- But now people want the great news in their inbox |

---?code=go/news3/news3.go&lang=Go&title=AddImages

@[5-37](AssembleNews is unchanged)
@[39-56](AddImages is doing the trick)

---?code=go/news3/news3.go&lang=Go&title=Contract With AddImages

@[58-59](the start is the same)
@[60-61](nice comment for maintainability)
@[94-110](contract part for AddImages)
@[58-111](all together)

---

## What Might Work Better

- Interfaces |
- Things like \_\_Min\_\_() for operators |
- Automated code generation |
- A solution open only to library writers |
- No change at all |

---

## Suggestion For Syntax

```go
func Stringify(type T stringer)(s []T) (ret []string) {
	//...
}

func Stringify(s []T:stringer) (ret []string) {
	//...
}
```

---

## Attributions

- Proposal: https://go.googlesource.com/proposal/+/master/design/go2draft-contracts.md
- Rune stone: By Henrik Sendelbach, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=256875
- Go community changes: https://www.youtube.com/watch?v=7yMXs9TRvVI
