---
title: Überprüfen der Replikation von Konfigurationseinstellungen
TOCTitle: Überprüfen der Replikation von Konfigurationseinstellungen
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205042(v=OCS.15)
ms:contentKeyID: 49294579
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der Replikation von Konfigurationseinstellungen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Sie können die Replikation von Konfigurationsinformationen auf den Edgeserver überprüfen, indem Sie das Lync Server 2013-Cmdlet **Get-CsManagementStoreReplicationStatus** auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet, oder auf einem beliebigen Computer in der Domäne, auf dem die Lync Server 2013-Hauptkomponenten installiert sind.

Anfänglich wird anstelle des Status "True" möglicherweise der Status "False" für die Replikation angezeigt. Führen Sie in diesem Fall das Cmdlet **Invoke-CsManagementStoreReplication** aus, und warten Sie den Abschluss der Replikation ab. Führen Sie anschließend erneut das Cmdlet **Get-CsManagementStoreReplicationStatus** aus.

