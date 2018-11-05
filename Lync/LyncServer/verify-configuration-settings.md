---
title: Überprüfen von Konfigurationseinstellungen
TOCTitle: Überprüfen von Konfigurationseinstellungen
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204885(v=OCS.15)
ms:contentKeyID: 49293997
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen von Konfigurationseinstellungen

 

_**Letztes Änderungsdatum des Themas:** 2012-09-06_

Sie können die Replikation von Konfigurationsinformationen auf den Edgeserver überprüfen, indem Sie das Lync Server 2013-Cmdlet **Get-CsManagementStoreReplicationStatus** auf dem internen Computer ausführen, auf dem Sie den zentralen Verwaltungsspeicher bereitgestellt haben (oder auf einem beliebigen Computer in der Domäne, auf dem die Lync Server 2013-Hauptkomponenten (OcsCore.msi) installiert sind).

Anfänglich wird anstelle des Status "True" möglicherweise der Status "False" für die Replikation angezeigt. Führen Sie in diesem Fall das Cmdlet **Invoke-CsManagementStoreReplication** aus, und warten Sie den Abschluss der Replikation ab. Führen Sie anschließend erneut das Cmdlet **Get-CsManagementStoreReplicationStatus** aus.

