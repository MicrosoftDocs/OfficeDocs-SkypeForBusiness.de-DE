---
title: Anruf Analyse- und Anrufqualität Dashboard
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Learn about Call Analytics and Call Quality Dashboard and when to use them to monitor and troubleshoot call-quality problems in Skype for Business.
ms.openlocfilehash: 3871db21fef268f9589246b31ee285aa117d0412
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205086"
---
# <a name="call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="f343f-103">Anruf Analyse- und Anrufqualität Dashboard</span><span class="sxs-lookup"><span data-stu-id="f343f-103">Call Analytics and Call Quality Dashboard</span></span>

<span data-ttu-id="f343f-104">Microsoft-Teams und Skype für Unternehmen bieten Ihnen zwei Möglichkeiten zur Überwachung und Problembehandlung Anrufqualität: Analytics aufrufen, und rufen Sie Qualitätsdashboard.</span><span class="sxs-lookup"><span data-stu-id="f343f-104">Microsoft Teams and Skype for Business give you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard.</span></span> <span data-ttu-id="f343f-105">In diesem Artikel werden beide Methoden beschrieben, und Sie erfahren, welche Sie jeweils verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="f343f-105">This article describes both and tells you when to use each one.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f343f-106">Anruf Analytics ist jetzt verfügbar in den Microsoft-Teams und Skype für Business Administrationscenter unter https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f343f-106">Call Analytics is now available in the Microsoft Teams and Skype for Business admin center at https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="f343f-107">Nur letzte 30 Tagen von Daten ist in Aufrufen Analytics verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f343f-107">Only last 30 days of data is available in Call Analytics.</span></span>
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="f343f-108">Was ist die Anrufanalyse, und wann sollte ich sie verwenden?</span><span class="sxs-lookup"><span data-stu-id="f343f-108">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="f343f-109">Anruf Analytics zeigt detaillierte Informationen zu den Geräten, Netzwerke und im Zusammenhang mit der bestimmte Aufrufe und Besprechungen für jeden Benutzer in einem Microsoft-Teams oder Skype für Konto Business Connectivity.</span><span class="sxs-lookup"><span data-stu-id="f343f-109">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="f343f-110">Wenn Sie ein Office 365-Administrator sind, können Sie Analytics Aufrufen von Anruf Qualität und Verbindung Problemen in Microsoft-Teams und Skype für Unternehmen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f343f-110">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems in Microsoft Teams and Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="f343f-111">Helpdesk-Agent-Berechtigungen und Netzwerk-Topologie hochladen verfügbar in das neue Administratorportal in den nächsten Monaten.</span><span class="sxs-lookup"><span data-stu-id="f343f-111">Helpdesk agent permissions and network topology upload will be available in the new admin portal in the coming months.</span></span>

<span data-ttu-id="f343f-112">Wenn Sie Benutzern ohne Administratorrechte (zum Beispiel Helpdesk-Agents eines externen Anbieters) die Verwendung der Anrufanalyse ermöglichen möchten, können Sie ihnen entsprechende Berechtigungen zuweisen, sodass sie zwar die Anrufanalyse verwenden, aber auf die übrigen Funktionen im Skype for Business Admin Center nicht zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="f343f-112">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics but they can't access the rest of the Skype for Business Admin center:</span></span> 
  
- <span data-ttu-id="f343f-p104">**Helpdesk-Agents mit Berechtigungen der Stufe 1**: Die Agents sehen in der Anrufanalyse in begrenztem Umfang Daten und personenbezogene Informationen. Sie können Problembehandlungen für Anrufe ausführen, müssen aber Probleme mit Besprechungen an einen Agent der Stufe 2 weitergeben.</span><span class="sxs-lookup"><span data-stu-id="f343f-p104">**Helpdesk agents with Tier 1 permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics. They can troubleshoot calls, but they will hand off problems with meetings to a Tier 2 agent.</span></span>
    
- <span data-ttu-id="f343f-p105">**Helpdesk-Agents mit Berechtigungen der Stufe 2**: Die Agents sehen in der Anrufanalyse alle verfügbaren Daten und führen Problembehandlungen für Anrufe und Besprechungen aus. Sie haben Vollzugriff auf Anruflisten und Kundeninformationen.</span><span class="sxs-lookup"><span data-stu-id="f343f-p105">**Helpdesk agents with Tier 2 permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings. They have full access to call logs and customer information.</span></span>
    
<span data-ttu-id="f343f-117">Details zum Einrichten der Anrufanalyse finden Sie unter [Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md).</span><span class="sxs-lookup"><span data-stu-id="f343f-117">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="f343f-118">Weitere Informationen zur Funktionsweise von Helpdesk-Agents mit Analysen aufrufen können finden Sie unter [Verwendung aufrufen Analytics für die Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span><span class="sxs-lookup"><span data-stu-id="f343f-118">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="f343f-119">Was ist das Anrufqualitätsdashboard, und wann sollte ich es verwenden?</span><span class="sxs-lookup"><span data-stu-id="f343f-119">What's the Call Quality Dashboard, and when should I use it?</span></span>

<span data-ttu-id="f343f-120">Die Anrufanalyse liefert Ihnen detaillierte, spezifische Informationen zu der Anrufqualität, die die Benutzer wahrnehmen.</span><span class="sxs-lookup"><span data-stu-id="f343f-120">Call Analytics gives you detailed, specific information about the call quality experienced by users.</span></span> <span data-ttu-id="f343f-121">Warum hatte der Benutzer Tony Smith heute Nachmittag einen Anruf mit schlechter Qualität?</span><span class="sxs-lookup"><span data-stu-id="f343f-121">Why did user Tony Smith have a poor call this afternoon?</span></span> <span data-ttu-id="f343f-122">Analytics anrufen verwenden, kann eine Microsoft-Teams oder Skype für Business Admin oder geschult Helpdesk-Agent des Geräts, Netzwerk, Konnektivität und anderen Faktoren im Zusammenhang mit Tony Anruf untersuchen.</span><span class="sxs-lookup"><span data-stu-id="f343f-122">Using Call Analytics, a Microsoft Teams or Skype for Business admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to Tony's call.</span></span>
  
<span data-ttu-id="f343f-p108">Während die Anrufanalyse dazu gedacht ist, Administratoren und Helpdesk-Agents bei der Behandlung von Problemen mit der Anrufqualität bei bestimmten Anrufen zu unterstützen, soll das Anrufqualitätsdashboard Skype for Business-Administratoren und Netzwerktechnikern beim Optimieren von Netzwerken helfen. Das Anrufqualitätsdashboard stellt nicht bestimmte Benutzer, sondern aggregierte Informationen für die gesamte Skype for Business-Organisation in den Mittelpunkt.</span><span class="sxs-lookup"><span data-stu-id="f343f-p108">Where CA is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Skype for Business admins and network engineers optimize a network. CQD shifts focus from specific users and instead looks at aggregate information for an entire Skype for Business organization.</span></span> 
  
<span data-ttu-id="f343f-p109">Vielleicht ist Tonys schlechte Anrufqualität auf ein Netzwerkproblem zurückzuführen, das sich auch auf viele andere Benutzer auswirkt. Wie Tony diesen einzelnen Anruf wahrgenommen hat, ist im Anrufqualitätsdashboard nicht sichtbar, dafür wird die allgemeine Qualität der Anrufe über Skype for Business erfasst. Durch das Anrufqualitätsdashboard können allgemeine Muster sichtbar werden, die Netzwerktechnikern fundierte Bewertungen der Anrufqualität ermöglichen. Das Anrufqualitätsdashboard bietet Berichte zu Qualitätsmetriken, die Ihnen Aufschluss über die allgemeine Anrufqualität, über Datenströme zwischen Server und Clients sowie zwischen Clients und über die [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) zur Sprachqualität geben.</span><span class="sxs-lookup"><span data-stu-id="f343f-p109">Maybe Tony's poor call quality is due to a network issue that's also affecting many other users. Tony's individual call experience isn't visible in CQD, but the overall quality of calls made using Skype for Business is captured. With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality. CQD provides reports of call quality metrics that give you insights into overall call quality, server-client and client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
<span data-ttu-id="f343f-131">Weitere Details finden Sie unter [Funktionen des Anrufqualitäts-Dashboards für Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span><span class="sxs-lookup"><span data-stu-id="f343f-131">For more details, see [Features of the Call Quality Dashboard for Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="f343f-p111">Die Anrufanalyse und das Anrufqualitätsdashboard werden parallel ausgeführt und können unabhängig voneinander oder zusammen verwendet werden. Beispiel: Ein Agent der Stufe 1 kommt zu dem Schluss, dass er bei der Behandlung eines Anrufproblems weitere Hilfe benötigt. Der Agent der Stufe 1 gibt den Anruf an einen Agent der Stufe 2 weiter, der auf mehr Informationen in der Anrufanalyse zugreifen kann als der Agent der Stufe 1. Der Agent der Stufe 2 wiederum kann einen Netzwerktechniker über ein Problem benachrichtigen. Der Netzwerktechniker kann im Anrufqualitätsdashboard überprüfen, ob möglicherweise ein allgemeines standortbezogenes Problem zur Ursache der Anrufprobleme beiträgt.</span><span class="sxs-lookup"><span data-stu-id="f343f-p111">Call Analytics and CQD run in parallel and can be used independently or together. For example, say a Tier 1 agent determines that they need more help troubleshooting a call problem. The Tier 1 agent passes the call to a Tier 2 agent, who has access to more information in Call Analytics than the Tier 1 agent. In turn, the Tier 2 agent can alert a network engineer to an issue. The network engineer may check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>
  
<span data-ttu-id="f343f-137">Weitere Informationen zu CQD finden Sie unter [aktivieren, und rufen Sie Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verwenden](turning-on-and-using-call-quality-dashboard.md) und [Dimensionen und Measures in Aufrufen Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verfügbar](dimensions-and-measures-available-in-call-quality-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="f343f-137">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f343f-138">See Also</span><span class="sxs-lookup"><span data-stu-id="f343f-138">Related topics</span></span>
[<span data-ttu-id="f343f-139">Einrichten der Anrufanalyse von Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f343f-139">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="f343f-140">Verwenden der Anrufanalyse für die Problembehandlung bei schlechter Anrufqualität in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f343f-140">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

  
 
