# N8N Workflows - Fixes & Improvements

Ce repository contient des sauvegardes et corrections de workflows N8N avec documentation détaillée des problèmes résolus.

## 🔧 Corrections Appliquées

### Fix Google Sheets Row Positioning (2025-07-08)

**Problème :** Les données étaient écrites dans la mauvaise ligne Google Sheets (ligne précédente au lieu de la ligne "pending" correcte).

**Solution :** Application du fix du PR #16632 de N8N qui corrige le type de `row_number` de `string` à `number` dans le schéma des nodes Google Sheets.

**Workflow concerné :** `FULL ASMR TEST` (ID: LPdk1oRiQAYEYURR)

**Modifications appliquées :**
- ✅ Node "Update Sheet with Prompts" : `row_number` type changé de `string` à `number`
- ✅ Node "Final Sheet Update" : `row_number` type changé de `string` à `number`  
- ✅ Node "Final Video Update" : `row_number` type changé de `string` à `number`
- ✅ Préservation de la logique `row_number` dans tous les nodes
- ✅ Validation complète du workflow (0 erreurs)

**Sources de recherche :**
- GitHub PR #16632 (N8N official fix)
- Documentation officielle N8N Google Sheets
- Discussions communautaires N8N
- Recherche Perplexity sur les meilleures pratiques

**Statut :** ✅ RÉSOLU - Le workflow écrit maintenant correctement dans la ligne "pending"

## 📁 Structure

```
workflows/
├── FULL_ASMR_TEST_FIXED_ROW_NUMBER.json  # Workflow corrigé avec documentation
└── [autres workflows...]
```

## 🚀 Utilisation

1. Importer le workflow JSON dans N8N
2. Configurer les credentials Google Sheets
3. Tester avec une ligne "pending" dans votre Google Sheet
4. Vérifier que les données sont écrites dans la bonne ligne

## 📞 Support

Pour toute question sur ces corrections, référez-vous aux commentaires dans les fichiers JSON ou aux sources de recherche mentionnées.