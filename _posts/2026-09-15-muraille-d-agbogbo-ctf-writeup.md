---
title: "Muraille d'Agbogbo CTF Writeup"
date: 2026-09-15 09:00:00 +0000
categories: [writeup, ctf]
tags: [cybersecurity, ctf, writeup, linux, networking]
image:
  path: https://images.unsplash.com/photo-1510511459019-5dda7724fd87?auto=format&fit=crop&w=1600&q=80
  alt: "Ordinateur affichant une session technique"
layout: post
author: josias
---

> Note : ce writeup est une trame de publication. Les flags, commandes et résultats doivent être remplacés par les éléments réellement observés pendant le challenge.

## Présentation

La **Muraille d'Agbogbo** est un challenge qui invite à progresser étape par étape : reconnaissance, identification de la surface d'attaque, exploitation contrôlée et recherche du flag.

L'objectif de ce compte rendu est de conserver une méthode reproductible, sans divulguer d'informations sensibles sur une infrastructure réelle.

## Reconnaissance

Je commence par identifier les services exposés et leurs versions :

```bash
nmap -sC -sV -oN scans/initial.txt <IP_CIBLE>
```

Les résultats doivent être consignés avant toute tentative d'exploitation. Cette étape permet de prioriser les services intéressants et d'éviter les hypothèses non vérifiées.

## Énumération

Pour chaque service découvert, je vérifie les chemins, les bannières et les mécanismes d'authentification. Pour une application web, cela peut inclure une énumération de contenu autorisée et l'inspection des réponses HTTP.

```bash
curl -I http://<IP_CIBLE>/
```

## Exploitation

Après validation de la piste, je documente :

1. La faiblesse observée.
2. La preuve minimale permettant de la confirmer.
3. L'impact sur le challenge.
4. La commande ou la requête utilisée.

Les valeurs sensibles sont volontairement laissées sous forme de placeholders dans cette version publique.

## Flag et leçons retenues

Le flag final sera ajouté ici au format prévu par le challenge. Les principaux enseignements à retenir sont la rigueur de la reconnaissance, la conservation des preuves et la validation de chaque hypothèse avant de passer à l'étape suivante.

## Conclusion

Ce challenge rappelle qu'une bonne méthodologie vaut souvent mieux qu'une longue liste d'outils : observer, formuler une hypothèse, tester proprement et documenter le résultat.
