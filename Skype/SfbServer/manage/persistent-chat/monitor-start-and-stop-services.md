---
title: Überwachen, Starten und Beenden der Dienste für beständigen Chat in Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Zusammenfassung: Informationen Sie zum Starten, beenden und die Dienste beständigen Chat in Skype für Business Server 2015 überwachen.'
ms.openlocfilehash: 272ea0f4270b1109ff77b5d809472051705b6f10
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20991589"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="57ab2-103">Überwachen, Starten und Beenden der Dienste für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="57ab2-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="57ab2-104">**Zusammenfassung:** Informationen Sie zum Starten, beenden und die Dienste beständigen Chat in Skype für Business Server 2015 überwachen.</span><span class="sxs-lookup"><span data-stu-id="57ab2-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="57ab2-105">Der Persistent Chat-Dienste und Kompatibilität für Persistent Chat-Dienste können sind Bestandteil der Skype für Business Server-Topologie und daher werden überwacht, beendet und gestartet mithilfe der folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="57ab2-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="57ab2-106">Get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="57ab2-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="57ab2-107">Gibt ausführliche Informationen über Skype für Business Server 2015 Komponenten, die als Windows-Dienste ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="57ab2-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="57ab2-108">Start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="57ab2-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="57ab2-109">Startet den Dienst.</span><span class="sxs-lookup"><span data-stu-id="57ab2-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="57ab2-110">Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="57ab2-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="57ab2-111">Beendet den Dienst.</span><span class="sxs-lookup"><span data-stu-id="57ab2-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="57ab2-112">Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="57ab2-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="57ab2-113">Die gleiche Funktionalität ist in Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="57ab2-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="57ab2-114">Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="57ab2-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="57ab2-115">Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden.</span><span class="sxs-lookup"><span data-stu-id="57ab2-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="57ab2-116">Ausführliche Informationen dazu, wie Sie die Cmdlets verwenden finden Sie unter [Skype für Business Server 2015-Verwaltungsshell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="57ab2-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

