---
title: 'Lync Server 2013: abschätzen der VoIP-Nutzung und des Datenverkehrs'
description: 'Lync Server 2013: einschätzen der VoIP-Nutzung und des Datenverkehrs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc288e6da65e8e6f221a05c6c82f0588414c8af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555011"
---
# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a>Schätzen der VoIP-Nutzung und des Datenverkehrs für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-08-07_

Im Planungs Tool Microsoft lync Server 2013 wird die folgende Metrik verwendet, um den Benutzerdatenverkehr an jedem Standort und die Anzahl der Ports, die zur Unterstützung des Datenverkehrs erforderlich sind, zu schätzen.

  - <span></span>  
    Für **geringes Datenaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.

  - <span></span>  
    Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.

  - <span></span>  
    Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.

Die Anzahl der Ports wiederum bestimmt die Anzahl von Vermittlungsservern und Gateways, die erforderlich sind. Die PSTN-Gateways (Public Switched Telephone Network), die in den meisten Organisationen in der Größe von 2 Ports auf bis zu 960 Ports bereitgestellt werden. (Es gibt sogar größere Gateways, die jedoch hauptsächlich von Telefoniedienstanbieter verwendet werden.)

Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.

</div>

<span> </span>

</div>

</div>

</div>

