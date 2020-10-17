---
title: 'Lync Server 2013: Gewähren von Setup Berechtigungen'
description: 'Lync Server 2013: Gewähren von Setup Berechtigungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5523494219d07907caeefc1bd139c41856effa54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554481"
---
# <a name="granting-setup-permissions-in-lync-server-2013"></a>Erteilen von Setup Berechtigungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-08-27_

Mit dem Cmdlet **Grant-CsSetupPermission** können Sie der Gruppe "RTCUniversalServerAdmins" Lese-, Schreib-, ReadSPN- und WriteSPN-Berechtigungen für eine angegebene Organisationseinheit (Organizational Unit, OU) in Active Directory zuweisen. Anschließend können Mitglieder der RTCUniversalServerAdmins-Gruppe in dieser Organisationseinheit Server mit lync Server 2013 in der angegebenen Domäne installieren, ohne Mitglied der Gruppe "Domänen-Admins" zu sein.

Verwenden Sie das Cmdlet **Test-CsSetupPermission** zum Überprüfen der Berechtigungen, die Sie mit dem Cmdlet **Grant-CsSetupPermission** gewähren.

Mit dem Cmdlet **Revoke-CsSetupPermission** können Sie Berechtigungen entfernen, die Sie mit dem Cmdlet **Grant-CsSetupPermission** zugewiesen haben.

<div>

## <a name="to-grant-setup-permissions"></a>So gewähren Sie Setupberechtigungen

1.  Melden Sie sich an einem Computer mit lync Server 2013 in der Domäne an, in der Sie Setup Berechtigungen erteilen möchten. Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Sie können den Parameter "ComputerOu" relativ zum Standardnamenskontext der festgelegten Domäne angeben (z. B. "CN=computers"). Alternativ können Sie für diesen Parameter den vollständigen Distinguished Name (DN) der OU angeben (beispielsweise "CN=computers,DC=Contoso,DC=com"). Im letzteren Fall müssen Sie einen OU-DN angeben, der mit der verwendeten Domäne konsistent ist.
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>So überprüfen Sie Setupberechtigungen

1.  Melden Sie sich an einem Computer mit lync Server 2013 in der Domäne an, in der Sie Setup Berechtigungen überprüfen möchten, die Sie mit dem Cmdlet **Grant-CsSetupPermission** erteilt haben. Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Sie können den Parameter "ComputerOu" relativ zum Standardnamenskontext der festgelegten Domäne angeben (z. B. "CN=computers"). Alternativ können Sie für diesen Parameter den vollständigen Distinguished Name (DN) der OU angeben (beispielsweise "CN=computers,DC=Contoso,DC=com"). Im letzteren Fall müssen Sie einen OU-DN angeben, der mit der verwendeten Domäne konsistent ist.
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>So entziehen Sie Setupberechtigungen

1.  Melden Sie sich an einem Computer mit lync Server 2013 in der Domäne an, in der Sie Setup Berechtigungen widerrufen möchten, die vom Cmdlet **Grant-CsSetupPermission** erteilt wurden. Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Sie können den Parameter "ComputerOu" relativ zum Standardnamenskontext der festgelegten Domäne angeben (z. B. "CN=computers"). Alternativ können Sie für diesen Parameter den vollständigen Distinguished Name (DN) der OU angeben (beispielsweise "CN=computers,DC=Contoso,DC=com"). Im letzteren Fall müssen Sie einen OU-DN angeben, der mit der verwendeten Domäne konsistent ist.
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

