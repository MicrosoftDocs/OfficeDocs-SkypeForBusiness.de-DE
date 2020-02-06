---
title: Überwachen, Starten und Beenden der Dienste für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die beständigen Chat Dienste in Skype for Business Server 2015 starten, beenden und überwachen.'
ms.openlocfilehash: 846d7376e1a3e9bd06ae74c20ee0812c8c78bbeb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817474"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="b1413-103">Überwachen, Starten und Beenden der Dienste für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b1413-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b1413-104">**Zusammenfassung:** Erfahren Sie, wie Sie die beständigen Chat Dienste in Skype for Business Server 2015 starten, beenden und überwachen können.</span><span class="sxs-lookup"><span data-stu-id="b1413-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b1413-105">Die beständigen Chat Dienste und die beständigen Chat-Konformitäts Dienste sind Teil der Skype for Business Server-Topologie und können daher mithilfe der folgenden Cmdlets überwacht, gestoppt und gestartet werden:</span><span class="sxs-lookup"><span data-stu-id="b1413-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b1413-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="b1413-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="b1413-107">Gibt detaillierte Informationen zu den Skype for Business Server 2015-Komponenten zurück, die als Windows-Dienste ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b1413-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="b1413-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="b1413-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="b1413-109">Startet den Dienst.</span><span class="sxs-lookup"><span data-stu-id="b1413-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="b1413-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="b1413-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="b1413-111">Beendet den Dienst.</span><span class="sxs-lookup"><span data-stu-id="b1413-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="b1413-112">Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b1413-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b1413-113">In Teams steht dieselbe Funktionalität zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b1413-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="b1413-114">Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="b1413-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="b1413-115">Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="b1413-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="b1413-116">Weitere Informationen zur Verwendung dieser Cmdlets finden Sie unter [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="b1413-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

