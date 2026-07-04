# ⛤ ARCANUM — Esoteric Engine v2.0
### DSLV.TECH

Un calcolatore esoterico interattivo che combina numerologia pitagorica, tarocchi e mappatura cosmica. Inserisci nome e data di nascita per ottenere la tua decrittazione vibrazionale completa.

---

## ✦ Funzionalità

- **Matrice Numerologica** — Life Path, Expression, Soul Urge, Personality con descrizioni approfondite
- **Identità Cosmica** — Segno zodiacale occidentale, zodiaco cinese, chakra dominante, pietra portafortuna
- **Carta del Giorno** — Arcano estratto algoritmicamente in base alla data corrente
- **3 Sigilli Divinatori** — Tre carte dei Tarocchi (Passato / Presente / Futuro) con flip animato
- **Analisi di Compatibilità** — Score vibrazionale tra due soggetti (opzionale)
- **Il Codice degli Arcani** — la Sequenza Sacra 0→XXI con la chiave esoterica di ogni arcano (tradizione egizio-occulta): I = *La Volontà*, II = *La Scienza occulta*… La chiave appare anche sulle carte estratte e sulla Carta del Giorno
- **Multilingua IT / EN** — selettore in alto a destra, rilevamento automatico della lingua del browser e memoria della scelta
- **Doppio tema** — ⛤ *Occult / Dark* e ❦ *Manoscritto Alchemico*, commutabili a runtime e persistenti
- **Condivisione** — genera un permalink che riapre la stessa lettura (nome, data, lingua ed eventuale compatibilità); usa il menu di condivisione nativo su mobile o copia il link negli appunti

## ✧ Note tecniche

- Zero dipendenze, single-file. Font caricati in modo non bloccante.
- Animazioni ottimizzate: particelle scalate sul viewport, pausa automatica a tab nascosta, rispetto di `prefers-reduced-motion`.
- Accessibilità di livello **WCAG AAA** come standard: contrasto testo ≥7:1 su entrambi i temi, target touch ≥44px, interlinea ≥1.5, heading semantici, label collegate, navigazione da tastiera dei tarocchi, `aria-live` sul loader, `prefers-reduced-motion`, validazione degli input.
- Meta tag SEO / Open Graph inclusi.

---

## ⚙️ Utilizzo

Nessuna dipendenza. Apri `Arcanum.html` direttamente nel browser.

---

## 🌐 Attivare GitHub Pages

1. **Crea un repository** su [github.com](https://github.com) — es. `arcanum`
2. **Carica i file** — trascina `Arcanum.html` e `README.md` nel repository
3. **Vai su Settings** → sezione **Pages** (nel menu laterale sinistro)
4. **Branch** → seleziona `main` e cartella `/ (root)` → clicca **Save**
5. Dopo circa 1 minuto il sito sarà live su:

```
https://<tuo-username>.github.io/arcanum/
```

> **Nota:** rinomina `Arcanum.html` in `index.html` prima di caricare — GitHub Pages serve automaticamente `index.html` come pagina principale.

---

## 🛠 Stack

`HTML5` · `CSS3` · `Vanilla JS` · `Canvas API` · `Google Fonts`

---

*DSLV.TECH — All rights reserved*
