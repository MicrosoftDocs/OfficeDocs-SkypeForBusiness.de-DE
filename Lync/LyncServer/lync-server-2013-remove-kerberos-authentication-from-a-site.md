---
title: 'Lync Server 2013: Entfernen der Kerberos-Authentifizierung von einer Website'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4f7fa1160e7ff0afbbc4d8d4cc5ec96ab08e0f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>In lync Server 2013 Entfernen der Kerberos-Authentifizierung von einer Website

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-01-16_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

Wenn Sie die Kerberos-Authentifizierung von einem Standort entfernen oder eine Website zurückziehen müssen, müssen Sie die Kerberos-Authentifizierungs Konto Zuweisung von der Website mithilfe des Cmdlets **Remove-CsKerberosAccountAssignment** entfernen. Verwenden Sie das folgende Verfahren, um die Zuweisung von Kerberos-Authentifizierungs Konten zu entfernen, wodurch die Zuweisung von allen Computern am Standort entfernt wird.

<div class=" ">


> [!WARNING]  
> Wenn Sie das Kerberos-fähige Konto dauerhaft in den Ruhestand ziehen, sollten Sie Active Directory Benutzer und Computer verwenden, um es aus Active Directory-Domänendienste zu löschen, nachdem Sie die Zuordnung entfernt haben. Wenn Sie das Objekt in der Zukunft verwenden möchten, sollten Sie das Active Directory-Objekt beibehalten.



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>So entfernen Sie die Kerberos-Authentifizierung aus einem Standort

1.  Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins bei einem Computer in der Domäne an, auf dem lync Server 2013 oder an einem Computer mit den Verwaltungstools installiert ist.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie an der Befehlszeile die folgenden zwei Befehle aus:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    Beispiel:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Nachdem Sie Änderungen an der Kerberos-Authentifizierung vorgenommen haben, wie beispielsweise das Hinzufügen eines Kontos oder das Entfernen eines Kontos, müssen Sie <STRONG>enable-CsTopology</STRONG> über die lync Server-Verwaltungsshell Eingabeaufforderung ausführen.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

