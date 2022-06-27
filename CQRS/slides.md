---
title: The "what" and "why" of CQRS
revealOptions:
  transition: none
---

# The *what* and *why* of CQRS

---

## Definition
<!-- .element: style="font-size: smaller; text-align: left;" -->

CQRS stands for Command and Query Responsibility Segregation, a pattern that
separates read and update operations for a data store. Implementing CQRS in
your application can maximize its performance, scalability, and security. The
flexibility created by migrating to CQRS allows a system to better evolve over
time and prevents update commands from causing merge conflicts at the domain
level.
<!-- .element: style="font-size: smaller; text-align: left;" -->

https://docs.microsoft.com/en-us/azure/architecture/patterns/cqrs
<!-- .element: style="font-size: small; text-align: left;" -->

Note:
- here's a definition of CQRS

---

<img src="./images/boring.gif">

https://media1.giphy.com/media/t7AI4TmE0PYI/giphy.gif
<!-- .element: style="font-size: small;" -->

Note:
- this is very boring
- instead let's take a step back and build up some context to better explain wahat CQRS is

---

```text
+-------+               +----+
|       | <-- reads --- |    |
| model |               | DB |
|       | -- writes --> |    |
+-------+               +----+
```

---

```text
+------------+                +---+
|            |                |   |
| read model | <-- reads ---- |   |
|            |                |   |
+------------+                |    |
                              | DB |
+-------------+               |    |
|             |               |   |
| write model | -- writes --> |   |
|             |               |   |
+-------------+               +---+
```

---

## read model <-> write model

---

![single model](./images/single-model.png)

https://martinfowler.com/bliki/images/cqrs/single-model.png
<!-- .element: style="font-size: small;" -->

---

![cqrs](./images/cqrs.png)

https://martinfowler.com/bliki/images/cqrs/cqrs.png
<!-- .element: style="font-size: small;" -->

---

| Reads        | Writes                             |
| -----        | ------                             |
| simple       | complex business logic             |
| can be stale | must be transactionally consistent |


---

## Resources

---

- [Martin Fowler: CQRS](https://martinfowler.com/bliki/CQRS.html)

