---
title: Verwalten von besprechungskonfigurationseinstellungen in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Zusammenfassung: Informationen zum Verwalten von besprechungskonfigurationseinstellungen in Skype für Business Server.'
ms.openlocfilehash: 28f0dc37579f762b8ae3b0ac8ac58440c6ce5e24
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966066"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="bf8f9-103">Verwalten von besprechungskonfigurationseinstellungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="bf8f9-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="bf8f9-104">**Zusammenfassung:** Informationen zum Verwalten von besprechungskonfigurationseinstellungen in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="bf8f9-105">In diesem Themenbereich wird die Verwaltung der Einstellungen der Besprechungskonfiguration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="bf8f9-106">Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Planen von Konferenzen in Skype für Business Server](../../plan-your-deployment/conferencing/conferencing.md) und [Konferenzen in Skype für Business Server bereitstellen](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="bf8f9-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="bf8f9-107">Besprechungskonfigurationseinstellungen bestimmen den Typ des Besprechungen, die Benutzer, müssen Sie zusätzlich zu steuern erstellen können wie (oder sogar ob) anonyme Benutzer und Benutzer von einwahlkonferenzen können an diesen Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="bf8f9-108">Beachten Sie, dass diese Einstellungen nur geplante Besprechungen wirken sich auf. Sie wirken sich nicht auf Ad-hoc-Besprechungen durch Klicken auf die Option Jetzt besprechen in Skype für Unternehmen erstellt.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="bf8f9-109">Die Konfigurationseinstellungen für Besprechungen definieren Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bf8f9-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="bf8f9-110">Werden Benutzer, die sich über das Telefonfestnetz (PSTN, Public Switched Telephone Network) einwählen, in den Wartebereich umgeleitet?</span><span class="sxs-lookup"><span data-stu-id="bf8f9-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="bf8f9-111">Welche Benutzer können als Referenten fungieren?</span><span class="sxs-lookup"><span data-stu-id="bf8f9-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="bf8f9-112">Wird der Konferenztyp standardmäßig zugeordnet?</span><span class="sxs-lookup"><span data-stu-id="bf8f9-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="bf8f9-113">Werden anonyme Benutzer (ohne Authentifizierung) standardmäßig zugelassen?</span><span class="sxs-lookup"><span data-stu-id="bf8f9-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="bf8f9-114">Sie können die Merkmale von Besprechungen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell definieren.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="bf8f9-115">Sie können angeben, Besprechung Einstellungen auf globaler Ebene (standardmäßig erstellt), site-Ebene oder -pool-Ebene.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="bf8f9-116">Standardmäßig werden die Besprechungen über die globalen Einstellungen definiert.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="bf8f9-117">Wenn Sie Einstellungen auf der Poolebene erstellen, gelten diese für alle Besprechungen, die von dem jeweiligen Pool gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="bf8f9-118">Wenn Sie keine Einstellungen auf der Poolebene erstellen, gelten die auf der Standortebene definierten Einstellungen (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="bf8f9-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="bf8f9-119">Sind keine Einstellungen auf der Standortebene definiert, werden die globalen Einstellungen auf sämtliche Besprechungen angewendet.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="bf8f9-120">Verwalten von Einstellungen für die Besprechung mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="bf8f9-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="bf8f9-121">So verwalten Sie besprechungseinstellungen mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="bf8f9-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="bf8f9-122">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="bf8f9-123">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="bf8f9-124">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="bf8f9-125">Verwalten von Einstellungen für die Besprechung mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="bf8f9-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="bf8f9-126">Verwenden Sie zum Verwalten von Besprechungen mithilfe von Skype für Business Server-Verwaltungsshell die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="bf8f9-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="bf8f9-127">**Konfigurationseinstellungen für Besprechungen**</span><span class="sxs-lookup"><span data-stu-id="bf8f9-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="bf8f9-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="bf8f9-128">**Cmdlet**</span></span>|<span data-ttu-id="bf8f9-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bf8f9-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="bf8f9-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf8f9-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="bf8f9-131">Gibt Informationen zu den derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen zurück.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="bf8f9-132">Mit New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf8f9-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="bf8f9-133">Erstellt eine neue Auflistung von Konfigurationseinstellungen für Besprechungen auf Standort- oder Dienstebene.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="bf8f9-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf8f9-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="bf8f9-135">Löscht eine vorhandene Auflistung von Konfigurationseinstellungen für Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="bf8f9-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf8f9-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="bf8f9-137">Passt die derzeit in Ihrer Organisation verwendeten Besprechungskonfigurationseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="bf8f9-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

