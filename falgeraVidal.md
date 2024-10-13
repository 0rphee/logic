# Ejercicios VI

## I.

### 62.

```
(∀xF(x,b) ∧ ¬∀y(G(y) → H(b,y))) ⊢ ¬(¬∀x¬G(x) → ∀y(F(y,b) → H(b,y)))
```

```
AxF(x,b) ^ -Ay(G(y) -> H(b,y)) :PR
AxAy(H(x,y) -> -H(y,x)) :PR
show: -(-Ax-G(x) -> Ay(F(y,b) -> H(b,y)))
  -Ax-G(x) -> Ay(F(y,b) -> H(b,y)) :AS
  -Ay(G(y) -> H(b,y)) :S 1
  Ey-(G(y) -> H(b,y)) :D-AN 5
  show: -Ey-(G(y) -> H(b,y))
    -(G(a) -> H(b,a)) :AS
    show: --(G(a) ^ -H(b,a))
      -(G(a) ^ -H(b,a)) :AS
      -G(a) v --H(b,a) :D-DMC 10
      show: -G(a) -> (-G(a) v H(b,a))
        -G(a) :AS
        -G(a) v H(b,a) :ADD 13
      :CD 14
      show: --H(b,a) -> (-G(a) v H(b,a))
        --H(b,a) :AS
        H(b,a) :DN 17
        -G(a) v H(b,a) :ADD 18
      :CD 19
      -G(a) v H(b,a) :D-HD 11,12,16
      G(a) -> H(b,a) :D-MII 21
    :ID 8,22
    G(a) ^ -H(b,a) :DN 9
    G(a) :S 24
    --G(a) :DN 25
    Ex--G(x) :EG 26
    -Ax-G(x) :D-NA 27
    Ay(F(y,b) -> H(b,y)) :MP 28,4
    F(a,b) -> H(b,a) :UI 29
    AxF(x,b) :S 1
    F(a,b) :UI 31
    H(b,a) :MP 30,32
    -H(b,a) :S 24
    -Ey-(G(y) -> H(b,y)) :D-EFQ 33,34
  :ED 6,8, 35
:ID 6,7
```
