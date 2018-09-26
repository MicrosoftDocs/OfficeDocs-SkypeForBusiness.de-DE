---
title: Planen der Anruf Data Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Übersicht über die Verwendung von Skype für Business Online Telemetrie-Tools zum Überwachen von einer lokale Implementierung in einer Hybrid-Szenario.
ms.openlocfilehash: 2c491a217f02af77a25f362697e6f89aceb9470c
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "25030700"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="4b6b3-103">Planen der Anruf Data Connector</span><span class="sxs-lookup"><span data-stu-id="4b6b3-103">Plan Call Data Connector</span></span>

[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a><span data-ttu-id="4b6b3-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="4b6b3-104">Overview</span></span>
<span data-ttu-id="4b6b3-105">In diesem Thema werden die Vorteile, Planungsaspekte, und Anforderungen für die Implementierung von Skype für Business Server rufen Sie Daten Connector.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="4b6b3-106">Weitere Informationen zum Konfigurieren von Data Connector aufrufen finden Sie unter [Call Data Connector konfigurieren](configure-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="4b6b3-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4b6b3-107">Unter public Preview-Version steht nur aufrufen Analytics Dashboard.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-107">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="4b6b3-108">Anruf Data Connector vereinfacht die Anruf-Überwachung in einer hybridumgebung, da Sie nicht mehr benötigen, um verschiedene Sätze von lokalen und online-Tools verwenden, um alle Ihre Benutzer die Anrufqualität zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-108">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="4b6b3-109">Ob Ihre Benutzer lokal verwaltete oder online sind, können Sie die Anrufqualität für die gesamte Organisation online anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-109">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="4b6b3-110">Mit Data Connector aufrufen, können Sie die folgenden Aufgaben ausführen, mithilfe einer einzelnen Toolset:</span><span class="sxs-lookup"><span data-stu-id="4b6b3-110">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="4b6b3-111">Überwachen Sie Ihre Benutzer wünschen über Microsoft-Teams, Skype für Business Online und Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-111">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="4b6b3-112">Zeigen Sie an und beheben Sie Probleme in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-112">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="4b6b3-113">Zuweisen von Helpdesk und Administrator Rollen für aufrufen, Analyse, sodass Mitarbeiter anzeigen und beheben Verantwortungsbereich Helpdesk Webinhalte.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-113">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span> 

<span data-ttu-id="4b6b3-114">Mit Anrufen Data Connector schiebt die Skype für Business Server Anrufdaten an den Clouddienst, damit Sie die Skype für Business Online aufrufen Analytics (CA), und rufen Sie Quality Dashboard (CQD) Tools nutzen können wie im folgenden Diagramm dargestellt:</span><span class="sxs-lookup"><span data-stu-id="4b6b3-114">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![SfB Cloud-Voicemail](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="4b6b3-116">Der Server legt Quality of Experience (QoE) und Aufzeichnung von Kommunikationsdatensätzen (KDS) Daten auf den online-Dienst.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-116">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="4b6b3-117">Die Analytics aufrufen und CQD Tools können Sie die Qualität von Anrufen zu überwachen und Problembehandlung für Verbindungsprobleme mit Microsoft-Teams und Skype für BusinessServices wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4b6b3-117">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="4b6b3-118">Rufen Sie Analytics konzentriert sich auf Qualitätsprobleme bei bestimmten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-118">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="4b6b3-119">Es zeigt detaillierte Informationen zu Anrufe und Besprechungen für jeden Benutzer in einer Skype für Business-Konto.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-119">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="4b6b3-120">Mit Analysen aufrufen können Sie Berechtigungen für einen Helpdesk-Operator zuweisen, die dann Anrufe überwachen können, ohne dass der Zugriff auf den Rest der der Skype für Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-120">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="4b6b3-121">Rufen Sie Qualitätsdashboard konzentriert sich auf die Leistung des Netzwerks und Probleme innerhalb einer Organisation.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-121">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="4b6b3-122">Skype für Administratoren in Unternehmen und Netzwerktechniker mit diesem Tool können Sie beheben und Optimieren der Leistung des Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-122">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="4b6b3-123">Weitere Informationen finden Sie unter [Analytics aufrufen, und rufen Sie Qualitätsdashboard](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="4b6b3-123">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="4b6b3-124">Sie möchten natürlich einige Anrufqualität Daten lokal speichern.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-124">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="4b6b3-125">Dies möglicherweise die Groß-/Kleinschreibung, z. B., wenn Sie ein Drittanbieter-Lösung mit benutzerdefinierte Berichte und Workflows.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-125">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="4b6b3-126">Anruf Data Connector können Sie sendende von Daten an den online-Dienst konfigurieren und eine Kopie der Daten auf dem lokalen Server auch weiterhin, wie im folgenden Diagramm dargestellt:</span><span class="sxs-lookup"><span data-stu-id="4b6b3-126">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![SfB Cloud-Voicemail](../../sfbserver2019/media/call-data-connector-plan-2.png)


## <a name="requirements"></a><span data-ttu-id="4b6b3-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b6b3-128">Requirements</span></span>

<span data-ttu-id="4b6b3-129">Die folgenden Anforderungen wird davon ausgegangen, dass Sie bereits Skype für Business Server in einer unterstützten Topologie bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-129">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="4b6b3-130">Weitere Informationen zur Bereitstellung von Skype für Business Server und unterstützten Topologien finden Sie unter [Grundlagen der Topologie](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span><span class="sxs-lookup"><span data-stu-id="4b6b3-130">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span></span>

- <span data-ttu-id="4b6b3-131">Hybrid-Diensten.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-131">Hybrid connectivity.</span></span> <span data-ttu-id="4b6b3-132">Wenn Sie Skype bereits für Business Server bereitgestellt haben, und rufen Sie Data Connector aktivieren möchten, müssen Sie sicherstellen, dass Sie hybridkonnektivität zwischen Ihrer lokalen und online-Umgebung eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="4b6b3-133">Dies ist eine geteilte Domänenkonfiguration bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-133">This is sometimes called a split domain configuration.</span></span> 

   <span data-ttu-id="4b6b3-134">Weitere Informationen finden Sie unter [hybridkonnektivität zwischen Skype für Business Server und Office 365 planen](plan-hybrid-connectivity.md) und [Konfigurieren von hybridkonnektivität zwischen Skype für Business Server und Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="4b6b3-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="4b6b3-135">Um Call Data Connector zu konfigurieren, müssen Sie Ihrem Office 365-Mandanten authentifizieren und stellen Sie sicher, dass Sie die folgenden Rollen aktiviert haben:</span><span class="sxs-lookup"><span data-stu-id="4b6b3-135">To configure Call Data Connector, you must authenticate to your Office 365 tenant and ensure that you have the following roles enabled:</span></span>

   - <span data-ttu-id="4b6b3-136">Skype für Business Server-Administrator</span><span class="sxs-lookup"><span data-stu-id="4b6b3-136">Skype for Business Server Administrator</span></span> 
   - <span data-ttu-id="4b6b3-137">Office 365 globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="4b6b3-137">Office 365 Global Administrator</span></span> 

- <span data-ttu-id="4b6b3-138">Wenn Sie dies nicht bereits geschehen ist, aktivieren Sie rufen Qualitätsdashboard gemäß [einschalten, und rufen Sie Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verwenden](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="4b6b3-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="4b6b3-139">Vergleich zwischen lokalen und online aufrufen Quality Dashboard (CQD)-Berichte</span><span class="sxs-lookup"><span data-stu-id="4b6b3-139">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="4b6b3-140">Feature-Berichte</span><span class="sxs-lookup"><span data-stu-id="4b6b3-140">Feature reports</span></span> | <span data-ttu-id="4b6b3-141">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4b6b3-141">Skype for Business Online</span></span> | <span data-ttu-id="4b6b3-142">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4b6b3-142">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="4b6b3-143">Anwendungsfreigabemetrik</span><span class="sxs-lookup"><span data-stu-id="4b6b3-143">Application sharing metric</span></span> |<span data-ttu-id="4b6b3-144">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-144">Yes</span></span> | <span data-ttu-id="4b6b3-145">Begrenzt</span><span class="sxs-lookup"><span data-stu-id="4b6b3-145">Limited</span></span> |
| <span data-ttu-id="4b6b3-146">Erstellen von Kundeninformationen</span><span class="sxs-lookup"><span data-stu-id="4b6b3-146">Customer building information</span></span>| <span data-ttu-id="4b6b3-147">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-147">Yes</span></span> | <span data-ttu-id="4b6b3-148">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-148">Yes</span></span> |
| <span data-ttu-id="4b6b3-149">Drilldown-Analyse</span><span class="sxs-lookup"><span data-stu-id="4b6b3-149">Drill-down analytics</span></span> | <span data-ttu-id="4b6b3-150">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-150">Yes</span></span> | <span data-ttu-id="4b6b3-151">Nein</span><span class="sxs-lookup"><span data-stu-id="4b6b3-151">No</span></span> |
| <span data-ttu-id="4b6b3-152">Medienzuverlässigkeitsmetriken</span><span class="sxs-lookup"><span data-stu-id="4b6b3-152">Media reliability metrics</span></span> | <span data-ttu-id="4b6b3-153">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-153">Yes</span></span> | <span data-ttu-id="4b6b3-154">Begrenzt</span><span class="sxs-lookup"><span data-stu-id="4b6b3-154">Limited</span></span> |
| <span data-ttu-id="4b6b3-155">Sofort einsatzbereite Berichte</span><span class="sxs-lookup"><span data-stu-id="4b6b3-155">Out-of-the-box reports</span></span> | <span data-ttu-id="4b6b3-156">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-156">Yes</span></span> | <span data-ttu-id="4b6b3-157">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-157">Yes</span></span> |
| <span data-ttu-id="4b6b3-158">Übersichtsberichte</span><span class="sxs-lookup"><span data-stu-id="4b6b3-158">Overview reports</span></span> | <span data-ttu-id="4b6b3-159">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-159">Yes</span></span> | <span data-ttu-id="4b6b3-160">Nein</span><span class="sxs-lookup"><span data-stu-id="4b6b3-160">No</span></span> |
| <span data-ttu-id="4b6b3-161">Pro Benutzerberichte</span><span class="sxs-lookup"><span data-stu-id="4b6b3-161">Per user reports</span></span> | <span data-ttu-id="4b6b3-162">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-162">Yes</span></span> | <span data-ttu-id="4b6b3-163">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-163">Yes</span></span> |
| <span data-ttu-id="4b6b3-164">Anpassen von Berichten set</span><span class="sxs-lookup"><span data-stu-id="4b6b3-164">Report set customization</span></span> <br> <span data-ttu-id="4b6b3-165">(Fügen Sie hinzu, löschen Sie, ändern Sie Berichte)</span><span class="sxs-lookup"><span data-stu-id="4b6b3-165">(add, delete, modify reports)</span></span> | <span data-ttu-id="4b6b3-166">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-166">Yes</span></span> | <span data-ttu-id="4b6b3-167">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-167">Yes</span></span> |
| <span data-ttu-id="4b6b3-168">Videobasierte Bildschirmfreigabe-Metriken</span><span class="sxs-lookup"><span data-stu-id="4b6b3-168">Video-based screen sharing metrics</span></span> | <span data-ttu-id="4b6b3-169">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-169">Yes</span></span> | <span data-ttu-id="4b6b3-170">Nein</span><span class="sxs-lookup"><span data-stu-id="4b6b3-170">No</span></span> |
| <span data-ttu-id="4b6b3-171">Daten-APIs für den programmgesteuerten Zugriff</span><span class="sxs-lookup"><span data-stu-id="4b6b3-171">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="4b6b3-172">zu CQD</span><span class="sxs-lookup"><span data-stu-id="4b6b3-172">to CQD</span></span> | <span data-ttu-id="4b6b3-173">Nein</span><span class="sxs-lookup"><span data-stu-id="4b6b3-173">No</span></span> | <span data-ttu-id="4b6b3-174">Ja</span><span class="sxs-lookup"><span data-stu-id="4b6b3-174">Yes</span></span> |



















