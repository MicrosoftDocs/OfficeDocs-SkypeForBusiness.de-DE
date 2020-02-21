---
title: 'Lync Server 2013: medienumgehung und Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10915a298fe2e50abdef09dc5acf92927a43cc65
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a>Medienumgehung und Anrufsteuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

Medienumgehung und Anrufsteuerung (Call Admission Control, CAC) arbeiten zusammen, um eine Bandbreitensteuerung für den Mediendatenverkehr bei Anrufen zu erzielen.  Die Medienumgehung fördert den Mediendatenfluss über Leitungen mit guter Konnektivität; die Anrufsteuerung verwaltet den Datenverkehr für Verbindungen mit Bandbreiteneinschränkungen. Da Medienumgehung und Anrufsteuerung sich gegenseitig ausschließen, müssen Sie bei der Planung die jeweils andere Funktion berücksichtigen. Die folgenden Kombinationen werden unterstützt:

  - Sowohl Anrufsteuerung als auch Medienumgehung sind aktiviert. Die Medienumgehung muss auf **Informationen zu Standort und Region verwenden** festgelegt sein. Die Informationen zu Standort und Region sind dieselben wie für die Anrufsteuerung.
    
    Wenn Sie die Anrufsteuerung aktivieren, können Sie die Option **Immer umgehen** nicht auswählen (und umgekehrt), da die zwei Konfigurationen sich gegenseitig ausschließen. Dies bedeutet, dass jeweils nur eine der zwei Optionen auf einen PSTN-Anruf angewendet wird. Zunächst wird überprüft, ob für den Anruf die Medienumgehung gilt. Ist dies der Fall, wird die Anrufsteuerung nicht verwendet. Dies ist plausibel, da ein für die Medienumgehung aktivierter Anruf per Definition eine Verbindung verwendet, für die eine Anrufsteuerung nicht notwendig ist. Wenn die Medienumgehung nicht auf den Anruf angewendet werden kann (d. h. die Umgehungs-ID von Client und Gateway stimmen nicht überein), wird die Anrufsteuerung auf den Anruf angewendet.

  - Die Anrufsteuerung ist nicht aktiviert, und die Medienumgehung ist auf **Immer umgehen** festgelegt.
    
    In dieser Konfiguration sind sowohl Client- als auch Trunksubnetze einer einzigen ID für die Umgehung zugeordnet, die durch das System berechnet wird.

  - Die Anrufsteuerung ist nicht aktiviert, und die Medienumgehung ist auf **Informationen zu Standort und Region verwenden** festgelegt.
    
    Wenn die Option **Informationen zu Standort und Region verwenden** aktiviert ist, funktioniert die Umgehungsermittlung im Prinzip in gleicher Weise – unabhängig davon, ob die Anrufsteuerung aktiviert ist oder nicht. Dies bedeutet, dass für einen PSTN-Anruf das Clientsubnetz einem bestimmten Standort zugeordnet ist, und die Umgehungs-ID für dieses Subnetz extrahiert wird. Ebenso ist das Gatewaysubnetz einem bestimmten Standort zugeordnet, und die Umgehungs-ID für dieses Subnetz wird extrahiert. Nur wenn die zwei Umgehungs-IDs identisch sind, findet eine Medienumgehung für den Anruf statt. Unterscheiden sich die IDs, findet keine Medienumgehung statt.
    
    Selbst wenn die Anrufsteuerung global deaktiviert wurde, müssen Bandbreitenrichtlinien für jeden Standort und jede Verbindung definiert werden, wenn die Konfiguration von Standorten und Regionen für Entscheidungen zur Medienumgehung herangezogen werden soll. Der tatsächliche Wert der Bandbreiteneinschränkung oder die Modalität spielen hierbei keine Rolle. Das Ziel besteht darin, dass das System automatisch unterschiedliche Umgehungs-IDs berechnet, die verschiedenen Standorten ohne gute Verbindung zugeordnet sind. Das Definieren einer Bandbreiteneinschränkung bedeutet per Definition, dass eine Verbindung keine gute Konnektivität aufweist.

  - Weder die Anrufsteuerung noch die Medienumgehung sind aktiviert. Dieser Fall tritt nur ein, wenn alle Gateways und IP-Nebenstellenanlagen über Leitungen mit geringer Konnektivität verbunden sind oder andere Anforderungen für die Medienumgehung nicht erfüllen. Ausführliche Informationen zu den Anforderungen für die medienumgehung finden Sie unter [Technical Requirements for Media Bypass in lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).

<div>

## <a name="see-also"></a>Siehe auch


[Übersicht über die medienumgehung in lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Medien Umgehungs Modi in lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Technische Anforderungen für die medienumgehung in lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

