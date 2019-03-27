---
title: Archivierungsrichtlinie
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 'Zum Aktivieren von Archivierungsrichtlinien verwendet und Archivierung für Benutzer deaktivieren auf Skype für Business Server verwaltet. In einer Archivierungsrichtlinie können Sie die Archivierung jeweils für eine oder beide der folgenden Kommunikationsarten aktivieren oder deaktivieren:'
ms.openlocfilehash: 4af5b5d8eb0f59d6899a73b7de6516d665fe041e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884796"
---
# <a name="archiving-policy"></a><span data-ttu-id="5712b-104">Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="5712b-104">Archiving Policy</span></span>
 
<span data-ttu-id="5712b-105">Zum Aktivieren von Archivierungsrichtlinien verwendet und Archivierung für Benutzer deaktivieren auf Skype für Business Server verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5712b-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="5712b-106">In einer Archivierungsrichtlinie können Sie die Archivierung jeweils für eine oder beide der folgenden Kommunikationsarten aktivieren oder deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="5712b-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="5712b-107">Interne Kommunikation</span><span class="sxs-lookup"><span data-stu-id="5712b-107">Internal communications</span></span>
    
- <span data-ttu-id="5712b-108">Externe Kommunikation (mit mindestens einem Benutzer außerhalb des internen Netzwerks)</span><span class="sxs-lookup"><span data-stu-id="5712b-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="5712b-109">Zu den Archivierungsrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Archivierungsrichtlinien für Standorte und Benutzer:</span><span class="sxs-lookup"><span data-stu-id="5712b-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="5712b-110">**Globale Richtlinie** Die globale Richtlinie wird standardmäßig in allen Bereitstellungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="5712b-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="5712b-111">Sie können die globale Richtlinie bearbeiten, aber Sie können diese Richtlinie nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="5712b-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="5712b-112">Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="5712b-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="5712b-113">**Richtlinien für den Standort (optional)** Sie können eine oder mehrere Website Archivierungsrichtlinien angeben, von denen jedes Sie zum Aktivieren und Deaktivieren der Archivierung von interner oder externer Kommunikation für eine einzelne Website konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="5712b-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="5712b-114">Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für die in den Archivierungsstandortrichtlinien angegebenen Standorte.</span><span class="sxs-lookup"><span data-stu-id="5712b-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="5712b-115">Sie können Standortrichtlinien bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="5712b-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="5712b-116">**Richtlinie für Benutzer (optional)** Sie können eine oder mehrere Benutzer Archivierungsrichtlinien angeben, von denen jedes Sie zum Aktivieren und Deaktivieren der Archivierung von interner oder externer Kommunikation für einen bestimmten Benutzer oder eine Benutzergruppe konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="5712b-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="5712b-117">Eine Benutzerrichtlinie setzt die globale Richtlinie und die Standortrichtlinien außer Kraft, jedoch nur für die Benutzer und Benutzergruppen, denen Sie Archivierungsrichtlinien auf Benutzerebene zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5712b-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="5712b-118">Sie können Benutzerrichtlinien bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="5712b-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5712b-119">Archivierungsrichtlinien gelten nur für Benutzer, die auf Skype für Business Server verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5712b-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="5712b-120">Wenn Sie Exchange-Integration zum Speichern von archivierten Daten in Microsoft Exchange verwenden, Richtlinien Steuerelement Archivierung für Exchange, der auf Exchange-Benutzer verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5712b-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="5712b-121">Zum Aktivieren der Archivierung für die Benutzer muss das Postfach des Benutzers auf Compliance-Archiv platziert werden.</span><span class="sxs-lookup"><span data-stu-id="5712b-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="5712b-p107">Auf der Seite **Archivierungsrichtlinie** sind die einzelnen Archivierungsrichtlinien aufgeführt, die für die Bereitstellung konfiguriert sind. Außerdem werden der Richtlinienname und -bereich (Global, Standort oder Benutzer) sowie die für eine Archivierungsrichtlinie aktivierten Archivierungsoptionen angezeigt. Auf der Seite **Archivierungsrichtlinie** haben Sie die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="5712b-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="5712b-125">**Neue** Sie können eine oder mehrere der folgenden optionalen Archivierungsrichtlinien hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="5712b-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="5712b-126">Standortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="5712b-126">Site policy</span></span>
    
  - <span data-ttu-id="5712b-127">Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="5712b-127">User policy</span></span>
    
- <span data-ttu-id="5712b-128">**Bearbeiten** Sie können keines der Archivierungsrichtlinien auf der Seite aufgeführten Optionen ändern.</span><span class="sxs-lookup"><span data-stu-id="5712b-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="5712b-129">Mit dieser Option haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="5712b-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="5712b-130">**Details anzeigen**   Mit dieser Option öffnen Sie ein Dialogfeld, in dem Sie die Archivierungsoptionen für eine Archivierungsrichtlinie ändern können.</span><span class="sxs-lookup"><span data-stu-id="5712b-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="5712b-131">**Alles auswählen** Mit dieser Option werden alle Archivierungsrichtlinien der Liste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="5712b-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="5712b-132">**Löschen**   Mit dieser Option werden alle ausgewählten Archivierungsrichtlinien gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5712b-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="5712b-133">**Aktion** Verwenden Sie diese Option, um schnell aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation in einer Richtlinie auf der Seite, anstatt zur Bearbeitung der Richtlinie aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5712b-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="5712b-134">Die unter **Aktion** verfügbaren Optionen richten sich danach, welche Option in der Archivierungsrichtlinie momentan angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="5712b-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="5712b-135">Alle Optionen sind verfügbar, mit Ausnahme der Option, die aktuell für die Archivierungsrichtlinie wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="5712b-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="5712b-136">Folgende Optionen sind vorhanden:</span><span class="sxs-lookup"><span data-stu-id="5712b-136">Options include the following:</span></span>
    
  - <span data-ttu-id="5712b-137">**Archivierung interner Kommunikation aktivieren**</span><span class="sxs-lookup"><span data-stu-id="5712b-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="5712b-138">**Archivierung interner Kommunikation deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="5712b-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="5712b-139">**Archivierung externer Kommunikation aktivieren**</span><span class="sxs-lookup"><span data-stu-id="5712b-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="5712b-140">**Archivierung externer Kommunikation deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="5712b-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="5712b-141">**Aktualisieren** Sie können die Seite **Archivierungsrichtlinie** zum Überprüfen des Status der Optionen aller Archivierungsrichtlinien aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5712b-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="5712b-142">Weitere Informationen über die Archivierungsfunktion und Funktionen, einschließlich Exchange-Integration finden Sie unter [Plan für die Archivierung in Skype für Business Server](../../../plan-your-deployment/archiving/archiving.md), [Archivierung für Skype für Business Server bereitstellen](../../../deploy/deploy-archiving/deploy-archiving.md)und verwalten [Archivierung in Skype für Unternehmen Server](../../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="5712b-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

