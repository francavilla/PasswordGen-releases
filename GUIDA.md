# PasswordGen: guida per un nuovo utente

PasswordGen genera password **casuali, sicure e facili da ricordare**, tiene lo **storico** dei cambi e ti ricorda **quando cambiarle**. Esiste per **Windows** e per **Android**.
Funziona subito, senza account e senza collegarsi a niente: la sincronizzazione tra PC e telefono e gli altri servizi online sono **facoltativi e spenti di base**.

## 1. Installare

### Windows (10 o 11)
1. Scarica `PasswordGen-Desktop-vX.Y.Z.zip` dalla [pagina delle release](https://github.com/francavilla/passwordgen-releases/releases/latest) (cerca quella «Desktop»).
2. (Facoltativo) Controlla che il file sia integro: nelle note della release c'è l'impronta **SHA-256**; in PowerShell `Get-FileHash -Algorithm SHA256 .\PasswordGen-Desktop-vX.Y.Z.zip` deve dare lo stesso valore.
3. Estrai lo zip in una cartella tua (per esempio `Documenti\PasswordGen`) e avvia `PasswordGen.exe`. Non c'è nessuna installazione.
4. Se Windows mostra «Windows ha protetto il PC», premi **Ulteriori informazioni → Esegui comunque**: il programma non è firmato digitalmente, per questo compare l'avviso.
   In alternativa, prima di estrarre, clic destro sullo zip → *Proprietà* → spunta **Annulla blocco**.

Serve il .NET Framework 4.8, già presente in Windows 10 (aggiornato) e in Windows 11.

### Android (7.0 o successivo, telefono ARM a 64 bit)
1. Dalla stessa [pagina delle release](https://github.com/francavilla/passwordgen-releases/releases/latest) scarica il file `PasswordGen-Android-vX.Y.Z.apk` (la release «Android»).
2. Aprilo dal telefono. Android chiede di consentire l'installazione da **origini sconosciute** per il browser o il gestore di file che stai usando: consentilo solo per questa installazione.
3. Se hai una versione precedente alla 2.17.0, va **disinstallata** prima (la chiave di firma è cambiata): esporta lo storico dall'app, disinstalla, installa la nuova e reimporta.
   Dalla 2.17.0 in poi gli aggiornamenti si installano normalmente sopra la versione precedente.

## 2. Il primo uso
1. Compaiono alcune **proposte** di password (tasto *Genera nuove proposte* per averne altre).
2. Scegli il **tipo**:
   - *Parole italiane* (consigliata): facile da digitare e ricordare, per esempio `Lampo-Cavallo-Nebbia-Fiume47!`;
   - *Sillabe pronunciabili*: si «leggono» come parole inventate;
   - *Caratteri casuali*: per quando basta copiarla.
3. Imposta le **regole** richieste dal tuo servizio o dall'azienda (lunghezza minima, maiuscole, numeri, caratteri speciali).
4. Premi **Copia** sulla proposta scelta e incollala dove serve: gli appunti si svuotano da soli dopo 30 secondi.
5. Dopo aver cambiato la password sul servizio, premi **Ho cambiato la password**: l'app ti chiede quale proposta hai usato e a quale **titolo** (il «dove la uso», per esempio «Portale HR») va associata.

## 3. Storico, titoli e scadenze
- L'**Storico** conserva le ultime 20 password **per ogni titolo**, con numero e data. Sono mascherate: puoi mostrarle, copiarle o eliminarne una.
- Una nuova password non può essere uguale a una delle ultime 20 dello stesso titolo, e le proposte evitano le varianti di quelle già usate.
- Ogni titolo ha la sua **scadenza**: puoi impostare una durata diversa dalla generale e **regole di generazione proprie** (lunghezza, simboli, caratteri esclusi).
- Un banner in alto (e una notifica su Android, o l'avvio con Windows se lo attivi) ti avvisa quando una password sta per scadere.
- Lo storico è **cifrato** sul tuo dispositivo: solo il tuo account Windows, o il Keystore del tuo telefono, può aprirlo.

## 4. Proteggere l'app
Nelle impostazioni puoi attivare il **blocco dell'app**: all'avvio e dopo il tempo che scegli in secondo piano chiede Windows Hello, l'impronta o il PIN del telefono, oppure un **PIN o una password dell'app**.
Dopo 5 errori scatta un'attesa crescente. Con il blocco attivo la finestra non compare negli screenshot.

## 5. Sincronizzare PC e telefono (facoltativo)
Per avere lo stesso storico e le stesse scadenze su più dispositivi si usa un **file cifrato** (`PasswordGen-sync.pgx`) protetto da una **frase segreta** scelta da te (almeno 8 caratteri).
**Non si può recuperare**: se la dimentichi il file non si apre più. Scrivila in un posto sicuro.

Tre scelte, in *Sincronizzazione e backup → Imposta...*:

| Scelta | Cosa serve | Cosa succede |
|---|---|---|
| **Nessuna sincronizzazione** | niente | L'app resta del tutto locale. Puoi sempre fare un backup con *Esporta* e riportarlo con *Importa*. |
| **Un file** | una cartella che già si sincronizza da sola (Google Drive per desktop, OneDrive, Dropbox...) | Ogni dispositivo legge e scrive quel file. Nessun accesso a Google dall'app. |
| **Il mio Google Drive** | un account Google **tuo** | L'app apre il browser, accedi con il tuo account e consenti l'accesso. Il file viene creato **nel tuo Drive**. |

Cose da sapere sul Drive:
- Ogni persona accede con **il proprio** account: nessuno vede il Drive di un altro, e l'app non ha mai la tua password di Google.
- L'app vede **solo i file che ha creato lei** (non il resto del tuo Drive).
- Per usare lo stesso storico su due dispositivi tuoi, collegali **allo stesso account e con la stessa frase segreta**.
- Se Google dice che l'app non è verificata o rifiuta l'accesso, usa l'opzione **Un file** oppure nessuna sincronizzazione: l'app funziona benissimo anche così.
- Due persone diverse non devono usare lo stesso file né la stessa frase: lo storico è personale.

Per aggiungere un secondo dispositivo: installa l'app, apri *Sincronizzazione e backup → Imposta...*, scegli lo stesso Drive o lo stesso file e inserisci **la stessa frase segreta**.

## 6. Cosa esce dal tuo dispositivo
Solo quello che attivi tu:
- **Sincronizzazione**: il file cifrato, nel Drive o nella cartella che scegli.
- **Controllo delle nuove versioni** (spento di base): legge un piccolo file pubblico con il numero della versione corrente; non invia niente di tuo.
- **Controllo delle password compromesse** (spento di base): dopo «Copia» chiede a *Pwned Passwords* (Have I Been Pwned) se la password è comparsa in violazioni di dati. Si inviano solo i **primi 5 caratteri** dell'impronta SHA-1: né la password né la sua impronta intera escono dal dispositivo.

## 7. Aggiornamenti
Attiva *Controlla all'avvio se esiste una nuova versione* in Impostazioni → Aggiornamenti, oppure premi **Controlla ora**. Quando c'è una novità compare un avviso con **Scarica** (apre la pagina della versione) e **Non ora**.
L'app non scarica né installa niente da sola: scarichi tu il nuovo zip o APK e lo sostituisci.

## 8. Se qualcosa non va
- **Messaggi di errore o salvataggi che non riescono**: in Impostazioni → Aggiornamenti c'è il **registro degli errori** («Mostra il registro» su Windows, «Copia il registro» su Android). Contiene data, punto del programma e messaggio, mai password né frasi segrete: puoi incollarlo in una segnalazione.
- **Ho dimenticato la frase segreta**: non si recupera. Puoi ripartire creando un nuovo file di sincronizzazione (lo storico locale resta sul dispositivo).
- **Il PIN dell'app è sbagliato troppe volte**: aspetta la fine dell'attesa; non c'è modo di aggirarla.
- **L'APK non si installa sopra la vecchia versione**: succede solo passando da una versione precedente alla 2.17.0 (vedi sopra).
