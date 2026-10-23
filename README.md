# MikroTik Backup — pagini pentru Google OAuth

Fișiere statice pentru contul GitHub `petru-csokany`, repository `mikrotik-backup`.
Acest pachet conține doar paginile informative. Nu configurează și nu rulează backup-uri.

## Publicare pe GitHub Pages

1. Dezarhivează pachetul ZIP.
2. Deschide https://github.com/new, alege owner `petru-csokany`, numele `mikrotik-backup` și vizibilitatea **Public**. Bifează **Add a README file**, apoi **Create repository**. Dacă repository-ul există deja, folosește-l fără a suprascrie fișiere care nu țin de acest proiect.
3. În repository: **Add file → Upload files**. Încarcă `index.html`, `privacy.html`, `terms.html`, `styles.css` și acest `README.md` direct la rădăcina repository-ului. Nu încărca arhiva ZIP și nici un folder care conține aceste fișiere. Confirmă cu **Commit changes**, în branch-ul `main`.
4. Deschide **Settings → Pages**. La **Build and deployment → Source**, selectează **Deploy from a branch**. Alege branch-ul **main**, folderul **/(root)**, apoi **Save**.
5. Așteaptă finalizarea publicării. Deschide adresele de mai jos într-o fereastră privată și verifică toate cele trei pagini. Dacă apar erori 404, verifică publicarea în **Actions** și amplasarea fișierelor în rădăcină. Nu completa Google cu adrese nefuncționale.

## Google Auth Platform → Branding

După ce paginile sunt publicate și accesibile fără autentificare, adaugă mai întâi în **Authorized domains → Add domain**:

`petru-csokany.github.io`

Apoi completează:

| Câmp | Valoare |
| --- | --- |
| Application home page | https://petru-csokany.github.io/mikrotik-backup/ |
| Application privacy policy link | https://petru-csokany.github.io/mikrotik-backup/privacy.html |
| Application terms of service link | https://petru-csokany.github.io/mikrotik-backup/terms.html |

Păstrează numele **MikroTik Backup** și adresele de e-mail completate în Google Cloud. Apasă **Save**, apoi revino la **Audience → Publish app**. Publicarea aplicației OAuth și verificarea brandingului sunt operații diferite. Paginile nu garantează aprobarea Google; dacă Google solicită verificarea proprietății domeniului sau afișează altă eroare, trebuie rezolvată acea cerință înainte de a continua.

În **Data Access**, păstrează numai:

`https://www.googleapis.com/auth/drive.file`

Pentru rclone este necesar propriul client OAuth de tip **Desktop app**. Nu publica Client Secret, token-uri sau `rclone.conf` în repository. În rclone folosește scope-ul `drive.file`, în acord cu paginile publicate.

## Ce trebuie verificat înainte de publicare

- Paginile descriu fluxul convenit: backup-uri `.backup` criptate cu parolă de RouterOS înainte de upload, Google Drive prin rclone, utilizare personală.
- Politica se aplică acestui flux, nu întregului dispozitiv sau oricărei configurații rclone posibile. Orice schimbare a permisiunilor ori utilizării datelor trebuie reflectată în pagini.
- Repository-ul public nu trebuie să conțină backup-uri, exporturi de router, parole, chei, token-uri ori configurația rclone.
- Contactul public este profilul GitHub; adresa Gmail din Google Cloud nu a fost inclusă în paginile publice.

## Documentație

- GitHub Pages: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- Google OAuth Branding: https://support.google.com/cloud/answer/15549049?hl=en
- Permisiuni Google Drive: https://developers.google.com/workspace/drive/api/guides/api-specific-auth
- rclone Google Drive: https://rclone.org/drive/#making-your-own-client-id

Pregătit la 23 octombrie 2026. Niciun site nu este publicat doar prin descărcarea acestui pachet.
