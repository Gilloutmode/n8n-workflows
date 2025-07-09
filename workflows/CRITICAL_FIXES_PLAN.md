# 🎯 PLAN DE CORRECTIONS CRITIQUES

## PROBLÈMES IDENTIFIÉS

### 1. PROMPT PERPLEXITY TROP COURT
- **Problème** : Prompt actuel génère des réponses de 3 mots
- **Cause** : Manque de spécifications de longueur et structure
- **Solution** : Optimiser le prompt avec demandes explicites de détails

### 2. PROMPTS HARDCODÉS PERSISTANTS
- **Problème** : Fallbacks "ceramic teacup tapping" encore présents
- **Cause** : Logique de fallback dans les nodes Code
- **Solution** : Supprimer tous les fallbacks hardcodés

### 3. EXTRACTION PERPLEXITY DÉFAILLANTE
- **Problème** : Regex ne capture pas les données Perplexity
- **Cause** : Format de réponse Perplexity différent de celui attendu
- **Solution** : Améliorer l'extraction avec patterns multiples

## CORRECTIONS À APPLIQUER

### CORRECTION 1: Optimiser le Prompt Perplexity
```
ANCIEN PROMPT (trop court):
"🎯 **CRITICAL UNIQUENESS MANDATE** 🎯..."

NOUVEAU PROMPT (détaillé):
"Provide a comprehensive analysis of 4 unique ASMR video trends currently viral on social media platforms. For EACH trend, provide detailed information in this EXACT format:

**TREND 1: [Descriptive Title]**
- **Visual Technique**: [Detailed description of the visual approach, camera angles, and filming style - minimum 15 words]
- **Materials/Objects**: [Specific list of all materials, tools, and objects used - minimum 10 words]
- **Platform**: [Primary platform where this trend is popular]
- **Viral Factor**: [Detailed explanation of why this trend is engaging and satisfying - minimum 20 words]
- **Production Details**: [Lighting setup, background, props, and technical aspects - minimum 15 words]

Requirements:
- Each trend description must be at least 100 words total
- Focus on visual ASMR content (no audio-only)
- Trends must be from the last 48 hours
- No repeated materials or techniques between trends
- Provide specific, actionable details for video production

Generate 4 completely unique trends following this format exactly."
```

### CORRECTION 2: Supprimer Fallbacks Hardcodés
Dans les nodes suivants, remplacer tous les fallbacks "ceramic teacup" par des extractions forcées des données Perplexity.

### CORRECTION 3: Améliorer l'Extraction
Ajouter des patterns regex multiples pour capturer différents formats de réponse Perplexity.

## ORDRE D'APPLICATION
1. **PREMIÈRE** : Corriger le prompt Perplexity (node "Get ASMR Trends")
2. **TESTER** : Vérifier que Perplexity génère des réponses détaillées
3. **DEUXIÈME** : Corriger l'extraction (node "Format Perplexity Data")
4. **TESTER** : Vérifier que les données sont correctement extraites
5. **TROISIÈME** : Supprimer fallbacks (nodes "Parse AI Scenes" et "Prepare Initial Update")
6. **TESTER** : Vérifier que les prompts utilisent les données Perplexity

## SÉCURITÉ
- ✅ Modifications incrémentales uniquement
- ✅ Test après chaque modification
- ✅ Préservation de la structure existante
- ✅ Aucune modification des connexions
- ✅ Sauvegarde avant chaque modification