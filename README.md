# Which positive dyadic filters can hide a frequency?

For positive $a,b$, the additional multiplier $a+b2^s$ vanishes at a point of the open critical strip exactly when $b<a<2b$. Of the 91 coprime pairs $1\le a,b\le12$, exactly 22 have such a zero.

Here $D_\Lambda(y)=2y\log2-\sum_n\Lambda(n)W(n/y)$, with $\Lambda$ the von Mangoldt function and $W$ the dyadic tent.

For real $y>0$, set

$$
 W(t)=
 \begin{cases}
 2(1-1/t) & 1<t\le2,\\
 4/t-1 & 2<t<4,\\
 0 & \text{otherwise},
 \end{cases}
 \qquad
 P(y)=\sum_{y<p<4y}(\log p)W(p/y).
$$



Take the prime-power deficits $aD_\Lambda(y)+bD_\Lambda(2y)$ with positive coprime integers $a,b\le12$. Their prime weights remain nonnegative. On the zero side the extra factor is $a+b2^s$. Its root has modulus $a/b$ in the variable $2^s$, so a frequency in the open strip disappears exactly when $b<a<2b$. In that case the missing frequencies are

$$
 s=\log_2(a/b)+i\,(2j+1)\pi/\log2,\quad j\in\mathbb Z.
$$

Among the 91 pairs, 22 have an interior zero of the multiplier, two have a boundary zero, and 67 have the extra root strictly outside. A blind frequency identifies where this method could hide a pole. Whether zeta has a zero at that frequency is a separate question. In the three-scale construction, canceling the constant and linear parts forces the polynomial in the dilation variable to be a multiple of $(z-1)(z-2)$. The coefficients are therefore unique up to scale. [Exact enumeration and arithmetic comparison](verify.py)

## Verification

The classification follows by taking the modulus and argument of $2^s=-a/b$. The finite count uses integer comparisons. Possible cancellation of a zeta pole at a particular frequency would additionally require a zeta zero there.

The recorded run used Python 3.9.6 on arm64 macOS. The verifier requires Python 3.9 or later and uses only the standard library.

```sh
bash verify-release.sh
```

The command checks the release manifest, reruns the arithmetic, and compares its output with the recorded result.

[Recorded verification output](evidence/check.txt) · [SHA-256 manifest](SHA256SUMS) · [Tagged publication](https://github.com/leecrossley/dyadic-filter-zeros/releases/tag/v1.0.0)
