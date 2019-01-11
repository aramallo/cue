[TOC](Readme.md) [Prev](selectors.md) [Next](emit.md)

# Aliases

An alias defines a local macro.

A typical use case is to provide access to a shadowed field.

Alias are not members of a struct and thus are not part of the model and
cannot be accessed.


<!-- CUE editor -->
```
A = a  // A is an alias to a
a: {
    d: 3
}
b: {
    a: {
        // A provides access to the outer "a" which would
        // otherwise be hidden by the inner one.
        c: A.d
    }
}
```

<!-- result -->
```
a: {
    d: 3
}
b: {
    a: {
        c: 3
    }
}
```