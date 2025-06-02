# CI/CD Dokumentation

Dieses Dokument beschreibt die Continuous Integration und Continuous Deployment (CI/CD) Pipelines für die Projekte **RezeptbuchAPI** und **RezeptbuchApplication**.

---

## 1. RezeptbuchAPI – Test Pipeline

Automatisiertes Testen der API bei jedem Push und Pull Request auf den Hauptbranch (`main`).  
**Hinweis:** Das Deployment der API erfolgt automatisch über Render, sobald ein erfolgreicher Commit im Hauptbranch landet. Die Pipeline selbst kümmert sich ausschließlich um Build und Tests.

### Ablauf der Pipeline

1. Checkout des Codes
2. Setzen des .NET SDK
3. Installieren der Abhängigkeiten
4. Bauen der Lösung
5. Ausführen der Tests

### Beispiel-Workflow (`.github/workflows/api-test.yml`)

```yaml
name: API Test Pipeline

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build-and-test:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v3

    - name: Setup .NET
      uses: actions/setup-dotnet@v4
      with:
        dotnet-version: '8.0.x'

    - name: Restore dependencies
      run: dotnet restore

    - name: Build
      run: dotnet build --no-restore

    - name: Test
      run: dotnet test --no-build --verbosity normal
```


## 2. RezeptbuchApplication – Build & Test Pipeline

Automatisiertes Bauen und Testen der Anwendung bei jedem Push und Pull Request auf den Hauptbranch (`main`).

### Ablauf der Pipeline

1. Checkout des Codes
2. Setzen des .NET SDK
3. Installieren der Abhängigkeiten
4. Bauen der Lösung
5. Ausführen der Tests

### Beispiel-Workflow (`.github/workflows/app-build.yml`)

```yaml
nname: Application Build & Test Pipeline

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build-and-test:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v3

    - name: Setup .NET
      uses: actions/setup-dotnet@v4
      with:
        dotnet-version: '8.0.x'

    - name: Restore dependencies
      run: dotnet restore

    - name: Build
      run: dotnet build --no-restore

    - name: Test
      run: dotnet test --no-build --verbosity normal
```
