# bijections
Tables of constants for various operations mod 2.

See https://mostlymangling.blogspot.com/2018/09/invertible-additions-mod-2.html

The tables describe all {2, 3, 4}-tuples of shifts that result in bijections on 2^w, w = {16, 32, 64}.

Assuming C, `uintw_t` being an unsigned word of w bits:

`shiftinverses-w-RL.txt.bz2` is the table with all pairs RL/LR that will result in a bijection on 2^w:
```
uintw_t f3(uintw_t x, int a, int b) {
  return (x >> a) ^ (x << b);
}
```
`shiftinverses-w-RRL.txt` is the table with all triples RRL/LLR that will result in a bijection on 2^w:
```
uintw_t f5_1(uintw_t x, int a, int b, int c) {
  return (x >> a) ^ (x >> b) ^ (x << c);
}
// Or f5-variant 2:
uintw_t f5_2(uintw_t x, int a, int b, int c) {
  return (x << a) ^ (x << b) ^ (x >> c);
}
```

`shiftinverses-w-RRLL.txt` is the table with all quads RRLL/LLRR that will result in a bijection on 2^w:
```
uintw_t f7_1(uintw_t x, int a, int b, int c, int d) {
  return (x >> a) ^ (x >> b) ^ (x << c) ^ (x << d);
}
// Or f7-variant 2:
uintw_t f7_2(uintw_t x, int a, int b, int c, int d) {
  return (x << a) ^ (x << b) ^ (x >> c) ^ (x >> d);
}
```

`shiftinverses-w-RRRL.txt` is the table with all quads RRRL/LLLR that will result in a bijection on 2^w:
```
uintw_t f8_1(uintw_t x, int a, int b, int c, int d) {
  return (x >> a) ^ (x >> b) ^ (x >> c) ^ (x << d);
}
// Or f8-variant 2:
uintw_t f8_2(uintw_t x, int a, int b, int c, int d) {
  return (x << a) ^ (x << b) ^ (x << c) ^ (x >> d);
}
```
