---
title: 'Lync Server 2013: Gewähren von Setupberechtigungen'
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
ms.openlocfilehash: 2a4642a9e0c77d9cf3aa77c146ff692a7fa7a6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>Gewähren von Setupberechtigungen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-08-27_

Sie können das Cmdlet **Grant-CsSetupPermission** verwenden, um der RTCUniversalServerAdmins-Gruppe für eine angegebene Active Directory-Organisationseinheit (OU) Lese-, Schreib-, ReadSPN-und WriteSPN-Berechtigungen hinzuzufügen. Anschließend können Mitglieder der RTCUniversalServerAdmins-Gruppe in dieser OU Server mit lync Server 2013 in der angegebenen Domäne installieren, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein.

Verwenden Sie das Cmdlet **Test-CsSetupPermission** , um die Berechtigungen zu überprüfen, die Sie mithilfe des Cmdlets **Grant-CsSetupPermission** eingerichtet haben.

Sie können das Cmdlet **REVOKE-CsSetupPermission** verwenden, um Berechtigungen zu entfernen, die Sie mit dem Cmdlet **Grant-CsSetupPermission** erteilt haben.

<div>

## <a name="to-grant-setup-permissions"></a>So erteilen Sie Setup Berechtigungen

1.  Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie Setup Berechtigungen erteilen möchten. Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Sie können den ComputerOu-Parameter als relativ zum Standardnamenskontext der angegebenen Domäne (beispielsweise CN = Computers) angeben. Sie können diesen Parameter auch als vollständigen Distinguished Name (DN) angeben (beispielsweise "CN = Computers, DC = contoso, DC = com"). In diesem Fall müssen Sie eine OU-DN angeben, die mit der von Ihnen angegebenen Domäne konsistent ist.
    
    Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>So überprüfen Sie die Setup Berechtigungen

1.  Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie die mit dem Cmdlet **Grant-CsSetupPermission** gewährten Setup Berechtigungen überprüfen möchten. Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Sie können den ComputerOu-Parameter als relativ zum Standardnamenskontext der angegebenen Domäne (beispielsweise CN = Computers) angeben. Sie können diesen Parameter auch als vollständigen Distinguished Name (DN) angeben (beispielsweise "CN = Computers, DC = contoso, DC = com"). In diesem Fall müssen Sie eine OU-DN angeben, die mit der von Ihnen angegebenen Domäne konsistent ist.
    
    Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>So widerrufen Sie die Setup Berechtigungen

1.  Melden Sie sich bei einem Computer mit lync Server 2013 in der Domäne an, in der Sie die vom Cmdlet **Grant-CsSetupPermission** gewährten Setup Berechtigungen widerrufen möchten. Verwenden Sie ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" oder der Gruppe "Organisations-Admins" ist, wenn sich die Organisationseinheit in einer anderen untergeordneten Domäne befindet.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Sie können den ComputerOu-Parameter als relativ zum Standardnamenskontext der angegebenen Domäne (beispielsweise CN = Computers) angeben. Sie können diesen Parameter auch als vollständigen Distinguished Name (DN) angeben (beispielsweise "CN = Computers, DC = contoso, DC = com"). In diesem Fall müssen Sie eine OU-DN angeben, die mit der von Ihnen angegebenen Domäne konsistent ist.
    
    Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.

</div>

</div>

<span> </span>

</div>

</div>

</div>

