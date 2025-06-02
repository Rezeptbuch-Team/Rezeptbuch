# CI/CD Dokumentation

Dieses Dokument beschreibt die Continuous Integration und Continuous Deployment (CI/CD) Prozesse für die Projekte **RezeptbuchAPI** und **RezeptbuchApplication**.  
Zudem wird das automatisierte Dependency-Management mit **Dependabot** erläutert.

---

## 1. Automatisiertes Dependency-Management mit Dependabot

Für beide Projekte wird [Dependabot](https://docs.github.com/de/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/about-dependabot-version-updates) genutzt, um Abhängigkeiten aktuell und sicher zu halten.  
Dependabot erstellt automatisch Pull Requests, wenn neue Versionen von Bibliotheken verfügbar sind.

- **RezeptbuchAPI:**  
  - Paket-Ökosystem: `nuget`  
  - Verzeichnis: `/RezeptbuchAPI/`  
  - Update-Intervall: wöchentlich

- **RezeptbuchApplication:**  
  - Paket-Ökosystem: `nuget`  
  - Verzeichnisse:  
    - `/src/ApplicationCore`  
    - `/src/ApplicationCore.Tests`  
    - `/src/GUI`  
  - Update-Intervall: täglich, jeweils 10:30 Uhr (Europe/Berlin)

---

## 2. CI/CD für RezeptbuchAPI

Für die **RezeptbuchAPI** existiert eine zentrale CI/CD-Pipeline (`.github/workflows/ci-cd.yml`), die folgende Schritte automatisiert:

### Build & Test

- **Auslöser:** Jeder Push oder Pull Request auf den `main`-Branch
- **Ablauf:**
  1. Checkout des Codes
  2. Setup des .NET SDK (Version 8.0.x)
  3. Wiederherstellen der Abhängigkeiten (`dotnet restore`)
  4. Build der Lösung im Release-Modus (`dotnet build --no-restore --configuration Release`)
  5. Ausführen der Tests mit Code Coverage (`dotnet test --no-build --configuration Release --collect:"XPlat Code Coverage"`)

### Deployment

- **Auslöser:** Erfolgreicher Abschluss von Build & Test auf dem `main`-Branch
- **Ablauf:**  
  Das Deployment erfolgt automatisiert über Render, sobald ein Commit erfolgreich auf `main` gelandet ist. Die Pipeline selbst enthält aktuell keinen expliziten Deployment-Schritt im Workflow, sondern bereitet das Projekt für Render vor.

---

## 3. CI/CD für RezeptbuchApplication

Für die **RezeptbuchApplication** gibt es mehrere Workflows, die verschiedene Aspekte automatisieren:

### 3.1. Build & Test für ApplicationCore (`.github/workflows/dotnet.yml`)

- **Auslöser:** Jeder Push oder Pull Request auf `main`
- **Ablauf:**
  1. Checkout des Codes
  2. Setup des .NET SDK (8.0.x)
  3. Wiederherstellen der Abhängigkeiten für die Tests
  4. Build von `ApplicationCore` und den Tests
  5. Ausführen der Tests

### 3.2. Windows-Build für die GUI (`.github/workflows/dotnet-build-windows.yml`)

- **Auslöser:** Jeder Push oder Pull Request auf `main`
- **Ablauf:**
  1. Checkout des Codes
  2. Setup des .NET SDK (8.0.x)
  3. Installation des MAUI-Workloads
  4. Wiederherstellen der Abhängigkeiten für die GUI
  5. Build und Publish der Windows-App (`dotnet publish`)
  6. Upload des Build-Artifacts

---

## 4. Hinweise und Best Practices

- **Branch Policy:**  
  Alle relevanten Pipelines werden auf dem `main`-Branch und bei Pull Requests ausgelöst. So wird sichergestellt, dass nur getesteter und gebauter Code in die Hauptentwicklung gelangt.
- **Testabdeckung:**  
  Die API-Pipeline sammelt zusätzlich Code Coverage.
- **Deployment:**  
  Die Bereitstellung der API erfolgt außerhalb der GitHub Actions-Pipeline automatisch über Render.
- **Abhängigkeiten:**  
  Durch Dependabot werden Sicherheitslücken und Updates automatisiert per Pull Request eingepflegt.

---

## 5. Übersicht der wichtigsten Workflow-Dateien

| Projekt                 | Workflow-Datei                              | Zweck                      |
|-------------------------|---------------------------------------------|----------------------------|
| RezeptbuchAPI           | `.github/workflows/ci-cd.yml`               | Build, Test, Vorbereitung Deployment |
| RezeptbuchApplication   | `.github/workflows/dotnet.yml`              | Build & Test (ApplicationCore) |
| RezeptbuchApplication   | `.github/workflows/dotnet-build-windows.yml`| Build & Artifact für Windows GUI |
| RezeptbuchAPI           | `.github/dependabot.yml`                    | Automatische Dependency-Updates |
| RezeptbuchApplication   | `.github/dependabot.yml`                    | Automatische Dependency-Updates |
