Senso Modules Catalog
Catalogo ufficiale dei moduli installabili tramite il comando:

Codice
php spark senso:install
Questo repository contiene il file modules.json, utilizzato da SensoCore per mostrare i moduli disponibili, verificarne la compatibilità e installarli automaticamente tramite Composer.

📁 Struttura del catalogo
Il file principale è:

Codice
modules.json
Contiene la lista dei moduli disponibili, con metadati utili per l’installer.

Esempio:

json
{
  "version": 1,
  "updated_at": "2026-02-09T22:30:00Z",
  "modules": [
    {
      "name": "elbambolo/senso-auth",
      "title": "SensoAuth",
      "description": "Autenticazione JWT con gestione utenti, gruppi e permessi.",
      "repository": "https://github.com/elbambolo/senso-auth",
      "branch": "dev-main",
      "category": "security",
      "required_core_version": ">=1.0.0"
    }
  ]
}
🧩 Campi supportati
name
Nome del pacchetto Composer.
È quello che l’insteller usa per eseguire:

Codice
composer require <name>:<branch>
title
Nome leggibile del modulo, mostrato nel menu CLI.

description
Breve descrizione funzionale del modulo.

repository
URL del repository GitHub del modulo.

branch
Branch da installare (es. dev-main).

category
Categoria funzionale del modulo.
Categorie consigliate:

security

dashboard

media

analytics

integrations

utilities

required_core_version
Versione minima di SensoCore necessaria per installare il modulo.
Usa sintassi Composer (es. >=1.0.0).

➕ Aggiungere un nuovo modulo al catalogo
Apri modules.json

Aggiungi un nuovo oggetto dentro modules[]

Compila tutti i campi richiesti

Aggiorna updated_at

Commit + push

Esempio:

json
{
  "name": "elbambolo/senso-media",
  "title": "SensoMedia",
  "description": "Gestione file, upload e media library.",
  "repository": "https://github.com/elbambolo/senso-media",
  "branch": "dev-main",
  "category": "media",
  "required_core_version": ">=1.1.0"
}
🔄 Versionamento del catalogo
Il campo version permette a SensoCore di:

invalidare cache locali

gestire aggiornamenti futuri del formato

mantenere retrocompatibilità

Incrementalo solo quando cambi la struttura del file.

🛠 Come viene usato da SensoCore
Il comando:

Codice
php spark senso:install
esegue:

download del file modules.json

parsing dei moduli

verifica compatibilità con SensoCore

menu interattivo

installazione via Composer

migrazioni automatiche

aggiornamento autoload

📬 Contatti
Per aggiungere nuovi moduli o proporre modifiche al catalogo, apri una pull request o contatta l’autore del framework.
