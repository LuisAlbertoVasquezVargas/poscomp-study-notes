<!-- File: calculus/integration_methods.md -->

# Integration Methods

TODO(luisvasquez): Add derivation and explanation of the integration by parts formula.

📺 [YouTube – Integration by Parts](https://www.youtube.com/watch?v=2I-_SV8cwsw)

---

## Integration by Parts

The integration by parts formula is:

$$
\int u\,dv = uv - \int v\,du
$$

📝 **Mnemonic (Spanish):** *“una vaca vestida de uniforme”*  

This helps remember the sequence:

$$
u\,dv \;\to\; uv - \int v\,du
$$

---

## Suggested Structure

### Derivation

Start from the product rule:

$$
\frac{d}{dx}(uv) = u\,\frac{dv}{dx} + v\,\frac{du}{dx}
$$

Now integrate both sides:

$$
\int \frac{d}{dx}(uv)\,dx = \int u\,dv + \int v\,du
$$

So:

$$
uv = \int u\,dv + \int v\,du \;\Rightarrow\; \int u\,dv = uv - \int v\,du
$$

---

### Examples

- $\int x\,e^x\,dx$
- $\int \ln(x)\,dx$
- $\int x\,\cos(x)\,dx$
