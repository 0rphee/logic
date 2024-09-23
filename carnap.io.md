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

## Chapter 10

## Ex. 13.9

```
⊤ ⊢ (((P → R) ∧ (Q → S)) → ((P ∧ Q) → (R ∧ S))) ✓
```

```
show ((P -> R) and (Q -> S)) -> ((P and Q) -> (R and S))
  (P -> R) and (Q -> S) :AS
  P -> R :S 2
  Q -> S :S 2
  show: P and Q -> R and S
    P and Q :AS
    P :S 6
    R :MP 7,3
    Q :S 6
    S :MP 4,9
    R and S :ADJ 8,10
  :CD 11
:CD 5
```

## Ex. 13.10

```
⊤ ⊢ ((P → (Q ↔ R)) ↔ ((P ∧ Q) ↔ (P ∧ R))) ✓
```

```
show: (P -> (Q <-> R)) <-> ((P and Q) <-> (P and R))
  show: (P -> (Q <-> R)) -> ((P and Q) <-> (P and R))
    P -> (Q <-> R) :AS
    show: (P and Q) -> (P and R)
      P and Q :AS
      P :S 5
      Q :S 5
      Q <-> R :MP 6,3
      Q -> R :BC 8
      R :MP 7,9
      P and R :ADJ 6,10
    :CD 11
    show: (P and R) -> (P and Q)
      P and R :AS
      P :S 14
      R :S 14
      Q <-> R :MP 15,3
      R -> Q :BC 17
      Q :MP 16,18
      P and Q :ADJ 19,15
    :CD 20
    (P and Q) <-> (P and R) :CB 4,13
  :CD 22
  show: ((P and Q) <-> (P and R)) -> (P -> (Q <-> R))
    (P and Q) <-> (P and R) :AS
    P and Q -> P and R :BC 25
    P and R -> P and Q :BC 25
    show: P -> (Q <-> R)
      P :AS
      show: Q -> R
        Q :AS
        P and Q :ADJ 29,31
        P and R :MP 32,26
        R :S 33
      :CD 34
      show: R -> Q
        R :AS
        P and R :ADJ 37,29
        P and Q :MP 27,38
        Q :S 39
      :CD 40
      Q <-> R :CB 30,36
    :CD 42
  :CD 28
  (P -> (Q <-> R)) <-> ((P and Q) <-> (P and R)) :CB 2,24
:DD 45
```

## Ex. 14.9

```
⊤ ⊢ (((P → Q) ∨ R) ↔ (P → (Q ∨ R))) ✓
```

### Answer 1

```
show: ((P -> Q) or R) <-> (P -> (Q or R))
  show: ((P -> Q) or R) -> (P -> (Q or R))
    (P -> Q) or R :AS
    show: not not ((not P or Q) or R)
      not ((not P or Q) or R) :AS
      not (not P or Q) and not R :D-DMA 5
      not (not P or Q) :S 6
      not R :S 6
      not not P and not Q :D-DMA 7
      P -> Q :MTP 8,3
      not not P :S 9
      P :DN 11
      not Q :S 9
      Q :MP 12,10
    :ID 13,14
    (not P or Q) or R :DN 4
    R or (not P or Q) :D-CDIS 16
    (R or not P) or Q :D-COMMOR 17
    Q or (R or not P) :D-CDIS 18
    (Q or R) or not P :D-COMMOR 19
    not P or (Q or R) :D-CDIS 20
    P -> (Q or R) :D-MII 21
  :CD 22
  show: (P -> (Q or R)) -> ((P -> Q) or R)
    P -> (Q or R) :AS
    show: not not ((not P or Q) or R)
      not ((not P or Q) or R) :AS
      not (not P or Q) and not R :D-DMA 27
      not (not P or Q) :S 28
      not not P and not Q :D-DMA 29
      not not P :S 30
      P :DN 31
      Q or R :MP 32,25
      not Q :S 30
      R :MTP 33,34
      not R :S 28
    :ID 35,36
    (not P or Q) or R :DN 26
    show: not not ((P -> Q) or R)
       not ((P -> Q) or R) :AS
       not (P -> Q) and not R :D-DMA 40
       not (P -> Q) :S 41
       not R :S 41
       not P or Q :MTP 43,38
       P -> Q :D-MII 44
    :ID 42,45
    (P -> Q) or R :DN 39
  :CD 47
  ((P -> Q) or R) <-> (P -> (Q or R)) :CB 24,2
:DD 49
```

### Answer 2

```
show: ((P -> Q) v R) <-> (P -> (Q v R))
  show:  ((P -> Q) v R) -> (P -> (Q v R))
    (P -> Q) v R :AS
    show: P -> (Q v R)
      P :AS
      show: R -> (Q v R)
        R :AS
        Q v R :ADD 7
      :CD 8
      show: (P -> Q) -> Q v R
        P -> Q :AS
        Q :MP 5,11
        Q v R :ADD 12
      :CD 13
      Q v R :D-HD 3,6,10
    :CD 15
  :CD 4
  show: (P -> (Q v R)) -> ((P -> Q) v R)
    P -> (Q v R) :AS
    not P v (Q v R) :D-MI 19
    (not P v Q) v R :D-COMMOR 20
    show: not P v Q -> (P -> Q)
      not P v Q :AS
      P -> Q :D-MII 23
    :CD 24
    (P -> Q) v R :D-ORCOND 22,21
  :CD 26
  ((P -> Q) v R) <-> (P -> (Q v R)) :CB 2,18
:DD 28
```

## Ex. 14.10

```
(P ↔ Q), (P ↔ R) ⊢ (P ↔ (Q ∨ R)) ✓
```

```
show: P <-> Q or R
  P <-> Q :PR
  P <-> R :PR
  P -> Q :BC 2
  P -> R :BC 3
  Q -> P :BC 2
  R -> P :BC 3
  show: P -> Q or R
    P :AS
    Q :MP 4,9
    Q or R :ADD 10
  :CD 11
  show: Q or R -> P
    Q or R :AS
    show: not not P
      not P :AS
      not Q :MT 6,16
      R :MTP 14,17
      not R :MT 7,16
    :ID 18,19
    P :DN 15
  :CD 21
  P <-> Q or R :CB 8,13
:DD 23
```

## Chapter 12

## Ex. 16.1

```
∀x(F(x) ∧ G(x)) ⊢ F(c) ✓
```

```
show: F(c)
  Ax(F(x) ^  G(x)) :PR
  F(c) ^ G(c) :UI 2
  F(c) :S 3
:DD 4
```

## Ex. 16.2

```
∀xF(x), (F(c) → G(c)) ⊢ G(c) ✓
```

```
show: G(c)
  Ax F(x) :PR
  F(c) -> G(c) :PR
  F(c) :UI 2
  G(c) :MP 3,4
:DD 5
```

## Ex. 16.3

```
∀xF(x), ((F(b) ∧ F(c)) → G(c)) ⊢ ∃xG(x) ✓
```

```
show: Ex G(x)
  Ax F(x) :PR
  (F(b) ^ F(c)) -> G(c) :PR
  F(b) :UI 2
  F(c) :UI 2
  F(b) ^ F(c) :ADJ 4,5
  G(c) :MP 3,6
  Ex G(x) :EG 7
:DD 8
```

## Ex. 16.4

```
∀x∀y(F(x) → G(y)), F(c) ⊢ G(d) ✓
```

```
show: G(d)
  AxAy (F(x) -> G(y)) :PR
  F(c) :PR
  Ay (F(c) -> G(y)) :UI 2
  F(c) -> G(d) :UI 4
  G(d) :MP 3,5
:DD 6
```

## Ex. 16.5

```
∀x∀y(F(x) ↔ G(y)), F(c) ⊢ F(d) ✓
```

```
show: F(d)
  AxAy(F(x) <-> G(y)) :PR
  F(c) :PR
  Ay(F(c) <-> G(y)) :UI 2
  F(c) <-> G(d) :UI 4
  F(c) -> G(d) :BC 5
  Ay(F(d) <-> G(y)) :UI 2
  F(d) <-> G(d) :UI 7
  G(d) -> F(d) :BC 8
  G(d) :MP 3,6
  F(d) :MP 9,10
:DD 11
```

## Ex. 17.1

```
∀x(F(x) → G(x)), ∀xF(x) ⊢ ∀xG(x) ✓
```

```
show: AxG(x)
  Ax(F(x) -> G(x)) :PR
  AxF(x) :PR
  F(a) -> G(a) :UI 2
  F(a) :UI 3
  G(a) :MP 4,5
:UD 6
```

## Ex. 17.2

```
∀x(F(x) → G(x)), ∀x(G(x) → H(x)) ⊢ ∀x(F(x) → H(x)) ✓
```

```
show: ∀x(F(x) → H(x))
  ∀x(F(x) → G(x)) :PR
  ∀x(G(x) → H(x)) :PR
  F(c) -> G(c) :UI 2
  G(c) -> H(c) :UI 3
  F(c) -> H(c) :D-HS 4,5
:UD 6
```

## Ex. 17.3

```
∀x(G(x) ∧ G(c)) ⊢ ∀xG(x) ✓
```

```
show: ∀xG(x)
  ∀x(G(x) ∧ G(c)) :PR
  G(a) ^ G(c) :UI 2
  G(a) :S 3
:UD 4
```
## Ex. 17.4

```
∀x¬F(x), F(d) ⊢ ¬∀xF(x) ✓
```

```
show: ¬∀xF(x)
  ∀x¬F(x) :PR
  F(d) :PR
  ~F(a) :UI 2
  show: ~Ax(F(x))
    AxF(x) :AS
    F(a) :UI 6
  :ID 4,7
:DD 5
```

## Ex. 17.5

```
¬∃xF(x) ⊢ ∀x¬F(x) ✓
```

```
show: ∀x¬F(x)
  ¬∃xF(x) :PR
  show: ~F(c)
    F(c) :AS
    ExF(x) :EG 4
  :ID 2,5
:UD 3
```

## Ex. 17.6

```
∃x(F(x) ∧ G(a)) ⊢ G(a) ✓
```

```
show: G(a)
  ∃x(F(x) ∧ G(a)) :PR
  show: G(a)
    F(c) ^ G(a) :AS
    G(a) :S 4
  :ED 2,4,5
:DD 3
```

## Ex. 17.7

```
∀x(F(x) → G(x)), ∃xF(x) ⊢ ∃xG(x) ✓
```

```
show: ∃xG(x)
  ∀x(F(x) → G(x)) :PR
  ∃xF(x) :PR
  show: ExG(x)
    F(a) :AS
    F(a) -> G(a) :UI 2
    G(a) :MP 5,6
    ExG(x) :EG 7
  :ED 3,5,8
:DD 4
```

## Ex. 17.8

```
∀x(F(x) → G(x)), ∃x(F(x) ∧ H(x)) ⊢ ∃x(G(x) ∧ H(x)) ✓
```

```
show: ∃x(G(x) ∧ H(x))
  ∀x(F(x) → G(x)) :PR
  ∃x(F(x) ∧ H(x)) :PR
  show: Ex(G(x) ^ H(x))
    F(a) ^ H(a) :AS
    F(a) :S 5
    F(a) -> G(a) :UI 2
    G(a) :MP 6,7
    H(a) :S 5
    G(a) ^ H(a) :ADJ 8,9
    Ex(G(x) ^ H(x)) :EG 10
  :ED 11, 5,3
:DD 4
```

## Ex. 17.9

```
∀x(F(x) → G(x)), ¬∃x(F(x) ∧ G(x)) ⊢ ¬∃xF(x) ✓
```

```
show: ¬∃xF(x)
  ∀x(F(x) → G(x)) :PR
  ¬∃x(F(x) ∧ G(x)) :PR
  F(a) -> G(a) :UI 2
  show: ~ExF(x)
    ExF(x) :AS
    show: Ex(F(x) ^ G(x))
      F(a) :AS
      G(a) :MP 8,4
      F(a) ^ G(a) :ADJ 8,9
      Ex(F(x) ^ G(x)) :EG 10
    :ED 6,8,11
  :ID 3,7
:DD 5
```

## Ex. 17.10

```
∃x¬F(x) ⊢ ¬∀xF(x) ✓
```

```
show: ¬∀xF(x)
  ∃x¬F(x) :PR
  show: ~AxF(x)
    ~F(a) :AS
     show: ~AxF(x)
       Ax(F(x)) :AS
       F(a) :UI 6
     :ID 7,4
  :ED 2,4,5
:DD 3
```

# Appendix: Practice Problems

## Ex. 0.1

```
∀x(F(x) → G(x)), ∃x(H(x) ∧ ¬G(x)) ⊢ ∃x(H(x) ∧ ¬F(x)) ✓
```

```
show: ∃x(H(x) ∧ ¬F(x))
  ∀x(F(x) → G(x)) :PR
  ∃x(H(x) ∧ ¬G(x)):PR
  F(a) -> G(a) :UI 2
  show: Ex(H(x) ^ ~F(x))
    H(a) ^ ~G(a) :AS
    ~G(a) :S 6
    ~F(a) :MT 4,7
    H(a) :S 6
    H(a) ^ ~F(a) :ADJ 9,8
    Ex(H(x) ^ ~F(x)) :EG 10
  :ED 3,6,11
:DD 5
```

## Ex. 0.2

```
∃x(F(x) ∧ ¬G(x)), ∀x(F(x) → H(x)) ⊢ ∃x(H(x) ∧ ¬G(x)) ✓
```

```
show: ∃x(H(x) ∧ ¬G(x))
  ∃x(F(x) ∧ ¬G(x)) :PR
  ∀x(F(x) → H(x)) :PR
  F(a) -> H(a) :UI 3
  show: Ex(H(x) ^ ~G(x))
    F(a) ^ ~G(a) :AS
    H(a) ^ ~G(a) :D-ANDCOND 6,4
    Ex(H(x) ^ ~G(x)) :EG 7
  :ED 2,6,8
:DD 5
```

## Ex. 0.3

```
∀x(F(x) → G(x)), ¬∃x(G(x) ∧ H(x)) ⊢ ¬∃x(H(x) ∧ F(x)) ✓
```

```
show: ¬∃x(H(x) ∧ F(x))
  ∀x(F(x) → G(x)) :PR
  ¬∃x(G(x) ∧ H(x)) :PR
  Ax(~(G(x) ^ H(x))) :D-EQ 3
  F(a) -> G(a) :UI 2
  ~(G(a) ^ H(a)) :UI 4
  ~G(a) v ~H(a) :D-DMC 6
  ~G(a) -> ~F(a) :D-CP 5
  ~F(a) v ~H(a) :D-ORCOND 7,8
  ~H(a) v ~F(a) :D-CDIS 9
  ~(H(a) ^ F(a)) :D-DMCC 10
  show: ~Ex(H(x) ^ F(x))
    Ex(H(x) ^ F(x)) :AS
    show: ~Ex(H(x) ^ F(x))
      H(a) ^ F(a) :AS
      ~Ex(H(x) ^F(x)) :D-EFQ 11,15
    :ED 13,15,16
  :ID 13,14
:DD 12
```

## Ex. 0.4

```
∀x(H(x) → F(x)), ¬∃x(F(x) ∧ G(x)) ⊢ ¬∃x(H(x) ∧ G(x)) ✓
```

```
show: ¬∃x(H(x) ∧ G(x))
   ∀x(H(x) → F(x)) :PR
   ¬∃x(F(x) ∧ G(x)) :PR
   H(a) -> F(a) :UI 2
   ~F(a) -> ~H(a) :D-CP 4
   show: ~Ex(H(x) ^ G(x))
     Ex(H(x) ^ G(x)) :AS
     show: ~Ex(H(x) ^ G(x))
       H(a) ^ G(a) :AS
       H(a) :S 9
       F(a) :MP 10,4
       G(a) :S 9
       F(a) ^ G(a) :ADJ 11,12
       Ex(F(x) ^ G(x)) :EG 13
       ~Ex(H(x) ^ G(x)) :D-EFQ 14,3
     :ED 7,9,15
   :ID 7,8
:DD 6
```

## Ex. 0.5

```
¬∃x(F(x) ∧ G(x)), ∃x(H(x) ∧ F(x)) ⊢ ∃x(H(x) ∧ ¬G(x)) ✓
```

```
show: ∃x(H(x) ∧ ¬G(x))
  ¬∃x(F(x) ∧ G(x)) :PR
  ∃x(H(x) ∧ F(x)) :PR
  show: Ex(H(x) ^ ~G(x))
    H(a) ^ F(a) :AS
    Ax(~(F(x) ^ G(x))) :D-EQ 2
    ~(F(a) ^ G(a)) :UI 6
    ~F(a) v ~G(a) :D-DMC 7
    F(a) :S 5
    ~~F(a) :DN 9
    ~G(a) :MTP 10,8
    H(a) :S 5
    H(a) ^ ~G(a) :ADJ 11,12
    Ex(H(x) ^ ~G(x)) :EG 13
  :ED 3,5,14
:DD 4
```

## Ex. 0.6

```
⊤ ⊢ (∀x(F(x) ∧ G(x)) ↔ (∀xF(x) ∧ ∀xG(x))) ✓
```

```
show: ∀x(F(x) ∧ G(x)) ↔ (∀xF(x) ∧ ∀xG(x))
  show: ∀x(F(x) ∧ G(x)) -> (∀xF(x) ∧ ∀xG(x))
     ∀x(F(x) ∧ G(x)) :AS
     F(a) ^ G(a) :UI 3
     show: AxF(x)
       F(a) :S 4
     :UD 6
     show: AxG(x)
       G(a) :S 4
     :UD 9
     AxF(x) ^ AxG(x) :ADJ 5,8
  :CD 11
  show: (∀xF(x) ∧ ∀xG(x)) -> ∀x(F(x) ∧ G(x))
     ∀xF(x) ∧ ∀xG(x) :AS
     AxF(x) :S 14
     AxG(x) :S 14
     show: Ax(F(x) ^ G(x))
       F(a) :UI 15
       G(a) :UI 16
       F(a) ^ G(a) :ADJ 18,19
     :UD 20
  :CD 17
  ∀x(F(x) ∧ G(x)) ↔ (∀xF(x) ∧ ∀xG(x)) :CB 2,13
:DD 23
```

## Ex. 0.7

```
⊤ ⊢ (∃x(F(x) ∨ G(x)) ↔ (∃xF(x) ∨ ∃xG(x))) ✓
```

```
show: ∃x(F(x) ∨ G(x)) ↔ (∃xF(x) ∨ ∃xG(x))
  show: ∃x(F(x) ∨ G(x)) -> (∃xF(x) ∨ ∃xG(x))
    ∃x(F(x) ∨ G(x)) :AS
    show: ~~(ExF(x) v ExG(x))
      ~(ExF(x) v ExG(x)) :AS
      ~ExF(x) ^ ~ExG(x) :D-DMA 5
      ~ExF(x) :S 6
      ~ExG(x) :S 6
      Ax~F(x) :D-EQ 7
      Ax~G(x) :D-EQ 8
      ~F(a) :UI 9
      ~G(a) :UI 10
      show: ExF(x) v ExG(x)
        F(a) v G(a) :AS
        F(a) :MTP 14,12
        ExF(x) v ExG(x) :D-EFQ 11,15
      :ED 16,14,3
    :ID 5,13
    ExF(x) v ExG(x) :DN 4
  :CD 19
  show: (∃xF(x) ∨ ∃xG(x)) -> ∃x(F(x) ∨ G(x))
    ∃xF(x) ∨ ∃xG(x) :AS
    show: ~~Ex(F(x) v G(x))
      ~Ex(F(x) v G(x)) :AS
      Ax~(F(x) v G(x)) :D-EQ 24
      ~(F(a) v G(a)) :UI 25
      ~F(a) ^ ~G(a) :D-DMA 26
      ~G(a) :S 27
      ~F(a) :S 27
      show: ~ExG(x)
        ExG(x) :AS
        show: ~ExG(x)
          G(a) :AS
          ~ExG(x) :D-EFQ 28,33
        :ED 31,33,34
      :ID 31,32
      ExF(x) :MTP 22,30
      show: Ex(F(x) v G(x))
        F(a) :AS
        F(a) v G(a) :ADD 39
        Ex(F(x) v G(x)) :EG 40
      :ED 37,39,41
    :ID 24,38
    Ex(F(x) v G(x)) :DN 23
  :CD 44
:CB 2,21
```

## Ex. 0.8

```
(∀xF(x) ∨ ∀xG(x)) ⊢ ∀x(F(x) ∨ G(x)) ✓
```

```
show: Ax(F(x) v G(x))
   ∀xF(x) ∨ ∀xG(x) :PR
   show: AxF(x) -> Ax(F(x) v G(x))
     AxF(x) :AS
     show: Ax(F(x) v G(x))
       F(a) :UI 4
       F(a) v G(a) :ADD 6
     :UD 7
   :CD 5
   show: AxG(x) -> Ax(F(x) v G(x))
     AxG(x) :AS
     show: Ax(F(x) v G(x))
       G(a) :UI 11
       F(a) v G(a) :ADD 13
     :UD 14
   :CD 12
   Ax(F(x) v G(x)) :D-HD 2,3,10
:DD 17
```

## Ex. 0.9

```
∃x(F(x) ∧ G(x)) ⊢ (∃xF(x) ∧ ∃xG(x)) ✓
```

```
show: ∃xF(x) ∧ ∃xG(x)
  ∃x(F(x) ∧ G(x)) :PR
  show: ExF(x) ^ ExG(x)
    F(a) ^ G(a) :AS
    F(a) :S 4
    G(a) :S 4
    ExF(x) :EG 5
    ExG(x) :EG 6
    ExF(x) ^ ExG(x) :ADJ 7,8
  :ED 2,4,9
:DD 3
```

## Ex. 0.10

```
∀x(F(x) ↔ G(x)) ⊢ (∀xF(x) ↔ ∀xG(x)) ✓
```

```
show: ∀xF(x) ↔ ∀xG(x)
  ∀x(F(x) ↔ G(x)) :PR
  F(a) <-> G(a) :UI 2
  F(a) -> G(a) :BC 3
  G(a) -> F(a) :BC 3
  show: AxF(x) <-> AxG(x)
    show: AxF(x) -> AxG(x)
      AxF(x) :AS
      show: AxG(x)
        F(a) :UI 8 
        G(a) :MP 10,4
      :UD 11
    :CD 9
    show: AxG(x) -> AxF(x)
      AxG(x) :AS
      show: AxF(x)
        G(a) :UI 15
        F(a) :MP 17,5
      :UD 18
    :CD 16
    AxF(x) <-> AxG(x) :CB 7,14
  :DD 21
:DD 6
```

## Ex. 0.11

```
(∃xF(x) → ∃xG(x)) ⊢ ∃x(F(x) → G(x)) ✓
```

```
show: ∃x(F(x) → G(x))
  ∃xF(x) → ∃xG(x) :PR
  show: ~~Ex(F(x) -> G(x))
    ~Ex(F(x) -> G(x)) :AS
    ~ExF(x) v ExG(x) :D-MI 2
    show: ~ExF(x) -> Ex(F(x) -> G(x))
      ~ExF(x) :AS
      Ax~F(x) :D-EQ 7
      ~F(a) :UI 8
      F(a) -> G(a) :D-MCN 9
      Ex(F(x) -> G(x)) :EG 10
    :CD 11
    show: ExG(x) -> Ex(F(x) -> G(x))
      ExG(x) :AS
      show: Ex(F(x) -> G(x))
        G(a) :AS
        F(a) -> G(a) :D-MCP 16
        Ex(F(x) -> G(x)) :EG 17
      :ED 14,16,18
    :CD 15
    Ex(F(x) -> G(x)) :D-HD 5,6,13
  :ID 4,21
  Ex(F(x) -> G(x)) :DN 3
:DD 23
```
