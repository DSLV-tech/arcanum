# ARCANUM — Checklist Audit WCAG 2.2 Livello AAA

Riferimento per validare formalmente l'accessibilità di `index.html`.
Legenda stato:

- ✅ **Implementato/verificato in codice** — soddisfatto e controllabile staticamente
- 🔍 **Da verificare manualmente** — richiede test con strumenti reali (screen reader, zoom, tastiera)
- ➖ **Non applicabile** — il criterio non riguarda contenuti presenti nell'app

I criteri AAA includono per definizione i requisiti A e AA sottostanti: qui sono elencati insieme, con enfasi sui delta AAA.

---

## 1. Percepibile

| Criterio | Livello | Stato | Note ARCANUM |
|---|---|---|---|
| 1.1.1 Contenuti non testuali | A | ✅ | Canvas decorativi con `aria-hidden`; pulsanti-icona (⛤ ❦) con `aria-label`; glifi/emoji accompagnati da testo. |
| 1.3.1 Info e relazioni | A | ✅ | `label` collegate agli input, sezioni come heading (`role=heading aria-level=2`), liste semantiche (`<ol>`). |
| 1.3.2 Sequenza significativa | A | ✅ | Ordine DOM = ordine di lettura logico. |
| 1.3.5 Identificare lo scopo dell'input | AA | ✅ | `autocomplete="name"`, `type="date"`. |
| 1.4.1 Uso del colore | A | ✅ | Stati (dritta/rovesciata, errori) hanno testo/etichetta, non solo colore. |
| 1.4.3 Contrasto minimo | AA | ✅ | Superato dal 1.4.6. |
| 1.4.5 Immagini di testo | AA | ✅ | Nessuna immagine di testo. |
| **1.4.6 Contrasto avanzato (7:1)** | **AAA** | ✅ | Verificato numericamente ≥7:1 (testo piccolo) e ≥4.5:1 (grande) su entrambi i temi e su tutte le superfici (pagina, card, fronte carta, pannello). |
| 1.4.8 Presentazione visiva | AAA | 🔍 | Interlinea ≥1.5 ✅, niente giustificato ✅, temi selezionabili dall'utente ✅. **Da verificare**: larghezza blocchi di testo ≤80 caratteri e assenza di scroll orizzontale a testo ingrandito. |
| **1.4.9 Immagini di testo (nessuna eccezione)** | **AAA** | ✅ | Tutto testo reale. |
| 1.4.10 Reflow | AA | 🔍 | Layout fluido con breakpoint 900/560/380px. **Da verificare** a 320px CSS / zoom 400%. |
| 1.4.11 Contrasto non testuale | AA | ✅ | Bordi input/pulsanti e stati focus con contrasto adeguato. |
| 1.4.12 Spaziatura del testo | AA | 🔍 | Nessuna altezza fissa che tronchi il testo nei blocchi discorsivi. **Da verificare** applicando il bookmarklet "text spacing". |
| 1.4.13 Contenuto su hover/focus | AA | ✅ | Le spiegazioni dei numeri sono visibili anche senza hover (mobile) e con `:focus-within`. |

---

## 2. Utilizzabile

| Criterio | Livello | Stato | Note ARCANUM |
|---|---|---|---|
| 2.1.1 Tastiera | A | ✅ | Tutti i controlli sono `<button>`/`<input>` nativi; le carte dei tarocchi hanno `role=button`, `tabindex=0` e gestione `Enter`/`Spazio`. |
| **2.1.3 Tastiera (nessuna eccezione)** | **AAA** | 🔍 | **Da verificare** con navigazione sola tastiera dell'intero flusso (form → risultati → flip carte → sequenza → share). |
| 2.2.1 Tempi regolabili | A | ✅ | Nessun limite di tempo sull'interazione utente. |
| **2.2.3 Nessun limite di tempo** | **AAA** | ✅ | Il loader è puramente decorativo (~2,5s), non un timeout imposto all'utente. |
| 2.3.1 Tre lampeggiamenti (soglia) | A | ✅ | Animazioni lente (glitch 8s, flicker 6s, scanline 5s): nessun flash. |
| **2.3.2 Tre lampeggiamenti (nessuna eccezione)** | **AAA** | ✅ | Nessuna animazione supera 3 flash/secondo; `prefers-reduced-motion` annulla comunque le animazioni. |
| 2.4.3 Ordine del focus | A | ✅ | Ordine naturale del DOM. |
| 2.4.7 Focus visibile | AA | ✅ | `:focus-visible` con outline oro 2px + offset. |
| **2.4.8 Posizione** | **AAA** | ➖ | Single-page, nessuna gerarchia di navigazione. |
| **2.4.9 Scopo del link (solo link)** | **AAA** | ✅ | Nessun link ambiguo; i pulsanti hanno etichette esplicite. |
| **2.4.10 Intestazioni di sezione** | **AAA** | ✅ | Ogni sezione dei risultati ha un heading di livello 2. |
| 2.4.11 Focus non oscurato (min) | AA (2.2) | 🔍 | **Da verificare** che header/toast non coprano l'elemento con focus. |
| **2.4.12 Focus non oscurato (avanzato)** | **AAA** (2.2) | 🔍 | Come sopra, criterio più stringente. |
| **2.4.13 Aspetto del focus** | **AAA** (2.2) | ✅🔍 | Outline **3px** oro + offset 3px + alone di contrasto (scuro/chiaro per tema). Resta da **confermare la misura** con color picker. |
| 2.5.3 Etichetta nel nome | A | ✅ | Nome accessibile dei pulsanti coerente col testo visibile. |
| 2.5.8 Dimensione target (minimo) | AA (2.2) | ✅ | Superato dal 2.5.5. |
| **2.5.5 Dimensione target (avanzato, 44px)** | **AAA** | ✅ | Pulsanti lingua/tema ≥44×44px; pulsanti azione ampiamente sopra. |

---

## 3. Comprensibile

| Criterio | Livello | Stato | Note ARCANUM |
|---|---|---|---|
| 3.1.1 Lingua della pagina | A | ✅ | `<html lang>` impostato e aggiornato dinamicamente (it/en). |
| 3.1.2 Lingua di parti | AA | 🔍 | I nomi degli arcani in una lingua diversa dall'interfaccia potrebbero richiedere `lang` locale. **Valutare** (impatto basso). |
| **3.1.3 Parole inusuali** | **AAA** | ✅ | **Glossario Esoterico** integrato: spiega in linguaggio semplice Sentiero di Vita, Espressione, Arcani, Chakra, Sinergia, ecc. (IT/EN). |
| **3.1.4 Abbreviazioni** | **AAA** | ➖ | Nessuna abbreviazione critica; "Master" e sigle spiegate nel glossario. |
| **3.1.5 Livello di lettura** | **AAA** | ✅🔍 | Il glossario fornisce una definizione in linguaggio piano per ogni termine tecnico. I testi divinatori restano evocativi per scelta editoriale. |
| 3.2.1 Al focus | A | ✅ | Nessun cambiamento di contesto al focus. |
| 3.2.2 All'input | A | ✅ | Nessun submit automatico digitando. |
| 3.2.3 Navigazione coerente | AA | ✅ | Header/controlli coerenti. |
| 3.2.4 Identificazione coerente | AA | ✅ | Icone/etichette coerenti tra le sezioni. |
| **3.2.5 Cambiamento su richiesta** | **AAA** | ✅ | L'unica lettura automatica (link condiviso) è avviata dall'utente aprendo l'URL. |
| 3.3.1 Identificazione errori | A | ✅ | Messaggi d'errore testuali per nome/data. |
| 3.3.2 Etichette o istruzioni | A | ✅ | Ogni campo ha label e placeholder. |
| 3.3.3 Suggerimento sull'errore | AA | ✅ | I messaggi indicano come correggere ("min. 2 lettere", "non futura"). |
| 3.3.5 Aiuto | AAA | 🔍 | **Valutare** testo d'aiuto contestuale (attualmente solo label descrittive). |
| 3.3.6 Prevenzione errori (tutti) | AAA | 🔍 | Dati non finanziari/legali; input reversibile via reset. **Verificare** se sufficiente. |

---

## 4. Robusto

| Criterio | Livello | Stato | Note ARCANUM |
|---|---|---|---|
| 4.1.2 Nome, ruolo, valore | A | ✅ | `aria-pressed` sugli switch, `aria-expanded`/`aria-controls` su toggle compat e sequenza, ruoli corretti. |
| 4.1.3 Messaggi di stato | AA | ✅ | Loader e toast con `role=status` + `aria-live=polite`. |

**Supporto extra:** blocco `@media (forced-colors: active)` — in modalità Alto contrasto/colori forzati i livelli decorativi (canvas, fog, scanline, vignette) vengono nascosti e ogni superficie/controllo mantiene un bordo visibile con i colori di sistema; il focus usa `Highlight`.

---

## Procedure di verifica manuale (i punti 🔍)

1. **Sola tastiera** (2.1.3, 2.4.11–2.4.13)
   Scollega il mouse. Con `Tab`/`Shift+Tab`/`Enter`/`Spazio` completa: compilazione form → invio → scorrimento risultati → flip delle tre carte → apertura "Sequenza Sacra" → "Condividi". Verifica che il focus sia sempre visibile e mai coperto da header o toast.

2. **Screen reader** (1.3.1, 2.4.10, 4.1.2, 4.1.3)
   - Windows: **NVDA** + Firefox. macOS: **VoiceOver** + Safari.
   - Naviga per intestazioni (`H`): devono comparire le 6 sezioni di livello 2.
   - Verifica che gli switch annuncino stato premuto/non premuto e che loader e toast vengano annunciati.

3. **Zoom & reflow** (1.4.8, 1.4.10)
   Browser al **200%** e **400%** (o viewport 320px CSS): nessuno scroll orizzontale, nessun testo tagliato o sovrapposto, controlli ancora raggiungibili.

4. **Text spacing** (1.4.12)
   Applica il bookmarklet ufficiale (line-height 1.5, spaziatura parole/lettere/paragrafi maggiorata): nulla deve troncarsi o sovrapporsi.

5. **Contrasto del focus** (2.4.13)
   Con un color picker, misura l'outline oro sul focus contro lo sfondo adiacente in **entrambi i temi**: target ≥3:1 e spessore adeguato.

6. **Movimento ridotto** (2.3.x)
   Attiva "Riduci movimento" nel sistema: canvas fermi su un frame, animazioni disattivate, funzionalità intatte.

7. **Forced colors / Alto contrasto**
   Attiva la modalità colori forzati (Windows High Contrast): verifica che testo e bordi restino percepibili (eventuale aggiunta futura di supporto `forced-colors`).

---

## Già aggiunti in questa iterazione

- ✅ **Glossario esoterico** (3.1.3 / 3.1.5): definizioni in linguaggio semplice per i termini della lettura, IT/EN.
- ✅ **Aspetto del focus rinforzato** (2.4.13): outline 3px + alone di contrasto per tema.
- ✅ **Supporto `forced-colors`** con override dedicati.

## Miglioramenti opzionali residui

- **Sintesi in linguaggio semplice per le descrizioni divinatorie** (3.1.5): una riga "in chiaro" accanto a ogni testo evocativo (oggi coperto dal glossario a livello di termini).
- **`lang` locale** sui nomi in lingua diversa dall'interfaccia (3.1.2) — impatto minimo, dato che i contenuti sono già localizzati.
- **Testo d'aiuto contestuale sul form** (3.3.5).

Questi non sono difetti di codice ma rifiniture editoriali: incidono su testo/contenuto, non sulla struttura, già conforme.
