---
title: 'Lync Server 2013: Stellvertretung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82be0bdc382440cc8a4307dc0ba981f31c5a9313
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a>Stellvertretung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-09_

Die Delegierungsfunktionen in lync sind auf die folgende Weise vom standortbasierten Routing betroffen:

  - Wenn eine für standortbasierte Weiterleitung aktivierte Stellvertretung einen Anruf im Auftrag eines Managers anbietet, wird die VoIP-Richtlinie des Stellvertreters verwendet, um den Anruf zu genehmigen, und die VoIP-Routing Richtlinie des Stellvertreters wird zum Weiterleiten des Anrufs verwendet.

  - Für eingehende Anrufe aus dem öffentlichen Telefonnetz für einen Vorgesetzten gelten die gleichen Regeln wie für Anrufweiterleitung oder paralleles Anrufen, wie in den Themen zur Anrufweiterleitung und -durchstellung bzw. zum parallelen Anrufen beschrieben.

  - Wenn eine Stellvertretung einen Endpunkt im öffentlichen Telefonnetz als Ziel für paralleles Anrufen festlegt, wird bei einem für den Vorgesetzten eingehenden Anruf die VoIP-Routingrichtlinie des Standorts, der dem eingehenden Trunk zugeordnet ist, für das Routen des Anrufs an den Endpunkt der Stellvertretung im öffentlichen Telefonnetz verwendet.

  - Für Stellvertretungen empfiehlt es sich, dass der Vorgesetzte und die ihm zugeordneten Stellvertretungen sich normalerweise am gleichen Netzwerkstandort befinden.

<div>

## <a name="see-also"></a>Siehe auch


[Szenarien für das standortbasierte Routing in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

