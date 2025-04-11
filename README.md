# 📦 Projet TypeScript + Yarn + Vitest

Ce projet est une base propre pour démarrer un développement TypeScript avec Yarn Berry (v4) et des tests unitaires via Vitest.

---

## 🔗 Liens utiles

- [Yarn Berry (v4)](https://yarnpkg.com/)
- [TypeScript](https://www.typescriptlang.org/)
- [Vitest (tests unitaires)](https://vitest.dev/)
- [ESLint (analyse statique)](https://eslint.org/)
- [Prettier (formatage de code)](https://prettier.io/)


---

## 🧰 Prérequis

- Node.js >= 16.9
- Corepack activé :
  
```bash
corepack enable
corepack prepare yarn@stable --activate
```

### 🚀 Installation

```bash
yarn install
```

---

## ⚙️ Création du projet

### 📁 1. Créer le dossier du projet

```bash
mkdir mon-kata-ts
cd mon-kata-ts
```

### 📦 2. Initialiser le projet avec Yarn

```bash
yarn init -y
```

### 🧠 3. Ajouter TypeScript

```bash
yarn add -D typescript
npx tsc --init
```

### 🧩 4. Ajouter les types de Node.js

```bash
yarn add -D @types/node
```

### 🧪 5. Ajouter Vitest pour les tests unitaires

```bash
yarn add -D vitest
```

### 📝 6. Ajouter le script de test dans `package.json`

```json
"scripts": {
  "test": "vitest"
}
```

### 📁 7. Créer la structure de base

```bash
mkdir src
mkdir tests
```

```bash
echo "export function sum(a: number, b: number) { return a + b; }" > src/sum.ts
```

```bash
echo "import { describe, it, expect } from 'vitest';
import { sum } from '../src/sum';

describe('sum', () => {
  it('adds two numbers', () => {
    expect(sum(2, 3)).toBe(5);
  });
});
" > tests/sum.test.ts
```

### ▶️ 8. Lancer les tests

```bash
yarn test
```

---

## 🔧 tsconfig.json recommandé

```json
echo '{
   "compilerOptions": {
     "target": "ES2020",
     "module": "ESNext",
     "moduleResolution": "Node",
     "esModuleInterop": true,
     "strict": true,
     "skipLibCheck": true,
     "forceConsistentCasingInFileNames": true,
     "outDir": "./dist",
     "rootDir": "./",
     "types": []
   },
   "include": ["src", "tests"]
 }' >  tsconfig.json
```

## 🧪 Générer un rapport de couverture de test

Vitest permet de générer un rapport de **coverage** (couverture de code).

### ▶️ 1. Ajouter la dépendance

```bash
yarn add -D @vitest/coverage-v8
```

### ▶️ 2. Modifier le script de test

Dans `package.json`, ajoute ou modifie :

```json
"scripts": {
  "test": "vitest",
  "test:coverage": "vitest run --coverage"
}
```

### ▶️ 3. Lancer les tests avec coverage

```bash
yarn test
```

Le rapport sera généré dans le dossier `coverage/` (par défaut en format text, HTML, lcov…).

Tu peux ouvrir `coverage/index.html` dans ton navigateur pour une vue visuelle.

---

## 🧹 Ajouter ESLint et Prettier

Pour garantir un code propre et cohérent, on ajoute **ESLint** pour la qualité du code et **Prettier** pour le formatage automatique.

### ▶️ 1. Installer ESLint

```bash
yarn add -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin
```

### ▶️ 2. Initialiser la configuration ESLint

```bash
npx eslint --init
```

Réponds comme suit :
- ❓ Comment voulez-vous utiliser ESLint ? `To check syntax, find problems, and enforce code style`
- ❓ Quel type de modules ? `JavaScript modules (import/export)`
- ❓ Framework : `None of these`
- ❓ TypeScript ? `Yes`
- ❓ Où s'exécutera ton code ? `Node`
- ❓ Format du fichier de config ? `JSON` ou `YAML` selon ta préférence

### ▶️ 3. Exemple de configuration `.eslintrc.json`

```json
{
  "parser": "@typescript-eslint/parser",
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended"
  ],
  "plugins": ["@typescript-eslint"],
  "env": {
    "node": true,
    "es2020": true
  }
}
```

---

### 🧼 4. Ajouter Prettier

```bash
yarn add -D prettier eslint-config-prettier
```

### ▶️ 5. Ajouter un fichier `.prettierrc`

```json
{
  "semi": true,
  "singleQuote": true,
  "printWidth": 80,
  "tabWidth": 2
}
```

---

### 🧪 6. Scripts dans `package.json`

```json
"scripts": {
  "lint": "eslint . --ext .ts",
  "format": "prettier --write ."
}
```

---

### ✅ Lancer les commandes

```bash
yarn lint     # Vérifie les erreurs de code
yarn format   # Formate automatiquement le code
```

