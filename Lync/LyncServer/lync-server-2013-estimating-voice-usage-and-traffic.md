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
# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a><span data-ttu-id="358e6-103">Schätzen der VoIP-Nutzung und des Datenverkehrs für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="358e6-103">Estimating voice usage and traffic for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="358e6-104">_**Letztes Änderungsstand des Themas:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="358e6-104">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="358e6-105">Im Planungs Tool Microsoft lync Server 2013 wird die folgende Metrik verwendet, um den Benutzerdatenverkehr an jedem Standort und die Anzahl der Ports, die zur Unterstützung des Datenverkehrs erforderlich sind, zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="358e6-105">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>

  - <span></span>  
    <span data-ttu-id="358e6-106">Für **geringes Datenaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.</span><span class="sxs-lookup"><span data-stu-id="358e6-106">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="358e6-107">Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.</span><span class="sxs-lookup"><span data-stu-id="358e6-107">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="358e6-108">Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.</span><span class="sxs-lookup"><span data-stu-id="358e6-108">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>

<span data-ttu-id="358e6-109">Die Anzahl der Ports wiederum bestimmt die Anzahl von Vermittlungsservern und Gateways, die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="358e6-109">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="358e6-110">Die PSTN-Gateways (Public Switched Telephone Network), die in den meisten Organisationen in der Größe von 2 Ports auf bis zu 960 Ports bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="358e6-110">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="358e6-111">(Es gibt sogar größere Gateways, die jedoch hauptsächlich von Telefoniedienstanbieter verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="358e6-111">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>

<span data-ttu-id="358e6-p102">Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="358e6-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

