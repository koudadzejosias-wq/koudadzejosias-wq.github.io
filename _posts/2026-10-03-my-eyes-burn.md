---
layout: post
title: "My eyes burn : chaîne de touches mortes"
date: 2026-10-03 12:12:00 +0000
categories: [writeups, misc]
tags: [ctf, writeup, unicode, keyboard]
author: josias
---

L’analyse du fichier `boardwriter.klc` repose sur le décodage UTF-16 et le suivi d’une chaîne de touches mortes. Chaque résultat devient la touche morte suivante jusqu’au caractère Unicode final représentant le soleil.

Flag obtenu : `sun{praisethesun}`.

[Lire le write-up complet sur Notion](https://app.notion.com/p/Writeup-my-eyes-burn-Misc-3eac5eb422c38122b26fd41e86729030)
