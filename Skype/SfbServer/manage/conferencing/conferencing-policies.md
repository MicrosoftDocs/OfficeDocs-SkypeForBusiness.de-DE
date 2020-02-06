---
title: Verwalten von Konferenzrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server verwalten.'
ms.openlocfilehash: fc069093b9cc7cf5ce0e1e1f1efc0ee9e18e335d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818646"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="9e3a5-103">Verwalten von Konferenzrichtlinien in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9e3a5-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="9e3a5-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="9e3a5-105">In diesem Themenbereich wird die Verwaltung der Konferenzrichtlinien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="9e3a5-106">Weitere Informationen zum Planen und Bereitstellen von Konferenzen finden Sie unter [Planen von Konferenzen in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) und [Bereitstellen von Konferenzen in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="9e3a5-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="9e3a5-p102">Mit den Konferenzrichtlinien können Sie eine breite Auswahl an Planungs- und Teilnahmeoptionen definieren, von der Verwendung von IP-Audio und -Video in einer Besprechung bis hin zur Höchstzahl der möglichen Teilnehmer. Sie können die Konferenzrichtlinien verwenden, um die Sicherheit, die Bandbreite und die rechtlichen Aspekte von Besprechungen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-p102">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="9e3a5-109">Die Konferenzrichtlinie kann auf drei Ebenen definiert werden: auf globaler, auf Standort- und auf Benutzerebene.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="9e3a5-110">Die Einstellungen gelten für einen bestimmten Benutzer vom engsten bis hin zum weitesten Bereich.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="9e3a5-111">Wenn Sie einem Benutzer eine Richtlinie zuweisen, erhalten diese Einstellungen Vorrang.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="9e3a5-112">Wenn Sie keine Benutzerrichtlinie zuweisen, gelten die Standorteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="9e3a5-113">Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale Richtlinie die Standardeinstellungen bereit.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="9e3a5-114">Eine globale Richtlinie ist standardmäßig vorhanden, sodass Sie keine neue globale Richtlinie erstellen können.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-114">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="9e3a5-115">Sie können auch die vorhandene globale Richtlinie nicht löschen, aber Sie können die vorhandene globale Richtlinie so ändern, dass die Standardeinstellungen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-115">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9e3a5-116">Verwalten von Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="9e3a5-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="9e3a5-117">So verwalten Sie Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung:</span><span class="sxs-lookup"><span data-stu-id="9e3a5-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="9e3a5-118">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="9e3a5-119">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9e3a5-120">Klicken Sie auf der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9e3a5-121">Verwalten von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="9e3a5-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="9e3a5-122">Verwenden Sie zum Verwalten von Besprechungen mithilfe der Skype for Business Server-Verwaltungsshell die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="9e3a5-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="9e3a5-123">**Konferenzrichtlinieneinstellungen**</span><span class="sxs-lookup"><span data-stu-id="9e3a5-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="9e3a5-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="9e3a5-124">**Cmdlet**</span></span>|<span data-ttu-id="9e3a5-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9e3a5-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="9e3a5-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="9e3a5-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="9e3a5-127">Gibt Informationen zu den Konferenzrichtlinien zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="9e3a5-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="9e3a5-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="9e3a5-129">Weist einzelnen Benutzern eine Konferenzrichtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="9e3a5-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="9e3a5-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="9e3a5-131">Erstellt eine neue Konferenzrichtlinie für die Verwendung in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="9e3a5-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="9e3a5-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="9e3a5-133">Entfernt die angegebene Konferenzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="9e3a5-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="9e3a5-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="9e3a5-135">Ändert eine vorhandene Konferenzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="9e3a5-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

