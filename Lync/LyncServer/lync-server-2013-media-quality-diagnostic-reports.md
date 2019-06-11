---
title: 'Lync Server 2013: Diagnoseberichte für Medienqualität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05836ea853c89b132d39eaaba1b66056fa958072
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="103cf-102">Berichte zur Medien Qualitäts Diagnose in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="103cf-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="103cf-103">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="103cf-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="103cf-104">Die Medienqualitäts-Diagnoseberichte bieten Informationen über die Anrufqualität sowie Diagnosedaten und Hinweise zur Problembehandlung für Anrufe, bei denen Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="103cf-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="103cf-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="103cf-105">In This Section</span></span>

  - <span data-ttu-id="103cf-106">[Zusammenfassungsbericht für Medienqualität in lync Server 2013](lync-server-2013-media-quality-summary-report.md)   bietet allgemeine Qualitätsdaten für unterschiedliche Endpunkttypen, einschließlich Peer-to-Peer-Anrufen für Unternehmens-VoIP, Enterprise-VoIP-Konferenzanrufe und Anrufe, die zumindest teilweise für die Öffentlichkeit angewiesen sind. Switched Telephone Network (PSTN).</span><span class="sxs-lookup"><span data-stu-id="103cf-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="103cf-107">[Der Bericht zur Medien Qualitäts Vergleichsfunktion in lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   bietet einen Vergleich der Werte für die Anrufqualität für verschiedene Arten von Audioanrufen (beispielsweise Anrufe, die über ein Drahtlosnetzwerk getätigt wurden, und Anrufe, die über eine Kabelverbindung erfolgen).</span><span class="sxs-lookup"><span data-stu-id="103cf-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="103cf-108">[Serverleistungsbericht in lync Server 2013](lync-server-2013-server-performance-report.md)   listet die Server auf, bei denen die meisten Probleme aufgetreten sind, basierend auf der Messung solcher wichtigen Qualitäts Metriken wie Abbau, Paketverlust und Jitter.</span><span class="sxs-lookup"><span data-stu-id="103cf-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="103cf-109">[Standortbericht in lync Server 2013](lync-server-2013-location-report.md)   enthält eine Liste der Netzwerkspeicherorte und eine Zusammenfassung der Medienqualität der Anrufe, die an jedem Standort erfolgen.</span><span class="sxs-lookup"><span data-stu-id="103cf-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="103cf-110">Für die Zwecke dieses Berichts basieren Speicherorte auf IP-Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="103cf-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="103cf-111">[Der gerätebericht in lync Server 2013](lync-server-2013-device-report.md)   bietet eine Zusammenfassung der Geräte, die für Enterprise-VoIP-Anrufe verwendet werden, und enthält die durchschnittliche Medienqualität der Anrufe nach Gerät.</span><span class="sxs-lookup"><span data-stu-id="103cf-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="103cf-112">[Der Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md)   enthält detaillierte Informationen zu Telefon anrufen, die in Ihrer Organisation getätigt oder empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="103cf-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="103cf-113">[Der Anruf Detail Bericht in lync Server 2013](lync-server-2013-call-detail-report.md)   enthält detaillierte Informationen zu Telefon anrufen, die in Ihrer Organisation getätigt oder empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="103cf-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="103cf-114">[Der Trend Bericht "Server Medienqualität" in lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   bietet eine Möglichkeit, bis zu 5 Server auf der Grundlage der Qualität von Erfahrungswerten wie Anruflautstärke, schlechtem Anruf Prozentsatz, Paketverlust und Jitter grafisch zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="103cf-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="103cf-115">[Der Verteilungs Bericht für Medien Qualitäts Metriken in lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   bietet ein Diagramm, in dem die Verteilungswerte für eine Qualität der Erfahrungs Metrik wie Jitter oder Paketverlust angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="103cf-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="103cf-116">[Der Standort Trendbericht in lync Server 2013](lync-server-2013-location-trend-report.md)   bietet Trendinformationen zur Anrufqualität für Netzwerkspeicherorte.</span><span class="sxs-lookup"><span data-stu-id="103cf-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

