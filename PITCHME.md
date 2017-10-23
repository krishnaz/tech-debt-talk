@title[Quantifying Tech Debt]
## Quantifying Tech Debt
 
#### Ideas to find and reduce tech debt

---
### What is tech debt?

- Has become a loose, umbrella term

Note:
* Catch all for bad code, not writing tests
* Putting off refactoring
* Not using the latest libs

---
### What is tech debt?

> "As an evolving program is continually changed, its complexity, reflecting  
> deteriorating structure, increases unless work is done to maintain or reduce it."

Meir "Manny" Lehman, 1980

Note:
* http://dl.acm.org/citation.cfm?id=681473
* Ages ago

---
### What is tech debt?

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

---
### What problems does it cause?

- Cause defects
- Slow down development of new features |
 - Directly: when implementing the feature |
 - Indirectly: by taking time away through maintenance |

Note:
* Through misunderstanding of overly complex code
* Through not applying DRY
* Through inefficient code/architecture
* Maintenance: bug squashing, manual intervention

---?image=assets/techDebtQuadrant.png&size=auto

Note:
* All can produce it
* Top right common in startups, to decrease time to market
* Bottom right is common case
* Bottom left, lack of knowledge
* Boy scout rule, Uncle Bob
* Broken window can have an effect too
* Could be bad culture, we don't want to see

---
### What can we do to minimise creation of it?

- Code review
 - Spread knowledge |
 - Catch refactoring candidates |
 - Catch missing test cases |
- Tooling |
 - Code coverage |
 - Mandatory reviews |
- Knowledge sharing |

Note:
* human factor
* Tooling to automate as much as possible

---
### Can we identify existing tech debt?


Note:

---
### Identifying tech debt in code


Note:

---
### Identifying tech debt in components


Note:

---
### Identifying tech debt in teams?


Note:

---
### What is the current ideal?


Note:

---
### Thoughts/questions?


Note:

---
