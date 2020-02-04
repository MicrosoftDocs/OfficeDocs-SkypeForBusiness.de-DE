---
title: 'Lync Server 2013: Gewähren von Berechtigungen für die Organisationseinheit'
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
ms.openlocfilehash: 084fb8cdebeda06d4441879f08f830021b65d2e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Gewähren von Berechtigungen für die Organisationseinheit in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-05-14_

Sie können das Cmdlet **Grant-CsOuPermission** verwenden, um den Objekten in bestimmten Organisationseinheiten (Organizational Units, OUs) Berechtigungen zu erteilen, damit Mitglieder der von Forest Preparation erstellten RTC-universellen Gruppen auf diese zugreifen können, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein. Die der angegebenen Organisationseinheit hinzugefügten Berechtigungen sind dieselben Berechtigungen, die das Cmdlet **enable-CsAdDomain** den Computern und Benutzer Containern während der Domänenvorbereitung hinzufügt.

Verwenden Sie das Cmdlet **Test-CsOuPermission** , um die Berechtigungen zu überprüfen, die Sie mithilfe des Cmdlets **Grant-CsOuPermission** eingerichtet haben.

Sie können das Cmdlet **REVOKE-CsOuPermission** verwenden, um Berechtigungen zu entfernen, die Sie mit dem Cmdlet **Grant-CsOuPermission** erteilt haben.

<div>

## <a name="to-grant-ou-permissions"></a>So erteilen Sie ou-Berechtigungen

1.  Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie ou-Berechtigungen erteilen möchten. Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.

</div>

<div>

## <a name="to-verify-ou-permissions"></a>So überprüfen Sie die OU-Berechtigungen

1.  Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie die mit dem Cmdlet **Grant-CsOuPermission** gewährten ou-Berechtigungen überprüfen möchten. Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>So widerrufen Sie ou-Berechtigungen

1.  Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie die vom Cmdlet **Grant-CsOuPermission** gewährten ou-Berechtigungen widerrufen möchten. Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.

</div>

</div>

<span> </span>

</div>

</div>

</div>

