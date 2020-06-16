---
title: Migrieren von Exchange Unified Messaging-Kontaktobjekten
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b3091a342b46b5c1aad1d456aa9159d951a4ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Migrieren von Exchange Unified Messaging-Kontaktobjekten

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Zum Migrieren von Kontaktobjekten der automatischen Telefonzentrale (AA) und des Teilnehmerzugriffs (SA) zur neuen lync Server 2013-Bereitstellung verschieben Sie zunächst die Objekte aus der vorversions Office Communications Server 2007 R2-Bereitstellung in die neue lync Server 2013-Bereitstellung mithilfe der Cmdlets **Get-CsExUmContact** und **verschieben-CsExUmContact** . Im Exchange Server führen Sie dann das **Skript "ExchUCUtil** -Windows PowerShell Skript aus, um die folgenden Schritte für den neu bereitgestellten lync-Pool auszuführen:

  - Hinzufügen der Kontaktobjekte zu den Unified Messaging-IP-Gateways

  - Hinzufügen der Kontaktobjekte zu den Unified Messaging-Sammelanschlüssen

<div>


> [!NOTE]  
> Um die Cmdlets <STRONG>Get-CsExUmContact</STRONG> und <STRONG>CsExUmContact</STRONG> verwenden zu können, müssen Sie Mitglied der RTCUniversalUserAdmins-Gruppe sein und über die Berechtigung Organisationseinheit (Organizational Unit, OU) für die OU verfügen, in der die Contacts-Objekte gespeichert sind. Die Berechtigung ou kann mit dem Cmdlet <STRONG>Grant-OUPermission</STRONG> erteilt werden.



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>So verschieben Sie Kontaktobjekte mithilfe der Lync Server-Verwaltungsshell

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Geben Sie für jeden Pool, der mit Exchange um registriert ist (wobei pool1.contoso.net ein Pool aus der Office Communications Server 2007 R2-Bereitstellung ist und pool2.contoso.net der Pool aus der lync Server 2013-Bereitstellung ist) an der Befehlszeile Folgendes ein:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Stellen Sie sicher, dass die Kontaktobjekte verschoben wurden, indem Sie das **Get-CsExumContact**-Cmdlet ausführen und sich vergewissern, dass **RegistrarPool** jetzt auf den neuen Pool zeigt.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>So führen Sie das Windows PowerShell-Skript "ExchUCUtil" aus

1.  Melden Sie sich als Benutzer mit der Berechtigung Exchange-Organisationsadministrator am Exchange UM-Server an.

2.  Navigieren Sie zum Skript Skript "ExchUCUtil Windows PowerShell.
    
    In Exchange 2007 befindet sich ExchUCUtil.ps1 unter: **% Program Files% \\ Microsoft \\ Exchange Server \\ Scripts \\ExchUCUtil.ps1**
    
    In Exchange 2010 befindet sich ExchUCUtil.ps1 unter: **% Program Files% \\ Microsoft \\ Exchange Server V14- \\ \\ Skripts \\ExchUCUtil.ps1**

3.  Wenn Exchange in einer einzigen Gesamtstruktur bereitgestellt wird, geben Sie Folgendes ein:
    
        exchucutil.ps1
    
    Oder geben Sie Folgendes ein, falls Exchange in mehreren Gesamtstrukturen bereitgestellt wird:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    Dabei gibt Gesamtstruktur-FQDN die Gesamtstruktur an, in der lync Server 2013 bereitgestellt wird.
    
    <div>
    

    > [!IMPORTANT]  
    > Starten Sie den Dienst <STRONG>Lync Server Front-End</STRONG> (rtcsrv.exe) neu, <EM>nachdem</EM> Sie "exchucutil.ps1" ausgeführt haben. Andernfalls werden von lync Server 2013 Unified Messaging in der Topologie nicht erkannt.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

