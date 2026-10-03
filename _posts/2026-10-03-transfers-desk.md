---
layout: post
title: "Transfers Desk : IDOR et race condition"
date: 2026-10-03 12:34:00 +0000
categories: [writeups, web]
tags: [ctf, writeup, web, idor, race-condition]
author: josias
---

Le challenge **Transfers Desk** repose sur plusieurs faiblesses applicatives combinées : conversion incorrecte d'identifiants UUID dans le frontend, contrôle d'accès insuffisant de type **IDOR**, puis validation incomplète des approbations.

## Méthode

Après la création d'un espace de travail, l'analyse du JavaScript frontend montre que `beneficiaryId` est converti en nombre alors qu'il s'agit d'un UUID. L'API peut donc être appelée directement avec des requêtes personnalisées.

Un endpoint de consultation des virements permet ensuite de récupérer des détails appartenant à une autre organisation, faute de contrôle d'appartenance correct. Enfin, l'endpoint d'approbation incrémente le compteur sans vérifier que les approbateurs sont réellement distincts : l'envoi de requêtes concurrentes permet de déclencher la validation.

Flag obtenu :

```text
EthACTF{b0la_then_t0ct0u_ch_settle_01}
```

[Lire le write-up original sur Notion](https://app.notion.com/p/Write-up-CTF-Transfers-Desk-3dec5eb422c38107ab17cbb4974cbeb7)
