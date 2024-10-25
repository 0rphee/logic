
# Demostrar Tollendo Ponens

```
(P ↔ Q), (P ↔ R) ⊢ (P ↔ (Q ∨ R)) ✓
```

```
show: Q
  P v Q :PR
  -P :PR
  show: --Q
    -Q :AS
    -P and -Q :ADJ 3,5
    -(P v Q) :D-DMAA 6
  :ID 2,7
  Q :DN 4
:DD 9
```

# Demostrar Tollendo Tolens

```
(P -> Q), -Q ⊢ -Q
```

```
show: -P
  P -> Q :PR
  -Q :PR
  show: -P
    P :AS
    Q :MP 2,5
  :ID 3, 6
:DD 4
```

# Demostrar equivalencias de cuantificadores (EMC)

# Equivalencia 1

```
¬∃xH(x) ⊢ ∀x¬H(x)
```

```
show: Ax-H(x)
  -ExH(x) :PR
  show: Ax-H(x)
    show: -H(a)
      H(a) :AS
      ExH(x) :EG 5
    :ID 2,6
  :UD 4
:DD 3
```

# Equivalencia 2

```
∀xH(x) ⊢ ¬∃x¬H(x)
```

```
show: -Ex-H(x)
  AxH(x) :AS
  show: -Ex-H(x)
    Ex-H(x) :AS
    show: -Ex-H(x)
      -H(a) :AS
      H(a) :UI 2
      -Ex-H(x) :D-EFQ 6,7
    :ED 4,6,8
  :ID 4,5
:DD 3
```

