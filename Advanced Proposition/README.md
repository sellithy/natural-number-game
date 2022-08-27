## 1

```
split,
exacts [p, q],
```

## 2
```
intro pAq,
cases pAq with p q,
split,
exacts [q, p],
```

## 3
```
intros pAq qAr,
split,
cases pAq with p q,
exact p,

cases qAr with q r,
exact r,
```

## 4
```
intros pIFFq qIFFr,

cases pIFFq with pIq qIp,
cases qIFFr with qIr rIq,
split,

intro p,
exact qIr(pIq(p)),

intro r,
exact qIp(rIq(r)),
```

## 5
```
intros pIFFq qIFFr,
split,

intro p,
exact qIFFr.1(pIFFq.1(p)),

intro r,
exact pIFFq.2(qIFFr.2(r)),
```

## 6
```
intro q,
right,
exact q,
```

## 7
```
intro pOq,
cases pOq with p q,

right,
exact p,

left,
exact q,
```

## 8
```
split,

-- 1
intro pANDqORr,
cc,
-- end 1

-- 2
intro h,
cases h with p q,

cc,

cc,
-- end 2
```

## 9
```
intro pANDNOTp,
exfalso,
rw not_iff_imp_false at pANDNOTp,

cases pANDNOTp with p pIfalse,
apply pIfalse,
exact p,
```

## 10
```
by_cases p : P; by_cases q : Q,
repeat {cc},
```
