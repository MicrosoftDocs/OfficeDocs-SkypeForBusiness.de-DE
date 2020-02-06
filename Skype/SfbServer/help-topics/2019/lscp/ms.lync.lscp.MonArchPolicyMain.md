---
title: Archivierungsrichtlinie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie verwenden Archivierungsrichtlinien, um die Archivierung für Benutzer zu aktivieren und zu deaktivieren, die in Skype for Business Server verwaltet werden. In einer Archivierungsrichtlinie können Sie die Archivierung jeweils für eine oder beide der folgenden Kommunikationsarten aktivieren oder deaktivieren:'
ms.openlocfilehash: cbd15a7ea1f183a90d30fac8f44fae46edc1610e
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795054"
---
# <a name="archiving-policy"></a><span data-ttu-id="c695e-104">Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="c695e-104">Archiving Policy</span></span>
 
<span data-ttu-id="c695e-105">Sie verwenden Archivierungsrichtlinien, um die Archivierung für Benutzer zu aktivieren und zu deaktivieren, die in Skype for Business Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="c695e-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="c695e-106">In einer Archivierungsrichtlinie können Sie die Archivierung jeweils für eine oder beide der folgenden Kommunikationsarten aktivieren oder deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="c695e-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="c695e-107">Interne Kommunikation</span><span class="sxs-lookup"><span data-stu-id="c695e-107">Internal communications</span></span>
    
- <span data-ttu-id="c695e-108">Externe Kommunikation (mit mindestens einem Benutzer außerhalb des internen Netzwerks)</span><span class="sxs-lookup"><span data-stu-id="c695e-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="c695e-109">Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Archivierungsrichtlinien für Standorte und Benutzer:</span><span class="sxs-lookup"><span data-stu-id="c695e-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="c695e-110">**Globale Richtlinie** Die globale Richtlinie wird in allen Bereitstellungen standardmäßig erstellt.</span><span class="sxs-lookup"><span data-stu-id="c695e-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="c695e-111">Sie können die globale Richtlinie bearbeiten, aber Sie können diese Richtlinie nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="c695e-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="c695e-112">Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="c695e-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="c695e-113">**Website Richtlinie (optional)** Sie können eine oder mehrere Website Archivierungsrichtlinien angeben, die jeweils für die Aktivierung und Deaktivierung der Archivierung interner oder externer Kommunikation für eine einzelne Website konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="c695e-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="c695e-114">Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für die in den Archivierungsstandortrichtlinien angegebenen Standorte.</span><span class="sxs-lookup"><span data-stu-id="c695e-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="c695e-115">Sie können Standortrichtlinien bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="c695e-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="c695e-116">**Benutzerrichtlinie (optional)** Sie können eine oder mehrere Benutzer Archivierungsrichtlinien angeben, die jeweils für die Aktivierung und Deaktivierung der Archivierung interner oder externer Kommunikation für einen bestimmten Benutzer oder eine Benutzergruppe konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="c695e-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="c695e-117">Eine Benutzerrichtlinie setzt die globale Richtlinie und die Standortrichtlinien außer Kraft, jedoch nur für die Benutzer und Benutzergruppen, denen Sie Archivierungsrichtlinien auf Benutzerebene zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c695e-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="c695e-118">Sie können Benutzerrichtlinien bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="c695e-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c695e-119">Archivierungsrichtlinien gelten nur für Benutzer, die in Skype for Business Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="c695e-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="c695e-120">Wenn Sie die Exchange-Integration zum Speichern von Archivierungsdaten in Microsoft Exchange verwenden, Steuern Exchange-Richtlinien die Archivierung für in Exchange beheimatete Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c695e-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="c695e-121">Um die Archivierung für diese Benutzer zu aktivieren, muss das Postfach des Benutzers in-situ-Speicherplatz platziert werden.</span><span class="sxs-lookup"><span data-stu-id="c695e-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="c695e-p107">Auf der Seite **Archivierungsrichtlinie** sind die einzelnen Archivierungsrichtlinien aufgeführt, die für die Bereitstellung konfiguriert sind. Außerdem werden der Richtlinienname und -bereich (Global, Standort oder Benutzer) sowie die für eine Archivierungsrichtlinie aktivierten Archivierungsoptionen angezeigt. Auf der Seite **Archivierungsrichtlinie** haben Sie die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="c695e-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="c695e-125">**Neu** Sie können eine oder mehrere der folgenden optionalen Archivierungsrichtlinien hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="c695e-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="c695e-126">Standortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="c695e-126">Site policy</span></span>
    
  - <span data-ttu-id="c695e-127">Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="c695e-127">User policy</span></span>
    
- <span data-ttu-id="c695e-128">**Bearbeiten** von Sie können die Optionen für alle auf der Seite aufgelisteten Archivierungsrichtlinien ändern.</span><span class="sxs-lookup"><span data-stu-id="c695e-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="c695e-129">Mit dieser Option haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="c695e-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="c695e-130">**Details anzeigen**   Mit dieser Option öffnen Sie ein Dialogfeld, in dem Sie die Archivierungsoptionen für eine Archivierungsrichtlinie ändern können.</span><span class="sxs-lookup"><span data-stu-id="c695e-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="c695e-131">**Alles auswählen** Mit dieser Option werden alle Archivierungsrichtlinien der Liste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="c695e-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="c695e-132">**Löschen**   Mit dieser Option werden alle ausgewählten Archivierungsrichtlinien gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c695e-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="c695e-133">**Aktion** Sie können diese Option verwenden, um die Archivierung interner oder externer Kommunikation in einer auf der Seite aufgelisteten Richtlinie schnell zu aktivieren oder zu deaktivieren, anstatt die Richtlinie zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c695e-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="c695e-134">Die unter **Aktion** verfügbaren Optionen richten sich danach, welche Option in der Archivierungsrichtlinie momentan angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c695e-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="c695e-135">Alle Optionen sind verfügbar, mit Ausnahme der Option, die aktuell für die Archivierungsrichtlinie wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="c695e-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="c695e-136">Folgende Optionen sind vorhanden:</span><span class="sxs-lookup"><span data-stu-id="c695e-136">Options include the following:</span></span>
    
  - <span data-ttu-id="c695e-137">**Archivierung interner Kommunikation aktivieren**</span><span class="sxs-lookup"><span data-stu-id="c695e-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="c695e-138">**Archivierung interner Kommunikation deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="c695e-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="c695e-139">**Archivierung externer Kommunikation aktivieren**</span><span class="sxs-lookup"><span data-stu-id="c695e-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="c695e-140">**Archivierung externer Kommunikation deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="c695e-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="c695e-141">**Aktualisieren** Sie können die Seite **Archivierungsrichtlinie** aktualisieren, um den Status der Optionen aller Archivierungsrichtlinien zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c695e-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="c695e-142">Details zum Archivierungsfeature und zu den Funktionen, einschließlich der Exchange-Integration, finden Sie unter [Planen der Archivierung in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Bereitstellen der Archivierung für Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)und [Verwalten der Archivierung in Skype for Business Server](../../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="c695e-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

