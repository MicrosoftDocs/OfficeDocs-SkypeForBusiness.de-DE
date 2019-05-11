---
title: Besprechungskonfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: Besprechungskonfigurationseinstellungen definieren Sie den Typ der Konferenzen (auch Calledmeetings), dass Benutzer erstellen können, und steuern, wie (oder ob) anonyme Benutzer und einwahlkonferenzbenutzer diesen Konferenzen teilnehmen können. Diese Einstellungen gelten nur für geplante Besprechungen. Sie gelten nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option Sofortbesprechung erstellt werden.
ms.openlocfilehash: 5381394d106c19091e6f8c29582358b60aa36912
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911016"
---
# <a name="meeting-configuration"></a><span data-ttu-id="1be6c-105">Besprechungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="1be6c-105">Meeting Configuration</span></span>

<span data-ttu-id="1be6c-p102">Konfigurationseinstellungen für Besprechungen legen fest, welche Arten von Konferenzen (auch „Besprechungen“ genannt) Benutzer erstellen können. Zusätzlich steuern sie, wie (bzw. ob) anonyme Benutzer und Benutzer von Einwahlkonferenzen an diesen Besprechungen teilnehmen können. Diese Einstellungen gelten nur für geplante Besprechungen und nicht für Ad-hoc-Besprechungen, die durch Klicken auf die Option „Sofortbesprechung“ erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1be6c-p102">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="1be6c-109">Konfigurationen für Besprechungen gelten auf globaler Ebene, Standortebene oder Poolebene:</span><span class="sxs-lookup"><span data-stu-id="1be6c-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="1be6c-110">**Globale besprechungskonfiguration:** Die globale besprechungskonfiguration wird standardmäßig erstellt.</span><span class="sxs-lookup"><span data-stu-id="1be6c-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="1be6c-111">Sie können die globale Besprechungskonfiguration bearbeiten, jedoch nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="1be6c-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="1be6c-112">Wenn Sie versuchen, die globale Besprechungskonfiguration zu entfernen, werden alle Einstellungen auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="1be6c-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="1be6c-113">**Website besprechungskonfiguration (optional):** Erstellen Sie einen oder mehrere Website besprechungskonfigurationen, von denen jedes an einen bestimmten Standort gilt.</span><span class="sxs-lookup"><span data-stu-id="1be6c-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="1be6c-114">Standortkonfigurationen setzen die globale Konfiguration außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="1be6c-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="1be6c-115">**Pool besprechungskonfiguration (optional):** Erstellen Sie einen oder mehrere Pools besprechungskonfigurationen, von denen jedes einem bestimmten Pool betrifft.</span><span class="sxs-lookup"><span data-stu-id="1be6c-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="1be6c-116">Poolkonfigurationen setzen die globale Konfiguration und die Standortkonfigurationen außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="1be6c-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="1be6c-117">Auf der Seite **Besprechungskonfiguration** wird eine Liste mit allen Besprechungskonfigurationen angezeigt, die für Ihre Organisation definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1be6c-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="1be6c-118">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1be6c-118">Tasks you can perform</span></span>

<span data-ttu-id="1be6c-119">Auf der Seite **Besprechungskonfiguration** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="1be6c-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="1be6c-120">Erstellen einer neuen Besprechungskonfiguration auf Standort- oder Poolebene</span><span class="sxs-lookup"><span data-stu-id="1be6c-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="1be6c-121">Ändern der globalen Konfiguration oder einer vorhandenen Standort- oder Poolkonfiguration</span><span class="sxs-lookup"><span data-stu-id="1be6c-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="1be6c-122">Löschen einer Standort- oder Poolkonfiguration</span><span class="sxs-lookup"><span data-stu-id="1be6c-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1be6c-123">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="1be6c-123">UI Reference</span></span>

<span data-ttu-id="1be6c-124">In der folgenden Liste werden die Befehle der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1be6c-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="1be6c-125">**Neue** Startet einen neuen besprechungskonfiguration auf Standort- oder Poolebene.</span><span class="sxs-lookup"><span data-stu-id="1be6c-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="1be6c-126">**Bearbeiten** Öffnet die ausgewählte besprechungskonfiguration zur Bearbeitung, wählt alle besprechungskonfigurationen in der Liste aus oder löscht die ausgewählte Standort- oder Poolkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="1be6c-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1be6c-127">Für die globale Besprechungskonfiguration werden die Einstellungen mit **Löschen** auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="1be6c-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="1be6c-128">**Aktualisieren** Aktualisiert die Liste mit den besprechungskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="1be6c-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="1be6c-129">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1be6c-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="1be6c-130">**Name** Die besprechungskonfiguration identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1be6c-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="1be6c-131">**Bereich** Gibt den Bereich der besprechungskonfiguration: global, Standort oder Pool.</span><span class="sxs-lookup"><span data-stu-id="1be6c-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="1be6c-132">Ausführliche Informationen zur Verwendung von Besprechungskonfigurationen finden Sie in der Betriebsdokumentation unter [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx).</span><span class="sxs-lookup"><span data-stu-id="1be6c-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span>


