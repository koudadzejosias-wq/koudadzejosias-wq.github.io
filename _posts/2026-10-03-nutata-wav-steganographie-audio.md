---
layout: post
title: "Nutata.wav : stéganographie sonore"
date: 2026-10-03 12:00:00 +0000
categories: [writeups, cybersecurity]
tags: [ctf, writeup, steganography, audacity, linux]
author: josias
---

## Introduction

Le challenge **nutata.wav** est un challenge de CTF de la catégorie **stéganographie sonore**. Il présente un fichier audio dans lequel une information est dissimulée. L'objectif est d'explorer les fréquences audio pour retrouver le secret.

## Étape 1 : identification du fichier

La première étape consiste à vérifier que le fichier est bien ce qu'il prétend être avant de l'analyser :

```bash
file nutata.wav
```

Le résultat confirme que nous traitons un fichier audio au format **WAVE**. Ce format non compressé est adapté à l'analyse de données cachées dans le signal.

## Étape 2 : préparation d'Audacity

La suite de l'analyse se fait avec **Audacity**, afin d'observer le signal audio et ses fréquences. La visualisation spectrale permet de rechercher une information qui ne serait pas perceptible à l'écoute normale.

## Méthode d'analyse

1. Conserver une copie originale du fichier.
2. Identifier le format avec `file`.
3. Ouvrir le fichier dans Audacity.
4. Examiner la forme d'onde et la représentation spectrale.
5. Documenter chaque observation avant de valider une hypothèse.

> La page Notion publique accessible ne contient actuellement que l'introduction et le début du challenge. La suite et le flag final seront ajoutés lorsqu'ils seront disponibles dans l'export ou dans la page publique complète.
