# Angular Academy - Fintech (backend)

> Backend da utilizzare durante lo sviluppo dell'applicazione Angular "Fintech".

## Feature

- Rotte specifiche per l'applicazione Fintech
- Registrazione
- Autenticazione (opzionale) via Cookie

## Get started

Assicurati che sia presente un file `.env` nella root del progetto, con questi campi:

```
PORT=...
APP_SECRET=...
FRONTEND_URL=...
```

- `PORT` specifica la porta di esecuzione del server (default `3000`)
- `APP_SECRET` è un valore segreto, usato per la codifica delle sessioni
- `FRONTEND_URL` è l'url del front-end (default `http://localhost:4200`) per CORS

### Se non ti serve autenticazione
Avvia il server con il comando `npm run dev`. Utilizza questo comando fino a che non avrai implementato un meccanismo di autenticazione sul front-end.

### Se ti serve autenticazione
Avvia il server con il comando `npm run dev:auth`.


## Come autenticarsi

Indicazioni generali:

0. Assicurati di inviare le richieste con `withCredentials` impostato a `true`.
1. Inizialmente fai una richiesta `GET` per un _CSRF Token_ all'endpoint `/csrf-token`.
2. Prendi il Cookie `XSRF-TOKEN`.
3. Da ora in poi, ogni richiesta non-GET dovrà includere questo token nell'Header `X-XSRF-Token`.
4. Registra un nuovo utente all'endpoint `/register`.
5. Accedi dall'endpoint `/login`.
6. Prendi le informazioni dell'utente dall'endpoint `/me`.
7. Logout all'endpoint `/logout`.

_Nota: Molti framework si occupano dei punti 2-3 in autonomia (es. Angular)_