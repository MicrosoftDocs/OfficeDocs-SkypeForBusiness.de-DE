---
title: Sichern von Dateispeichern
TOCTitle: Sichern von Dateispeichern
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202167(v=OCS.15)
ms:contentKeyID: 52056295
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sichern von Dateispeichern

 

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

Die Sicherung der Lync Server-Dateispeicher umfasst alle von Lync Server-Komponenten verwendeten Dateien und Ordner:

## So sichern Sie Dateispeicher

1.  Für die Suche nach spezifischen Speicherorten für Ihre Lync Server-Dateispeicher und Archivierungsdateispeicher öffnen Sie den Topologie-Generator und suchen im Knoten **Dateispeicher**.

2.  Verwenden Sie Robocopy oder ein anderes Dateisystemverwaltungstool, um jeden Dateispeicher nach **$Backup\\filestore** zu kopieren.

