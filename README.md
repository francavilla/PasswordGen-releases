# PasswordGen: eseguibili

Qui si pubblicano le **release** di PasswordGen, un generatore di password casuali, sicure e facili da ricordare (parole italiane, sillabe, caratteri casuali), con storico cifrato, promemoria del cambio password e sincronizzazione facoltativa su Google Drive.

- **Windows**: scaricare `PasswordGen-Desktop-vX.Y.Z.zip` dalla [pagina delle release](../../releases), estrarlo e avviare `PasswordGen.exe` (Windows 10/11 con .NET Framework 4.8).
- **Android**: scaricare `PasswordGen-Android-vX.Y.Z.apk` (Android 7.0 o successivo, telefono ARM a 64 bit) e installarlo, consentendo l'installazione da origini sconosciute.

Le note di ogni release riportano l'impronta **SHA-256** del file: verificarla con `Get-FileHash -Algorithm SHA256 <file>` (PowerShell) o `sha256sum <file>` (Linux).

La cartella `updates/` contiene i piccoli file `desktop.json` e `android.json` con la versione corrente: li legge l'avviso di nuova versione dell'app (facoltativo, spento di base). Li scrive il workflow di release: non modificarli a mano.

I sorgenti sono in un repository privato.
