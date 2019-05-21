---
title: Archivierungskonfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Sie verwenden Archivierungs Konfigurationen, um Archivierungsoptionen für Ihre Skype for Business Server-Bereitstellung zu steuern, einschließlich der Aktivierung und Deaktivierung der folgenden Optionen:'
ms.openlocfilehash: 8f3ed4289d68359cb8eb0d4cb0bfc3a303c53dd3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299848"
---
# <a name="archiving-configuration"></a><span data-ttu-id="0f0ad-103">Archivierungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="0f0ad-103">Archiving Configuration</span></span>
 
<span data-ttu-id="0f0ad-104">Sie verwenden Archivierungs Konfigurationen, um Archivierungsoptionen für Ihre Skype for Business Server-Bereitstellung zu steuern, einschließlich der Aktivierung und Deaktivierung der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="0f0ad-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="0f0ad-105">Blockieren von Chat- und Konferenzsitzungen bei Archivierungsfehlern</span><span class="sxs-lookup"><span data-stu-id="0f0ad-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="0f0ad-106">Integration in Exchange 2013-Speicher für Benutzer, die in Exchange 2013 verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="0f0ad-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="0f0ad-107">Bereinigen archivierter Daten</span><span class="sxs-lookup"><span data-stu-id="0f0ad-107">Purging of archived data</span></span>
    
<span data-ttu-id="0f0ad-108">Zu den Archivierungskonfigurationen gehören die globale Konfiguration und optional eine oder mehrere Archivierungskonfigurationen:</span><span class="sxs-lookup"><span data-stu-id="0f0ad-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="0f0ad-109">**Globale Konfiguration** Die globale Konfiguration wird standardmäßig in allen Skype for Business Server-Bereitstellungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="0f0ad-110">Sie können die globale Konfiguration bearbeiten, aber Sie können diese Archivierungskonfiguration nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="0f0ad-111">Wenn Sie versuchen, sie zu löschen, werden alle Optionen auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="0f0ad-112">**Websitekonfiguration (optional)** Sie können eine oder mehrere Website Archivierungs Konfigurationen angeben, die jeweils für die Steuerung der Archivierungsoptionen für eine bestimmte Website konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="0f0ad-113">Eine Standortkonfiguration setzt die globale Konfiguration außer Kraft, jedoch nur für die in den Archivierungsstandortkonfigurationen angegebenen Standorte.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="0f0ad-114">Sie können Standortkonfigurationen bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="0f0ad-115">**Pool Konfiguration (optional)** Sie können eine oder mehrere Pool Archivierungskonfiguration angeben, um Archivierungsoptionen für einen bestimmten Pool zu steuern.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="0f0ad-116">Eine Poolkonfiguration setzt die globale Konfiguration und die Standortkonfiguration außer Kraft, jedoch nur für die in den Archivierungspoolkonfigurationen angegebenen Pools.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="0f0ad-117">Sie können Poolkonfigurationen bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0f0ad-118">Archivierungs Konfigurationen gelten für Benutzer, die sich in Skype for Business Server befinden, und, wenn Sie Exchange zum Speichern von Archivierungsdaten in Microsoft Exchange verwenden, für Benutzer, die auf Exchange 2013, aber für Benutzer, die in Exchange 2013 verwaltet werden, etwas anders implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="0f0ad-119">Die Unterschiede werden im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="0f0ad-p105">Auf der Seite **Archivierungskonfiguration** werden die einzelnen Archivierungsrichtlinien aufgeführt, die für die Bereitstellung konfiguriert sind. Außerdem werden der Richtlinienname und -bereich (Global, Standort oder Pool) sowie die für eine Archivierungskonfiguration aktivierten Archivierungsoptionen angezeigt. Auf der Seite **Archivierungskonfiguration** haben Sie die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="0f0ad-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="0f0ad-123">**Neu** Sie können eine oder mehrere der folgenden optionalen Archivierungs Konfigurationen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="0f0ad-124">Standortkonfiguration</span><span class="sxs-lookup"><span data-stu-id="0f0ad-124">Site configuration</span></span>
    
  - <span data-ttu-id="0f0ad-125">Poolkonfiguration</span><span class="sxs-lookup"><span data-stu-id="0f0ad-125">Pool configuration</span></span>
    
- <span data-ttu-id="0f0ad-126">**Bearbeiten** von Sie können die Optionen für alle auf der Seite aufgelisteten Archivierungs Konfigurationen ändern.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="0f0ad-127">Mit dieser Option haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="0f0ad-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="0f0ad-128">**Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Archivierungsoptionen für die ausgewählte Archivierungskonfiguration ändern können.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="0f0ad-129">Sie können nur für jeweils eine Archivierungskonfiguration Details anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="0f0ad-130">**Alle auswählen** Mit dieser Option werden alle Archivierungs Konfigurationen in der Liste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="0f0ad-131">**Löschen** Mit dieser Option werden alle ausgewählten Archivierungs Konfigurationen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="0f0ad-132">**Aktion** Sie können diese Option verwenden, um die Archivierung von Chatsitzungen oder Webkonferenz Sitzungen in einer beliebigen auf der Seite aufgeführten Konfiguration schnell zu aktivieren oder zu deaktivieren, anstatt die Konfiguration zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="0f0ad-133">Die unter **Aktion** verfügbaren Optionen richten sich danach, welche Option in der Archivierungskonfiguration momentan angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="0f0ad-134">Alle Optionen sind verfügbar, mit Ausnahme der Option, die für die Archivierungskonfiguration derzeit wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="0f0ad-135">Folgende Optionen sind vorhanden:</span><span class="sxs-lookup"><span data-stu-id="0f0ad-135">Options include the following:</span></span>
    
  - <span data-ttu-id="0f0ad-136">**Chatsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="0f0ad-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="0f0ad-137">**Chat- und Webkonferenzsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="0f0ad-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="0f0ad-138">**Archivierung deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="0f0ad-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="0f0ad-139">**Aktualisieren** Sie können die Seite **Archivierungskonfiguration** aktualisieren, um den Status der Optionen aller Archivierungs Konfigurationen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="0f0ad-140">Details zum Archivierungsfeature und zu den Funktionen, einschließlich der Exchange-Integration, finden Sie unter [Planen der Archivierung in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Bereitstellen der Archivierung für Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)und [Verwalten der Archivierung in Skype für Business Server 2015](../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="0f0ad-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

