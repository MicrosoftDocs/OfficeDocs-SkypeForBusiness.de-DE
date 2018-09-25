---
title: Überwachung und Problembehandlung von direkten Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: In diesem Artikel wird beschrieben, wie zur Überwachung und Problembehandlung für die direkte Routing-Konfiguration.
ms.openlocfilehash: 46fd5ad046551d30bf3822d11864edc2a5353a26
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014933"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="c6f2a-103">Überwachung und Problembehandlung von direkten Routing</span><span class="sxs-lookup"><span data-stu-id="c6f2a-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="c6f2a-104">In diesem Artikel wird beschrieben, wie zur Überwachung und Problembehandlung für die direkte Routing-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="c6f2a-105">Die Möglichkeit zum tätigen und Entgegennehmen von Anrufen durch direktes Routing umfasst die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="c6f2a-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="c6f2a-106">Session Border Controller (SBCs)</span><span class="sxs-lookup"><span data-stu-id="c6f2a-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="c6f2a-107">Direkte Routing-Komponenten in der Microsoft-Cloud</span><span class="sxs-lookup"><span data-stu-id="c6f2a-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="c6f2a-108">Telekommunikation trunks</span><span class="sxs-lookup"><span data-stu-id="c6f2a-108">Telecom trunks</span></span> 

<span data-ttu-id="c6f2a-109">Wenn Sie Probleme bei der Behandlung von Problemen haben, öffnen Sie eine Supportanfrage mit Ihrer SBC-Anbieter oder Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="c6f2a-110">Microsoft ist funktionsfähig, klicken Sie auf Weitere Tools für die Problembehandlung und Überwachung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="c6f2a-111">Überprüfen Sie die Dokumentation in regelmäßigen Abständen nach Updates.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="c6f2a-112">Überwachen der Verfügbarkeit von Session Border Controller über Session Initiation Protocol (SIP) Optionen Nachrichten</span><span class="sxs-lookup"><span data-stu-id="c6f2a-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) Options messages</span></span>

<span data-ttu-id="c6f2a-113">Direktes Routing verwendet SIP-Optionen, die von der Session Border Controller gesendet, um SBC Integrität zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-113">Direct Routing uses SIP Options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="c6f2a-114">Es sind keine Aktionen, die von der mandantenadministrator erforderlich sind, um die Optionen SIP-Überwachung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-114">There are no actions required from the tenant administrator to enable the SIP Options monitoring.</span></span> <span data-ttu-id="c6f2a-115">Die gesammelte Informationen wird berücksichtigt, wenn Routingentscheidungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="c6f2a-116">Beispielsweise wenn für einen bestimmten Benutzer, mehrere SBCs zum Weiterleiten eines Anrufs verfügbar sind, berücksichtigt direkten Routing von jedem SBC-routing bestimmen erhaltenen Informationen SIP-Optionen.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP Options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="c6f2a-117">Das folgende Diagramm zeigt ein Beispiel für die Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="c6f2a-117">The following diagram shows an example of the configuration:</span></span> 

![Beispiel für die Konfiguration von SIP-Optionen](media/sip-options-config-example.png)

<span data-ttu-id="c6f2a-119">Wenn ein Benutzer einen Anruf an Anzahl +1 425 herstellt \<alle sieben Ziffern >, direkten Routing wertet die Route.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="c6f2a-120">Es gibt zwei SBCs in der Route: sbc1.contoso.com und sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="c6f2a-121">Beide SBCs haben die gleiche Priorität in der Route.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="c6f2a-122">Vor der Entnahme eines SBC, wertet der routing-Mechanismus die Integrität der SBCs basierend auf, wenn der SBC die Optionen SIP gesendet letzten Zeit.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP Options last time.</span></span> 

<span data-ttu-id="c6f2a-123">Ein SBC gilt fehlerfrei, ob Statistiken zum Zeitpunkt der den Anruf senden angezeigt, dass der SBC Optionen in regelmäßigen Abständen gesendet.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="c6f2a-124">Direktes Routing berechnet regelmäßige Abständen, indem Sie zwei Mal den Mittelwert nutzen, wenn der SBC Optionen sendet, bevor der Aufruf und Hinzufügen von fünf Minuten.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends Options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="c6f2a-125">Beispielsweise wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="c6f2a-125">For example, assume the following:</span></span> 

- <span data-ttu-id="c6f2a-126">Ein SBC ist so konfiguriert, zum Senden von "Optionen" jede Minute.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-126">An SBC is configured to send Options every minute.</span></span> 
- <span data-ttu-id="c6f2a-127">Der SBC wurde um 11:00 Uhr kombiniert.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="c6f2a-128">Der SBC sendet Optionen auf 11.01 Uhr, 11.02 Uhr.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="c6f2a-129">An 11.15 ein Benutzer einen Anruf tätigt, und der routing Mechanismus markiert dieses SBC.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="c6f2a-130">Die folgende Logik angewendet wird: doppelt das durchschnittliche Intervall der SBC Optionen (1 Minute plus eine Minute = zwei Minuten) plus fünf Minuten = sieben Minuten sendet.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-130">The following logic is applied: Two times the average interval when the SBC sends Options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="c6f2a-131">Dies ist der Wert der der regelmäßigen Intervall für die SBC.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="c6f2a-132">Wenn der SBC in unserem Beispiel gesendete Optionen auf einen beliebigen Zeitraum zwischen 11:08 und 11:15 Uhr (Zeit, die der Anruf getätigt wurde), wird es fehlerfrei betrachtet.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="c6f2a-133">Wenn dies nicht der Fall ist, wird der SBC aus der Route herabgestuft werden.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="c6f2a-134">Herabstufung bedeutet, dass der SBC nicht zuerst getestet werden.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="c6f2a-135">Zum Beispiel haben wir sbc1.contoso.com und sbc2.contoso.com mit gleiche Priorität.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="c6f2a-136">Sbc1.contoso.com wie oben beschrieben keine SIP-Optionen in regelmäßigen Abständen sendet, wird es herabgestuft.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-136">If sbc1.contoso.com does not send SIP Options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="c6f2a-137">Im nächsten Schritt versucht sbc2.contoso.com für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="c6f2a-138">Wenn den Aufruf von sbc2.contoso.con nicht zugestellt werden kann, die sbc1.contoso.com (tiefer gestuft) erneut versucht werden soll, bevor ein Fehler generiert wird.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="c6f2a-139">Überwachen der Qualität Analytics aufrufen Dashboard und SBC-Protokolle</span><span class="sxs-lookup"><span data-stu-id="c6f2a-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="c6f2a-140">In einigen Fällen vor allem in Zeiten der anfänglichen Paarung möglicherweise Probleme im Zusammenhang mit falsche Konfiguration der der SBCs und/oder direkte Routing Service.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="c6f2a-141">Die folgenden Tools können Sie Ihre Konfiguration überwachen:</span><span class="sxs-lookup"><span data-stu-id="c6f2a-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="c6f2a-142">Anrufqualitäts-Dashboard</span><span class="sxs-lookup"><span data-stu-id="c6f2a-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="c6f2a-143">SBC-Protokolle</span><span class="sxs-lookup"><span data-stu-id="c6f2a-143">SBC logs</span></span> 

<span data-ttu-id="c6f2a-144">Direktes Routing Service hat sehr beschreibenden Fehlercodes gemeldet Analytics aufrufen oder die SBC-Protokolle.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="c6f2a-145">Das Aufrufen Qualitätsdashboard bietet Informationen zur Anrufqualität und Zuverlässigkeit.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="c6f2a-146">Weitere Informationen zum Beheben von Problemen mit Aufrufen Analytics finden Sie unter [aktivieren, und rufen Sie Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verwenden](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) und [Verwendung aufrufen Analysen für die Qualität der Anrufe schlechter Qualität Problembehandlung bei](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="c6f2a-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="c6f2a-147">Im Fall eines WAN-anruffehlern bietet Analytics rufen Sie standard-SIP-Codes, die Sie bei der Problembehandlung zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![SIP-Beispielcode für das Fehlschlagen des Anrufs](media/failed-response-code.png)

<span data-ttu-id="c6f2a-149">Analytics aufrufen können jedoch nur bei Anrufen die internen Komponenten des direkten Routing erreichen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="c6f2a-150">Im Fall eines WAN-Probleme bei der Paarung SBC oder Probleme, auf dem SIP "Einladen" (beispielsweise den Namen des Trunks, den FQDN falsch konfiguriert ist) abgelehnt wurde, trägt Analytics Anruf nicht.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="c6f2a-151">In diesem Fall finden Sie die SBC-Protokolle.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="c6f2a-152">Direktes Routing sendet eine detaillierte Beschreibung der Probleme an die SBCs. Diese Probleme können aus den Protokollen SBC gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="c6f2a-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
