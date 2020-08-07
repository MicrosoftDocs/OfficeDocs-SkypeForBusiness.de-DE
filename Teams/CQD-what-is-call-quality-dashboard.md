---
title: Was ist das Anruf Qualitäts Dashboard (CQD)?
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Erfahren Sie mehr über das Anruf Qualitäts Dashboard (CQD) und wie Sie es verwenden können, um Berichte über die Qualität von Besprechungen und anrufen in Microsoft Teams anzuzeigen.
ms.openlocfilehash: 9ba1956533887314a9ffa7ad994cbb4c81ffe103
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583484"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="5363e-103">Was ist das Anruf Qualitäts Dashboard (CQD)?</span><span class="sxs-lookup"><span data-stu-id="5363e-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="5363e-104">Das Microsoft Call Quality-Dashboard (CQD) – [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) zeigt die Anruf-und Besprechungs Qualität auf **organisationsweiter Ebene**für Microsoft Teams, Skype for Business Online und Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5363e-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="5363e-105">Die neueste Version von CQD verfügt über einen [fast-Echtzeit-Datenfeed (NRT)](CQD-data-and-reports.md), was bedeutet, dass anrufdatensätze innerhalb von 30 Minuten nach dem Ende eines Anrufs in CQD zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="5363e-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="5363e-106">Unabhängig davon, wo CQD [Endbenutzer-identifizierbare Daten (EUII)](CQD-data-and-reports.md#euii-data)enthält, wird es auf die gleiche Weise wie [EUII in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5363e-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="5363e-107">CQD wurde entwickelt, um Teams-Administratoren, Skype for Business-Administratoren und Netzwerk Ingenieuren zu helfen, die Anruf-und Besprechungs Qualität auf organisationsweiter Ebene zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="5363e-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="5363e-108">Sie verwenden CQD, damit Sie **Ihr Netzwerk optimieren** können, um die Leistungsqualität zu steigern.</span><span class="sxs-lookup"><span data-stu-id="5363e-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="5363e-109">Wenn Sie die Anruf-und Besprechungsinformationen für einen **bestimmten Benutzer**untersuchen müssen, verwenden Sie CQD-Daten in Verbindung mit der pro-Benutzer- [anrufanalyse](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span><span class="sxs-lookup"><span data-stu-id="5363e-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="5363e-110">So können Sie beispielsweise mithilfe von CQD feststellen, dass die schlechte Anrufqualität eines Benutzers (die Sie bei der Verwendung der pro-Benutzer-anrufanalyse beobachtet haben) auf ein Netzwerkproblem zurückzuführen ist, das auch viele andere Benutzer betrifft.</span><span class="sxs-lookup"><span data-stu-id="5363e-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="5363e-111">CQD erfasst sowohl die individuelle Anruf Erfahrung als auch die Gesamtqualität von anrufen, die über Teams oder Skype for Business getätigt wurden.</span><span class="sxs-lookup"><span data-stu-id="5363e-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="5363e-112">Bei CQD können die allgemeinen Muster deutlich werden, sodass Netzwerkingenieure fundierte Bewertungen der Anrufqualität vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="5363e-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="5363e-113">CQD stellt Berichte über Anruf Qualitäts Metriken bereit, mit denen Sie Einblicke in die allgemeine Anrufqualität, Server-Client-Streams, Client-Client-Streams und [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)für die Sprachqualität erhalten.</span><span class="sxs-lookup"><span data-stu-id="5363e-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Screenshot des Dashboards für die Anrufqualität.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="5363e-115">In CQD empfehlen wir Ihnen, Gebäude-und Endpunktinformationen hochzuladen, sodass Sie mithilfe von Standort optimierten Berichten die Anrufqualität und Zuverlässigkeit im Gebäude eines Benutzers analysieren können.</span><span class="sxs-lookup"><span data-stu-id="5363e-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="5363e-116">Die Daten können ausgewertet werden, um festzustellen, ob das Problem für einen einzelnen Benutzer isoliert ist oder ein größeres Segment von Benutzern betrifft.</span><span class="sxs-lookup"><span data-stu-id="5363e-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="5363e-117">Damit Sie Gebäude-oder Endpunkt spezifische Ansichten in CQD aktivieren können, muss ein Administrator [Gebäude-oder Endpunktinformationen](CQD-upload-tenant-building-data.md) auf der CQD-Seite für **Mandantendaten** hochladen.</span><span class="sxs-lookup"><span data-stu-id="5363e-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![Screenshot der Standort optimierten Berichte des Anruf Qualitäts Dashboards](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="5363e-119">Verpassen Sie nicht unseren Artikel " [Anruf-und Besprechungs Qualität verwalten](quality-of-experience-review-guide.md) ", der detaillierte Anleitungen für den Team-Administrator oder Support-Techniker bietet, der für die Verwaltung der Dienstqualität in Microsoft Teams verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="5363e-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="5363e-120">Ältere Version von CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="5363e-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="5363e-121">Die aktuelle Version von CQD ( https://CQD.Teams.microsoft.com) ersetzt die ältere Version von CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="5363e-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="5363e-122">Sie können weiterhin CQD.lync.com verwenden (im Skype for Business Admin Center verfügbar), aber ab dem 1. Juli 2020 werden die Daten von CQD verwendet. Teams.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5363e-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="5363e-123">Wir werden den Zugriff auf CQD.lync.com bald deaktivieren, daher sollten Sie zu CQD wechseln. Teams.Microsoft.com, wenn dies noch nicht geschehen ist.</span><span class="sxs-lookup"><span data-stu-id="5363e-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5363e-124">Ab dem 1. Juli 2020 können Sie Ihre Gebäude-oder Abfrage Daten aus dem alten CQD (CQD.lync.com) nicht mehr anzeigen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="5363e-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="5363e-125">Wenn Sie diese Daten noch nicht von CQD.lync.com migriert haben und Sie dennoch benötigen, melden Sie ein Support Ticket.</span><span class="sxs-lookup"><span data-stu-id="5363e-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="5363e-126">Verwenden von Power BI zum Analysieren von CQD-Daten</span><span class="sxs-lookup"><span data-stu-id="5363e-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="5363e-127">Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="5363e-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="5363e-128">Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.</span><span class="sxs-lookup"><span data-stu-id="5363e-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="5363e-129">Lesen [verwenden Sie Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md) , um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5363e-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="5363e-130">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5363e-130">Related topics</span></span>

[<span data-ttu-id="5363e-131">Verbessern und Überwachen der Anrufqualität für Teams</span><span class="sxs-lookup"><span data-stu-id="5363e-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="5363e-132">Einrichten des Dashboards für die Anrufqualität (CQD)</span><span class="sxs-lookup"><span data-stu-id="5363e-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="5363e-133">Hochladen von Mandanten-und Gebäudedaten</span><span class="sxs-lookup"><span data-stu-id="5363e-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="5363e-134">CQD-Daten und-Berichte</span><span class="sxs-lookup"><span data-stu-id="5363e-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="5363e-135">Verwenden von CQD zum Verwalten von Anruf-und Besprechungs Qualität</span><span class="sxs-lookup"><span data-stu-id="5363e-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="5363e-136">In CQD verfügbare Dimensionen und Measures</span><span class="sxs-lookup"><span data-stu-id="5363e-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="5363e-137">Datenstrom Klassifizierung in CQD</span><span class="sxs-lookup"><span data-stu-id="5363e-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="5363e-138">Verwenden von Power BI zum Analysieren von CQD-Daten</span><span class="sxs-lookup"><span data-stu-id="5363e-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="5363e-139">Teams-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="5363e-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)