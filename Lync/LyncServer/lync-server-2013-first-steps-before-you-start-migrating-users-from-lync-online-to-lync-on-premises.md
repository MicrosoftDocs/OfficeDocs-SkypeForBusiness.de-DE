---
title: 'Lync Server 2013: Erste Schritte vor dem Start der Migration von Benutzern von lync online zu lync lokal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf61b4e2f3e3a14d5e2434ff80bd5d6f612f267
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>Erste Schritte vor dem Start der Migration von Benutzern von lync online zu lync lokal in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-08_

Bevor Sie mit dem Verschieben lync Online Benutzer in Ihre lokale Umgebung beginnen, überprüfen Sie, dass alle der folgenden Bedingungen erfüllt sind:

  - Ihre lync Server lokale Umgebung muss vollständig bereitgestellt und überprüft werden. Weitere Informationen finden Sie unter [Deploying lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - Ihr lync Online-Mandant muss für den Remote-PowerShell-Zugriff konfiguriert sein.
    
    Installieren Sie dazu zunächst das lync Online Modul für Windows PowerShell, das Sie hier erhalten können: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).
    
    Nachdem Sie das Modul installiert haben, können Sie eine Remotesitzung einrichten, indem Sie die folgenden Cmdlets in der lync Server-Verwaltungsshell eingeben:
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    Weitere Informationen zum Einrichten einer Remote-PowerShell-Sitzung mit lync Online finden Sie unter [Herstellen einer Verbindung mit lync Online mithilfe von Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
    Weitere Informationen zum Verwenden des lync Online-PowerShell-Moduls finden Sie unter [using Windows PowerShell to manage lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - Ihr lync Online muss für den freigegebenen SIP-Adressraum konfiguriert sein. Starten Sie dazu zunächst eine Remote-PowerShell-Sitzung mit lync online. Führen Sie dann das folgende Cmdlet aus:
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

Nachdem Sie diese Schritte abgeschlossen haben, können Sie mit der [Migration lync Online Benutzer zu lokal in lync Server 2013 in lync](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)fortfahren.

</div>

<span> </span>

</div>

</div>

</div>

