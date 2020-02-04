---
title: Standortrichtlinie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: Anhand von Standortrichtlinien wird bestimmt, ob E9-1-1 aktiviert ist, wie es verwendet wird und wie Standortinformationen für Benutzer und Kontakte verwendet werden.
ms.openlocfilehash: 82126acf09ed4e0cd1b98b20f22760f23038226c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41704610"
---
# <a name="location-policy"></a><span data-ttu-id="2006c-103">Standortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="2006c-103">Location Policy</span></span>

<span data-ttu-id="2006c-104">Anhand von Standortrichtlinien wird bestimmt, ob E9-1-1 aktiviert ist, wie es verwendet wird und wie Standortinformationen für Benutzer und Kontakte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2006c-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="2006c-105">Zu den Standortrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Standort- und Benutzerrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="2006c-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="2006c-106">**Globale Richtlinie:** Standardmäßig wird die globale Richtlinie erstellt.</span><span class="sxs-lookup"><span data-stu-id="2006c-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="2006c-107">Sie können die globale Richtlinie bearbeiten, jedoch nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="2006c-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="2006c-108">Wenn Sie versuchen, die globale Richtlinie zu entfernen, werden alle Einstellungen auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2006c-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="2006c-109">**Website Richtlinien (optional):** Sie können eine oder mehrere Website Standortrichtlinien erstellen, die jeweils für eine bestimmte Website gelten.</span><span class="sxs-lookup"><span data-stu-id="2006c-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="2006c-110">Standortrichtlinien setzen die globale Richtlinie außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="2006c-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="2006c-111">**Benutzerrichtlinien (optional):** Sie können eine oder mehrere Benutzerstandort Richtlinien erstellen, die jeweils für einen bestimmten Benutzer oder eine Gruppe von Benutzern gelten.</span><span class="sxs-lookup"><span data-stu-id="2006c-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="2006c-112">Benutzerrichtlinien setzen die globale Richtlinie und Standortrichtlinien außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="2006c-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="2006c-113">Außerdem können Sie Standortrichtlinien Netzwerkstandorten hinzufügen, wobei es sich um Gruppen von Subnetzen handelt.</span><span class="sxs-lookup"><span data-stu-id="2006c-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="2006c-114">Netzwerkstandorten zugewiesene Standortrichtlinien haben Vorrang vor allen anderen Benutzerrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="2006c-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="2006c-115">Details zum Zuweisen von Standortrichtlinien zu Netzwerk Websites mithilfe von Cmdlets finden Sie unter [Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="2006c-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="2006c-116">Details zur Verwendung der Skype for Business Server-Systemsteuerung zum Zuweisen einer Standortrichtlinie zu einer Netzwerk Website finden Sie unter [Konfigurieren von Netzwerkstandorten](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span><span class="sxs-lookup"><span data-stu-id="2006c-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="2006c-117">Auf der Seite **Standortrichtlinie** wird eine Liste mit allen Standortrichtlinien angezeigt, die für Ihre Organisation definiert sind.</span><span class="sxs-lookup"><span data-stu-id="2006c-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2006c-118">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2006c-118">Tasks you can perform</span></span>

<span data-ttu-id="2006c-119">Auf der Seite **Standortrichtlinie** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="2006c-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="2006c-120">Erstellen einer neuen Standortrichtlinie für Standorte oder Benutzer</span><span class="sxs-lookup"><span data-stu-id="2006c-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="2006c-121">Ändern der globalen Richtlinie oder einer vorhandenen Standort- oder Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="2006c-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="2006c-122">Löschen einer Standort- oder Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="2006c-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2006c-123">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="2006c-123">UI Reference</span></span>

<span data-ttu-id="2006c-124">In der folgenden Liste werden die Befehle der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2006c-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="2006c-125">**Neu** Startet eine neue Website Standortrichtlinien-oder Benutzerstandort Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="2006c-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="2006c-126">**Bearbeiten** von Öffnet die ausgewählte Standortrichtlinie, um Sie zu bearbeiten, wählt alle Standortrichtlinien in der Liste aus oder löscht die ausgewählte Website Richtlinie oder Benutzerrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="2006c-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2006c-127">Für die globale Richtlinie werden die Einstellungen mit **Löschen** auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2006c-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="2006c-128">**Aktualisieren** Aktualisiert die Liste der Standortrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="2006c-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="2006c-129">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2006c-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2006c-130">**Name** Identifiziert die Standortrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="2006c-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="2006c-131">**Bereich** Identifiziert den Bereich der Standortrichtlinie: Global, Site oder User.</span><span class="sxs-lookup"><span data-stu-id="2006c-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="2006c-132">**E9-1-1** Überprüft, ob Benutzer, denen diese Standortrichtlinie zugewiesen ist, für E9-1-1 aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="2006c-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="2006c-133">**Ort** Gibt an, ob Benutzer zur Eingabe von Standortinformationen aufgefordert werden, wenn sich der Client mit Skype for Business Server an einem neuen Speicherort registriert und ob er eine Verzichtserklärung erhält, wenn er die Eingabeaufforderung ohne Angabe von Standortinformationen versieht.</span><span class="sxs-lookup"><span data-stu-id="2006c-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="2006c-134">**PSTN-Verwendung** Gibt die PSTN-Nutzung (Public Switched Telephone Network) an, die verwendet wird, um die VoIP-Route zu ermitteln, die für die Weiterleitung von Notrufen von Clients mit diesem Profil verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2006c-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="2006c-135">**E9-1-1 Nummer** Gibt die Nummer an, die zum Erreichen von Notfalldiensten gewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="2006c-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="2006c-136">**E9-1-1-Maske** Gibt eine Zahl an, die ein Benutzer anwählt, die dann in die Notrufnummer übersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="2006c-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="2006c-137">Ausführliche Informationen zu den Features und Funktionen des Enterprise-VoIP-Notfall Diensts finden Sie unter [Übersicht über E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2006c-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="2006c-138">Ausführliche Informationen zur Verwendung von Standortrichtlinien finden Sie in der Betriebsdokumentation unter [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx).</span><span class="sxs-lookup"><span data-stu-id="2006c-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


