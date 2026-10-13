# CBC / Radio-Canada — Connecto (Trouveur d'Experts)

Un outil interne, confidentiel et ultra-rapide conçu pour identifier instantanément les experts et personnes-ressources (*Subject Matter Experts*) au sein de **CBC / Radio-Canada**.

Couvre l'ensemble des départements stratégiques :
- **Technologies & Infrastructure (T&I) :** Cloud, Streaming OTT, Dalet/iNews, Trint, Transcription IA, Cybersécurité, Émetteurs hertzien, Ingénierie broadcast (SMPTE 2110).
- **Information & Nouvelles (Editorial) :** Correspondants parlementaires, journalisme d'enquête, économie & marchés, climat & environnement, affaires autochtones, santé.
- **Affaires Juridiques & Corporatives :** Droit des médias, CRTC, Loi C-11, Droits d'auteur, Archives historiques & préservation numérique.

---

## 🚀 Démarrage Rapide

Double-cliquez simplement sur :
```text
run.bat
```
L'application se lance immédiatement dans votre navigateur par défaut (Microsoft Edge ou Google Chrome) via un serveur local sécurisé (`http://127.0.0.1:8765/`).

> [!NOTE]
> **Aucune installation de logiciel ni droit d'administrateur requis.** L'outil fonctionne directement sur les postes CBC/Radio-Canada sans modifier le système.

---

## 🔒 Confidentialité & Sécurité des Données

- **100% Local :** Toutes les données (profils, contacts, courriels, documents importés) restent exclusivement stockées dans le stockage local de votre navigateur (`IndexedDB` / `LocalStorage`).
- **Zéro fuite de données :** Aucun contact interne ni extrait de document n'est envoyé à un serveur tiers ou dans le nuage.

---

## 🔍 Fonctionnalités Clés

1. **Recherche sémantique bilingue (FR / EN) :**
   - Comprend automatiquement les équivalences :
     - *« IA »* ↔ *« Artificial Intelligence » / « Machine Learning »*
     - *« Diffusion »* ↔ *« Broadcast » / « ST 2110 »*
     - *« Cybersécurité »* ↔ *« Cybersecurity » / « Zero Trust »*
     - *« Économie »* ↔ *« Banque du Canada » / « Inflation »*
   - Recherche en temps réel avec surbrillance des termes trouvés.

2. **Actions directes en un clic :**
   - **Courriel direct :** Ouvre un nouveau courriel avec l'adresse du spécialiste et un objet pré-rempli.
   - **Copier fiche :** Copie le nom, le poste, le courriel et les compétences en un clic pour vos comptes-rendus ou notes.

3. **Importation multi-sources :**
   - **Glisser-déposer CSV / Workday :** Importez des listes d'employés existantes (un modèle exemple est disponible dans `data/template-contacts-cbc-rc.csv`).
   - **Analyseur de documents :** Collez un extrait de compte-rendu, note de réunion ou courriel interne : l'outil extrait automatiquement les adresses courriels et associe les compétences correspondantes.
   - **Exportation :** Exportez votre annuaire à tout moment au format Excel/CSV ou JSON pour le partager avec vos collègues.

---

## 📁 Structure du Projet

```text
cbc-rc-expert-finder/
├── index.html               # Interface utilisateur principale (Tailwind + Lucide)
├── run.bat                  # Lanceur Windows en 1 clic
├── start-server.ps1         # Serveur web local .NET HttpListener
├── js/
│   ├── app.js               # Contrôleur principal et gestion d'état
│   ├── search-engine.js     # Moteur de recherche sémantique bilingue
│   ├── seed-data.js         # Profils certifiés CBC / Radio-Canada par défaut
│   ├── importer.js          # Ingestion CSV et analyseur de documents internes
│   └── storage.js           # Persistance locale (LocalStorage / Export)
└── data/
    └── template-contacts-cbc-rc.csv # Modèle d'importation CSV
```
