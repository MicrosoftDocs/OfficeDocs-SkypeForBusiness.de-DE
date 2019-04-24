---
title: Medienqualitäts-Diagnoseberichte in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
description: 'Zusammenfassung: Lernen Sie die Medienqualitäts-Diagnoseberichte in Skype für Business Server.'
ms.openlocfilehash: a7861d60e9108dcf599c5cecee9a678248715e44
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197534"
---
# <a name="media-quality-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="4f4b6-103">Medienqualitäts-Diagnoseberichte in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="4f4b6-103">Media Quality Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="4f4b6-104">**Zusammenfassung:** Lernen Sie die Medienqualitäts-Diagnoseberichte in Skype für Business Server aus.</span><span class="sxs-lookup"><span data-stu-id="4f4b6-104">**Summary:** Learn about the Media Quality Diagnostic Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="4f4b6-105">Die Medienqualitäts-Diagnoseberichte bieten Informationen über die Anrufqualität sowie Diagnosedaten und Hinweise zur Problembehandlung für Anrufe, bei denen Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="4f4b6-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="4f4b6-106">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="4f4b6-106">In this section</span></span>

- <span data-ttu-id="4f4b6-107">[Zusammenfassender Bericht über Medienqualität in Skype für Business Server](summary.md) Stellt allgemeine Qualitätsdaten für verschiedene Endpunkttypen, einschließlich Enterprise-VoIP-Peer-zu-Peer-Anrufe, Enterprise-VoIP-Telefonkonferenzen und Anrufe, die abhängig sind, zumindest teilweise, in der öffentlichen gewechselt Telefonnetz (PSTN).</span><span class="sxs-lookup"><span data-stu-id="4f4b6-107">[Media Quality Summary Report in Skype for Business Server](summary.md) Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="4f4b6-108">[Media Quality Comparison Report in Skype für Business Server](comparison.md) Bietet einen Vergleich der Anruf Qualitätswerte für verschiedene Typen von Audioanrufe (beispielsweise Anrufe über ein drahtloses Netzwerk im Vergleich zu Anrufe über eine drahtgebundene Verbindung).</span><span class="sxs-lookup"><span data-stu-id="4f4b6-108">[Media Quality Comparison Report in Skype for Business Server](comparison.md) Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>
    
- <span data-ttu-id="4f4b6-109">[Server Performance Report in Skype für Business Server](server-performance.md) Listet die Server, auf dem die meisten Probleme, basierend auf Messungen von solchen wichtige Qualitätsmetriken als Beeinträchtigung, Jitter und Paketverlust aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="4f4b6-109">[Server Performance Report in Skype for Business Server](server-performance.md) Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="4f4b6-110">[Standortbericht in Skype für Business Server](location-report.md) Enthält eine Liste von Netzwerkadressen und eine Übersicht über die Medienqualität der Anrufe, die an jedem Standort auftreten.</span><span class="sxs-lookup"><span data-stu-id="4f4b6-110">[Location Report in Skype for Business Server](location-report.md) Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="4f4b6-111">Aus Gründen der in diesem Bericht basiert auf IP-Subnetze Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="4f4b6-111">For purposes of this report, locations are based on IP subnets.</span></span>
    
- <span data-ttu-id="4f4b6-112">[Device Report in Skype für Business Server](device-report.md) Bietet eine Übersicht über die Geräte, die für Enterprise-VoIP- Anrufe verwendeten Angaben zur durchschnittlichen Medienqualität der Anrufe, aufgeschlüsselt nach Gerät enthält.</span><span class="sxs-lookup"><span data-stu-id="4f4b6-112">[Device Report in Skype for Business Server](device-report.md) Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>
    
- <span data-ttu-id="4f4b6-113">[Call List Report in Skype für Business Server](call-list-report-0.md) Enthält ausführliche Informationen zu den Anrufen geführte oder in Ihrer Organisation eingingen.</span><span class="sxs-lookup"><span data-stu-id="4f4b6-113">[Call List Report in Skype for Business Server](call-list-report-0.md) Provides detailed information about phone calls made or received within your organization.</span></span>
    
- <span data-ttu-id="4f4b6-114">[Aufrufdetailbericht in Skype für Business Server](call-detail-report.md) Enthält ausführliche Informationen zu den anrufen, die aus oder in Ihrer Organisation eingingen.</span><span class="sxs-lookup"><span data-stu-id="4f4b6-114">[Call Detail Report in Skype for Business Server](call-detail-report.md) Provides detailed information about phone calls made from or received within your organization.</span></span>
    
- <span data-ttu-id="4f4b6-115">[Server Trendbericht über Medienqualität in Skype für Business Server](server-media-quality-trend-report.md) Bietet eine Möglichkeit für Sie bis zu fünf Servern auf Quality of Experience-Metriken wie Anrufvolumen, Prozentsatz der Anrufe schlechter Qualität, Jitter und Paketverlust grafisch zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="4f4b6-115">[Server Media Quality Trend Report in Skype for Business Server](server-media-quality-trend-report.md) Provides a way for you to graphically compare up to five servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="4f4b6-116">[Vom Media Quality Metrics Distribution Report in Skype für Business Server](media-quality-metrics-distribution-report.md) Enthält ein Diagramm, das die Verteilung Werte für Quality of Experience Metrik wie Jitter oder Paketverlusten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="4f4b6-116">[The Media Quality Metrics Distribution Report in Skype for Business Server](media-quality-metrics-distribution-report.md) Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>
    
- <span data-ttu-id="4f4b6-117">[Standort-Trendbericht in Skype für Business Server](location-trend-report.md) Informationen Anrufqualität Trend zur Netzwerkadressen.</span><span class="sxs-lookup"><span data-stu-id="4f4b6-117">[Location Trend Report in Skype for Business Server](location-trend-report.md) Provides call quality trend information for network locations.</span></span>
    

