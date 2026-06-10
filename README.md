# LEXIS – 140 propositions · Loi-cadre intégrale contre les violences sexuelles

> **LEXIS** est un outil d’assistance juridique qui intègre l’intégralité des **140 propositions** de la Coalition Féministe pour une loi-cadre contre les violences sexuelles. Chaque mesure est enrichie par un **assistant IA** (Mistral AI) dont le prompt est spécialisé selon le contenu juridique de la proposition.

![Interface LEXIS](https://via.placeholder.com/800x400?text=LEXIS+Interface)

---

## 📚 Table des matières

1. [À propos](#-à-propos)
2. [Fonctionnalités clés](#-fonctionnalités-clés)
3. [Obtenir une clé API Mistral (gratuit)](#-obtenir-une-clé-api-mistral-gratuit)
4. [Installation & utilisation](#-installation--utilisation)
5. [Mode d’emploi détaillé](#-mode-demploi-détaillé)
6. [Améliorer les outils IA](#-améliorer-les-outils-ia)
7. [Personnalisation & contribution](#-personnalisation--contribution)
8. [Licence](#-licence)

---

## 🧭 À propos

LEXIS transforme le travail de la société civile en outil interactif accessible à toutes et tous :

- **140 propositions** classées par thème (Cadre général, Éducation & culture, Protection des enfants, Parcours judiciaire, Prévention récidive, Angles morts).
- **Assistant IA** paramétré pour chaque proposition : génération de lettres types, explications juridiques, recours possibles.
- **Outils annexes** : Violentomètre, checklist « sac de fuite », simulateur d’ordonnance de protection.

---

## ✨ Fonctionnalités clés

| Module | Description |
|--------|-------------|
| **Grille des 140 propositions** | Recherche, filtrage par thème, affichage détaillé de chaque mesure |
| **Assistant IA spécialisé** | Prompt personnalisé selon la proposition (ex: rédiger un amendement, une circulaire, un plan d’action) |
| **Violentomètre** | Évaluation du niveau de danger (N1 à N7) avec conseils juridiques immédiats |
| **Checklist « Sac de fuite »** | Liste des documents et objets essentiels en cas de départ d’urgence |
| **Simulateur d’OP** | Simulation d’une requête d’ordonnance de protection (art. 515-9 Code civil) |

---

## 🔑 Obtenir une clé API Mistral (gratuit)

LEXIS utilise l’API **Mistral AI** (modèle `mistral-large-2411`). Voici comment obtenir une clé gratuite (Free Tier) :

### Étape 1 – Créer un compte Mistral AI
- Rendez‑vous sur [console.mistral.ai](https://console.mistral.ai)
- Inscrivez‑vous avec votre email ou via Google/GitHub

### Étape 2 – Récupérer votre clé API
- Une fois connecté, accédez à la section **API Keys** (menu latéral)
- Cliquez sur **« Create new key »**
- Donnez un nom (ex: `LEXIS`)
- Copiez immédiatement la clé générée (elle ne sera plus affichée)

> ⚠️ Le Free Tier de Mistral AI offre des crédits gratuits limités (environ 1 million de tokens). Pour une utilisation personnelle ou de démonstration, cela reste très confortable. Si vos besoins augmentent, vous pouvez passer au **Pay‑As‑You‑Go**.

---

## 🚀 Installation & utilisation

### 1. Cloner le dépôt
```bash
git clone https://github.com/votre-compte/lexis-140-propositions.git
cd lexis-140-propositions
```

### 2. Ouvrir la page dans votre navigateur
LEXIS est une application **100% front‑end** (HTML/CSS/JS). Aucun serveur requis.
- Double‑cliquez sur `index.html` (ou servez‑la avec `npx serve .`)

### 3. Configurer votre clé API
- Sur la page, dans la barre d’outils, saisissez votre **clé API Mistral** dans le champ prévu à cet effet.
- La clé est stockée localement (dans le champ de saisie) – aucun serveur externe n’enregistre votre clé.

### 4. Explorer les propositions
- Utilisez la **barre de recherche** ou le **filtre par thème**.
- Cliquez sur une carte de proposition pour ouvrir le modal détaillé.
- Posez une question dans l’assistant IA, qui utilisera le **prompt spécialisé** propre à cette proposition.

---

## 📖 Mode d’emploi détaillé

### 🔎 Recherche et filtrage
- **Recherche textuelle** : saisissez un numéro de proposition (ex: `26`), un mot‑clé (ex: `inceste`, `ordonnance`).
- **Filtrage par thème** : utilisez la liste déroulante ou les boutons de filtre rapide.

### 🤖 Assistant IA par proposition
Chaque proposition est accompagnée d’un **prompt système** unique. Exemples :
- *Proposition 26 (Imprescriptibilité des viols sur mineurs)* : le prompt demande une argumentation juridique et un projet d’amendement.
- *Proposition 7 (EVARS à l’école)* : le prompt génère un décret d’application.

**Utilisation** : dans le modal d’une proposition, posez votre question (ex: *« Rédige une lettre type pour signaler un défaut d’application de cette proposition »*). L’IA répondra en se calant sur le contexte juridique de la mesure.

### 🛠️ Outils annexes
- **Violentomètre** : cliquez sur le niveau correspondant à votre situation. L’outil affiche les qualifications pénales et les actions prioritaires.
- **Sac de fuite** : cochez les éléments déjà préparés – la barre de progression vous aide à ne rien oublier.
- **Simulateur d’OP** : renseignez vos informations et obtenez un projet d’ordonnance de protection structuré.

---

## 🧠 Améliorer les outils IA

### 1. Ajuster les prompts par proposition
Les prompts sont définis dans le tableau `proposalsData` (à l’intérieur de `index.html`). Chaque objet `addProp` contient le paramètre `customPromptSystem`.

**Exemple d’évolution** : vous pouvez enrichir le prompt avec des références à des jurisprudence récentes ou à des articles précis du Code pénal.

```javascript
addProp(26, "Protection des enfants", "Imprescriptibilité des viols sur mineurs",
        "...",
        "Tu es un·e expert·e en droit pénal. Cite les arrêts récents de la Cour de cassation et la Convention d'Istanbul. Propose un projet d'article pour le CPP.");
```

### 2. Changer le modèle Mistral
Par défaut, le modèle utilisé est `mistral-large-2411`. Vous pouvez le remplacer par `mistral-medium` ou `mistral-small` pour réduire les coûts (Free Tier).

```javascript
// Dans la fonction callMistral, modifier le paramètre model
await callMistral(apiKey, "mistral-small-latest", systemPrompt, userMsg);
```

### 3. Ajouter des outils annexes (RAG, recherche documentaire)
Pour améliorer la pertinence juridique, vous pouvez intégrer une **recherche vectorielle** sur les textes officiels (Code pénal, Code de procédure pénale, Convention d’Istanbul).

- Utilisez la bibliothèque `transformers.js` pour embarquer un petit modèle de recherche (ex: `all-MiniLM-L6-v2`).
- Indexez les articles de loi dans un index vectoriel local (IndexedDB).

### 4. Personnaliser l’interface
- **Thème** : les variables CSS (`--accent`, `--border`, etc.) sont dans la balise `:root` du fichier.
- **Langue** : tout le texte est en français ; vous pouvez facilement adapter les libellés.

### 5. Sécurité et confidentialité
- La clé API Mistral n’est **jamais envoyée** à un serveur externe – elle est utilisée directement dans l’appel `fetch()` depuis le navigateur.
- Aucune donnée utilisateur (questions, réponses) n’est stockée. Si vous souhaitez ajouter une persistance, utilisez `localStorage` ou un serveur auto‑hébergé (ex: Supabase).

---

## 🤝 Personnalisation & contribution

Les contributions sont les bienvenues !

### Structure du fichier `index.html`
- `proposalsData` : tableau des 140 propositions (id, thème, titre, description, prompt).
- `renderGrid()` : affichage dynamique des cartes.
- `openProposition()` : ouverture du modal avec le prompt dédié.
- `callMistral()` : appel à l’API Mistral.

### Ajouter une nouvelle proposition
```javascript
addProp(141, "Angles morts", "Titre", "Description", "Prompt système spécialisé");
```

### Signaler un bogue ou proposer une amélioration
Utilisez l’onglet **Issues** du dépôt GitHub.

---

## ⚖️ Licence

Ce projet est distribué sous licence **MIT**. Vous êtes libre de l’utiliser, de le modifier et de le redistribuer, à condition de conserver la mention de la paternité et l’avis de licence.

---

## 📞 Ressources utiles

- [Texte intégral des 140 propositions (PDF)](https://www.loi-integrale.fr)  
- [API Mistral AI – Documentation](https://docs.mistral.ai)  
- [Convention d’Istanbul](https://www.coe.int/fr/web/istanbul-convention)  
- [Numéro 3919 – Violences femmes info](https://solidarites.gouv.fr/le-3919-violences-femmes-info)  

---

**Fait avec ❤️ pour les droits des femmes et l’accès à la justice.**  
*LEXIS – Parce que chaque proposition doit devenir une réalité.*
