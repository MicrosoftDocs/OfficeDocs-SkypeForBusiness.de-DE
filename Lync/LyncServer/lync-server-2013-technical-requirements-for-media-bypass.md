---
title: 'Lync Server 2013: technische Anforderungen für die medienumgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad685e59616f7f2a90cc8a9d3feb5f4ea669587
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Technische Anforderungen für die medienumgehung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Für jeden Anruf im PSTN bestimmt der Vermittlungsserver, ob Medien aus dem lync-Endpunkt des Ursprungs direkt an einen Vermittlungsserver Peer gesendet werden können, ohne das Vermittlungsserver zu durchlaufen. Der Peer kann ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) bei einem Anbieter von Internettelefoniediensten sein, der zu der Leitung zwischen dem Vermittlungsserver gehört, bei dem der Anruf weitergeleitet wird.

Die Medienumgehung kann implementiert werden, wenn die folgenden Voraussetzungen erfüllt sind:

  - Ein Vermittlungsserver Peer muss die erforderlichen Funktionen für die medienumgehung unterstützen, wobei es sich dabei um die Möglichkeit handelt, mehrere gegabelte Antworten zu verarbeiten ("frühe Dialoge" genannt). Wenden Sie sich an den Hersteller Ihres Gateways oder Ihrer Nebenstellenanlage oder an Ihr ITSP, um den Wert für die maximale Anzahl von frühzeitigen Dialogen zu erhalten, die das Gateway, die Nebenstellenanlage oder der SBC annehmen kann.

  - Der Vermittlungsserver Peer muss den Mediendatenverkehr direkt von lync-Endpunkten akzeptieren. Viele internettelefoniediensten ermöglichen, dass Ihr SBC nur Datenverkehr aus dem Vermittlungsserver empfängt. Wenden Sie sich an Ihren ITSP, um zu ermitteln, ob der SBC Mediendatenverkehr direkt von lync-Endpunkten akzeptiert.

  - Lync-Clients und ein Vermittlungsserver Peer müssen gut verbunden sein, was bedeutet, dass Sie sich entweder in derselben netzwerkregion oder an Netzwerkstandorten befinden, die über WAN-Verbindungen, die keine Bandbreiteneinschränkungen aufweisen, eine Verbindung mit der Region herstellen.

<div>

## <a name="see-also"></a>Siehe auch


[Medien Umgehungs Modi in lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Medienumgehung und Anrufsteuerung in lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

