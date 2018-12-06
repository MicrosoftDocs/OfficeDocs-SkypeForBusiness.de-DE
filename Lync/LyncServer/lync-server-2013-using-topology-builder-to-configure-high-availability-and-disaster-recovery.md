---
title: 'Lync Server 2013: Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators'
TOCTitle: Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205172(v=OCS.15)
ms:contentKeyID: 49295059
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Führen Sie die folgenden Schritte im Topologie-Generator aus, um eine hohe Verfügbarkeit und die Notfallwiederherstellung für den Server für beständigen Chat zu konfigurieren.

1.  Fügen Sie die Spiegeldatenbanken und die SQL Server-Speicher für die sekundäre Protokollversanddatenbank hinzu.

2.  Bearbeiten Sie die Diensteigenschaften für den Server für beständigen Chat wie folgt:
    
    1.  Aktivieren Sie die Spiegelung für die primäre Datenbank.
    
    2.  Fügen Sie den primären Spiegelspeicher für SQL Server zu.
    
    3.  Aktivieren Sie die Protokollversanddatenbank für SQL Server.
    
    4.  Fügen Sie den sekundären SQL Server-Speicher für den SQL Server-Protokollversand hinzu.
    
    5.  Fügen Sie den SQL Server-Speicherspiegel für die sekundäre Datenbank hinzu.
    
    6.  Veröffentlichen Sie die Topologie.

