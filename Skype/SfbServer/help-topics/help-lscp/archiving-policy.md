---
title: Archivierungsrichtlinie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Sie verwenden Archivierungsrichtlinien, um die Archivierung für Benutzer zu aktivieren und zu deaktivieren, die in Skype for Business Server verwaltet werden. In einer Archivierungsrichtlinie können Sie die Archivierung jeweils für eine oder beide der folgenden Kommunikationsarten aktivieren oder deaktivieren:'
ms.openlocfilehash: c0bd80dcbe2c140d861829ff5bd1476d070423ba
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687018"
---
# <a name="archiving-policy"></a><span data-ttu-id="cbd0f-104">Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cbd0f-104">Archiving Policy</span></span>
 
<span data-ttu-id="cbd0f-105">Sie verwenden Archivierungsrichtlinien, um die Archivierung für Benutzer zu aktivieren und zu deaktivieren, die in Skype for Business Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="cbd0f-106">In einer Archivierungsrichtlinie können Sie die Archivierung jeweils für eine oder beide der folgenden Kommunikationsarten aktivieren oder deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="cbd0f-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="cbd0f-107">Interne Kommunikation</span><span class="sxs-lookup"><span data-stu-id="cbd0f-107">Internal communications</span></span>
    
- <span data-ttu-id="cbd0f-108">Externe Kommunikation (mit mindestens einem Benutzer außerhalb des internen Netzwerks)</span><span class="sxs-lookup"><span data-stu-id="cbd0f-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="cbd0f-109">Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Archivierungsrichtlinien für Standorte und Benutzer:</span><span class="sxs-lookup"><span data-stu-id="cbd0f-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="cbd0f-110">**Globale Richtlinie** Die globale Richtlinie wird in allen Bereitstellungen standardmäßig erstellt.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="cbd0f-111">Sie können die globale Richtlinie bearbeiten, aber Sie können diese Richtlinie nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="cbd0f-112">Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="cbd0f-113">**Website Richtlinie (optional)** Sie können eine oder mehrere Website Archivierungsrichtlinien angeben, die jeweils für die Aktivierung und Deaktivierung der Archivierung interner oder externer Kommunikation für eine einzelne Website konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="cbd0f-114">Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für die in den Archivierungsstandortrichtlinien angegebenen Standorte.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="cbd0f-115">Sie können Standortrichtlinien bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="cbd0f-116">**Benutzerrichtlinie (optional)** Sie können eine oder mehrere Benutzer Archivierungsrichtlinien angeben, die jeweils für die Aktivierung und Deaktivierung der Archivierung interner oder externer Kommunikation für einen bestimmten Benutzer oder eine Benutzergruppe konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="cbd0f-117">Eine Benutzerrichtlinie setzt die globale Richtlinie und die Standortrichtlinien außer Kraft, jedoch nur für die Benutzer und Benutzergruppen, denen Sie Archivierungsrichtlinien auf Benutzerebene zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="cbd0f-118">Sie können Benutzerrichtlinien bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cbd0f-119">Archivierungsrichtlinien gelten nur für Benutzer, die in Skype for Business Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="cbd0f-120">Wenn Sie die Exchange-Integration zum Speichern von Archivierungsdaten in Microsoft Exchange verwenden, Steuern Exchange 2013-Richtlinien die Archivierung für Benutzer, die in Exchange 2013 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="cbd0f-121">Um die Archivierung für diese Benutzer zu aktivieren, muss das Postfach des Benutzers in-situ-Speicherplatz platziert werden.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="cbd0f-p107">Auf der Seite **Archivierungsrichtlinie** sind die einzelnen Archivierungsrichtlinien aufgeführt, die für die Bereitstellung konfiguriert sind. Außerdem werden der Richtlinienname und -bereich (Global, Standort oder Benutzer) sowie die für eine Archivierungsrichtlinie aktivierten Archivierungsoptionen angezeigt. Auf der Seite **Archivierungsrichtlinie** haben Sie die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="cbd0f-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="cbd0f-125">**Neu** Sie können eine oder mehrere der folgenden optionalen Archivierungsrichtlinien hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="cbd0f-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="cbd0f-126">Standortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cbd0f-126">Site policy</span></span>
    
  - <span data-ttu-id="cbd0f-127">Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cbd0f-127">User policy</span></span>
    
- <span data-ttu-id="cbd0f-128">**Bearbeiten** von Sie können die Optionen für alle auf der Seite aufgelisteten Archivierungsrichtlinien ändern.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="cbd0f-129">Mit dieser Option haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="cbd0f-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="cbd0f-130">**Details anzeigen**   Mit dieser Option öffnen Sie ein Dialogfeld, in dem Sie die Archivierungsoptionen für eine Archivierungsrichtlinie ändern können.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="cbd0f-131">**Alles auswählen** Mit dieser Option werden alle Archivierungsrichtlinien der Liste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="cbd0f-132">**Löschen**   Mit dieser Option werden alle ausgewählten Archivierungsrichtlinien gelöscht.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="cbd0f-133">**Aktion** Sie können diese Option verwenden, um die Archivierung interner oder externer Kommunikation in einer auf der Seite aufgelisteten Richtlinie schnell zu aktivieren oder zu deaktivieren, anstatt die Richtlinie zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="cbd0f-134">Die unter **Aktion** verfügbaren Optionen richten sich danach, welche Option in der Archivierungsrichtlinie momentan angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="cbd0f-135">Alle Optionen sind verfügbar, mit Ausnahme der Option, die aktuell für die Archivierungsrichtlinie wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="cbd0f-136">Folgende Optionen sind vorhanden:</span><span class="sxs-lookup"><span data-stu-id="cbd0f-136">Options include the following:</span></span>
    
  - <span data-ttu-id="cbd0f-137">**Archivierung interner Kommunikation aktivieren**</span><span class="sxs-lookup"><span data-stu-id="cbd0f-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="cbd0f-138">**Archivierung interner Kommunikation deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="cbd0f-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="cbd0f-139">**Archivierung externer Kommunikation aktivieren**</span><span class="sxs-lookup"><span data-stu-id="cbd0f-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="cbd0f-140">**Archivierung externer Kommunikation deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="cbd0f-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="cbd0f-141">**Aktualisieren** Sie können die Seite **Archivierungsrichtlinie** aktualisieren, um den Status der Optionen aller Archivierungsrichtlinien zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="cbd0f-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="cbd0f-142">Details zum Archivierungsfeature und zu den Funktionen, einschließlich der Exchange-Integration, finden Sie unter [Planen der Archivierung in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Bereitstellen der Archivierung für Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)und [Verwalten der Archivierung in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="cbd0f-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

