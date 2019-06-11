---
title: 'Lync Server 2013: Bewährte Methoden für die Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89be654a01615c750ce4f49f866e9339bc7e261
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="1d5fa-102">Bewährte Methoden für die Anrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d5fa-102">Best practices for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d5fa-103">_**Letztes Änderungsdatum des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="1d5fa-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="1d5fa-104">Halten Sie sich bei der Bereitstellung der Anrufsteuerung an die folgenden bewährten Methoden, um die Leistung zu verbessern und die Bereitstellung zu vereinfachen:</span><span class="sxs-lookup"><span data-stu-id="1d5fa-104">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="1d5fa-105">Stellen Sie sicher, dass WANs für den aktuellen und den erwarteten Mediendatenverkehr angemessen ausgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="1d5fa-105">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d5fa-p101">Es empfiehlt sich, bei der Bandbreiteneinschränkungen einen Puffer einzurechnen. Manche Szenarien, z. B. Racebedingungen, wirken sich auf die verwendete Gesamtbandbreite aus und können zu Situationen führen, in denen die Bandbreitengrenze überschritten wird. Wenn beispielsweise zwei Anrufe gestartet werden, während der Mediendatenverkehr sich einer Bandbreitengrenze nähert, wird möglicherweise einer der beiden Anrufe abgewiesen, weil der andere zuerst gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="1d5fa-p101">We recommend that you factor in a buffer to your bandwidth limits. There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded. For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="1d5fa-109">Überwachen Sie die Netzwerkbelegung und die Kommunikationsdatensätze, damit Sie die optimalen Einstellungen für die Anrufsteuerung wählen und diese bei Änderungen in der Netzwerkbelegung aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="1d5fa-109">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="1d5fa-110">Verwenden Sie Richtlinien für die Anrufsteuerung zur Ergänzung der QoS-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="1d5fa-110">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="1d5fa-111">Wenn Sie blockierte Anrufe zum PSTN umleiten möchten, überprüfen Sie die Funktionalität und die Kapazität des PSTN.</span><span class="sxs-lookup"><span data-stu-id="1d5fa-111">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="1d5fa-112">Ausführliche Informationen finden Sie unter [Planen des ausgehenden VoIP-Routings in lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="1d5fa-112">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d5fa-113">„Kapazität“ bezieht sich auf die Anzahl der Ports, die Sie zur Unterstützung einer möglichen PSTN-Umleitung öffnen müssen.</span><span class="sxs-lookup"><span data-stu-id="1d5fa-113">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

