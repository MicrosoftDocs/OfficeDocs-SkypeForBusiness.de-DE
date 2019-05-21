---
title: Überwachung und Problembehandlung von direktem Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: In diesem Artikel wird beschrieben, wie Sie Ihre direkte Routing Konfiguration überwachen und beheben können.
ms.openlocfilehash: b4d53ad566cd0c31696ce688044ce1587d771a7d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290408"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="012ae-103">Überwachung und Problembehandlung von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="012ae-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="012ae-104">In diesem Artikel wird beschrieben, wie Sie Ihre direkte Routing Konfiguration überwachen und beheben können.</span><span class="sxs-lookup"><span data-stu-id="012ae-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="012ae-105">Die Möglichkeit zum tätigen und empfangen von Anrufen mithilfe des direkten Routings umfasst die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="012ae-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="012ae-106">Session Border Controllers (SBCS)</span><span class="sxs-lookup"><span data-stu-id="012ae-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="012ae-107">Direkte Routing Komponenten in der Microsoft-Cloud</span><span class="sxs-lookup"><span data-stu-id="012ae-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="012ae-108">Telekom-Stämme</span><span class="sxs-lookup"><span data-stu-id="012ae-108">Telecom trunks</span></span> 

<span data-ttu-id="012ae-109">Wenn Sie Probleme bei der Problembehandlung haben, öffnen Sie bitte einen Support-Fall mit Ihrem SBC-Anbieter oder Microsoft.</span><span class="sxs-lookup"><span data-stu-id="012ae-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="012ae-110">Microsoft arbeitet an der Bereitstellung weiterer Tools für die Problembehandlung und Überwachung.</span><span class="sxs-lookup"><span data-stu-id="012ae-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="012ae-111">Bitte überprüfen Sie die Dokumentation regelmäßig auf Updates.</span><span class="sxs-lookup"><span data-stu-id="012ae-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="012ae-112">Überwachen der Verfügbarkeit von Sitzungs Grenz Controllern mithilfe von SIP-Options Meldungen (Session Initiation Protocol)</span><span class="sxs-lookup"><span data-stu-id="012ae-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) Options messages</span></span>

<span data-ttu-id="012ae-113">Das direkte Routing verwendet SIP-Optionen, die von den Session Border Controllern zur Überwachung des SBC-Status gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="012ae-113">Direct Routing uses SIP Options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="012ae-114">Vom mandantenadministrator sind keine Aktionen erforderlich, um die Überwachung der SIP-Optionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="012ae-114">There are no actions required from the tenant administrator to enable the SIP Options monitoring.</span></span> <span data-ttu-id="012ae-115">Die gesammelten Informationen werden berücksichtigt, wenn Routingentscheidungen getroffen werden.</span><span class="sxs-lookup"><span data-stu-id="012ae-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="012ae-116">Wenn beispielsweise für einen bestimmten Benutzer mehrere SBCS verfügbar sind, um einen Anruf weiterleiten zu können, werden bei der direkten Weiterleitung die SIP-Options Informationen berücksichtigt, die von jedem SBC empfangen werden, um das Routing zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="012ae-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP Options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="012ae-117">Das folgende Diagramm zeigt ein Beispiel für die Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="012ae-117">The following diagram shows an example of the configuration:</span></span> 

![Konfigurationsbeispiel für SIP-Optionen](media/sip-options-config-example.png)

<span data-ttu-id="012ae-119">Wenn ein Benutzer einen Anruf an Number + 1 425 \<mit sieben digits> tätigt, wertet Direct Routing die Route aus.</span><span class="sxs-lookup"><span data-stu-id="012ae-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="012ae-120">Die Route umfasst zwei SBCS: sbc1.contoso.com und sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="012ae-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="012ae-121">Beide SBCS haben in der Route dieselbe Priorität.</span><span class="sxs-lookup"><span data-stu-id="012ae-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="012ae-122">Vor der Auswahl eines SBC bewertet der Routingmechanismus die Integrität des SBCS basierend auf dem Zeitpunkt, zu dem der SBC die SIP-Optionen beim letzten Mal gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="012ae-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP Options last time.</span></span> 

<span data-ttu-id="012ae-123">Ein SBC wird als "fehlerfrei" eingestuft, wenn beim Senden des Anrufs Statistiken angezeigt werden, dass die SBC-Optionen in regelmäßigen Abständen gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="012ae-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="012ae-124">Beim direkten Routing werden reguläre Intervalle berechnet, indem der SBC zwei Mal den Mittelwert einnimmt, wenn der SBC Optionen sendet, bevor er den Anruf annimmt und fünf Minuten hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="012ae-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends Options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="012ae-125">Nehmen Sie beispielsweise Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="012ae-125">For example, assume the following:</span></span> 

- <span data-ttu-id="012ae-126">Ein SBC ist so konfiguriert, dass Optionen jede Minute gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="012ae-126">An SBC is configured to send Options every minute.</span></span> 
- <span data-ttu-id="012ae-127">Der SBC wurde um 11,00 Uhr gekoppelt.</span><span class="sxs-lookup"><span data-stu-id="012ae-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="012ae-128">Der SBC sendet Optionen für 11,01 Uhr, 11,02 Uhr usw.</span><span class="sxs-lookup"><span data-stu-id="012ae-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="012ae-129">Bei 11,15 führt ein Benutzer einen Anruf aus, und der Routingmechanismus wählt diesen SBC aus.</span><span class="sxs-lookup"><span data-stu-id="012ae-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="012ae-130">Die folgende Logik wird angewendet: das Zweifache des durchschnittlichen Intervalls, wenn der SBC Optionen sendet (eine Minute plus eine Minute = zwei Minuten) plus fünf Minuten = sieben Minuten.</span><span class="sxs-lookup"><span data-stu-id="012ae-130">The following logic is applied: Two times the average interval when the SBC sends Options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="012ae-131">Dies ist der Wert des regulären Intervalls für den SBC.</span><span class="sxs-lookup"><span data-stu-id="012ae-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="012ae-132">Wenn der SBC in unserem Beispiel Optionen zu einem beliebigen Zeitraum zwischen 11,08 und 11,15 Uhr (der Zeitpunkt, zu dem der Anruf getätigt wurde) gesendet hat, wird er als fehlerfrei angesehen.</span><span class="sxs-lookup"><span data-stu-id="012ae-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="012ae-133">Wenn dies nicht der Fall ist, wird der SBC von der Route herabgestuft.</span><span class="sxs-lookup"><span data-stu-id="012ae-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="012ae-134">Herabstufung bedeutet, dass der SBC nicht zuerst getestet wird.</span><span class="sxs-lookup"><span data-stu-id="012ae-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="012ae-135">Beispielsweise haben wir sbc1.contoso.com und sbc2.contoso.com mit gleicher Priorität.</span><span class="sxs-lookup"><span data-stu-id="012ae-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="012ae-136">Wenn sbc1.contoso.com die SIP-Optionen nicht wie oben beschrieben in regelmäßigen Abständen sendet, wird es herabgestuft.</span><span class="sxs-lookup"><span data-stu-id="012ae-136">If sbc1.contoso.com does not send SIP Options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="012ae-137">Als nächstes versucht sbc2.contoso.com den Anruf.</span><span class="sxs-lookup"><span data-stu-id="012ae-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="012ae-138">Wenn sbc2. contoso. con den Anruf nicht übermitteln kann, wird der sbc1.contoso.com (degradiert) erneut versucht, bevor ein Fehler generiert wird.</span><span class="sxs-lookup"><span data-stu-id="012ae-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="012ae-139">Überwachen von Anruf Qualitätsanalyse-Dashboard und SBC-Protokollen</span><span class="sxs-lookup"><span data-stu-id="012ae-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="012ae-140">In einigen Fällen, besonders während der anfänglichen Kopplung, gibt es möglicherweise Probleme im Zusammenhang mit der Fehlkonfiguration des SBCS und/oder des Direct Routing-Diensts.</span><span class="sxs-lookup"><span data-stu-id="012ae-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="012ae-141">Sie können die folgenden Tools verwenden, um Ihre Konfiguration zu überwachen:</span><span class="sxs-lookup"><span data-stu-id="012ae-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="012ae-142">Anrufqualitäts-Dashboard</span><span class="sxs-lookup"><span data-stu-id="012ae-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="012ae-143">SBC-Protokolle</span><span class="sxs-lookup"><span data-stu-id="012ae-143">SBC logs</span></span> 

<span data-ttu-id="012ae-144">Der Direct Routing-Dienst weist sehr anschauliche Fehlercodes auf, die entweder für die anrufanalyse oder für die SBC-Protokolle gemeldet wurden.</span><span class="sxs-lookup"><span data-stu-id="012ae-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="012ae-145">Das Dashboard "Anrufqualität" bietet Informationen zur Anrufqualität und Zuverlässigkeit.</span><span class="sxs-lookup"><span data-stu-id="012ae-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="012ae-146">Weitere Informationen zur Behandlung von Problemen mit der anrufanalyse finden Sie unter [aktivieren und Verwenden von Anruf Qualitäts Dashboard für Microsoft Teams und Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) und [Verwenden von Anruf Analysen zur Behandlung schlechter Anrufqualität](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="012ae-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="012ae-147">Bei Anruf Fehlern bietet die anrufanalyse Standard-SIP-Codes, die Ihnen bei der Problembehandlung helfen.</span><span class="sxs-lookup"><span data-stu-id="012ae-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Beispiel für SIP-Code für Anruf Fehler](media/failed-response-code.png)

<span data-ttu-id="012ae-149">Anruf Analysen können jedoch nur dann hilfreich sein, wenn Anrufe die internen Komponenten des direkten Routings erreichen und Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="012ae-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="012ae-150">Bei Problemen mit SBC-Kopplungen oder Problemen, bei denen SIP "Invite" abgelehnt wurde (beispielsweise ist der Name des trunk-FQDN falsch konfiguriert), kann die anrufanalyse nicht helfen.</span><span class="sxs-lookup"><span data-stu-id="012ae-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="012ae-151">Beziehen Sie sich in diesem Fall bitte auf die SBC-Protokolle.</span><span class="sxs-lookup"><span data-stu-id="012ae-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="012ae-152">Direktes Routing sendet eine detaillierte Beschreibung der Probleme an die SBCS. Diese Probleme können aus den SBC-Protokollen gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="012ae-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
