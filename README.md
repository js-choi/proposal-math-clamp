# `Math.clamp` for JavaScript
ECMAScript Stage 0 Proposal. J. S. Choi, 2021.

**This proposal has been superseded by the
[new Math.clamp proposal](https://github.com/tc39/proposal-math-clamp)**
by Oliver Medhurst (@canadahonk) and Richie Bendall (@richienb).

<details>
<summary>Old explainer</summary>

## Rationale
Clamping is a frequent mathematical function in any programming language
for its usefulness in normalizing numeric values to be within specified ranges.
Even the ECMAScript specification itself uses it in several locations.
A number-clamping function would be useful for many developers.

Clamping is present in many other languages’ standard libraries, including
those of C++, C#, Lua, and OpenGL.

Memoization is useful and common. We therefore propose exploring the addition
of a memoization API to the JavaScript language.

If this proposal is approved for Stage 1, then we would explore various
directions for the API’s design. We would also assemble as many real-world use
cases as possible and shape our design to fulfill them.

## Description
`Math.clamp` would be a function that accepts three Numbers: `x`, `minX`, and
`maxX`. The first Number is the main input, and the other two Numbers form an
inclusive range:

* It returns `x` if it is between `minX` and `maxX` inclusive.
* It returns `minX` if `x < minX`.
* It returns `maxX` if `maxX < x`.
* It returns a `NaN` if any argument is a `NaN`.
* It throws a TypeError if any argument is not a numeric value.

For example, to clamp an integer `x` to be an unsigned 8-bit integer,
we would write `Math.clamp(x, 0, 255)`.

(The precedent in C++, C#, Lua, and OpenGL all seems to have the interval
limits always be inclusive on both sides.)

</details>
