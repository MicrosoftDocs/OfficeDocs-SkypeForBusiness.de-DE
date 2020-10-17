---
title: 'Lync Server 2013: Cmdlets für Infrastruktur und Bereitstellung'
description: 'Lync Server 2013: Cmdlets für Infrastruktur und Bereitstellung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Infrastructure and deployment cmdlets
ms:assetid: 0a6e872a-9f70-4f23-a4a5-8820dbf55370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398153(v=OCS.15)
ms:contentKeyID: 48183364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcd527d804422bbed28d63d320c267a85068e61d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552751"
---
# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a>Cmdlets für die Infrastruktur und Bereitstellung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Die in Microsoft lync Server 2013 enthaltenen Cmdlets für die Infrastruktur und die Bereitstellung können beim erstmaligen Einrichten und Bereitstellen des Produkts hilfreich sein. Nachdem lync Server bereitgestellt wurde, können diese Cmdlets dann verwendet werden, um zu überprüfen, ob die Komponenten wie erwartet funktionieren; Verwalten von Replikationseinstellungen; und sichern und Wiederherstellen der lync Server-Topologie,-Richtlinien und-Konfigurationseinstellungen.

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a>Cmdlets für Infrastruktur und Bereitstellung

Administratoren müssen nur selten viele der Infrastrukturen und der Bereitstellung direkt aufrufen. Dies liegt daran, dass diese Cmdlets automatisch aufgerufen werden, wenn Sie Setup oder den Topologie-Generator ausführen. (Eine wichtige Ausnahme ist möglicherweise das Cmdlet **Export-CsConfiguration** , mit dem Sie eine Sicherungskopie Ihrer lync Server Topologie, der Richtlinien und der Konfigurationseinstellungen erstellen können.) Bei Bedarf können die Infrastruktur-und Bereitstellungs-Cmdlets jedoch auch über die lync Server-Verwaltungsshell oder in einem Skript ausgeführt werden. mit einem Skript können Sie bestimmte Aufgaben automatisieren. Im folgenden finden Sie eine Liste der Cmdlets, die sich direkt auf Infrastruktur und Bereitstellung beziehen:

**[Active Directory-Cmdlets in lync Server 2013](lync-server-2013-active-directory-cmdlets.md)**

  - <span></span>  
    [Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))

  - <span></span>  
    [Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))

  - <span></span>  
    [Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))

  - <span></span>  
    [Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))

  - <span></span>  
    [Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))

  - <span></span>  
    [Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))

**[Replikations-Cmdlets in lync Server 2013](lync-server-2013-replication-cmdlets.md)**

  - <span></span>  
    [Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-csreplica "](https://technet.microsoft.com/library/Gg425965(v=OCS.15))

  - <span></span>  
    [Test-csreplica "](https://technet.microsoft.com/library/JJ205289(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))

  - <span></span>  
    [New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))

  - <span></span>  
    [Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))

  - <span></span>  
    [Gruppe-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))

**[Topologie-Cmdlets Jn lync Server 2013](lync-server-2013-topology-cmdlets.md)**

  - <span></span>  
    [Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))

  - <span></span>  
    [Gruppe-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))

  - <span></span>  
    [Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))

  - <span></span>  
    [Veröffentlichen-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))

  - <span></span>  
    [Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))

  - <span></span>  
    [Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))

  - <span></span>  
    [Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))

  - <span></span>  
    [Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))

  - <span></span>  
    [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))

**[Cmdlets für Sicherung und hohe Verfügbarkeit in lync Server 2013](lync-server-2013-backup-and-high-availability-cmdlets.md)**

  - [Get-csbackupserviceconfiguration "](https://technet.microsoft.com/library/JJ205087(v=OCS.15))

  - [Remove-csbackupserviceconfiguration "](https://technet.microsoft.com/library/JJ204903(v=OCS.15))

  - [Gruppe-csbackupserviceconfiguration "](https://technet.microsoft.com/library/JJ205006(v=OCS.15))

<!-- end list -->

  - [Get-CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))

<!-- end list -->

  - [Invoke-CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))

<!-- end list -->

  - [Debug-csintrapoolreplication "](https://technet.microsoft.com/library/JJ205103(v=OCS.15))

<!-- end list -->

  - [Sicherung-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))

<!-- end list -->

  - [Get-cspoolbackuprelationship "](https://technet.microsoft.com/library/JJ204745(v=OCS.15))

<!-- end list -->

  - [Get-CsPoolFabricState](https://technet.microsoft.com/library/JJ619188(v=OCS.15))

<!-- end list -->

  - [Invoke-CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))

<!-- end list -->

  - [Invoke-CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))

<!-- end list -->

  - [Get-cspoolupgradereadinessstate "](https://technet.microsoft.com/library/JJ204689(v=OCS.15))

<!-- end list -->

  - [Invoke-CsStorageServiceFlush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))

<!-- end list -->

  - [Sync-csuserdata "](https://technet.microsoft.com/library/JJ205242(v=OCS.15))

<!-- end list -->

  - [Remove-csadminrole](https://technet.microsoft.com/library/JJ205003(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Lync Server PowerShell-Blog](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

