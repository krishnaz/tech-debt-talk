@title[Quantifying Tech Debt]
## Quantifying Tech Debt
 
#### Ideas to find and reduce tech debt

Note:
* First try to define tech debt
* Problems it causes
* Cause of it
* How to minimise creation
* Quantitatively identify it at code/component/team level

---
### What is tech debt?

- Has become a loose, umbrella term |

Note:
* Catch all for bad code, not writing tests, not following software eng
* Putting off refactoring
* Not using the latest libs

---
### Tech debt occurs organically

> "As an evolving program is continually changed, its complexity, reflecting  
> deteriorating structure, increases unless work is done to maintain or reduce it."

Meir "Manny" Lehman, 1980

Note:
* http://dl.acm.org/citation.cfm?id=681473
* Ages ago

---
### Not all tech debt is equal

> "A little debt speeds development so 
> long as it is paid back promptly with a rewrite... 
> The danger occurs when the debt is not repaid. Every minute spent on not-quite-right 
> code counts as interest on that debt. 
> Entire engineering organizations can be brought to a stand-still under excess debt..."

Ward Cunningham, 1992

Note:
* http://c2.com/doc/oopsla92.html
* Kinda ages ago
* re-worded slightly to fit
* Every extra minute spent is an interest payment
* Key point, is incurring interest only when spending time on it
* function of time
* Not all tech debt is equal
* Various interest rates based on quality as well as time spent on it

---?image=assets/techDebtQuadrant.png&size=auto

Note:
* All can produce it
* Top right common in startups, to decrease time to market
* Bottom right is common case
* Bottom left, lack of knowledge, layering: separation of concerns
* Could be bad culture, we don't want to see
* Broken window can have an effect too
* Boy scout rule, Uncle Bob

---
### What problems does it cause?

- Cause defects |
- Slow down development of new features |
 - Directly: when implementing the feature |
 - Indirectly: by taking time away through maintenance |

Note:
* Through misunderstanding of overly complex code
* Through not applying DRY
* Through inefficient code/architecture
* Maintenance: bug squashing, manual intervention

---
### What can we do to minimise creation of it?

- Code review |
 - Spread knowledge |
 - Catch refactoring candidates |
 - Catch missing test cases |
- Tooling |
 - Code coverage |
 - Mandatory reviews |
- Knowledge sharing |
- In a utopia this would all happen, and all tools in place from day 0 |

Note:
* Tooling to automate as much as possible
* human factor
* quick fixes
* Friday evening PRs
* Tooling not in place
* Large PRs
* But also tools only useful if react, otherwise just noise

---
### Not all tech debt is costly

- Overall quality should be high |
- Quality should be highest where code is changed most often |
- Not always predictable |
- History could be used |

Note:
* Culture

---
### Identifying high interest tech debt in code

- Measure code complexity |
 - Cyclomatic complexity not as useful for functional |
 - whitespace as a proxy |
 - function length |
- Use git logs |
 - Wealth of info |
  - Number of changes |
  - Number of authors |
  - Link to Jira ticket ID |
   - Feature vs Bug rate info |

Note:
* Ideas from Tech debt talk by Adam Tornhill: https://www.infoq.com/presentations/priority-technical-debt
* not cyclomatic, but just whitespace analysis. Could try others
* historical gold mine: git log

---
### Analysis examples to identify tech debt in code

- Used Code Maat tool by Adam Tornhill |
- Looked at Apache Spark codebase |
- HotSpot Analysis |
- Complexity and LoC trends |
- Temporal coupling |

Note:
* Apache Spark code base
* Used CodeScene tool, opensource scripts available
* 

---?image=assets/hotSpotKey.png&size=auto


Note:
* size and colour
* Git log for changes
* whitespace analysis for complexity indicator

---?image=assets/powerLawFilesChangeFreq.png&size=auto
      
      
Note:
* General rule
* focus efforts

---?image=assets/sparkHotSpotOverview.png&size=auto
   
   
Note:
* hotspot overview
* Reflects package structure
* uses MoosePlatform for visualisations
   
---?image=assets/hotSpotSparkSqlParserFocus.png&size=auto
      
      
Note:
* Focus on problem file
* Highlights SparkSqlParser.scala

---?image=assets/sparkSqlParserFunctionAnalysis.png&size=auto
      
      
Note:
* Focus on file
* Focus on particular functions

---?image=assets/sparkSqlParserComplexityLoCTrends.png&size=auto
      
      
Note:
* Complexity and LoC trends
* Bad from beginning
* refactor attempted
* creeping up again
* Monitor trends, build tool?

---?image=assets/temporalCouplingDesc.png&size=auto
      
      
Note:
* Temporal coupling
* % of commits where a particular other file is also modified
* git log has this
* Identify refactor candidates, merge files to be more cohesive

---
### Identifying high interest tech debt in components

- Change frequency
- Jira Ticket ID |
 - temporal coupling |
 - feature based |
 - bug based |
- Alert based | 
- LoC change frequency trends |

Note:
* Similar analysis, but at component level
* Temporal may mean merge components, or reduce coupling to increase cohesion
* Highly changed means refactor to ease change
* Highly buggy could indicate issues
* Alert based, similar to bugs, but shows high maintenance
* LoC should ideally stabilise, could indicate attracting change for multiple reasons

---
### Identifying tech debt in teams?

- Separate teams frequently working together |
 - Inefficiencies of communication |
- Coupled teams |
 - Coupled components across teams |
- Diverse features requiring same team |
 - Spawn separate teams? |

Note:
* Separate but always working on features together -> merge
* Coupled teams -> major change in one team requiring changes in another -> reduce coupling
* Diverse features requiring same team to implement -> split team?

---
### Thoughts/questions?


Note:

---
