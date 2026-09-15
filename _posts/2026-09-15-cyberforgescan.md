---
title: "CyberForgeScan : analyse de logs avec Python"
date: 2026-09-15 12:00:00 +0000
categories: [projects]
tags: [cybersecurity, python, linux]
image:
  path: https://images.unsplash.com/photo-1558494949-ef010cbdcc31?auto=format&fit=crop&w=1600&q=80
  alt: "Infrastructure réseau et serveurs"
layout: post
author: josias
---

## Le besoin

Les journaux système contiennent souvent les premiers indices d'un comportement anormal. **CyberForgeScan** est un outil Python conçu pour faciliter leur lecture, repérer des motifs intéressants et accélérer une première analyse.

## Objectifs

- Charger des fichiers de logs de manière claire.
- Repérer des événements liés aux erreurs, aux accès et aux tentatives répétées.
- Produire une sortie lisible pour aider à la qualification.
- Garder une base simple à étendre avec de nouvelles règles.

## Approche technique

Le projet s'appuie sur Python et sur une organisation modulaire : lecture des entrées, normalisation des événements, application de règles et génération d'un rapport.

```python
from pathlib import Path

log_file = Path("access.log")
for line in log_file.read_text(encoding="utf-8").splitlines():
    if "failed" in line.lower() or "error" in line.lower():
        print(line)
```

Cet extrait illustre le principe minimal. La version complète a vocation à séparer les règles de détection de l'affichage et à gérer proprement les formats de logs rencontrés.

## Utilisation envisagée

CyberForgeScan peut servir dans un laboratoire Linux, pour des exercices de formation ou comme point de départ d'un pipeline d'analyse plus complet. Il ne remplace pas un SIEM et ses résultats doivent toujours être vérifiés dans leur contexte.

## Suite du projet

Les prochaines étapes sont la couverture de plusieurs formats, l'ajout de règles configurables, l'export de rapports et l'intégration de tests automatisés.
