---
description: "Vérifie qu’un diff respecte DRY, SOLID, Design Patterns et Clean Architecture."
agent: "build"
---

Entrées: $DIFF (ou sélection)
Tâche:

1. Signale toute violation de DRY, SOLID, Clean Architecture (Ports/Adapters), et conventions (naming, RLS-first, secrets).
2. Propose un patch minimal (≤50 lignes) pour corriger les 2 problèmes les plus impactants.
   Format:

- Diagnostic (puces courtes)
- Patch (diff unifié)
- Check de sortie (liste de vérifications)
