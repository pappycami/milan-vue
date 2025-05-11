# Composables Vue 3

Ce dossier contient les composables réutilisables de l'application. Les composables sont des fonctions qui encapsulent la logique réutilisable avec la Composition API de Vue 3.

Principes de base :
- Chaque composable doit avoir une responsabilité unique
- Utiliser TypeScript pour le typage des paramètres et retours
- Documenter clairement l'utilisation avec des exemples
- Suivre la convention de nommage 'use' prefix

Structure recommandée :
```typescript
export function useMonComposable(params: ParamsType) {
  // État réactif
  const state = ref<StateType>(initialState)

  // Méthodes et computed properties
  const computedValue = computed(() => /* ... */)

  // Logique du composable
  function handleAction() {
    // ...
  }

  // Retourner les valeurs et méthodes nécessaires
  return {
    state,
    computedValue,
    handleAction
  }
}
```

N'oubliez pas d'ajouter des tests unitaires pour chaque composable dans le dossier `__tests__`.