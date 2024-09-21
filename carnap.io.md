## Chapter 9

## Ex. 12.1

```
(P ↔ S), (¬Q → ¬P), (¬R → P) ⊢ (R ∨ (S ∧ Q)) ✓
```

```
show: R or (S and Q)
  P <-> S :PR
  not Q -> not P :PR
  not R -> P :PR
  not not Q or not P :D-MI 3
  show: not R -> R or (S and Q)
    not R :AS
    P :MP 4,7
    not not P :DN 8
    not not Q :MT 9,3
    P -> S :BC 2
    S :MP 8,11
    Q :DN 10
    S and Q :ADJ 12,13
    R or (S and Q) :ADD 14
  :CD 15
  show: R -> R or (S and Q)
    R :AS
    R or (S and Q) :ADD 18
  :CD 19
  R or (S and Q) :D-DA 17,6
:DD 21
```

## Ex. 12.2

```
(P ∨ S), (S → ¬(Q → ¬P)) ⊢ (P ∨ R)
```

```
show: P or R
  P or S :PR
  S -> not (Q -> not P) :PR
  show: S -> P
    S :AS
    not not S :DN 5
    not (Q -> not P) :MP 5,3
    show: not (not Q or not P)
      not Q or not P :AS
      Q -> not P :D-MII 9
    :ID 7,10
    not not Q and not not P :D-DMA 8
    not not Q :S 12
    Q :DN 13
    not not P :S 12
    P :DN 15
  :CD 16
  show: P or S -> P
    show: P -> P
      P :AS
    :CD 20
    P :D-HD 2,4,19
  :CD 22
  P :MP 18,2
  P or R :ADD 24
:DD 25
```

