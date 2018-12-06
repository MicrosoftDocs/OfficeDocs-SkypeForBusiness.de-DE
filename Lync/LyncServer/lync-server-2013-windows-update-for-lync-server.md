---
title: 'Lync Server 2013: Windows Update für Lync Server'
TOCTitle: Windows Update für Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn518337(v=OCS.15)
ms:contentKeyID: 60476351
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Windows Update für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-12-05_

Verwenden Sie Windows Update Services, um regelmäßig zu prüfen, ob Updates und Sicherheitsupdates verfügbar sind, und wenden Sie diese an. Damit vermeiden Sie Sicherheitsrisiken in anderen Systemkomponenten, die dazu führen könnten, dass Angreifer Zugriff mit Administratorrechten auf Server mit Microsoft Lync Server 2013 erlangen und damit Lync Server 2013 gefährden.

Updates für Microsoft SQL Server 2008 Express (64-Bit-Edition) können auf allen Lync Server 2013 Standard Edition-Servern (für die Back-End-Datenbanken) und allen anderen Lync Server 2013-Serverrollen (für den lokalen Konfigurationsspeicher) ausgeführt werden, solange Sie diese Datenbanken nicht auf SQL Server 2008 R2 Express aktualisiert haben. Sie sollten diese Datenbanken als Teil der routinemäßigen Sicherheitsupdatewartung berücksichtigen, ebenso wie SQL Server in der Back-End-Datenbank eines Front-End-Pools, die Überwachungsdatenbank und die Archivierungsdatenbank.

## Bewährte Methode

  - Bleiben Sie mit Windows Update stets auf dem neuesten Stand.

