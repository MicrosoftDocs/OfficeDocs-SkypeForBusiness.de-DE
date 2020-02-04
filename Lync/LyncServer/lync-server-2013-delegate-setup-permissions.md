---
title: 'Lync Server 2013: Delegieren von Setupberechtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 245fa0cb3bb5393f1d0f09a3f3b9c10176c015ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Delegieren von Setupberechtigungen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Wenn Sie Benutzern oder Gruppen, die lync Server 2013 bereitstellen, keine Mitgliedschaft in der Gruppe der Domänenadministratoren gewähren möchten, können Sie Mitgliedern der RTCUniversalServerAdmins-Gruppe das Ausführen des Windows PowerShell **-Cmdlets Enable-CsTopology** auf Servern mit lync Server 2013 ermöglichen. Standardmäßig verfügen Mitglieder der RTCUniversalServerAdmins-Gruppe nicht über die Möglichkeit zum Ausführen dieses Cmdlets. Sie erteilen Administratorrechte und Berechtigungen zum Ausführen von **enable-CsTopology** auf Servern mit lync Server mithilfe des Cmdlets **Grant-CsSetupPermission** und Angeben einer Organisationseinheit, in der Computerobjekte für den Server mit lync Server 2013 gespeichert sind.

Bei der Domänenvorbereitung, die bei der Installation von lync Server erfolgt, werden nicht automatisch die Berechtigungen hinzugefügt, mit denen Mitglieder der RTCUniversalServerAdmins-Gruppe das Cmdlet Enable-CsTopology ausführen können. Das bedeutet, dass Sie standardmäßig ein Domänenadministrator sein müssen, um eine Topologie zu aktivieren. Um Mitgliedern der RTCUniversalServerAdmins-Gruppe das Recht zu geben, eine Topologie zu aktivieren, müssen Sie das Grant-CsSetupPermissions-Cmdlet ausführen. Darüber hinaus müssen Sie dieses Cmdlet für jeden Active Directory-Container ausführen, auf dem Computer mit lync Server ausgeführt werden.

Beachten Sie, dass dieses Cmdlet nur der RTCUniversalServerAdmins-Gruppe Berechtigungen gewährt. das Cmdlet kann nicht verwendet werden, um anderen Sicherheitsgruppen oder einzelnen Benutzern Berechtigungen zu gewähren.

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> ist das Schlüssel-Cmdlet, das es den RTCUniversalServerAdmins-Gruppenmitgliedern ermöglicht, lync Server 2013 einzurichten und bereitzustellen.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>So fügen Sie die Möglichkeit hinzu, Enable-CsTopology zur RTCUniversalServerAdmins-Gruppe zu führen

1.  Melden Sie sich bei einem Server als Mitglied der Gruppe der Domänenadministratoren für die Domäne an, auf der der Delegierte Benutzer **enable-CsTopology**ausführen soll.

2.  Öffnen Sie die lync Server 2013-Verwaltungsshell. Die lync Server 2013-Verwaltungsshell wird automatisch auf jedem Front-End-Server oder auf jedem Computer installiert, auf dem die lync Server 2013-Verwaltungstools installiert wurden. Details zur lync Server 2013-Verwaltungsshell finden Sie unter [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) in der Betriebsdokumentation.

3.  Führen Sie das folgende Cmdlet aus der lync Server 2013-Verwaltungsshell aus:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > Wenn die Organisationseinheit nicht oberste Ebene ist, müssen Sie den vollständigen Domänennamen angeben.

    
    </div>
    
    Im folgenden Beispiel ist die OU "lync Servers", die sich in der contoso.com-Domäne befindet.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

