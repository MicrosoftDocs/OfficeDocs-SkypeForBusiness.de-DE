---
title: Verwalten von konferenzrichtlinien in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Zusammenfassung: Erfahren Sie, wie konferenzrichtlinien in Skype für Business Server verwalten.'
ms.openlocfilehash: d5fed0c6615747069d71015fca33144ca41dd64b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986657"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="aba14-103">Verwalten von konferenzrichtlinien in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="aba14-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="aba14-104">**Zusammenfassung:** Erfahren Sie, wie konferenzrichtlinien in Skype für Business Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="aba14-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="aba14-105">In diesem Themenbereich wird die Verwaltung der Konferenzrichtlinien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aba14-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="aba14-106">Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Planen von Konferenzen in Skype für Business Server](../../plan-your-deployment/conferencing/conferencing.md) und [Konferenzen in Skype für Business Server bereitstellen](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="aba14-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="aba14-p102">Mit den Konferenzrichtlinien können Sie eine breite Auswahl an Planungs- und Teilnahmeoptionen definieren, von der Verwendung von IP-Audio und -Video in einer Besprechung bis hin zur Höchstzahl der möglichen Teilnehmer. Sie können die Konferenzrichtlinien verwenden, um die Sicherheit, die Bandbreite und die rechtlichen Aspekte von Besprechungen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="aba14-p102">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="aba14-p103">Die Konferenzrichtlinie kann auf drei Ebenen definiert werden: auf globaler, auf Standort- und auf Benutzerebene. Die Einstellungen gelten für einen bestimmten Benutzer vom engsten bis hin zum weitesten Bereich. Wenn Sie einem Benutzer eine Richtlinie zuweisen, erhalten diese Einstellungen Vorrang. Wenn Sie keine Benutzerrichtlinie zuweisen, gelten die Standorteinstellungen. Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale Richtlinie die Standardeinstellungen bereit.</span><span class="sxs-lookup"><span data-stu-id="aba14-p103">You can define conferencing policy on three levels: global scope, site scope, and user scope. Settings apply to a specific user from the narrowest scope to the widest scope. If you assign a policy to a user, those settings take precedence. If you do not assign a user policy, site settings apply. If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="aba14-p104">Eine globale Richtlinie ist standardmäßig vorhanden. Sie können daher keine neue globale Richtlinie erstellen. Außerdem können Sie die vorhandene globale Richtlinie nicht löschen. Es ist jedoch möglich, die vorhandene globale Richtlinie Ihren Standardeinstellungen entsprechend anzupassen.</span><span class="sxs-lookup"><span data-stu-id="aba14-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="aba14-116">Verwalten von konferenzrichtlinien mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="aba14-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="aba14-117">So verwalten Sie konferenzrichtlinien mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="aba14-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="aba14-118">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="aba14-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="aba14-119">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="aba14-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="aba14-120">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="aba14-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="aba14-121">Verwalten von konferenzrichtlinien mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="aba14-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="aba14-122">Verwenden Sie zum Verwalten von Besprechungen mithilfe von Skype für Business Server-Verwaltungsshell die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="aba14-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="aba14-123">**Konferenzrichtlinieneinstellungen**</span><span class="sxs-lookup"><span data-stu-id="aba14-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="aba14-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="aba14-124">**Cmdlet**</span></span>|<span data-ttu-id="aba14-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="aba14-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="aba14-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="aba14-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="aba14-127">Gibt Informationen zu den Konferenzrichtlinien zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="aba14-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="aba14-128">GRANT-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="aba14-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="aba14-129">Weist einzelnen Benutzern eine Konferenzrichtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="aba14-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="aba14-130">Mit New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="aba14-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="aba14-131">Erstellt eine neue Konferenzrichtlinie für die Verwendung in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="aba14-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="aba14-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="aba14-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="aba14-133">Entfernt die angegebene Konferenzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="aba14-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="aba14-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="aba14-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="aba14-135">Ändert eine vorhandene Konferenzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="aba14-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

