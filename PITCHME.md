@title[Quantifying Tech Debt]
## Quantifying Tech Debt
 
#### Ideas to identify costly tech debt

Krishna Rao - ATE BE Engineer

Note:
* First try to define tech debt
* Problems it causes
* Reasons it is created/increases
* Quantitatively identify it at code/component/team level

---
### What is tech debt?

- Has become a loose, umbrella term |

Note:
* Catch all for bad code, not writing tests, not following software eng
* Not an excuse to put off refactoring

---
### Code deteriorates organically

> "As an evolving program is continually changed, its complexity, reflecting  
> deteriorating structure, increases unless work is done to maintain or reduce it."

Meir "Manny" Lehman, 1980

Note:
* Software changes, evolves, organically will deteriorate
* Ages ago
* http://dl.acm.org/citation.cfm?id=681473

---
### Not all tech debt is equal

> "A little debt speeds development so 
> long as it is paid back promptly with a rewrite... 
> The danger occurs when the debt is not repaid. Every minute spent on not-quite-right 
> code counts as interest on that debt. 
> Entire engineering organizations can be brought to a stand-still under excess debt..."

Ward Cunningham, 1992

Note:
* Analogy to financial debt
* Key point, is incurring interest only when spending time on it
* function of not only quality but also on time spent on it in future
* Every extra minute spent is an interest payment
* Various interest rates based on quality as well as time spent on it
* http://c2.com/doc/oopsla92.html (re-worded slightly to fit)

---?image=assets/techDebtQuadrant.png&size=auto

Note:
* Top right common in startups, to decrease time to market
* Bottom right is common case
* Bottom left, lack of knowledge, layering: separation of concerns
* Could be new tech, not tuned right
* Top left: Could be bad culture, we don't want to see

---
### What problems could it cause?

- Cause defects |
- Slow down development of new features |
 - Directly: when implementing the feature |
 - Indirectly: by taking time away through maintenance |

Note:
* Defects through misunderstanding of overly complex code
* Defects through not applying DRY
* Directly by needing to first understand complex code
* Indirectly through maintenance: bug squashing, manual intervention

---
### Not all tech debt is costly

- Overall quality should be high everywhere |
- Quality should be highest where code is changed most often |
- Not always predictable |
- History could be used |

Note:
* overall quality from culture and standards

---
### Identifying high interest rates in code

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
* git log: historical gold mine

---
### Analysis examples to identify tech debt in code

- Used Code Maat & CodeScene tool by Adam Tornhill |
- Looked at Apache Spark codebase |
- HotSpot Analysis |
- Complexity and LoC trends |
- Temporal coupling |

Note:
* Apache Spark code base
* Used CodeScene tool, opensource scripts available

---?image=assets/hotSpotKey.png&size=auto


Note:
* size for complexity and colour for num changes
* Git log for changes
* whitespace analysis for complexity indicator

---?image=assets/powerLawFilesChangeFreq.png&size=contain
      
      
Note:
* General rule
* focus efforts

---?image=assets/sparkHotSpotOverview.png&size=contain
   
   
Note:
* Spark hotspot overview
* Reflects package structure
* uses MoosePlatform for visualisations
   
---?image=assets/hotSpotSparkSqlParserFocus.png&size=contain
      
      
Note:
* Focus on problem file
* Highlights SparkSqlParser.scala

---?image=assets/sparkSqlParserFunctionAnalysis.png&size=contain
      
      
Note:
* Focus on file
* Focus on particular functions
* Perhaps not as side project, but warning before next development task touching it

---?image=assets/sparkSqlParserComplexityLoCTrends.png&size=contain
      
      
Note:
* Complexity and LoC trends for this file
* Bad from beginning
* refactor attempted
* creeping up again
* Monitor trends, build tool, warn on uptick

---?image=assets/temporalCouplingDesc.png&size=auto


Note:
* Temporal coupling
* Again git log has this
* % of commits where a particular other file is also modified
* Identify refactor candidates, merge files to be more cohesive

---
### Identifying high interest tech debt in components

- Change frequency |
- Jira Ticket ID |
 - temporal coupling |
 - bug based |
- Alert based |
- LoC change frequency trends |

Note:
* Similar analysis, but at component level
* Frequency high means refactor to ease change
* Temporal may mean merge components, or reduce coupling to increase cohesion
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
### Summary

- Demystified tech debt |
- Not all tech debt is costly |
- Identify costly tech debt in code |
- Identify costly component tech debt |
- Touched upon broadening tech debt to apply to teams |

Note:
* Demystified, clarified term
* Not all: prioritise defeating costly tech debt
* Quantitative approach to identifying costly tech debt
* Touch upon applying to components
* Could we apply to teams to reduce inefficiencies?

---
### Thoughts/questions?


Note:

---
