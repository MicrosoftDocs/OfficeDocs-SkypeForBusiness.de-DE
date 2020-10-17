---
title: 'Lync Server 2013: Diagnoseberichte für Medienqualität'
description: 'Lync Server 2013: Diagnoseberichte für Medienqualität.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e346d0f9b8997158cb926ad830d5477950e846d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548211"
---
# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="f44f8-103">Diagnoseberichte zur Medienqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44f8-103">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f44f8-104">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f44f8-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f44f8-105">Die Medienqualitäts-Diagnoseberichte bieten Informationen über die Anrufqualität sowie Diagnosedaten und Hinweise zur Problembehandlung für Anrufe, bei denen Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="f44f8-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f44f8-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f44f8-106">In This Section</span></span>

  - <span data-ttu-id="f44f8-107">[Zusammenfassender Bericht über Medienqualität in lync Server 2013](lync-server-2013-media-quality-summary-report.md)     Stellt allgemeine Qualitätsdaten für unterschiedliche Endpunkttypen bereit, einschließlich Enterprise-VoIP-Peer-zu-Peer-Anrufe, Enterprise-VoIP-Konferenzanrufe und Anrufe, die mindestens teilweise im Telefon Festnetz (Public Switched Telephone Network, PSTN) basieren.</span><span class="sxs-lookup"><span data-stu-id="f44f8-107">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="f44f8-108">[Vergleichsbericht über Medienqualität in lync Server 2013](lync-server-2013-media-quality-comparison-report.md)     Bietet einen Vergleich der Werte für die Anrufqualität für verschiedene Arten von Audioanrufen (beispielsweise Anrufe über ein drahtloses Netzwerk im Vergleich zu anrufen, die über eine kabelgebundene Verbindung hergestellt werden).</span><span class="sxs-lookup"><span data-stu-id="f44f8-108">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="f44f8-109">[Bericht über die Server Leistung in lync Server 2013](lync-server-2013-server-performance-report.md)     Listet die Server auf, auf denen die meisten Probleme aufgetreten sind, basierend auf den Messungen dieser wichtigen Qualitäts Metriken wie Verschlechterung, Paketverlust und Jitter.</span><span class="sxs-lookup"><span data-stu-id="f44f8-109">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="f44f8-110">[Standortbericht in lync Server 2013](lync-server-2013-location-report.md)     Enthält eine Liste von Netzwerkstandorten und eine Zusammenfassung der Medienqualität der Anrufe, die an jedem Standort stattfinden.</span><span class="sxs-lookup"><span data-stu-id="f44f8-110">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="f44f8-111">Für diesen Bericht basieren Standorte auf IP-Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="f44f8-111">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="f44f8-112">[Gerätebericht in lync Server 2013](lync-server-2013-device-report.md)     Enthält eine Zusammenfassung der Geräte, die für Enterprise-VoIP-Anrufe verwendet werden, und enthält die durchschnittliche Medienqualität der Anrufe nach Gerät.</span><span class="sxs-lookup"><span data-stu-id="f44f8-112">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="f44f8-113">[Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md)     Enthält detaillierte Informationen zu Telefon anrufen, die in Ihrer Organisation getätigt oder empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="f44f8-113">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="f44f8-114">[Anruf Detail Bericht in lync Server 2013](lync-server-2013-call-detail-report.md)     Enthält detaillierte Informationen zu Telefon anrufen, die in Ihrer Organisation getätigt oder empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="f44f8-114">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="f44f8-115">[Trend Bericht über Server Medienqualität in lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)     Bietet Ihnen die Möglichkeit, bis zu fünf Server mit Metriken für die Qualität der Benutzerfreundlichkeit, wie Anruflautstärke, Prozentsatz der Anruf Rate, Paketverlust und Jitter, grafisch zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="f44f8-115">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="f44f8-116">[Der Verteilungs Bericht zur Medien Qualitätsmetrik in lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)     Stellt ein Diagramm zur Verfügung, in dem die Verteilungswerte für eine Metrik mit hoher Benutzerfreundlichkeit wie Jitter oder Paketverlust angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f44f8-116">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="f44f8-117">[Standort Trend Bericht in lync Server 2013](lync-server-2013-location-trend-report.md)     Bietet Trendinformationen zur Anrufqualität für Netzwerkstandorte.</span><span class="sxs-lookup"><span data-stu-id="f44f8-117">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

