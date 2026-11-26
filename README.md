<p align="center">
  <a href="https://ag.tavardt.com/it/">
    <img src="https://ag.tavardt.com/img/tavardt-banner.png" alt="TAVARDT" width="1024" />
  </a>
</p>

# Ispettore di Meta Tag e Open Graph

[![Ispettore Meta Tag](https://img.shields.io/badge/TAVARDT-Meta%20Tag-5b3cf5.svg)](https://tools.tavardt.com/it/analisi-meta-tag-seo/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Il **TAVARDT Ispettore di Meta Tag e Open Graph** fornisce verifica automatizzata dei metadati HTML, delle direttive del protocollo Open Graph, dei link canonici e dell'anteprima SERP in Italia.

***

## Architettura dei Metadati e Matrice Diagnostica

I motori di ricerca e le reti social utilizzano i metadati di intestazione per indicizzare i contenuti e mostrare schede visive di anteprima. Metadati errati o mancanti determinano cali di posizionamento organico e una riduzione della percentuale di clic.

Questo strumento diagnostico analizza i limiti di lunghezza del titolo, della meta description, dei tag Open Graph e del link canonico partendo da 100 punti base senza dipendenze esterne.

Il motore di scansione esamina i tag di intestazione HTML verificandone la conformità rispetto ai requisiti dei motori e delle piattaforme social:

<table>
  <thead>
    <tr>
      <th>Tag di Intestazione</th><th>Criterio di Validazione</th><th>Deduzione</th><th>Impatto SEO e Social Network</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Elemento Title</strong></td><td>Richiede la presenza di <code>&lt;title&gt;</code>. Lunghezza ideale: 30-60 caratteri. Penalizzato se &lt;20 caratteri (-10 pts) o &gt;70 caratteri (-10 pts). Assente: -25 pts.</td><td>Fino a -25 pts</td><td>Fattore principale di indicizzazione e titolo cliccabile nella SERP.</td>
    </tr>
    <tr>
      <td><strong>Meta Description</strong></td><td>Richiede <code>&lt;meta name='description'&gt;</code>. Lunghezza ideale: 120-160 caratteri. Penalizzato se &lt;70 caratteri (-10 pts) o &gt;175 caratteri (-10 pts). Assente: -20 pts.</td><td>Fino a -20 pts</td><td>Sommario visualizzato determinante per il tasso di clic organico.</td>
    </tr>
    <tr>
      <td><strong>Protocollo Open Graph</strong></td><td>Verifica cinque tag fondamentali: <code>og:title</code>, <code>og:description</code>, <code>og:image</code>, <code>og:url</code> e <code>og:type</code>.</td><td>-5 pts per tag mancante (Max -25 pts)</td><td>Genera schede visive accattivanti su LinkedIn, Facebook, Slack e chat.</td>
    </tr>
    <tr>
      <td><strong>Direttiva Canonica</strong></td><td>Richiede la presenza di <code>&lt;link rel='canonical'&gt;</code> con URL di destinazione assoluto.</td><td>-10 pts</td><td>Previene problemi di contenuti duplicati e consolida i segnali di autorità.</td>
    </tr>
    <tr>
      <td><strong>Errore di Connessione</strong></td><td>Scadenza del timeout di richiesta o errore di negoziazione TLS/HTTP.</td><td>Punteggio azzerato a 0</td><td>Inaccessibilità dell'host che impedisce l'ispezione dei metadati HTML.</td>
    </tr>
  </tbody>
</table>

### Scala di Qualità e Livelli di Stato

Lo strumento definisce un punteggio complessivo di qualità classificando lo stato della pagina:

* <strong>85 a 100 (OPTIMAL)</strong>: Metadati perfettamente ottimizzati; title, description, canonico e Open Graph pienamente conformi.
* <strong>65 a 84 (ACCEPTABLE)</strong>: Configurazione funzionale con lievi scostamenti di lunghezza o assenza parziale di tag social.
* <strong>0 a 64 (DEFICIENT)</strong>: Gravi omissioni nei tag principali con impatto negativo su indicizzazione e condivisione.

***

## Installazione ed Esecuzione

Sviluppato unicamente con moduli standard di Python 3.8+, senza dipendenze esterne.

```bash
git clone https://github.com/TAVARDT-Italia/meta-tags-inspector-it.git
cd meta-tags-inspector-it
```

### Esecuzione Standard CLI

```bash
python meta_inspector.py esempio.it
```

### Output Strutturato per Pipeline in JSON

```bash
python meta_inspector.py esempio.it -j
```

### Configurazione di Timeout Personalizzato

```bash
python meta_inspector.py esempio.it -j -t 15
```

***

## Linee Guida Nazionali e Integrità Web in Italia

Il controllo della corretta struttura dei metadati rispetta i criteri di affidabilità e trasparenza digitale raccomandati in ambito nazionale. Metadati accurati difendono l'identità del marchio da manipolazioni nelle anteprime social.

Si raccomanda l'inserimento di audit automatici di metadati nei processi continui di rilascio applicativo per garantire una presenza digitale coerente.

***

## Domande Frequenti Tecniche

### Qual è la lunghezza ottimale in caratteri per il tag title?

L'ispettore consiglia una lunghezza compresa tra 30 e 60 caratteri. Un titolo inferiore a 20 caratteri subisce una deduzione di 10 punti per debolezza semantica, mentre oltre i 70 caratteri perde 10 punti per rischio di troncamento nei risultati di ricerca. L'assenza completa comporta 25 punti di penalità.

### In che modo viene valutata la meta description?

Il motore verifica che il testo sia compreso tra 120 e 160 caratteri. Se inferiore a 70 o superiore a 175 caratteri si applica una penalità di 10 punti. L'assenza totale della meta description comporta la deduzione di 20 punti.

### Quali proprietà Open Graph sono obbligatorie per la conformità?

Vengono richiesti cinque tag essenziali: <code>og:title</code>, <code>og:description</code>, <code>og:image</code>, <code>og:url</code> e <code>og:type</code>. Ciascun tag assente comporta una deduzione di 5 punti, fino a un massimo di 25 punti.

### Perché il tag canonical è determinante per la SEO tecnica?

L'elemento <code>&lt;link rel="canonical"&gt;</code> specifica ai motori di ricerca l'URL di riferimento ufficiale, consolidando i segnali di ranking e prevenendo problemi di contenuti duplicati. La sua mancanza comporta una detrazione di 10 punti.

### Cosa indicano i livelli di punteggio e le classi di stato?

Un punteggio tra 85 e 100 corrisponde allo stato OPTIMAL. Da 65 a 84 punti indica uno stato ACCEPTABLE con margini di miglioramento, mentre al di sotto di 65 punti lo stato è DEFICIENT, imponendo un intervento tempestivo sui tag prioritari.

***

## Supporto Tecnico e Consulenza Digitale

Per verifiche approfondite di SEO tecnica, ottimizzazione dei metadati e standard di conformità web, contattare gli esperti di **TAVARDT**.

***

## Link Utili

* **Portale Aziendale:** https://ag.tavardt.com/it/
* **Suite di Diagnostica:** https://tools.tavardt.com/it/
* **Contatto Tecnico:** https://ag.tavardt.com/it/contatto/

***

### Licenza
Rilasciato sotto licenza MIT.

***

© 2026 TAVARDT. Tutti i diritti riservati.
