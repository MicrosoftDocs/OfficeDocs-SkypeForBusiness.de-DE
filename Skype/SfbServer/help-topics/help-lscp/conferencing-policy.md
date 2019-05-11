---
title: Konferenzrichtlinie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: Eine konferenzrichtlinie definiert die Features und Funktionen, die Benutzern während einer Konferenz (auch als Besprechung bezeichnet) zur Verfügung stehen.
ms.openlocfilehash: 62aa6dbe2c237cd27a1dc8798da70a68685640ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929090"
---
# <a name="conferencing-policy"></a><span data-ttu-id="65026-103">Konferenzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="65026-103">Conferencing Policy</span></span>

<span data-ttu-id="65026-104">Eine konferenzrichtlinie definiert die Features und Funktionen, die Benutzern während einer Konferenz (auch als Besprechung bezeichnet) zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="65026-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>

<span data-ttu-id="65026-105">Konferenzrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Standort- und Benutzerrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="65026-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="65026-106">**Globale Richtlinie:** Die globale Richtlinie wird standardmäßig erstellt.</span><span class="sxs-lookup"><span data-stu-id="65026-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="65026-107">Sie können die globale Richtlinie bearbeiten, jedoch nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="65026-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="65026-108">Wenn Sie versuchen, die globale Richtlinie zu entfernen, werden alle Einstellungen auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="65026-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="65026-109">**Websiterichtlinien (optional):** Sie können eine oder mehrere Website konferenzrichtlinien erstellen, von die jeder auf eine bestimmte Website angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="65026-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="65026-110">Standortrichtlinien setzen die globale Richtlinie außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="65026-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="65026-111">**Richtlinien für Benutzer (optional):** Sie können eine oder mehrere Benutzer konferenzrichtlinien erstellen, von die jedes auf einen bestimmten Benutzer oder eine Gruppe von Benutzern angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="65026-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="65026-112">Benutzerrichtlinien setzen die globale Richtlinie und Standortrichtlinien außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="65026-112">User policies override the global policy and site policies.</span></span>

<span data-ttu-id="65026-113">Die Seite **Konferenzrichtlinie** zeigt eine Liste aller konferenzrichtlinien, die für Ihre Organisation definiert sind.</span><span class="sxs-lookup"><span data-stu-id="65026-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="65026-114">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="65026-114">Tasks you can perform</span></span>

<span data-ttu-id="65026-115">Auf der Seite **Standortrichtlinie** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="65026-115">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="65026-116">Erstellen einer neuen konferenzrichtlinie für Standorte oder Benutzer</span><span class="sxs-lookup"><span data-stu-id="65026-116">Create a new site conferencing policy or user conferencing policy</span></span>

- <span data-ttu-id="65026-117">Ändern der globalen Richtlinie oder einer vorhandenen Standort- oder Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="65026-117">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="65026-118">Löschen einer Standort- oder Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="65026-118">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="65026-119">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="65026-119">UI Reference</span></span>

<span data-ttu-id="65026-120">In der folgenden Liste werden die Befehle der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65026-120">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="65026-121">**Neue** Startet einen neuen konferenzrichtlinie für Standorte oder Benutzer.</span><span class="sxs-lookup"><span data-stu-id="65026-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>

- <span data-ttu-id="65026-122">**Bearbeiten** Öffnet die ausgewählte konferenzrichtlinie zur Bearbeitung, wählt alle konferenzrichtlinien in der Liste aus oder löscht die ausgewählte Standort- oder Benutzerrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="65026-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="65026-123">Für die globale Richtlinie werden die Einstellungen mit **Löschen** auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="65026-123">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="65026-124">**Aktualisieren** Aktualisiert die Liste der konferenzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="65026-124">**Refresh** Refreshes the list of conferencing policies.</span></span>

<span data-ttu-id="65026-125">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65026-125">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="65026-126">**Name** Identifiziert die konferenzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="65026-126">**Name** Identifies the conferencing policy.</span></span>

- <span data-ttu-id="65026-127">**Bereich** Gibt den Bereich der konferenzrichtlinie: global, Standort oder Benutzer.</span><span class="sxs-lookup"><span data-stu-id="65026-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>

- <span data-ttu-id="65026-128">**Zusammenarbeit an Daten** Aktiviert, wenn der konferenzrichtlinie angegeben, dass die Datenzusammenarbeit in Konferenzen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="65026-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>

- <span data-ttu-id="65026-129">**Anwendungsfreigabe** Aktiviert, wenn der konferenzrichtlinie angegeben, dass die Anwendungsfreigabe in Konferenzen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="65026-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>

- <span data-ttu-id="65026-130">**Audio** Aktiviert, wenn der konferenzrichtlinie angegeben, dass sich, dass die audiodatenfunktion in Konferenzen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="65026-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>

- <span data-ttu-id="65026-131">**Video** Aktiviert, wenn der konferenzrichtlinie angegeben, dass das Video in Konferenzen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="65026-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>

- <span data-ttu-id="65026-132">**PSTN** Aktiviert, wenn der konferenzrichtlinie angegeben, dass PSTN-einwahlkonferenzen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="65026-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>

- <span data-ttu-id="65026-133">**Aufzeichnen** Aktiviert, wenn der konferenzrichtlinie angegeben, dass die Aufzeichnung in Konferenzen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="65026-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>

<span data-ttu-id="65026-p104">Ausführliche Informationen zu den Konferenzfunktionen finden Sie in der Planungsdokumentation unter [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx). Ausführliche Informationen zur Verwendung von Konferenzrichtlinien finden Sie in der Betriebsdokumentation unter [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx).</span><span class="sxs-lookup"><span data-stu-id="65026-p104">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation. For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


