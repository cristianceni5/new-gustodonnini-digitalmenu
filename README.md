# Gustò Donnini — Menu & Ordini (web)

Web app statica (solo HTML/CSS/JS) per consultare il menu, filtrare/cercare i piatti e preparare una comanda da inviare su WhatsApp.

## Come si usa

- Apri `index.html` in un browser (oppure servi la cartella con un server statico).
- Il menu viene caricato da `menu.js` (variabile globale `window.menu` / `menu`).
- Aggiungi articoli cliccando sulle card; l’ordine si aggiorna nella sezione “Il tuo ordine”.
- Per alcune categorie/elementi è disponibile una personalizzazione via modal (con quantità e totale aggiornati).
- L’invio ordine usa i pulsanti WhatsApp già configurati nella pagina.

## Struttura progetto

- `index.html` — pagina principale (menu + ordine + modal).
- `styles.css` — stile UI.
- `script.js` — logica interfaccia (filtri, carrello, modal, totale, ecc.).
- `menu.js` — dati del menu.
- `img/` — immagini e icone.
- `old/` — versione precedente (tenuta come riferimento/backup).

## Cosa cambia rispetto alla vecchia versione

La vecchia versione è conservata in `old/`. La versione attuale (root) introduce:

- **UI/UX più stabile su mobile**: layout “ordine” vincolato allo schermo, senza overflow orizzontale; testo gestito con wrap + clamp.
- **Quantità nel modal**: pulsanti `+/-` affiancati all’input, con gestione corretta di `min/max` e disabilitazione ai limiti.
- **Scroll più prevedibile**: al refresh la pagina riparte sempre dall’alto (niente “ripresa” in basso).
- **Scrollbar meno invasive**: scrollbar nascoste in modal e pannelli che scrollano, mantenendo lo scroll attivo.
- **Percorsi asset più robusti**: riferimenti a `img/icone%20e%20loghi/...` (spazi URL-encoded) per evitare rotture in alcuni deploy/server.
- **Pulizia repo**: aggiunto `.gitignore` per escludere backup/temporanei (`.local_backup/`, `.tmp_*`, ecc.).

## Note

- Il progetto non richiede build né dipendenze.
- Se pubblichi su hosting/static server, assicurati che tutti gli asset in `img/` vengano serviti (attenzione ai path con spazi).

