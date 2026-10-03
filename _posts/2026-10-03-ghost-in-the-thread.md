---
layout: post
title: "Ghost in the Thread : investigation forensics"
date: 2026-10-03 16:42:00 +0000
categories: [writeups, forensics]
tags: [ctf, writeup, forensics, linux, ghostscript]
author: josias
---

## Présentation

Le challenge fournit un instantané HTML d'un forum et une appliance VirtualBox `GhostInTheThread.ova`. Un message particulier contient une pièce jointe absente de l'archive HTML, ce qui indique qu'il faut rechercher le fichier sur le disque de la VM.

## Méthode d'investigation

Le message `184726` est l'anomalie : son horodatage contient des secondes inhabituelles et sa pièce jointe pointe vers elle-même au lieu d'un fichier encodé. L'appliance est une archive TAR qui peut être explorée sans démarrer la VM :

```bash
tar xf GhostInTheThread.ova
qemu-img convert -f vmdk -O raw GhostInTheThread-disk1.vmdk disk.raw
fdisk -l disk.raw
```

Après montage en lecture seule de la partition ext4, le journal `/var/log/sunchan/uploads.log` révèle le chemin `/srv/sunchan/uploads/po/184726.pdf`.

Le fichier présenté comme un PDF est en réalité du PostScript. Ses commentaires donnent un `Document-ID` et orientent vers le binaire `gs-resource.bin`. L'analyse avec `file` et `strings` précède toute exécution ; le programme fonctionne hors ligne et attend l'identifiant du document.

```bash
echo "po-184726" | ./gs-resource.bin
```

## Flag

```text
sun{tfw_hacked_by_offboarders}
```

Le challenge rappelle l'importance de comparer les anomalies HTML, de vérifier le contenu réel d'un fichier avec `file`, et d'explorer les images disque sans exécuter aveuglément des artefacts inconnus.

[Lire le write-up original sur Notion](https://app.notion.com/p/Writeup-Ghost-in-the-Thread-Forensics-3eec5eb422c38160aac3c400159943cf)
