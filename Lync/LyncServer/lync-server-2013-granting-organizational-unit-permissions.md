---
title: 'Lync Server 2013: Erteilen von Berechtigungen für Organisationseinheiten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85c43cb727b83b06d6427e2bf3b6027d78dc025e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Erteilen von Berechtigungen für Organisationseinheiten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-05-14_

Mithilfe des Cmdlets **Grant-CsOuPermission** können Sie auch Objekten in bestimmten Organisationseinheiten Berechtigungen gewähren, sodass Mitglieder der während der Gesamtstrukturvorbereitung erstellten universellen RTC-Gruppen auf diese Objekte zugreifen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein. Bei den Berechtigungen, die Sie der angegebenen Organisationseinheit hinzufügen, handelt es sich um die gleichen Berechtigungen, die das Cmdlet **Enable-CsAdDomain** während der Domänenvorbereitung den Containern für Computer und Benutzer hinzufügt.

Verwenden Sie das Cmdlet **Test-CsOuPermission** zum Überprüfen der Berechtigungen, die Sie mit dem Cmdlet **Grant-CsOuPermission** gewähren.

Mit dem Cmdlet **Revoke-CsOuPermission** können Sie Berechtigungen entfernen, die Sie mit dem Cmdlet **Grant-CsOuPermission** zugewiesen haben.

<div>

## <a name="to-grant-ou-permissions"></a>So gewähren Sie Organisationseinheitenberechtigungen

1.  Melden Sie sich an einem Computer mit lync Server 2013 in der Domäne an, in der Sie Organisationseinheiten Berechtigungen erteilen möchten. Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

</div>

<div>

## <a name="to-verify-ou-permissions"></a>So überprüfen Sie Organisationseinheitenberechtigungen

1.  Melden Sie sich an einem Computer mit lync Server 2013 in der Domäne an, in der Sie die mit dem Cmdlet **Grant-CsOuPermission** gewährten ou-Berechtigungen überprüfen möchten. Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>So entziehen Sie Organisationseinheitenberechtigungen

1.  Melden Sie sich an einem Computer mit lync Server 2013 in der Domäne an, in der Sie Organisationseinheiten Berechtigungen widerrufen möchten, die vom Cmdlet **Grant-CsOuPermission** erteilt wurden. Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die OU in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

