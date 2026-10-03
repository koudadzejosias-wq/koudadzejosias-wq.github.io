---
layout: post
title: "Muraille d'Agbogbo CTF : write-up"
date: 2026-10-03 10:00:00 +0000
categories: [writeups, cybersecurity]
tags: [ctf, writeup, steganography, togo]
author: josias
---

## Introduction

Ce write-up présente ma démarche de résolution du challenge **Muraille d'Agbogbo**. L'objectif est de documenter le raisonnement, les vérifications et les outils utilisés, sans remplacer l'analyse personnelle nécessaire pour progresser en CTF.

## Méthodologie

1. Identifier le type de fichier et vérifier ses métadonnées avec `file` et `exiftool`.
2. Rechercher les données ajoutées ou les fichiers imbriqués avec `binwalk`.
3. Inspecter les chaînes lisibles et les données encodées.
4. Tester les pistes de stéganographie avec les outils adaptés, notamment `steghide` ou `stegseek` lorsque le format le permet.
5. Valider le flag dans le format attendu par la compétition.

## Leçons retenues

- Toujours conserver une copie originale du fichier analysé.
- Vérifier les métadonnées avant d'utiliser des outils plus spécialisés.
- Documenter chaque hypothèse et chaque résultat négatif.

> Les commandes et le flag final peuvent être complétés ici avec les détails exacts du challenge après publication des éléments autorisés par la compétition.
