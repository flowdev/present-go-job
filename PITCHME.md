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
- Performance critical stuff often hidden behind interfaces |
- Many engineers love to work on the performance critical stuff |
- Enough rooms for junior devs who can implement web APIs |
- Few companies, small teams |

---

## Cloud technologies

- Command line tools |
- Low level programming |
- Low latency services |
- Highly skilled engineers |
- Few companies, small teams |

---

## Fintech

- Mistakes can cost a lot of money |
- Web APIs |
- Rooms for junior devs who can implement web APIs and test carefully |
- Quite some companies, teams from small to medium |

---

## Blockchain technologiy

- Distributed services |
- Highly skilled engineers |
- Few companies, small teams |

---

## Diverse companies building services

- Web APIs |
- Lots of room for junior devs who can implement web APIs |
- Many companies, teams from small to huge |

---

## Job market take away

- By far most Go jobs are about web APIs |
- Growing with more adoption of Go |

---

## Topics:


---

### Authentication, authorization, user management (5 minutes)

- differences between authentication/authentication
- sessions (cookie, jwt, other?)
- authorization strategy (role based)
- security (should be at least mentioned)
- trade-offs, pain points, past experiences

---

### HTTP layer (5 minutes)

- REST vs rpc
- is HTTP stateless or state-full, and what does that imply
- existing methods, what is an idempotent method and which ones should be
- caching
- knowledge about GraphQL?

---

### Database layer (5-10 minutes)

- types of databases (RDBM, document-oriented, graph)
- different use cases ("it depends")
- schema (design, management)
- transactions (how do they work, why and when to use them)

---

### 3rd party API (5 minutes)

- resilience against down-times
- error handling
- call to 3rd party in the context of a transaction

---

### Testing/quality (5-10 minutes)

- test pyramid (layers: unit tests, integration, end-to-end, percentage for each layers: ~70%, 20%, 10%)
- what about 3rd parties/external dependencies
- clean code!




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
