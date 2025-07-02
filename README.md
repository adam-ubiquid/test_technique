# Test technique Ubiquid – Développeur Web Fullstack

![header](./header.png)

## 🎯 Objectif

Ce test a pour but d’évaluer vos compétences en développement web fullstack (Node.js / React) à travers la mise en place d’une application de gestion d’offres d’emploi.

---

## ⚙️ Prérequis

- Node.js LTS (v22) — à installer de préférence via [NVM](https://github.com/nvm-sh/nvm)

---

## 🚀 Installation

- Le projet est découpé en deux packages :
  - L’interface utilisateur : `/packages/ui`
  - L’API backend : `/packages/api`

### Étapes :

```bash
# UI
cd /packages/ui
npm install
npm run dev

# API
cd /packages/api
npm install
npm run dev
```

- L’API est disponible sur : [http://localhost:3000](http://localhost:3000)
- L’interface UI est disponible sur : [http://localhost:5173](http://localhost:5173)

---

## 🧠 Exercices

Nous souhaitons construire une interface web permettant de gérer des offres d’emploi.

La maquette est disponible ici : [Figma – Jobtalk](https://www.figma.com/design/GXOPhuCPKx6DOH1xwdQPx5)

---

### 📝 Exercice 1 : Affichage de la liste des offres

- Implémenter dans l’UI la liste des offres d’emploi avec les filtres et tris visibles dans la maquette.
- Endpoint pour récupérer la liste : `GET http://localhost:3000/jobs/list`

---

### ✏️ Exercice 2 : Fonctions CRUD

- Implémenter les fonctionnalités de création, édition et suppression d’offres d’emploi côté API et UI.
- Utiliser les modales (cf. maquette) pour les formulaires.
- Côté API, utiliser [LowDB](https://github.com/typicode/lowdb) (déjà intégré) :

```js
import { db } from "../db/db"; // -> packages/api/db/db.js
```

---

### 📊 Exercice 3 : Création d’un endpoint de statistiques

Un client souhaite visualiser des statistiques sur les offres d’emploi. Votre mission est d’ajouter un endpoint :

```
GET /jobs/stats
```

Ce dernier devra retourner un objet JSON contenant au minimum les statistiques suivantes :

```json
{
  "averageSalary": number,             // Salaire moyen des offres
  "mostCommonContractType": string,   // Type de contrat le plus fréquent
  "mostCommonJobTitle": string,       // Intitulé de poste le plus proposé
  "offersPerCity": {                  // Répartition du nombre d'offres par ville
    "Paris": 12,
    "Lyon": 5,
    "Remote": 8
  }
}
```

> 💡 Vous pouvez enrichir la réponse avec d’autres indicateurs si vous le jugez pertinent (ex. : nombre d’offres par type de contrat, fourchette de salaires, etc.).

---

## ✅ Consignes générales

- Qualité du code (lisibilité, organisation, bonnes pratiques)
- Pertinence fonctionnelle (respect des specs / maquette)
- Autonomie et capacité à proposer des améliorations simples mais utiles
- Utilisation raisonnable de librairies externes
