---
title: Verwalten von Archivierungsrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Benutzerrichtlinien für die Archivierung von Skype for Business Server verwalten.'
ms.openlocfilehash: f6918907f73ffe1b098ed96e1997d8ab8ffe4f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278426"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="36c17-103">Verwalten von Archivierungsrichtlinien in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="36c17-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="36c17-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Benutzerrichtlinien für die Archivierung von Skype for Business Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="36c17-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="36c17-105">Sie haben zunächst Archivierungsrichtlinien eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="36c17-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="36c17-106">Archivierungsrichtlinien bestimmen, ob Sie archivieren:</span><span class="sxs-lookup"><span data-stu-id="36c17-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="36c17-107">Interne Kommunikation</span><span class="sxs-lookup"><span data-stu-id="36c17-107">Internal communications</span></span>
    
- <span data-ttu-id="36c17-108">Externe Kommunikation</span><span class="sxs-lookup"><span data-stu-id="36c17-108">External communications</span></span>
    
<span data-ttu-id="36c17-109">Archivierungsrichtlinien können auf globaler, Website-oder Benutzerebene eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="36c17-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="36c17-110">Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-Richtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="36c17-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="36c17-111">Ausführliche Informationen finden Sie unter [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) und [Konfigurieren der Integration in Exchange Storage für Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="36c17-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="36c17-112">Verwalten von Archivierungsrichtlinien über die Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="36c17-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="36c17-113">Sie können Archivierungsrichtlinien wie folgt mit der Systemsteuerung verwalten:</span><span class="sxs-lookup"><span data-stu-id="36c17-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="36c17-114">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="36c17-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="36c17-115">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="36c17-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="36c17-116">Klicken Sie in der linken Navigationsleiste auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="36c17-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="36c17-117">Verwalten von Archivierungsrichtlinien mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="36c17-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="36c17-118">Sie können die Archivierungsrichtlinien auch mithilfe der in der folgenden Tabelle aufgeführten Windows PowerShell-Cmdlets konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="36c17-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="36c17-119">Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter, finden Sie unter [Skype for Business Server-Verwaltungsshell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="36c17-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="36c17-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="36c17-120">**Cmdlet**</span></span>|<span data-ttu-id="36c17-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="36c17-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="36c17-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="36c17-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="36c17-123">Gibt Informationen zu Archivierungsrichtlinien für Chatsitzungen zurück.</span><span class="sxs-lookup"><span data-stu-id="36c17-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="36c17-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="36c17-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="36c17-125">Weist Benutzern oder Gruppen von Benutzern Chat-Archivierungsrichtlinien für Sofortnachrichten (im) zu.</span><span class="sxs-lookup"><span data-stu-id="36c17-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="36c17-126">Mithilfe dieser Archivierungsrichtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.</span><span class="sxs-lookup"><span data-stu-id="36c17-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="36c17-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="36c17-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="36c17-128">Erstellt neue Archivierungsrichtlinien für Chatsitzungen.</span><span class="sxs-lookup"><span data-stu-id="36c17-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="36c17-129">Mithilfe dieser Archivierungsrichtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.</span><span class="sxs-lookup"><span data-stu-id="36c17-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="36c17-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="36c17-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="36c17-131">Entfernt die angegebene Sofortnachrichten-Archivierungsrichtlinie, die bestimmt, ob Skype for Business Server automatisch alle Chatsitzungen speichert, die zwischen internen Benutzern und/oder allen Chatsitzungen zwischen internen Benutzern und Verbundpartnern stattfinden.</span><span class="sxs-lookup"><span data-stu-id="36c17-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="36c17-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="36c17-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="36c17-133">Ändert eine vorhandene Instant Messaging-Archivierungsrichtlinie (im).</span><span class="sxs-lookup"><span data-stu-id="36c17-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="36c17-134">Eine Archivierungsrichtlinie bietet Ihnen die Möglichkeit, alle Chatsitzungen und Konferenzen zu archivieren, die zwischen internen Benutzern stattfinden. Sie können auch Sitzungen archivieren, die zwischen internen Benutzern und Verbundpartnern stattfinden.</span><span class="sxs-lookup"><span data-stu-id="36c17-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

