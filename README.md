# Ispettore di Meta Tag e Open Graph

[![Ispettore Meta Tag](https://img.shields.io/badge/TAVARDT-Meta%20Tag-5b3cf5.svg)](https://tools.tavardt.com/it/analisi-meta-tag-seo/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)

Verifica tecnica dei metadati HTML, analisi della lunghezza di title e meta description, anteprima dei social card e direttive di indicizzazione.

Sviluppato e gestito dalla divisione di ottimizzazione tecnica e dati web di **TAVARDT**.

***

## Funzionalita dell'Audit dei Metadati e Social Card

* **Ispezione di Title e Meta Description**: Analisi della lunghezza ottimale per la corretta visualizzazione nei risultati di ricerca.
* **Protocollo Open Graph**: Verifica strutturale di og:title, og:description, og:image, og:url e og:type.
* **Twitter Cards**: Controllo della formattazione e delle immagini per la condivisione sui canali social.
* **Direttive di Indicizzazione**: Monitoraggio di meta robots (noindex, nofollow) e presenza del link canonical.
* **Indice di Qualita dello Snippet**: Punteggio quantitativo da 0 a 100 con istruzioni pratiche di bonifica.

***

## Installazione ed Esecuzione

Richiede Python 3.8 o superiore senza dipendenze esterne.

```bash
git clone https://github.com/TAVARDT-Italia/meta-tags-inspector-it.git
cd meta-tags-inspector-it
python meta_inspector.py esempio.it
```

Per l'output in formato JSON:

```bash
python meta_inspector.py esempio.it -json
```

***

## Piattaforma di Diagnosi Online

Per simulare e testare in tempo reale i social card e le anteprime di ricerca:

* **Ispettore di Meta Tag Ufficiale**
* **[Portale Aziendale TAVARDT](https://ag.tavardt.com/it/)**

***

## Consulenza in SEO Tecnico e Visibilita Web

Per progetti dedicati di ottimizzazione semantica in conformita con Standard W3C e Buone Pratiche SEO, contattare **TAVARDT**.

***

© 2026 TAVARDT. Tutti i diritti riservati.
