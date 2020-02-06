---
title: Diagnoseberichte für Medienqualität in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
description: 'Zusammenfassung: erfahren Sie mehr über die diagnostischen Berichte zur Medienqualität in Skype for Business Server.'
ms.openlocfilehash: e02ea51681b31b524bf87005e7c4b4fcf48bef62
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817864"
---
# <a name="media-quality-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="3ec38-103">Diagnoseberichte für Medienqualität in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3ec38-103">Media Quality Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="3ec38-104">**Zusammenfassung:** Informieren Sie sich über die diagnostischen Berichte zur Medienqualität in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3ec38-104">**Summary:** Learn about the Media Quality Diagnostic Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="3ec38-105">Die Medienqualitäts-Diagnoseberichte bieten Informationen über die Anrufqualität sowie Diagnosedaten und Hinweise zur Problembehandlung für Anrufe, bei denen Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="3ec38-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="3ec38-106">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="3ec38-106">In this section</span></span>

- <span data-ttu-id="3ec38-107">[Zusammenfassungsbericht für Medienqualität in Skype for Business Server](summary.md) Bietet allgemeine Qualitätsdaten für unterschiedliche Endpunkttypen, darunter Enterprise-VoIP-Peer-to-Peer-Anrufe, Enterprise-VoIP-Konferenzanrufe und Anrufe, die zumindest teilweise auf dem öffentlichen Telefonnetz (PSTN) beruhen.</span><span class="sxs-lookup"><span data-stu-id="3ec38-107">[Media Quality Summary Report in Skype for Business Server](summary.md) Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="3ec38-108">[Bericht zum Vergleich der Medienqualität in Skype for Business Server](comparison.md) Bietet einen Vergleich der Werte für die Anrufqualität für verschiedene Arten von Audioanrufen (beispielsweise Anrufe, die über ein Drahtlosnetzwerk getätigt wurden, und Anrufe, die über eine Kabelverbindung erfolgen).</span><span class="sxs-lookup"><span data-stu-id="3ec38-108">[Media Quality Comparison Report in Skype for Business Server](comparison.md) Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>
    
- <span data-ttu-id="3ec38-109">[Bericht zur Server Leistung in Skype for Business Server](server-performance.md) Listet die Server auf, bei denen die meisten Probleme aufgetreten sind, basierend auf der Messung solcher wichtigen Qualitäts Metriken wie Degradation, Paketverlust und Jitter.</span><span class="sxs-lookup"><span data-stu-id="3ec38-109">[Server Performance Report in Skype for Business Server](server-performance.md) Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="3ec38-110">[Standortbericht in Skype for Business Server](location-report.md) Enthält eine Liste der Netzwerkspeicherorte und eine Zusammenfassung der Medienqualität der Anrufe, die an jedem Standort erfolgen.</span><span class="sxs-lookup"><span data-stu-id="3ec38-110">[Location Report in Skype for Business Server](location-report.md) Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="3ec38-111">Für die Zwecke dieses Berichts basieren Speicherorte auf IP-Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="3ec38-111">For purposes of this report, locations are based on IP subnets.</span></span>
    
- <span data-ttu-id="3ec38-112">[Gerätebericht in Skype for Business Server](device-report.md) Enthält eine Zusammenfassung der Geräte, die für Enterprise-VoIP-Anrufe verwendet werden, und umfasst die durchschnittliche Medienqualität der Anrufe nach Gerät.</span><span class="sxs-lookup"><span data-stu-id="3ec38-112">[Device Report in Skype for Business Server](device-report.md) Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>
    
- <span data-ttu-id="3ec38-113">[Bericht zur Anrufliste in Skype for Business Server](call-list-report-0.md) Enthält detaillierte Informationen zu Telefon anrufen, die in Ihrer Organisation getätigt oder empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="3ec38-113">[Call List Report in Skype for Business Server](call-list-report-0.md) Provides detailed information about phone calls made or received within your organization.</span></span>
    
- <span data-ttu-id="3ec38-114">[Anruf Detail Bericht in Skype for Business Server](call-detail-report.md) Enthält detaillierte Informationen zu Telefon anrufen, die in Ihrer Organisation getätigt oder empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="3ec38-114">[Call Detail Report in Skype for Business Server](call-detail-report.md) Provides detailed information about phone calls made from or received within your organization.</span></span>
    
- <span data-ttu-id="3ec38-115">[Trend Bericht zur Server Medienqualität in Skype for Business Server](server-media-quality-trend-report.md) Bietet eine Möglichkeit, bis zu fünf Server auf der Grundlage der Qualität von Erfahrungswerten wie Anruflautstärke, schlechter Anruf Prozentsatz, Paketverlust und Jitter grafisch zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="3ec38-115">[Server Media Quality Trend Report in Skype for Business Server](server-media-quality-trend-report.md) Provides a way for you to graphically compare up to five servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="3ec38-116">[Der Verteilungs Bericht zur Medien Qualitätsmetrik in Skype for Business Server](media-quality-metrics-distribution-report.md) Stellt ein Diagramm bereit, in dem die Verteilungswerte für eine Qualität der Erfahrungs Metrik wie Jitter oder Paketverlust angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3ec38-116">[The Media Quality Metrics Distribution Report in Skype for Business Server](media-quality-metrics-distribution-report.md) Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>
    
- <span data-ttu-id="3ec38-117">[Standort Trend Bericht in Skype for Business Server](location-trend-report.md) Bietet Trendinformationen zur Anrufqualität für Netzwerkspeicherorte.</span><span class="sxs-lookup"><span data-stu-id="3ec38-117">[Location Trend Report in Skype for Business Server](location-trend-report.md) Provides call quality trend information for network locations.</span></span>
    

