# package manager : npm vs pnpm vs yarn berry 

**Date:** 2026-05-01  
**Category:** CS / package manager / library / tools

## What I learned

I was using npm so far and whaaaat? You might think I am ignorant ngl,, 
There are three popular package managers. Lemme introduce them!
- **npm**
- **pnpm**
- **yarn berry**
Let's take a look from npm!

---

## npm - Classic package manager 

**Characteristics**  
👉 Node is already included. No need to intall node. <br/>
👉 node_modules architecture ( traditional )<br/>

### Pros
- stable
- biggest ecosystem
- good compatibility

### Cons 
- slow
- big node_modules
- overlapping package
  
---

## pnpm - Rookie package manager 

**Characteristics**  
👉 Store based on hard link <br/>
👉 Store in the center repository and share it. <br/>

### Pros
- faaast 
- less disk usage
- strict dependency architecture

### Cons 
- some libraries has compatibility problems
- learning curve 

--

## yarn berry - unique package manager 

**Characteristics**  
👉 Plug'n'Play (PnP) based <br/>
👉 dependency based on zip file <br/>

### Pros
- super fast 
- less disk usage
- strong for monorepo

### Cons 
- some libraries has compatibility problems
- learning curve
- hard to debug
  
---


## So which one is better?

It depends on what project are you on!

If you are working on monorepo project, then yarn berry can be a good choice! 🐈‍⬛ <br/>
If you are using many dependencies, pnpm is better! 🐈 <br/>

---
## Why this is interesting

Well, Well, I remember I learned this difference long time ago. <br/>
Now it's time to move on pnpm from npm😮 <br/>
