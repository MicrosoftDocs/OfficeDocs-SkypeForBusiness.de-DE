---
title: Verwalten von Archivierungsrichtlinien in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Zusammenfassung: Informationen Sie zum Verwalten von Benutzerrichtlinien für die Archivierung für Skype für Business Server.'
ms.openlocfilehash: d29d30c99320631279114d3ebdfa8ee7db00b677
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21013321"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="cc7aa-103">Verwalten von Archivierungsrichtlinien in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="cc7aa-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="cc7aa-104">**Zusammenfassung:** Informationen Sie zum Verwalten von Benutzerrichtlinien für die Archivierung für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="cc7aa-105">Zunächst eingerichtet werden Archivierungsrichtlinien, wenn Sie die Archivierung bereitstellen, jedoch können Sie ändern, hinzufügen und Löschen von Konfigurationen nach der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="cc7aa-106">Archivierungsrichtlinien bestimmen, ob das archivieren:</span><span class="sxs-lookup"><span data-stu-id="cc7aa-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="cc7aa-107">Interne Kommunikation</span><span class="sxs-lookup"><span data-stu-id="cc7aa-107">Internal communications</span></span>
    
- <span data-ttu-id="cc7aa-108">Externe Kommunikation</span><span class="sxs-lookup"><span data-stu-id="cc7aa-108">External communications</span></span>
    
<span data-ttu-id="cc7aa-109">Archivierungsrichtlinien kann Set auf globaler, Standort- oder Benutzerebene sein.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc7aa-110">Wenn Sie Microsoft Exchange-Integration für die Bereitstellung, Exchange-Richtlinien Steuerelement aktiviert, ob Archivierung aktiviert ist, für die Benutzer, die sich auf Exchange befinden und haben ihren Postfächern zu Compliance-Archiv platzieren.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="cc7aa-111">Weitere Informationen hierzu finden Sie unter [Planen für die Archivierung in Skype für Business Server](../../plan-your-deployment/archiving/archiving.md) und [Integration mit Exchange-Speicher für Skype für Business Server konfigurieren](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="cc7aa-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="cc7aa-112">Verwalten von Archivierungsrichtlinien über die Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="cc7aa-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="cc7aa-113">Sie können Archivierungsrichtlinien wie folgt mit der Systemsteuerung verwalten:</span><span class="sxs-lookup"><span data-stu-id="cc7aa-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="cc7aa-114">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="cc7aa-115">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="cc7aa-116">Klicken Sie in der linken Navigationsleiste auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="cc7aa-117">Verwalten von Archivierungsrichtlinien mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc7aa-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="cc7aa-118">Sie können die Archivierungsrichtlinien auch mithilfe der in der folgenden Tabelle aufgeführten Windows PowerShell-Cmdlets konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="cc7aa-119">Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter finden Sie unter [Skype für Business Server-Verwaltungsshell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="cc7aa-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="cc7aa-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="cc7aa-120">**Cmdlet**</span></span>|<span data-ttu-id="cc7aa-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="cc7aa-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc7aa-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="cc7aa-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="cc7aa-123">Gibt Informationen zu Archivierungsrichtlinien für Chatsitzungen zurück.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="cc7aa-124">GRANT-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="cc7aa-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="cc7aa-125">Instant messaging (IM) Sitzung Archivierungsrichtlinien für Benutzer oder Gruppen von Benutzern zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="cc7aa-126">Mithilfe dieser Archivierungsrichtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="cc7aa-127">Mit New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="cc7aa-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="cc7aa-128">Erstellt neue Archivierungsrichtlinien für Chatsitzungen.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="cc7aa-129">Mithilfe dieser Archivierungsrichtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="cc7aa-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="cc7aa-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="cc7aa-131">Entfernt die angegebene Sofortnachrichten (Instant messaging) Archivierungsrichtlinie, der bestimmt, ob Skype für Business Server automatisch alle Sofortnachrichtensitzungen gespeichert, die zwischen internen Benutzern und/oder alle Sofortnachrichtensitzungen zwischen internen Benutzern und Verbundpartner stattfinden.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="cc7aa-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="cc7aa-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="cc7aa-133">Ändert eine vorhandene Sofortnachrichten (Instant messaging) Archivierungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="cc7aa-134">Eine Archivierungsrichtlinie bietet die Möglichkeit, alle IM-Sitzungen und Konferenzen, die stattfinden zwischen internen Benutzern archivieren. Sie können auch Sitzungen archivieren, die zwischen internen Benutzern und Verbundpartner stattfinden.</span><span class="sxs-lookup"><span data-stu-id="cc7aa-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

