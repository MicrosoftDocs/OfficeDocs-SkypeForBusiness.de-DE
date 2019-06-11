---
title: 'Lync Server 2013: Cmdlets für Infrastruktur und Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Infrastructure and deployment cmdlets
ms:assetid: 0a6e872a-9f70-4f23-a4a5-8820dbf55370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398153(v=OCS.15)
ms:contentKeyID: 48183364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38d41545c7d128e57919c4a2bc66069e9a27b67c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a>Cmdlets für Infrastruktur und Bereitstellung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Die in Microsoft lync Server 2013 enthaltenen Cmdlets für Infrastruktur und Bereitstellung können bei der erstmaligen Einrichtung und Bereitstellung des Produkts hilfreich sein. nach der Bereitstellung von lync Server können diese Cmdlets dann verwendet werden, um zu überprüfen, ob Komponenten wie erwartet funktionieren. Verwalten von Replikationseinstellungen und sichern und Wiederherstellen der lync Server-Topologie,-Richtlinien und-Konfigurationseinstellungen.

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a>Cmdlets für Infrastruktur und Bereitstellung

Administratoren müssen nur selten viele Infrastrukturen und die Bereitstellung direkt anrufen. Dies liegt daran, dass diese Cmdlets automatisch aufgerufen werden, wenn Sie Setup oder den Topologie-Generator ausführen. (Eine wichtige Ausnahme kann das Cmdlet " **Export-CsConfiguration** " sein, mit dem Sie eine Sicherungskopie Ihrer lync Server-Topologie,-Richtlinien und-Konfigurationseinstellungen erstellen können.) Bei Bedarf können die Cmdlets für die Infrastruktur und die Bereitstellung aber auch über die lync Server-Verwaltungsshell oder in einem Skript ausgeführt werden. durch die Verwendung eines Skripts können Sie bestimmte Aufgaben automatisieren. Die folgende Liste enthält Cmdlets, die sich direkt auf Infrastruktur und Bereitstellung beziehen:

**[Active Directory-Cmdlets in lync Server 2013](lync-server-2013-active-directory-cmdlets.md)**

  - <span></span>  
    [Deaktivieren-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))

  - <span></span>  
    [Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))

  - <span></span>  
    [Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Deaktivieren-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))

  - <span></span>  
    [Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))

  - <span></span>  
    [Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))

  - <span></span>  
    [Installieren-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))

**[Replikations-Cmdlets in lync Server 2013](lync-server-2013-replication-cmdlets.md)**

  - <span></span>  
    [Debug-CsInterPoolReplication](https://technet.microsoft.com/en-us/library/JJ619185(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-CsManagementStoreReplication](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-CsReplica](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))

  - <span></span>  
    [Test-CsReplica](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))

  - <span></span>  
    [Neu – CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))

  - <span></span>  
    [Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))

  - <span></span>  
    [Satz-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))

**[Topologie-Cmdlets Jn lync Server 2013](lync-server-2013-topology-cmdlets.md)**

  - <span></span>  
    [Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))

  - <span></span>  
    [Satz-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))

  - <span></span>  
    [Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))

  - <span></span>  
    [Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))

  - <span></span>  
    [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))

  - <span></span>  
    [Importieren-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Deaktivieren-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))

  - <span></span>  
    [Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))

  - <span></span>  
    [Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))

  - <span></span>  
    [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))

**[Cmdlets für Backup und höhere Verfügbarkeit in lync Server 2013](lync-server-2013-backup-and-high-availability-cmdlets.md)**

  - [Get-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))

  - [Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))

  - [Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))

<!-- end list -->

  - [Get-CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))

<!-- end list -->

  - [Invoke-CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))

<!-- end list -->

  - [Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))

<!-- end list -->

  - [Backup-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))

<!-- end list -->

  - [Get-CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))

<!-- end list -->

  - [Get-CsPoolFabricState](https://technet.microsoft.com/en-us/library/JJ619188(v=OCS.15))

<!-- end list -->

  - [Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))

<!-- end list -->

  - [Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))

<!-- end list -->

  - [Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))

<!-- end list -->

  - [Invoke-CsStorageServiceFlush](https://technet.microsoft.com/en-us/library/JJ619175(v=OCS.15))

<!-- end list -->

  - [Sync-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))

<!-- end list -->

  - [Remove-CsUserStoreBackupData](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Lync Server PowerShell-Blog](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

