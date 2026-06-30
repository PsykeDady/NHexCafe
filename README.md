# NHexCafe

Repository minimale che contiene un archivio in formato JSON con migliaia di pillole tech in italiano. Il file `techPills.json` e' pensato come fonte dati riutilizzabile per bot, applicazioni web, newsletter tecniche, quiz, oppure per piccoli esperimenti di NLP su contenuti IT.

## Contenuto del dataset

- `techPills`: array di oggetti, ognuno rappresenta una singola pillola autonoma.
- Ogni elemento contiene:
  - `text`: frase sintetica con l'informazione.
  - `tags`: lista di parole chiave per classificazione e filtro.
- Il formato e' JSON UTF-8 e privilegia pillole brevi, indipendenti e leggibili in pochi secondi.

## Come usare il file

1. Copia il file nella tua applicazione o aggiungi questo repository come submodule/subtree.
2. Carica il JSON con il linguaggio che preferisci. Esempio in Node.js:

```js
import { readFileSync } from 'node:fs';

const file = readFileSync('techPills.json', 'utf8');
const { techPills } = JSON.parse(file);

// Estrai una pillola casuale
const randomPill = techPills[Math.floor(Math.random() * techPills.length)];
console.log(randomPill.text, randomPill.tags);
```

3. (Opzionale) Filtra per tag per mostrare solo contenuti su un tema specifico.

## Note qualitative

- Le pillole sono progettate per essere comprensibili anche fuori dal contesto originale.
- Dove possibile, i duplicati concettuali vengono rimossi per mantenere una base pulita.
- Prima di usare il dataset in produzione, valida il tono e il livello tecnico rispetto al tuo pubblico.
