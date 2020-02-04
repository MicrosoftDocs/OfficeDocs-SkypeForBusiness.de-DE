---
title: Verschieben von Exchange Unified Messaging-Kontaktobjekten
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d79354522675daaf221052579b0863899d1176ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Verschieben von Exchange Unified Messaging-Kontaktobjekten

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Zum Migrieren von Kontaktobjekten der automatischen Telefonzentrale (AA) und des Abonnenten Zugriffs (SA) zur neuen lync Server 2013-Bereitstellung verschieben Sie zunächst die Objekte aus der Legacy Office Communications Server 2007 R2-Bereitstellung auf die neue lync Server 2013-Bereitstellung mithilfe der Cmdlets **Get-CsExUmContact** und **Move-CsExUmContact** . Auf dem Exchange-Server führen Sie dann das Windows PowerShell- **exchucutil** -Skript aus, um die folgenden Schritte für den neu bereitgestellten lync-Pool durchzuführen:

  - Fügen Sie Sie den Unified Messaging-IP-Gateways hinzu.

  - Fügen Sie es den Unified Messaging-Sammelanschlüssen hinzu.

<div>


> [!NOTE]  
> Um die Cmdlets " <STRONG>Get-CsExUmContact</STRONG> " und " <STRONG>Move-CsExUmContact</STRONG> " verwenden zu können, müssen Sie ein Mitglied der RTCUniversalUserAdmins-Gruppe sein und über die Organisations Einheits Berechtigung für die OU verfügen, in der die Kontaktobjekte gespeichert sind. Die OU-Berechtigung kann mit dem <STRONG>Grant-OUPermission-</STRONG> Cmdlet gewährt werden.



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>So verschieben Sie Kontaktobjekte mithilfe der lync Server-Verwaltungsshell

1.  Öffnen Sie die lync Server-Verwaltungsshell.

2.  Geben Sie für jeden Pool, der bei Exchange um registriert ist (wobei pool1.contoso.net ein Pool aus der Bereitstellung von Office Communications Server 2007 R2 ist und pool2.contoso.net der Pool aus der lync Server 2013-Bereitstellung ist) in der Befehlszeile Folgendes ein:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Führen Sie das Cmdlet " **Get-CsExumContact** " aus, um zu überprüfen, ob die Kontaktobjekte verschoben wurden, und bestätigen Sie, dass **RegistrarPool** nun auf den neuen Pool zeigt.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>So führen Sie das exchucutil-Windows PowerShell-Skript aus

1.  Melden Sie sich beim Exchange um-Server als Benutzer mit Administrator Rechten für Exchange-Organisation an.

2.  Navigieren Sie zum Windows PowerShell-Skript exchucutil.
    
    In Exchange 2007 befindet sich exchucutil. ps1 unter: **% Program Files%\\Microsoft\\Exchange Server\\-Skripts\\exchucutil. ps1.**
    
    In Exchange 2010 befindet sich exchucutil. ps1 unter: **\\% Program Files% Microsoft\\Exchange Server\\V14\\Scripts\\exchucutil. ps1**

3.  Wenn Exchange in einer einzelnen Gesamtstruktur bereitgestellt wird, geben Sie Folgendes ein:
    
        exchucutil.ps1
    
    Wenn Exchange in mehreren Gesamtstrukturen bereitgestellt wird, geben Sie Folgendes ein:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    Dabei gibt Gesamtstruktur-FQDN die Gesamtstruktur an, in der lync Server 2013 bereitgestellt wird.
    
    <div>
    

    > [!IMPORTANT]  
    > Stellen Sie sicher, dass der <STRONG>lync Server-Front-End-</STRONG> Dienst (RtcSrv. exe) <EM>nach</EM> der Ausführung von exchucutil. ps1 neu gestartet wird. Andernfalls wird in lync Server 2013 Unified Messaging in der Topologie nicht erkannt.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

