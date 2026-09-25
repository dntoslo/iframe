# Test av iframe

Enkel side som viser en Claude-artifact (en kalkulator) i en iframe.

- Siden: `index.html`
- Innholdet i iframen: `kalkulator.html` (kopi av artifacten)
- Original artifact: https://claude.ai/artifact/8ucvmbQXv1xERtdn2a9224
- Publisert: https://dntoslo.github.io/iframe/

## Hvorfor en kopi og ikke lenken direkte?

claude.ai sender `Content-Security-Policy: frame-ancestors 'self'`, så nettleseren
nekter å laste artifact-lenken i en iframe fra et annet domene. Derfor ligger
HTML-en fra artifacten som `kalkulator.html` i repoet, og iframen peker dit.

Artifacten bruker Claude sitt lagrings-runtime (`window.claude`) for historikk og
filopplasting. Det finnes ikke utenfor claude.ai, så kopien faller tilbake til
lagring i minnet: alt fungerer, men ingenting lagres mellom besøk.

Publisert med GitHub Pages fra `main`.
