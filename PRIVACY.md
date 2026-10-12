# PasswordGen: informativa sulla privacy

Ultimo aggiornamento: 12 ottobre 2026

PasswordGen è un'applicazione per Windows e Android che genera password e ne tiene lo storico. **Non esiste un server di PasswordGen**: chi sviluppa l'app non riceve, non raccoglie e non conserva nessun dato degli utenti.
L'app non contiene pubblicità, statistiche d'uso né sistemi di tracciamento.

## Dove stanno i tuoi dati
- Le **impostazioni**, lo **storico delle password** e le **frasi segrete** restano sul tuo dispositivo. Lo storico e le frasi sono cifrati con le protezioni del sistema (DPAPI su Windows, Keystore su Android).
- Le password che copi vengono cancellate dagli appunti dopo 30 secondi.
- Il **registro degli errori** (`passwordgen.log`) resta sul dispositivo e non contiene mai password, frasi segrete né voci dello storico. Lo condividi solo se decidi tu di farlo.

## Cosa esce dal dispositivo (solo se attivi tu la funzione)
Tutte queste funzioni sono **facoltative e spente di base**.

1. **Sincronizzazione con Google Drive.** Accedi con il **tuo** account Google; l'app crea nel tuo Drive il file cifrato `PasswordGen-sync.pgx` e lo aggiorna.
   L'app chiede un solo permesso, `drive.file`: può vedere e modificare **soltanto i file che ha creato lei**, non il resto del tuo Drive. Non vede la password del tuo account Google.
   Il file è cifrato con una frase segreta che conosci solo tu: nemmeno Google o chi sviluppa l'app può leggerne il contenuto. Il token di accesso resta sul dispositivo, cifrato. Puoi revocare l'accesso in qualsiasi momento dalle impostazioni dell'account Google
   (Sicurezza → Accesso di terze parti) o dall'app, disattivando la sincronizzazione.
2. **Sincronizzazione con un file.** Il file cifrato viene scritto nella cartella che scegli (per esempio una cartella già sincronizzata da un altro servizio): la gestione di quel servizio è soggetta alla sua informativa.
3. **Controllo delle nuove versioni.** L'app scarica un piccolo file pubblico con il numero dell'ultima versione (da `raw.githubusercontent.com`, GitHub). Non invia nulla di tuo; come ogni richiesta web, GitHub vede l'indirizzo IP.
4. **Controllo delle password compromesse.** Dopo «Copia», l'app chiede al servizio pubblico *Pwned Passwords* (`api.pwnedpasswords.com`) se la password è comparsa in violazioni di dati. Si usa il metodo «k-anonymity»: si invia solo l'inizio (5 caratteri) dell'impronta SHA-1 della password;
   il confronto con il resto avviene sul tuo dispositivo, quindi né la password né la sua impronta intera escono dal dispositivo.

## Uso dei dati ricevuti dalle API di Google
L'uso e il trasferimento a qualsiasi altra app delle informazioni ricevute dalle API di Google rispetta la [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy), inclusi i requisiti sull'uso limitato (*Limited Use*).
PasswordGen usa l'accesso a Drive solo per leggere e scrivere il file di sincronizzazione che crea, non lo condivide con nessuno e non lo usa per pubblicità o altri scopi.

## Cancellare i tuoi dati
- Disinstallando l'app (o eliminando la cartella `%AppData%\PasswordGen` su Windows) si cancellano le impostazioni e lo storico locali.
- Il file `PasswordGen-sync.pgx` nel tuo Drive si può eliminare dal tuo Drive in qualsiasi momento.
- Per scollegare l'app da Google: account Google → Sicurezza → Accesso di terze parti → PasswordGen → Rimuovi accesso.

## Contatti e modifiche
Per domande su questa informativa apri una segnalazione nel repository [`francavilla/passwordgen-releases`](https://github.com/francavilla/passwordgen-releases/issues) oppure scrivi all'indirizzo di assistenza indicato nella schermata di consenso di Google.
Se l'informativa cambia, la nuova versione sarà pubblicata in questa pagina con la data aggiornata.
