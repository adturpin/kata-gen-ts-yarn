# 📦 Projet TypeScript + Yarn + Vitest

Ce projet est une base propre pour démarrer un développement TypeScript avec Yarn Berry (v4) et des tests unitaires via Vitest.

---

## 🧰 Prérequis

- Node.js >= 16.9
- Corepack activé :
  
```bash
corepack enable
corepack prepare yarn@stable --activate
```

---

## 🚀 Installation

```bash
yarn install
```

---

## ⚙️ Création du projet

### 📁 1. Créer le dossier du projet

```bash
mkdir mon-projet-ts
cd mon-projet-ts
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
yarn add -D vitest @vitest/globals
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
{
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
    "types": ["vitest/globals"]
  },
  "include": ["src", "tests"]
}
```

---

## 🔗 Liens utiles

- [Yarn Berry (v4)](https://yarnpkg.com/)
- [TypeScript](https://www.typescriptlang.org/)
- [Vitest (tests unitaires)](https://vitest.dev/)
- [ESLint (analyse statique)](https://eslint.org/)
- [Prettier (formatage de code)](https://prettier.io/)
