# kata-gen-ts-yarn

```bash

# 📦 1. Initialiser le projet avec Yarn
yarn init -y
```
```bash
# 🧠 2. Ajouter TypeScript
yarn add -D typescript
npx tsc --init
```
```bash
# 🧩 3. Ajouter les types de Node.js
yarn add -D @types/node
```
```bash
# 🧪 4. Ajouter Vitest pour les tests unitaires
yarn add -D vitest @vitest/globals
```
```bash
# 📝 5. Ajouter le script de test dans package.json
# Ouvre package.json et remplace ou ajoute :
# "scripts": {
#   "test": "vitest"
# }
```
```bash
# 📁 6. Créer la structure de base
mkdir src tests

# Créer un fichier avec une fonction simple à tester
echo "export function sum(a: number, b: number) { return a + b; }" > src/sum.ts

# Créer le test correspondant
echo "import { describe, it, expect } from 'vitest';
import { sum } from '../src/sum';

describe('sum', () => {
  it('adds two numbers', () => {
    expect(sum(2, 3)).toBe(5);
  });
});
" > tests/sum.test.ts
```
```bash
# ▶️ 7. Lancer les tests
yarn test
```
