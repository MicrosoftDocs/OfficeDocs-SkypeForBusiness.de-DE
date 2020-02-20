---
title: 'Lync Server 2013: Delegieren von Setup Berechtigungen'
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
ms.openlocfilehash: d5660a78bcad4d125fbf32204331b433978a831d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Delegieren von Setup Berechtigungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-05_

Wenn Sie Benutzern oder Gruppen, die lync Server 2013 bereitstellen, keine Mitgliedschaft in der Gruppe "Domänen-Admins" gewähren möchten, können Sie Mitgliedern der Gruppe "RTCUniversalServerAdmins" das Cmdlet **enable-CsTopology** Windows PowerShell auf Servern mit lync Server 2013 ermöglichen. Standardmäßig verfügen Mitglieder der Gruppe "RTCUniversalServerAdmins" nicht über die Berechtigung zum Ausführen dieses Cmdlets. Sie gewähren Administratorrechte und Berechtigungen zum Ausführen von **enable-CsTopology** auf Servern mit lync Server mithilfe des Cmdlets **Grant-CsSetupPermission** und der Angabe einer Organisationseinheit (Organizational Unit, OU), in der sich Computerobjekte für den Server befinden, auf dem lync Server 2013 ausgeführt werden.

Bei der Domänenvorbereitung, die bei der Installation von lync Server erfolgt, werden nicht automatisch die Berechtigungen hinzugefügt, mit denen Mitglieder der RTCUniversalServerAdmins-Gruppe das Cmdlet Enable-CsTopology ausführen können. Dies bedeutet, dass Sie standardmäßig ein Domänenadministrator sein müssen, um eine Topologie zu aktivieren. Um Mitgliedern der Gruppe "RTCUniversalServerAdmins" das Recht zum Aktivieren einer Topologie zu erteilen, müssen Sie das Cmdlet Grant-CsSetupPermissions ausführen. Darüber hinaus müssen Sie dieses Cmdlet für jeden Active Directory Container ausführen, in dem sich Computer befinden, auf denen lync Server ausgeführt wird.

Beachten Sie, dass dieses Cmdlet nur der Gruppe "RTCUniversalServerAdmins" Berechtigungen erteilt; das Cmdlet kann keiner anderen Sicherheitsgruppe oder einzelnen Benutzern Berechtigungen gewähren.

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> ist das Schlüssel-Cmdlet, das es den Mitgliedern der RTCUniversalServerAdmins-Gruppe ermöglicht, lync Server 2013 einzurichten und bereitzustellen.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>So erteilen Sie der Gruppe "RTCUniversalServerAdmins" die Möglichkeit zum Ausführen von "Enable-CsTopology"

1.  Melden Sie sich bei einem Server als Mitglied der Gruppe "Domänen-Admins" für die Domäne an, in der der delegierte Benutzer **Enable-CsTopology** ausführen soll.

2.  Öffnen Sie die lync Server 2013 Management-Shell. Die lync Server 2013-Verwaltungsshell wird automatisch auf jedem Front-End-Server oder auf einem Computer installiert, auf dem die lync Server 2013-Verwaltungstools installiert wurden. Ausführliche Informationen zur lync Server 2013-Verwaltungsshell finden Sie unter [lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in der Betriebsdokumentation.

3.  Führen Sie das folgende Cmdlet aus der Verwaltungsshell für die lync Server 2013 Verwaltung aus:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > Wenn die Organisationseinheit nicht die oberste Ebene ist, müssen Sie den vollständigen Domänennamen angeben.

    
    </div>
    
    Im folgenden Beispiel wird als Organisationseinheit "Lync Servers" in der Domäne "contoso.com" festgelegt.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

