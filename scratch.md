# SCRATCH

TODO: organize these in other sections

* nim makes some common idioms in D first-class citizens. For example, imperative type declarations are first-class citizens so all the boiler plate around "if (isInputRange!(R))" type stuff goes away in Nim

* Nim is the only language that leverages automated proof technology to perform a disjoint check for your parallel code. Working on disjoint data means no locking is required and yet data races are impossible:

```
parallel:
  var i = 0
  while i <= a.high:
    spawn f(a[i])
    spawn f(a[i+1])
    # ERROR: cannot prove a[i] is disjoint from a[i+1]
    # BUT: replace 'i += 1' with 'i += 2' and the code compiles!
    i += 1
```

* The syntax seems more orthogonal with fewer bultin constructs and many generated by library, eg: 'a>b is a hygyenic macro that generates 'b<a'; associative arrays (tables) are in library

