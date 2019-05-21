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
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die beständigen Chat Dienste in Skype for Business Server 2015 starten, beenden und überwachen.'
ms.openlocfilehash: 161bda3cb02bf6208b4db9f1c6825d3fe433eeca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279291"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="2dab4-103">Überwachen, Starten und Beenden der Dienste für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2dab4-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2dab4-104">**Zusammenfassung:** Erfahren Sie, wie Sie die beständigen Chat Dienste in Skype for Business Server 2015 starten, beenden und überwachen können.</span><span class="sxs-lookup"><span data-stu-id="2dab4-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2dab4-105">Die beständigen Chat Dienste und die beständigen Chat-Konformitäts Dienste sind Teil der Skype for Business Server-Topologie und können daher mithilfe der folgenden Cmdlets überwacht, gestoppt und gestartet werden:</span><span class="sxs-lookup"><span data-stu-id="2dab4-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2dab4-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="2dab4-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="2dab4-107">Gibt detaillierte Informationen zu den Skype for Business Server 2015-Komponenten zurück, die als Windows-Dienste ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2dab4-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="2dab4-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="2dab4-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="2dab4-109">Startet den Dienst.</span><span class="sxs-lookup"><span data-stu-id="2dab4-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="2dab4-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="2dab4-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="2dab4-111">Beendet den Dienst.</span><span class="sxs-lookup"><span data-stu-id="2dab4-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="2dab4-112">Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2dab4-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2dab4-113">In Teams steht dieselbe Funktionalität zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2dab4-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="2dab4-114">Weitere Informationen finden Sie unter [Reise von Skype for Business zu Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="2dab4-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="2dab4-115">Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="2dab4-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="2dab4-116">Weitere Informationen zur Verwendung dieser Cmdlets finden Sie unter [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="2dab4-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

