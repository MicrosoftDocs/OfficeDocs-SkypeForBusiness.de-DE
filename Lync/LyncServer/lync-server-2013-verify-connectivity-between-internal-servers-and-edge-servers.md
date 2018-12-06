---
title: 'Lync Server 2013: Überprüfen der Konnektivität zwischen internen Servern und Edgeservern'
TOCTitle: Überprüfen der Konnektivität zwischen internen Servern und Edgeservern
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398292(v=OCS.15)
ms:contentKeyID: 49293410
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der Konnektivität zwischen internen Servern und Edgeservern in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

In Lync Server 2013 stand ein separater Überprüfungs-Assistent zum Prüfen der Konnektivität zwischen Edgeservern und internen Servern zur Verfügung. In Lync Server 2013 wird die Konnektivität automatisch überprüft, wenn Sie Ihre Edgeserver installieren.

Sie können die Replikation von Konfigurationsinformationen auf den Edgeserver überprüfen, indem Sie das Windows PowerShell-Cmdlet **Get-CsManagementStoreReplicationStatus** auf dem internen Computer ausführen, auf dem Sie den zentralen Verwaltungsspeicher bereitgestellt haben (oder auf einem beliebigen Computer in der Domäne, auf dem die Lync Server 2013-Hauptkomponenten (OcsCore.msi) installiert sind). Anfänglich wird anstelle des Status "True" möglicherweise der Status "False" für die Replikation angezeigt. Führen Sie in diesem Fall das Cmdlet **Invoke-CsManagementStoreReplication** aus, und warten Sie den Abschluss der Replikation ab. Führen Sie anschließend erneut das Cmdlet **Get-CsManagementStoreReplicationStatus** aus.

Sie können die Konnektivität für externe Benutzer separat überprüfen, einschließlich Verwendung der Remoteverbindungsanalyse von Office Communications Server zum Überprüfen der Remotebenutzerkonnektivität. Ausführliche Informationen finden Sie unter [Überprüfen der Konnektivität für externe Benutzer in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).

