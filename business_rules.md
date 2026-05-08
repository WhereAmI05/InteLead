# 📐 Règles métier — FinancePilot 360

## Règles de fiabilité des données

| Niveau | Signification |
|--------|--------------|
| **Réelle** | Donnée issue d'un document officiel (facture, relevé bancaire) |
| **Estimée** | Donnée calculée à partir d'hypothèses raisonnables |
| **Déclaratif** | Donnée transmise oralement ou par email par le dirigeant |
| **Hypothèse** | Valeur assumée pour le modèle, à confirmer |
| **Manquant** | Donnée non trouvée dans les sources — à collecter |

---

## Calculs de marge NORA

### Marge brute
```
Marge brute = CA HT - Coûts directs estimés
Coûts directs estimés = Nb sessions × 2 000 MAD (hypothèse)
```

### Marge nette (à compléter quand coûts partagés disponibles)
```
Marge nette = CA HT - Coûts directs - Quote-part coûts partagés
Quote-part coûts partagés = CA HT × 15% (hypothèse)
```

### Seuil de rentabilité par formation
```
Seuil participants = Coûts directs / Prix par participant
(Applicable uniquement aux formations au participant)
```

---

## Calculs SalesX

### Taux de financement
```
Taux financement = Subvention / Coût total projet
= 200 000 / 250 000 = 80%
```

### CAC (Coût d'Acquisition Client)
```
CAC = Budget marketing / Nombre clients acquis
Exemple réaliste : 60 000 / 20 = 3 000 MAD/client
```

### Seuil de rentabilité
```
Nb clients seuil = Charges fixes annuelles / Prix annuel par client
= 100 000 / 10 000 = 10 clients minimum
```

### Scénarios CA
```
CA scénario = Nb clients × Prix annuel/client
Prudent  : 5  × 10 000 = 50 000 MAD
Réaliste : 20 × 10 000 = 200 000 MAD
Ambitieux: 40 × 10 000 = 400 000 MAD
```

---

## Niveaux de risque régularisation

```
ÉLEVÉ  → Obligation non déclarée + année ancienne
       → OU retard historique confirmé (ex: CNSS)
       → OU statut inconnu sur obligation critique (TVA)

MOYEN  → Obligation en cours de traitement
       → OU statut inconnu sur obligation secondaire

FAIBLE → Obligation déclarée et payée
       → OU non applicable à l'entité

INCONNU → Données insuffisantes pour évaluer
```

---

## Incohérences détectées

### Pricing SalesX
- **Source BP** : 5 000–10 000 MAD/an
- **Source Business Model** : 54 000 MAD/an
- **Source Pitch Deck** : ~10 000 MAD/an
- **Action** : Clarifier avec le dirigeant avant toute projection

### CA SalesFlow vs CA Intelead
- Les revenus Intelead (45 000 MAD historiques) NE doivent PAS être consolidés comme CA SalesFlow
- SalesFlow CA propre 2024-2025 = 0 MAD (phase R&D, confirmé par email Tamwilcom)

---

## Règles de présentation

1. Toujours afficher le niveau de fiabilité sur chaque indicateur
2. Distinguer clairement données réelles / estimées / hypothèses
3. Ne pas présenter les projections comme des résultats
4. Toute recommandation doit être reliée à un indicateur
5. Signaler explicitement toute incohérence détectée
