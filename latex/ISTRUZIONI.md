# Template progetto – Software Security e Blockchain (UNIVPM)

Template LaTeX per la relazione del progetto su **certificati di sicurezza e SBOM per gli sviluppatori di software**,
corso di Software Security e Blockchain, Laurea Magistrale in Ingegneria Informatica e dell'Automazione.

## Contenuto della cartella

| File / cartella | Funzione |
|---|---|
| `main.tex` | File principale: pacchetti, stile, ordine dei capitoli. Si compila questo. |
| `metadati.tex` | **Unico file da modificare per il frontespizio**: titolo, corso, 4 studenti con matricola, docente, assistente, anno accademico, repository. |
| `frontespizio.tex` | Grafica del frontespizio (catena di blocchi, scudo, codice a barre di hash). Non serve toccarlo. |
| `capitoli/` | Un file per capitolo (`01_introduzione.tex` … `07_conclusioni.tex`), abstract e appendice con la ripartizione del lavoro. |
| `bibliografia.bib` | Riferimenti bibliografici (BibTeX). |
| `immagini/` | Figure e, facoltativamente, il logo `logo-univpm.png`. |

## Come usarlo

### Su Overleaf (consigliato per lavorare in 4)
1. Crea un nuovo progetto con *Upload Project* e carica lo zip della cartella.
2. Imposta `main.tex` come *Main document* (Menu → Settings).
3. Compilatore: **pdfLaTeX**. Poi *Share* per invitare gli altri tre componenti del gruppo.

### In locale
Servono una distribuzione TeX Live o MiKTeX con i pacchetti `babel-italian`, `biblatex`, `tikz`, `listings`, `lmodern`.
Dalla cartella del progetto:

    latexmk -pdf main.tex

`latexmk` esegue in automatico le passate necessarie (indice, riferimenti, bibliografia).
Per pulire i file temporanei: `latexmk -c`.

## Passi iniziali
1. Apri `metadati.tex` e sostituisci i segnaposto: nomi e matricole dei 4 studenti, `\docente`, `\assistente`, anno accademico, repository (lascia `\repository` vuoto con `\renewcommand{\repository}{}` se non serve).
2. *(Facoltativo)* Copia il logo dell'ateneo in `immagini/logo-univpm.png`: comparirà nella fascia in alto a destra al posto dello scudo.
3. Ricerca i `\todo{...}` (compaiono in rosso nel PDF) e sostituiscili con il testo. Prima della consegna cerca `TODO` in tutti i file: non deve restarne nessuno.

## Scrivere in gruppo
- Assegnate un capitolo per persona: ogni capitolo è un file separato in `capitoli/`, quindi si riducono i conflitti con Git.
- Compilate la ripartizione del lavoro nell'Appendice A (`capitoli/A_ripartizione_lavoro.tex`).
- Se usate Git, aggiungete a `.gitignore`: `*.aux *.log *.out *.toc *.lof *.lot *.lol *.bbl *.blg *.fls *.fdb_latexmk *.bcf *.run.xml`.

## Elementi pronti all'uso

**Citazioni.** Aggiungi la voce in `bibliografia.bib` e cita con `\cite{chiave}`.

**Codice.** Ambiente `lstlisting` con linguaggio Solidity già definito:

    \begin{lstlisting}[language=Solidity, caption={Titolo}, label={lst:nome}]
    ...
    \end{lstlisting}

Per altri linguaggi: `language=Python`, `language=bash`, `language=Java`, ecc. Per file esterni: `\lstinputlisting[language=Solidity]{codice/Contratto.sol}`.

**Figure e tabelle.** Usate `figure`/`table` con `\caption` e `\label`, poi `Figura~\ref{fig:nome}`. L'esempio di architettura in TikZ è nel Capitolo 4.
Per immagini esterne: `\includegraphics[width=0.8\linewidth]{immagini/nome.png}`.

**Comandi personalizzati.**
- `\sbom` → SBOM in maiuscoletto
- `\codice{testo}` → testo a spaziatura fissa
- `\todo{testo}` → promemoria rosso
- `\begin{riquadro}{Titolo} ... \end{riquadro}` → riquadro evidenziato

## Personalizzazioni frequenti
- **Colori**: `navy` e `teal` sono definiti all'inizio di `main.tex`; cambiandoli si aggiorna tutto, frontespizio compreso.
- **Fronte-retro**: sostituisci `oneside` con `twoside` nella `\documentclass`.
- **Interlinea**: modifica `\onehalfspacing` in `main.tex` (usa `\singlespacing` per ridurla).
- **Capitoli in più**: crea il file in `capitoli/` e aggiungi la riga `\input{capitoli/nome.tex}` in `main.tex`.
- **Cambio di lingua**: sostituisci `italian` con `english` nel pacchetto `babel`.

## Problemi comuni
- *`File 'xxx.sty' not found`*: manca un pacchetto nella distribuzione locale; installalo con `tlmgr install xxx` oppure usa Overleaf.
- *Citazioni come `[?]`*: ricompila due volte oppure usa `latexmk`.
- *Caratteri accentati sbagliati*: salva i file in UTF-8.
