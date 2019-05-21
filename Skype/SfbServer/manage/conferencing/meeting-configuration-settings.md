---
title: Verwalten von Besprechungs Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Konfigurationseinstellungen für Besprechungen in Skype for Business Server verwalten.'
ms.openlocfilehash: d9ed049fe4873428729149e1ea624bf715bb81ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283739"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e49e5-103">Verwalten von Besprechungs Konfigurationseinstellungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e49e5-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="e49e5-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie die Konfigurationseinstellungen für Besprechungen in Skype for Business Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="e49e5-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="e49e5-105">In diesem Themenbereich wird die Verwaltung der Einstellungen der Besprechungskonfiguration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e49e5-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="e49e5-106">Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Planen von Konferenzen in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) und [Bereitstellen von Konferenzen in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="e49e5-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="e49e5-107">Die Konfigurationseinstellungen für Besprechungen diktieren die Art der Besprechungen, die Benutzer erstellen können, und Steuern, wie (oder sogar ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="e49e5-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="e49e5-108">Beachten Sie, dass sich diese Einstellungen nur auf geplante Besprechungen auswirken. Sie wirken sich nicht auf Ad-hoc-Besprechungen aus, die durch Klicken auf die Option "jetzt besprechen" in Skype for Business erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e49e5-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="e49e5-109">Die Konfigurationseinstellungen für Besprechungen definieren Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e49e5-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="e49e5-110">Werden Benutzer, die sich über das Telefonfestnetz (PSTN, Public Switched Telephone Network) einwählen, in den Wartebereich umgeleitet?</span><span class="sxs-lookup"><span data-stu-id="e49e5-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="e49e5-111">Welche Benutzer können als Referenten fungieren?</span><span class="sxs-lookup"><span data-stu-id="e49e5-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="e49e5-112">Wird der Konferenztyp standardmäßig zugeordnet?</span><span class="sxs-lookup"><span data-stu-id="e49e5-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="e49e5-113">Werden anonyme Benutzer (ohne Authentifizierung) standardmäßig zugelassen?</span><span class="sxs-lookup"><span data-stu-id="e49e5-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="e49e5-114">Sie können die Merkmale von Besprechungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell definieren.</span><span class="sxs-lookup"><span data-stu-id="e49e5-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="e49e5-115">Sie können Besprechungseinstellungen auf globaler Ebene (standardmäßig erstellt), Websiteebene oder Poolebene angeben.</span><span class="sxs-lookup"><span data-stu-id="e49e5-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="e49e5-116">Standardmäßig werden die Besprechungen über die globalen Einstellungen definiert.</span><span class="sxs-lookup"><span data-stu-id="e49e5-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="e49e5-117">Wenn Sie Einstellungen auf der Poolebene erstellen, gelten diese für alle Besprechungen, die von dem jeweiligen Pool gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="e49e5-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="e49e5-118">Wenn Sie keine Einstellungen auf der Poolebene erstellen, gelten die auf der Standortebene definierten Einstellungen (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="e49e5-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="e49e5-119">Sind keine Einstellungen auf der Standortebene definiert, werden die globalen Einstellungen auf sämtliche Besprechungen angewendet.</span><span class="sxs-lookup"><span data-stu-id="e49e5-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e49e5-120">Verwalten von Besprechungseinstellungen mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="e49e5-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="e49e5-121">So verwalten Sie Besprechungseinstellungen mithilfe der Skype for Business Server-Systemsteuerung:</span><span class="sxs-lookup"><span data-stu-id="e49e5-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="e49e5-122">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="e49e5-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="e49e5-123">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="e49e5-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e49e5-124">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e49e5-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e49e5-125">Verwalten von Besprechungseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="e49e5-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="e49e5-126">Verwenden Sie zum Verwalten von Besprechungen mithilfe der Skype for Business Server-Verwaltungsshell die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e49e5-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="e49e5-127">**Konfigurationseinstellungen für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="e49e5-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="e49e5-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="e49e5-128">**Cmdlet**</span></span>|<span data-ttu-id="e49e5-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e49e5-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e49e5-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e49e5-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="e49e5-131">Gibt Informationen zu den derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen zurück.</span><span class="sxs-lookup"><span data-stu-id="e49e5-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="e49e5-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e49e5-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="e49e5-133">Erstellt eine neue Auflistung von Konfigurationseinstellungen für Besprechungen auf Standort- oder Dienstebene.</span><span class="sxs-lookup"><span data-stu-id="e49e5-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="e49e5-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e49e5-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="e49e5-135">Löscht eine vorhandene Auflistung von Konfigurationseinstellungen für Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="e49e5-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="e49e5-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e49e5-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="e49e5-137">Passt die derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="e49e5-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

