# zoran-gitops
Templates CI/CD: Actions réutilisables (lint/test/build/release/docker/pipy/npm).
# zoran-gitops

**Modèles CI/CD** pour l’écosystème Zoran / QuantaGlottal©® — Actions réutilisables pour lint, tests, build, release, packaging (Docker, PyPI, npm).

---

## ✨ Fonctionnalités
- **Workflows GitHub Actions prêts à l’emploi** :
  - Lint (Python, JS/TS)
  - Tests automatisés
  - Build multi-cibles
  - Release versionnée
  - Publication Docker, PyPI, npm
- **Variables et secrets** centralisés
- **Exécution conditionnelle** selon branche, tag ou PR
- **Templates YAML réutilisables** entre dépôts
- **Notifications** (Slack, Teams, email)

---

## 📦 Installation / Utilisation
Dans un dépôt Zoran, ajouter dans `.github/workflows/ci.yml` :
```yaml
name: CI
on:
  push:
    branches: [ "main" ]
  pull_request:

jobs:
  use-zoran-ci:
    uses: Alformpro/zoran-gitops/.github/workflows/ci-template.yml@main
    with:
      python-version: "3.11"
      node-version: "20"


---

🧱 Structure suggérée

.github/
  workflows/
    ci-template.yml         # lint + tests
    build-template.yml      # build et artefacts
    release-template.yml    # création tag + changelog + release
    docker-template.yml     # build/push image docker
    pypi-template.yml       # build/push package Python
    npm-template.yml        # build/publish package npm
scripts/
  lint.sh
  test.sh
  build.sh
LICENSE
README.md


---

🧪 Tests

Les workflows incluent des étapes de validation :

lint Python (flake8, black)

lint JS/TS (eslint, prettier)

tests unitaires (pytest, jest)



---

🔐 Éthique

Les pipelines CI/CD sont conçus pour la sécurité et la traçabilité :

vérification des dépendances

signatures des artefacts

journalisation complète



---

📜 Licence

MIT — voir LICENSE.


---

Auteur : Frédéric Tabary — Institut IA
Contact : 0645605023 — Canada, Montréal, France
INSTITUT🦋 IA INC., 7100-380, rue Saint-Antoine Ouest, Montréal (Québec) H2Y 3X7.
