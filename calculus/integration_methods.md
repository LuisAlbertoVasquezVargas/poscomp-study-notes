# Integration Methods

TODO(luisvasquez): Add derivation and explanation of the `uv` (integration by parts) formula.

\[
\int u \, dv = uv - \int v \, du
\]

📺 [YouTube – Integration by Parts](https://www.youtube.com/watch?v=2I-_SV8cwsw)

---

## Suggested Structure

### Derivation

Start from the product rule:

\[
\frac{d}{dx}(uv) = u \frac{dv}{dx} + v \frac{du}{dx}
\]

Integrate both sides:

\[
\int \frac{d}{dx}(uv)\,dx = \int u \, dv + \int v \, du
\]

Rewriting:

\[
uv = \int u \, dv + \int v \, du \Rightarrow \int u \, dv = uv - \int v \, du
\]

---

### Examples

- \(\int x e^x dx\)
- \(\int \ln(x) dx\)
- \(\int x \cos(x) dx\)
