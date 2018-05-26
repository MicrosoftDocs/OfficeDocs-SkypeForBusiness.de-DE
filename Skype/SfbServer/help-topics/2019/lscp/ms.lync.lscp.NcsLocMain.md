---
title: Standortrichtlinie
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: Anhand von Standortrichtlinien wird bestimmt, ob E9-1-1 aktiviert ist, wie es verwendet wird und wie Standortinformationen für Benutzer und Kontakte verwendet werden.
ms.openlocfilehash: 0a4d438ac208af88229f75e7fc8f9eec4d3e7697
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2018
---
# <a name="location-policy"></a><span data-ttu-id="6c62d-103">Standortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6c62d-103">Location Policy</span></span>
 
<span data-ttu-id="6c62d-104">Anhand von Standortrichtlinien wird bestimmt, ob E9-1-1 aktiviert ist, wie es verwendet wird und wie Standortinformationen für Benutzer und Kontakte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6c62d-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span> 
  
<span data-ttu-id="6c62d-105">Zu den Standortrichtlinien gehören die globale Richtlinie und optional eine oder mehrere Standort- und Benutzerrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="6c62d-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="6c62d-106">**Globale Richtlinie:** Die globale Richtlinie wird standardmäßig erstellt.</span><span class="sxs-lookup"><span data-stu-id="6c62d-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="6c62d-107">Sie können die globale Richtlinie bearbeiten, jedoch nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="6c62d-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="6c62d-108">Wenn Sie versuchen, die globale Richtlinie zu entfernen, werden alle Einstellungen auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="6c62d-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>
    
- <span data-ttu-id="6c62d-109">**Websiterichtlinien (optional):** Sie können eine oder mehrere Website Speicherort Richtlinien erstellen, von die jeder auf eine bestimmte Website angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c62d-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="6c62d-110">Standortrichtlinien setzen die globale Richtlinie außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="6c62d-110">Site policies override the global policy.</span></span>
    
- <span data-ttu-id="6c62d-111">**Richtlinien für Benutzer (optional):** Sie können eine oder mehrere Benutzer Standortrichtlinien erstellen, von die jedes auf einen bestimmten Benutzer oder eine Gruppe von Benutzern angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c62d-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="6c62d-112">Benutzerrichtlinien setzen die globale Richtlinie und Standortrichtlinien außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="6c62d-112">User policies override the global policy and site policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6c62d-113">Außerdem können Sie Standortrichtlinien Netzwerkstandorten hinzufügen, wobei es sich um Gruppen von Subnetzen handelt.</span><span class="sxs-lookup"><span data-stu-id="6c62d-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="6c62d-114">Netzwerkstandorten zugewiesene Standortrichtlinien haben Vorrang vor allen anderen Benutzerrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="6c62d-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="6c62d-115">Weitere Informationen zum Zuweisen von Standortrichtlinien zu Netzwerkstandorten mithilfe von Cmdlets finden Sie unter [Hinzufügen einer ortungsrichtlinie zu einem Netzwerkstandort in Skype für Business Server 2015](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="6c62d-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="6c62d-116">Weitere Informationen zur Verwendung von Skype Business Server-Systemsteuerung einem Netzwerkstandort eine Standortrichtlinie zugewiesen finden Sie unter [Konfigurieren von Netzwerkstandorten](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span><span class="sxs-lookup"><span data-stu-id="6c62d-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span> 
  
<span data-ttu-id="6c62d-117">Auf der Seite **Standortrichtlinie** wird eine Liste mit allen Standortrichtlinien angezeigt, die für Ihre Organisation definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6c62d-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="6c62d-118">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="6c62d-118">Tasks you can perform</span></span>

<span data-ttu-id="6c62d-119">Auf der Seite **Standortrichtlinie** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="6c62d-119">You can perform the following tasks from the **Location Policy** page:</span></span>
  
- <span data-ttu-id="6c62d-120">Erstellen einer neuen Standortrichtlinie für Standorte oder Benutzer</span><span class="sxs-lookup"><span data-stu-id="6c62d-120">Create a new site location policy or user location policy</span></span>
    
- <span data-ttu-id="6c62d-121">Ändern der globalen Richtlinie oder einer vorhandenen Standort- oder Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6c62d-121">Change the global policy or an existing site policy or user policy</span></span>
    
- <span data-ttu-id="6c62d-122">Löschen einer Standort- oder Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6c62d-122">Delete a site policy or user policy</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="6c62d-123">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="6c62d-123">UI Reference</span></span>

<span data-ttu-id="6c62d-124">In der folgenden Liste sind die Befehle der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c62d-124">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="6c62d-125">**Neue** Ermöglicht die Erstellung einer neuen Standortrichtlinie oder Standortrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="6c62d-125">**New** Starts a new site location policy or user location policy.</span></span>
    
- <span data-ttu-id="6c62d-126">**Bearbeiten** Öffnet die ausgewählte Standortrichtlinie zur Bearbeitung, wählt alle Standortrichtlinien in der Liste aus oder löscht die ausgewählte Standort- oder Benutzerrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="6c62d-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6c62d-127">Für die globale Richtlinie werden die Einstellungen mit **Löschen** auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="6c62d-127">For the global policy, **Delete** resets the settings to the default values.</span></span>
  
- <span data-ttu-id="6c62d-128">**Aktualisieren** Aktualisiert die Liste mit den Standortrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="6c62d-128">**Refresh** Refreshes the list of location policies.</span></span>
    
<span data-ttu-id="6c62d-129">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c62d-129">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="6c62d-130">**Name** Identifiziert die Standortrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="6c62d-130">**Name** Identifies the location policy.</span></span>
    
- <span data-ttu-id="6c62d-131">**Bereich** Gibt den Bereich der Standortrichtlinie: global, Standort oder Benutzer.</span><span class="sxs-lookup"><span data-stu-id="6c62d-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>
    
- <span data-ttu-id="6c62d-132">**E9-1-1** Überprüft, wenn der Benutzer, denen diese Standortrichtlinie zugewiesen für E9-1-1 aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="6c62d-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>
    
- <span data-ttu-id="6c62d-133">**Speicherort** Gibt an, ob Benutzer Standortinformationen eingeben, wenn deren Clients bei Skype für Business Server an einem neuen Standort registriert wird, und ob sie einen Haftungsausschluss angezeigt, wenn sie die Meldung schließen, ohne Eingabe von Standortinformationen aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="6c62d-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>
    
- <span data-ttu-id="6c62d-134">**PSTN-Verwendung** Gibt das Telefonfestnetz (PSTN) Netzwerkauslastung, das verwendet wird, zum Bestimmen der VoIP-Route zur Weiterleitung von Notrufen von Clients, die mit diesem Profil verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c62d-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>
    
- <span data-ttu-id="6c62d-135">**Anzahl der E9-1-1** Gibt die Nummer, die zum Erreichen der notrufdienste gewählt wird.</span><span class="sxs-lookup"><span data-stu-id="6c62d-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>
    
- <span data-ttu-id="6c62d-136">**Maske E9-1-1** Gibt eine Zahl, die ein Benutzer wählt, die dann in die Notrufnummer Nummer übersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="6c62d-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>
    
<span data-ttu-id="6c62d-137">Weitere Informationen zu Enterprise-VoIP notrufunterstützung Features und Funktionen finden Sie unter [Übersicht über E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6c62d-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="6c62d-138">Ausführliche Informationen zum Arbeiten mit ortungsrichtlinien finden Sie unter [Standortrichtlinie konfigurieren](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6c62d-138">For details about working with location policies, see [Configuring Location Policy](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>
  

