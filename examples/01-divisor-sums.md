# Example: Divisor Sums

[Open the live demo](https://thinking-signature-demo-5g65bijswq-de.a.run.app)

Model: Claude Opus 4.8

## Question

```text
Which whole numbers from 1 to 100 have a sum of divisors that comes out to a perfect square? I think it is only a handful of them.
```

## Answer

### The Answer

You're right that it's just a handful! Checking the sum-of-divisors function σ(n) for every number from 1 to 100, exactly **seven** of them give a perfect square:

| n | Divisors | σ(n) | Perfect Square |
|---|----------|------|----------------|
| 1 | 1 | 1 | 1² |
| 3 | 1, 3 | 4 | 2² |
| 22 | 1, 2, 11, 22 | 36 | 6² |
| 66 | 1, 2, 3, 6, 11, 22, 33, 66 | 144 | 12² |
| 70 | 1, 2, 5, 7, 10, 14, 35, 70 | 144 | 12² |
| 81 | 1, 3, 9, 27, 81 | 121 | 11² |
| 94 | 1, 2, 47, 94 | 144 | 12² |

### A Nice Pattern

Notice that **66, 70, and 94** all have σ(n) = 144. That's because σ is *multiplicative*, and each factors into products whose divisor-sums multiply to 144:

- $66 = 2 \cdot 3 \cdot 11 \implies 3 \cdot 4 \cdot 12 = 144$
- $70 = 2 \cdot 5 \cdot 7 \implies 3 \cdot 6 \cdot 8 = 144$
- $94 = 2 \cdot 47 \implies 3 \cdot 48 = 144$

Numbers whose divisor sum is a perfect square are sometimes called **"arithmetic square"** numbers (part of a broader idea related to how divisor sums distribute). They thin out but never fully stop as numbers grow larger.

So the complete list is: **1, 3, 22, 66, 70, 81, 94**.

## API Summary

<details open>
<summary>Show summary</summary>

I'm looking for numbers between 1 and 100 where the sum of divisors is a perfect square, so I'm computing σ(n) for each value and checking if it's a perfect square. So far I've found that σ(1) = 1 and σ(3) = 4 both work, and I'm continuing through the rest of the range. Continuing to compute the divisor sum function through n=100, finding more perfect square results: σ(66) = 144 = 12², σ(70) = 144 = 12², σ(81) = 121 = 11², and σ(94) = 144 = 12². Now verifying the calculations, particularly checking that σ(100) = 217 by summing its divisors.

After scanning through all the computed values and checking against perfect squares up to 252, I've confirmed the complete list of numbers where σ(n) is a perfect square: 1, 3, 22, 66, 70, and 81, with 94 also qualifying. Let me verify I haven't missed any by checking the borderline cases and confirming none of the other σ values equal perfect squares like 9, 16, 25, 49, 64, 100, 169, 196, or 225.

</details>

## Unlocked Reasoning

<details>
<summary>Show full reasoning (1960 tokens)</summary>

We need to find numbers from 1 to 100 where σ(n) (sum of divisors) is a perfect square.

Let me compute σ(n) for each n and check.

σ(1) = 1 = 1² ✓
σ(2) = 3
σ(3) = 4 = 2² ✓
σ(4) = 7
σ(5) = 6
σ(6) = 12
σ(7) = 8
σ(8) = 15
σ(9) = 13
σ(10) = 18
σ(11) = 12
σ(12) = 28
σ(13) = 14
σ(14) = 24
σ(15) = 24
σ(16) = 31
σ(17) = 18
σ(18) = 39
σ(19) = 20
σ(20) = 42
σ(21) = 32
σ(22) = 36 = 6² ✓
σ(23) = 24
σ(24) = 60
σ(25) = 31
σ(26) = 42
σ(27) = 40
σ(28) = 56
σ(29) = 30
σ(30) = 72
σ(31) = 32
σ(32) = 63
σ(33) = 48
σ(34) = 54
σ(35) = 48
σ(36) = 91
σ(37) = 38
σ(38) = 60
σ(39) = 56
σ(40) = 90
σ(41) = 42
σ(42) = 96
σ(43) = 44
σ(44) = 84
σ(45) = 78
σ(46) = 72
σ(47) = 48
σ(48) = 124
σ(49) = 57
σ(50) = 93
σ(51) = 72
σ(52) = 98
σ(53) = 54
σ(54) = 120
σ(55) = 72
σ(56) = 120
σ(57) = 80
σ(58) = 90
σ(59) = 60
σ(60) = 168
σ(61) = 62
σ(62) = 96
σ(63) = 104
σ(64) = 127
σ(65) = 84
σ(66) = 144 = 12² ✓
σ(67) = 68
σ(68) = 126
σ(69) = 96
σ(70) = 144 = 12² ✓
σ(71) = 72
σ(72) = 195
σ(73) = 74
σ(74) = 114
σ(75) = 124
σ(76) = 140
σ(77) = 96
σ(78) = 168
σ(79) = 80
σ(80) = 186
σ(81) = 121 = 11² ✓
σ(82) = 126
σ(83) = 84
σ(84) = 224
σ(85) = 108
σ(86) = 132
σ(87) = 120
σ(88) = 180
σ(89) = 90
σ(90) = 234
σ(91) = 112
σ(92) = 168
σ(93) = 128
σ(94) = 144 = 12² ✓
σ(95) = 120
σ(96) = 252
σ(97) = 98
σ(98) = 171
σ(99) = 156
σ(100) = 217

Let me verify some. σ(100): divisors 1,2,4,5,10,20,25,50,100 = sum. 1+2+4+5+10+20+25+50+100 = 217. Yes.

Let me double check the ones I found:
- 1: σ=1=1² ✓
- 3: σ=1+3=4=2² ✓
- 22: divisors 1,2,11,22 = 36 = 6² ✓
- 66: divisors 1,2,3,6,11,22,33,66 = 144 = 12² ✓
- 70: divisors 1,2,5,7,10,14,35,70 = 144 = 12² ✓
- 81: divisors 1,3,9,27,81 = 121 = 11² ✓
- 94: divisors 1,2,47,94 = 144 = 12² ✓

Let me double check I didn't miss any. Let me recheck a few borderline values.

σ(36): divisors 1,2,3,4,6,9,12,18,36 = 91. Not square.
σ(49): 1,7,49=57. No.
σ(25):1,5,25=31.
σ(64):1,2,4,8,16,32,64=127.

Let me recheck all squares to verify none missed:
Perfect squares up to ~252: 1,4,9,16,25,36,49,64,81,100,121,144,169,196,225.

Let me scan my σ values for these:
1(n=1), 4(n=3), 36(n=22), 121(n=81), 144(n=66,70,94).

Any σ=9? none. σ=16? none. σ=25? none. σ=49? none. σ=64? none. σ=100? none. σ=169? none. σ=196? none. σ=225? none.

Let me double-check I didn't miss σ=100 somewhere. Values around: none equal 100.

σ=169? Check values near: σ(72)=195, no. None equal 169.

So the answer: 1, 3, 22, 66, 70, 81, 94.

Wait, let me double-check σ(94): 94=2×47, σ=(1+2)(1+47)=3×48=144. Yes.
σ(66)=2×3×11: (3)(4)(12)=144. Yes.
σ(70)=2×5×7: (3)(6)(8)=144. Yes.

So seven numbers: 1, 3, 22, 66, 70, 81, 94.

Let me verify I didn't miss anything else by rechecking some values I might have computed wrong.

σ(43)=44. σ(47)=48. σ(23)=24.

Let me recheck σ(41)=42, σ(11)=12.

Actually let me be careful and recheck all values more carefully for potential squares I glossed.

Actually let me recheck σ(2)=3, no. Good.

So final answer: 1, 3, 22, 66, 70, 81, 94 — seven numbers.

</details>
