# GitHub Pages — Einrichtungsschritte

Kurze Anleitung, um die zuvor angelegte GitHub Action (`.github/workflows/pages.yml`) für das Deployment Ihrer statischen Seite zu aktivieren.

1. Repository pushen
   - Stellen Sie sicher, dass Ihr Repository auf GitHub liegt und der Branch `main` vorhanden ist.

2. Workflow prüfen
   - Die Workflow-Datei liegt unter `.github/workflows/pages.yml` und wird bei Push auf `main` ausgeführt.

3. Berechtigungen & Actions
   - Öffnen Sie auf GitHub die Repository-Settings → Actions und erlauben Sie, dass GitHub Actions Workflows für dieses Repository laufen.

4. GitHub Pages-Einstellungen
   - Öffnen Sie Repository → Settings → Pages.
   - Bei der neuen Pages-Experience wählen Sie als Source `GitHub Actions` (die Action `actions/deploy-pages` schreibt das Pages-Artefakt automatisch).

5. Deployment auslösen
   - Committen und pushen Sie Änderungen auf `main`:

```bash
git add .
git commit -m "Trigger GitHub Pages deploy"
git push origin main
```

6. Kontrolle
   - In GitHub: Actions → wählen Sie den Workflow `Deploy static site to GitHub Pages` und prüfen Sie den Run.
   - In Settings → Pages sehen Sie die veröffentlichte URL (z. B. `https://<user>.github.io/<repo-name>`).

7. Hinweise
   - Für private Repositories oder Organisationen kann es nötig sein, dass ein Administrator Pages-Deployments durch Actions erlaubt.
   - Falls Sie eine benutzerdefinierte Domain verwenden möchten, tragen Sie diese in Settings → Pages ein und aktualisieren Sie DNS-Einträge gemäß GitHub-Anleitung.

Wenn Sie möchten, passe ich die Workflow-Datei so an, dass nur ein bestimmter Ordner (z. B. `public/`) deployed wird.
