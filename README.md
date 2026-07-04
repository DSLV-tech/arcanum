# ⛤ ARCANUM — Esoteric Engine v2.0
### DSLV.TECH

Un calcolatore esoterico interattivo che combina numerologia pitagorica, tarocchi e mappatura cosmica. Inserisci nome e data di nascita per ottenere la tua decrittazione vibrazionale completa.

---

## ✦ Funzionalità

- **Matrice Numerologica** — Life Path, Expression, Soul Urge, Personality con descrizioni approfondite e una sintesi "In chiaro" in linguaggio semplice
- **Identità Cosmica** — Segno zodiacale occidentale, zodiaco cinese, chakra dominante, pietra portafortuna
- **Carta del Giorno** — Arcano estratto algoritmicamente in base alla data corrente
- **Cicli Personali** — Anno, Mese e Giorno personale calcolati sulla data odierna: cambiano nel tempo, un motivo per tornare ogni giorno
- **3 Sigilli Divinatori** — Tre carte dei Tarocchi (Passato / Presente / Futuro) con flip animato
- **La Lettura** — sintesi interpretativa che collega i quattro numeri tra loro (direzione vs manifestazione, anima vs personalità) e intreccia i tre Arcani in un'unica narrazione Passato→Presente→Futuro (appare dopo aver girato le carte)
- **Analisi di Compatibilità** — Score vibrazionale tra due soggetti (opzionale)
- **Il Codice degli Arcani** — la Sequenza Sacra 0→XXI con la chiave esoterica di ogni arcano (tradizione egizio-occulta) e la **frase iniziatica** che le lega in un unico racconto del cammino dell'anima. Ogni arcano estratto e la Carta del Giorno hanno anche una sintesi "In chiaro"
- **Multilingua IT / EN** — selettore in alto a destra, rilevamento automatico della lingua del browser e memoria della scelta
- **Doppio tema** — ⛤ *Occult / Dark* e ❦ *Manoscritto Alchemico*, commutabili a runtime e persistenti
- **Glossario Esoterico** — sezione collassabile che spiega in linguaggio semplice i termini della lettura (Sentiero di Vita, Espressione, Arcani, Chakra…), IT/EN
- **Condivisione** — genera un permalink che riapre la stessa lettura (nome, data, lingua ed eventuale compatibilità); usa il menu di condivisione nativo su mobile o copia il link negli appunti

## ✧ Note tecniche

- Zero dipendenze, single-file. Font caricati in modo non bloccante.
- Animazioni ottimizzate: particelle scalate sul viewport, pausa automatica a tab nascosta, rispetto di `prefers-reduced-motion`.
- Accessibilità di livello **WCAG AAA** come standard: contrasto testo ≥7:1 su entrambi i temi, target touch ≥44px, interlinea ≥1.5, heading semantici, label collegate, navigazione da tastiera dei tarocchi, `aria-live` sul loader, `prefers-reduced-motion`, validazione degli input.
- Meta tag SEO / Open Graph inclusi.
- **PWA installabile e offline**: `manifest.webmanifest` + service worker (`sw.js`) e icone. Una volta pubblicata su HTTPS, l'app può essere "aggiunta alla schermata Home" e funziona senza connessione.

---

## ⚙️ Utilizzo

Apri `index.html` direttamente nel browser per l'uso locale. Per le funzioni PWA (installazione, offline) e la condivisione con permalink servono un contesto HTTPS: pubblica la cartella su GitHub Pages (o qualsiasi hosting statico).

### File del progetto

- `index.html` — l'app completa
- `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` — supporto PWA
- `ACCESSIBILITA-AAA.md` — checklist per l'audit di accessibilità

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
