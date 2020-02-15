---
title: 'Lync Server 2013: medienumgehung und Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 426499da4659548d90ed2160c23a905565edddd6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Medienumgehung und Vermittlungsserver in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Die medienumgehung ist eine lync Server Funktion, mit der ein Administrator das Anrufrouting so konfigurieren kann, dass es direkt zwischen dem Benutzer Endpunkt und dem PSTN-Gateway (Public Switched Telephone Network) fließt, ohne das Vermittlungsserver zu durchlaufen. Durch die medienumgehung wird die Anrufqualität verbessert, da Wartezeit, unnötige Übersetzung, Möglichkeit von Paketverlusten und die Anzahl potenzieller Fehlerpunkte reduziert werden. Wenn ein Remotestandort ohne Vermittlungsserver über eine oder mehrere WAN-Verbindungen mit eingeschränkter Bandbreite mit einem zentralen Standort verbunden ist, verringert die medienumgehung die Bandbreitenanforderung, indem Medien von einem Client an einem Remotestandort direkt an das lokale Gateway weiter fließen können, ohne dass Zunächst müssen Sie über die WAN-Verbindung zu einem Vermittlungsserver am zentralen Standort und zurückfließen. Diese Verringerung der Medienverarbeitung ergänzt auch die Fähigkeit der Vermittlungsserver, mehrere Gateways zu steuern.

Die Medienumgehung und die Anrufsteuerung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung implementiert wird, wird für diesen Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden.

<div>

## <a name="see-also"></a>Siehe auch


[Anrufsteuerung und Vermittlungsserver in lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)  


[Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

