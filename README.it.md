# Buy Decision Tool

[English](README.md) · **Italiano** · [Français](README.fr.md)

👉 **[Guida rapida: installazione e uso in 2 minuti](GUIDE.it.md)**

Un unico file HTML che ti aiuta a decidere **cosa comprare prima**. Combina cinque tecniche note in un'unica classifica:

| Tecnica | Cosa fa qui |
|---|---|
| **Matrice decisionale pesata** | Dai a ogni articolo un voto da 1 a 10 su criteri che scegli e pesi tu. Prezzo e costo per utilizzo sono votati in automatico. |
| **MoSCoW** | Must / Should / Could / Won't have. Moltiplica il punteggio; i "Won't have" sono esclusi. |
| **Matrice di Eisenhower** | Urgente × importante. Moltiplica il punteggio e colloca ogni articolo in uno dei quattro quadranti. |
| **Costo per utilizzo** | Prezzo ÷ (utilizzi al mese × durata prevista in mesi). |
| **Regola dell'attesa** | Gli articoli aspettano qualche giorno (o settimana, sopra una soglia di prezzo) prima di poter essere consigliati. Filtra gli acquisti d'impulso. |

> Non è uno strumento per gestire un budget: se metti un articolo in lista è perché te lo puoi permettere. Serve solo a capire se e quando comprarlo.

In più:

- **Pacchetti**: collega gli articoli da comprare insieme. Un pacchetto viene classificato e consigliato come un unico acquisto.
- **Valore e convenienza**: una matrice a quattro settori (Affare, Investimento, Sfizio, Da evitare) che unisce tutti i criteri in due assi: i voti manuali danno il valore, prezzo e costo per utilizzo danno la convenienza.
- **Note** per ogni articolo (link, modelli, negozi, dubbi).
- **Stato** di ogni articolo: *Comprato* e *Non serve più* lo spostano in un archivio (fuori dalla classifica); *Rimandato di N giorni o mesi* lo toglie dalla classifica fino a quella data e lo mostra fra i *Rimandati* nei risultati.
- **Descrizioni** sotto ogni campo e impostazione, che puoi nascondere quando le conosci. Le impostazioni sono raggruppate in sotto-schede: valuta, regola dell'attesa, criteri, dati e backup, come funziona.
- **Lingue**: italiano, inglese, francese. La pagina segue la lingua del browser e ha un selettore.
- **Valute**: EUR, USD, GBP, CHF, CAD, AUD, JPY.
- **Backup**: scarica i dati in JSON e reimportali ovunque.

## Usalo dove preferisci

Non ci sono server né account. I dati restano dove apri la pagina.

1. **Sul tuo computer.** Scarica [`buy-decision-tool.html`](buy-decision-tool.html) e aprilo con qualsiasi browser (Safari, Chrome, Firefox, Edge). I dati sono salvati nella memoria locale di quel browser.
2. **Sul tuo sito o hosting.** È un file statico: mettilo su qualsiasi hosting statico (il tuo GitHub Pages, Netlify, un NAS, una intranet). I dati di ogni visitatore restano nel suo browser.
3. **Nel tuo account claude.ai.** Chiedi a Claude di pubblicare `buy-decision-tool.html` come artifact con la capability `db` (e `downloads` per i backup). La pagina riconosce claude.ai da sola e salva nel database di quell'artifact invece che nel browser, così ritrovi la stessa lista su ogni dispositivo in cui hai fatto l'accesso.

La pagina carica due font da Google Fonts. Se non sono disponibili (per esempio offline), usa i font di sistema e funziona comunque.

## I tuoi dati

- **Modalità browser** (opzioni 1 e 2): i dati stanno nel `localStorage` del browser per quella pagina. Se cancelli i dati dei siti, usi una finestra privata o cambi browser, riparti da una lista vuota. Usa spesso **Scarica backup** e **Importa JSON** per ripristinare.
- **Modalità claude.ai** (opzione 3): i dati stanno nel database del tuo artifact, privati finché non condividi l'artifact.
- Il file di backup è JSON semplice: puoi leggerlo, tenerlo nel tuo cloud o spostarlo da una modalità all'altra.

La pagina mostra un promemoria quando l'ultimo backup ha più di 8 giorni.

## Come si calcola il punteggio

```
punteggio finale = punteggio matrice pesata × fattore MoSCoW × fattore Eisenhower
```

- Matrice pesata: media dei voti 1–10, pesata con i pesi dei criteri. I criteri automatici danno 10 all'articolo più conveniente e 1 al più caro (lineare in mezzo).
- MoSCoW: Must ×1, Should ×0,75, Could ×0,5, Won't = escluso.
- Eisenhower: urgente e importante ×1,2, solo importante ×1, solo urgente ×0,8, nessuno dei due ×0,6.
- Regola dell'attesa: un articolo ancora in attesa resta in classifica ma non viene consigliato. Gli altri sono **Pronti**: il primo della classifica è il prossimo acquisto consigliato.

Ognuno dei tre metodi (matrice, MoSCoW, Eisenhower) si può disattivare in **Impostazioni → Metodi di classifica**, dove trovi anche il link alla pagina Wikipedia di ciascuno. Con tutti e tre disattivati, la classifica segue solo il prezzo.

Tutto è JavaScript semplice dentro il file HTML: puoi leggerlo e modificarlo.

## Disclaimer

È uno strumento di supporto, non una consulenza. I risultati dipendono solo da ciò che inserisci, possono essere sbagliati e la decisione finale è tua. Vedi [DISCLAIMER.md](DISCLAIMER.md#italiano).

## Licenza

[MIT](LICENSE) © 2026 Rolando Chioda
