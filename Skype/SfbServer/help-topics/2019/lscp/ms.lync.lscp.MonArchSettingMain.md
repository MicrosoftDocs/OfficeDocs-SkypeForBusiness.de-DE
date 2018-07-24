---
title: Archivierungskonfiguration
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 'Verwenden Sie Archivierungskonfigurationen Steuerelement Archivierungsoptionen für Ihre Skype für Business Server-Bereitstellung, einschließlich aktivieren und deaktivieren die folgenden Optionen aus:'
ms.openlocfilehash: d8e7adec0918cf13104857957442f1f0a5f4ff3d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21004260"
---
# <a name="archiving-configuration"></a><span data-ttu-id="03782-103">Archivierungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="03782-103">Archiving Configuration</span></span>
 
<span data-ttu-id="03782-104">Verwenden Sie Archivierungskonfigurationen Steuerelement Archivierungsoptionen für Ihre Skype für Business Server-Bereitstellung, einschließlich aktivieren und deaktivieren die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="03782-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="03782-105">Blockieren von Chat- und Konferenzsitzungen bei Archivierungsfehlern</span><span class="sxs-lookup"><span data-stu-id="03782-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="03782-106">Integration mit Exchange-Speicher für Benutzer, die sich in Exchange</span><span class="sxs-lookup"><span data-stu-id="03782-106">Integration with Exchange storage, for users homed on Exchange</span></span>
    
- <span data-ttu-id="03782-107">Bereinigen archivierter Daten</span><span class="sxs-lookup"><span data-stu-id="03782-107">Purging of archived data</span></span>
    
<span data-ttu-id="03782-108">Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Archivierungskonfigurationen:</span><span class="sxs-lookup"><span data-stu-id="03782-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="03782-109">**Globale Konfiguration** Die globale Konfiguration wird standardmäßig in allen Skype für Business Server-Bereitstellungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="03782-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="03782-110">Sie können die globale Konfiguration bearbeiten, aber Sie können diese Archivierungskonfiguration nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="03782-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="03782-111">Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="03782-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="03782-112">**Standortkonfiguration (optional)** Sie können eine oder mehrere Website Archivierungskonfigurationen angeben, von denen jedes Steuerelement Archivierungsoptionen für einen bestimmten Standort konfigurierbaren.</span><span class="sxs-lookup"><span data-stu-id="03782-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="03782-113">Eine Standortkonfiguration setzt die globale Konfiguration außer Kraft, jedoch nur für die in den Archivierungsstandortkonfigurationen angegebenen Standorte.</span><span class="sxs-lookup"><span data-stu-id="03782-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="03782-114">Sie können Standortkonfigurationen bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="03782-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="03782-115">**Pool-Konfiguration (optional)** Sie können eine oder mehrere Pools Archivierungskonfiguration Steuerelement Archivierungsoptionen für einen bestimmten Pool angeben.</span><span class="sxs-lookup"><span data-stu-id="03782-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="03782-116">Eine Poolkonfiguration setzt die globale Konfiguration und die Standortkonfiguration außer Kraft, jedoch nur für die in den Archivierungspoolkonfigurationen angegebenen Pools.</span><span class="sxs-lookup"><span data-stu-id="03782-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="03782-117">Sie können Poolkonfigurationen bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="03782-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="03782-118">Archivierung Konfigurationen gelten für Benutzer, der in Skype für Business Server verwaltet und, wenn Sie Exchange, zum Speichern von archivierten Daten in Microsoft Exchange verwenden, für Benutzer, die sich in Exchange aber etwas unterschiedlich implementiert werden, für Benutzer in Exchange verwaltet.</span><span class="sxs-lookup"><span data-stu-id="03782-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange but are implemented slightly differently for users homed on Exchange.</span></span> <span data-ttu-id="03782-119">Im nächsten Abschnitt werden die Unterschiede beschrieben.</span><span class="sxs-lookup"><span data-stu-id="03782-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="03782-p105">Auf der Seite **Archivierungskonfiguration** werden die einzelnen Archivierungsrichtlinien aufgeführt, die für die Bereitstellung konfiguriert sind. Außerdem werden der Richtlinienname und -bereich (Global, Standort oder Pool) sowie die für eine Archivierungskonfiguration aktivierten Archivierungsoptionen angezeigt. Auf der Seite **Archivierungskonfiguration** haben Sie die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="03782-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="03782-123">**Neue** Sie können eine oder mehrere der folgenden optionalen Archivierungskonfigurationen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="03782-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="03782-124">Standortkonfiguration</span><span class="sxs-lookup"><span data-stu-id="03782-124">Site configuration</span></span>
    
  - <span data-ttu-id="03782-125">Poolkonfiguration</span><span class="sxs-lookup"><span data-stu-id="03782-125">Pool configuration</span></span>
    
- <span data-ttu-id="03782-126">**Bearbeiten** Sie können keines der Archivierungskonfiguration erst auf der Seite aufgeführten Optionen ändern.</span><span class="sxs-lookup"><span data-stu-id="03782-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="03782-127">Mit dieser Option haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="03782-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="03782-128">**Details anzeigen** Diese Option öffnet ein Dialogfeld, in dem Sie die Archivierungsoptionen für den ausgewählten Archivierungskonfiguration ändern können.</span><span class="sxs-lookup"><span data-stu-id="03782-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="03782-129">Sie können nur für jeweils eine Archivierungskonfiguration Details anzeigen.</span><span class="sxs-lookup"><span data-stu-id="03782-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="03782-130">**Wählen Sie alle** Diese Option werden alle Archivierungskonfigurationen der Liste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="03782-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="03782-131">**Löschen** Diese Option werden alle ausgewählte Archivierungskonfigurationen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="03782-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="03782-132">**Aktion** Verwenden Sie diese Option, um schnell aktivieren oder Deaktivieren der Archivierung von Sofortnachrichtensitzungen oder webkonferenzsitzungen in einer Konfiguration auf der Seite, anstatt zur Bearbeitung der Konfigurations aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="03782-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="03782-133">Die unter **Aktion** verfügbaren Optionen richten sich danach, welche Option in der Archivierungskonfiguration momentan angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="03782-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="03782-134">Alle Optionen sind verfügbar, mit Ausnahme der Option, die für die Archivierungskonfiguration derzeit wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="03782-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="03782-135">Folgende Optionen sind vorhanden:</span><span class="sxs-lookup"><span data-stu-id="03782-135">Options include the following:</span></span>
    
  - <span data-ttu-id="03782-136">**Chatsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="03782-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="03782-137">**Chat- und Webkonferenzsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="03782-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="03782-138">**Archivierung deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="03782-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="03782-139">**Aktualisieren** Sie können den Status der Optionen aller Archivierungskonfigurationen zu überprüfen, um die Seite **Archivierungskonfiguration** aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="03782-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="03782-140">Weitere Informationen über die Archivierungsfunktion und Funktionen, einschließlich Exchange-Integration finden Sie unter [Plan für die Archivierung in Skype für Business Server](../../../plan-your-deployment/archiving/archiving.md), [Archivierung für Skype für Business Server bereitstellen](../../../deploy/deploy-archiving/deploy-archiving.md)und verwalten [Archivierung in Skype für Unternehmen Server](../../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="03782-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

