---
title: Besprechungskonfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: Die Konfigurationseinstellungen für Besprechungen definieren den Typ von Konferenzen (auch calledmeetings), die Benutzer erstellen können, und Steuern, wie (oder ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Konferenzen teilnehmen können. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option Sofortbesprechung erstellt werden.
ms.openlocfilehash: e237e9c5122547338f9ea33848a22b87fabce368
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822678"
---
# <a name="meeting-configuration"></a><span data-ttu-id="bec60-105">Besprechungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="bec60-105">Meeting Configuration</span></span>

<span data-ttu-id="bec60-p102">Konfigurationseinstellungen für Besprechungen legen fest, welche Arten von Konferenzen (auch „Besprechungen“ genannt) Benutzer erstellen können. Zusätzlich steuern sie, wie (bzw. ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können. Diese Einstellungen gelten nur für geplante Besprechungen und nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option „Sofortbesprechung“ erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bec60-p102">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="bec60-109">Konfigurationen für Besprechungen gelten auf globaler Ebene, Standortebene oder Poolebene:</span><span class="sxs-lookup"><span data-stu-id="bec60-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="bec60-110">**Globale besprechungskonfiguration:** Die globale besprechungskonfiguration wird standardmäßig erstellt.</span><span class="sxs-lookup"><span data-stu-id="bec60-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="bec60-111">Sie können die globale Besprechungskonfiguration bearbeiten, jedoch nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="bec60-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="bec60-112">Wenn Sie versuchen, die globale Besprechungskonfiguration zu entfernen, werden alle Einstellungen auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="bec60-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="bec60-113">**Konfiguration der Website Besprechung (optional):** Sie können eine oder mehrere Website Besprechungs Konfigurationen erstellen, die jeweils für eine bestimmte Website gelten.</span><span class="sxs-lookup"><span data-stu-id="bec60-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="bec60-114">Standortkonfigurationen setzen die globale Konfiguration außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="bec60-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="bec60-115">**Pool-besprechungskonfiguration (optional):** Sie können eine oder mehrere Pool-Besprechungs Konfigurationen erstellen, die jeweils für einen bestimmten Pool gelten.</span><span class="sxs-lookup"><span data-stu-id="bec60-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="bec60-116">Poolkonfigurationen setzen die globale Konfiguration und die Standortkonfigurationen außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="bec60-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="bec60-117">Auf der Seite **Besprechungskonfiguration** wird eine Liste mit allen Besprechungskonfigurationen angezeigt, die für Ihre Organisation definiert sind.</span><span class="sxs-lookup"><span data-stu-id="bec60-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="bec60-118">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="bec60-118">Tasks you can perform</span></span>

<span data-ttu-id="bec60-119">Auf der Seite **Besprechungskonfiguration** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="bec60-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="bec60-120">Erstellen einer neuen Besprechungskonfiguration auf Standort- oder Poolebene</span><span class="sxs-lookup"><span data-stu-id="bec60-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="bec60-121">Ändern der globalen Konfiguration oder einer vorhandenen Standort- oder Poolkonfiguration</span><span class="sxs-lookup"><span data-stu-id="bec60-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="bec60-122">Löschen einer Standort- oder Poolkonfiguration</span><span class="sxs-lookup"><span data-stu-id="bec60-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="bec60-123">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="bec60-123">UI Reference</span></span>

<span data-ttu-id="bec60-124">In der folgenden Liste werden die Befehle der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bec60-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="bec60-125">**Neu** Startet eine neue Konfiguration für eine Website Besprechung oder eine Pool-besprechungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="bec60-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="bec60-126">**Bearbeiten** von Öffnet die ausgewählte besprechungskonfiguration, um Sie zu bearbeiten, wählt alle Besprechungs Konfigurationen in der Liste aus oder löscht die ausgewählte Websitekonfiguration oder Poolkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="bec60-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bec60-127">Für die globale Besprechungskonfiguration werden die Einstellungen mit **Löschen** auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="bec60-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="bec60-128">**Aktualisieren** Aktualisiert die Liste der Besprechungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="bec60-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="bec60-129">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bec60-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="bec60-130">**Name** Identifiziert die besprechungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="bec60-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="bec60-131">**Bereich** Identifiziert den Bereich der besprechungskonfiguration: Global, Site oder Pool.</span><span class="sxs-lookup"><span data-stu-id="bec60-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="bec60-132">Ausführliche Informationen zur Verwendung von Besprechungskonfigurationen finden Sie in der Betriebsdokumentation unter [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx).</span><span class="sxs-lookup"><span data-stu-id="bec60-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span>


