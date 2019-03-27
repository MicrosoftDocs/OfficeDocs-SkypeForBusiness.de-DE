---
title: Clientversionskonfiguration Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: Konfigurationseinstellungen für Clientversionen dienen zum Aktivieren oder deaktivieren Sie die Versionskontrolle für Clients. Die globale clientversionskonfiguration mit Skype für Business Server installiert und wird zum Aktivieren oder Deaktivieren der clientversionskontrolle für die gesamte serverbereitstellung verwendet. Wenn die Konfiguration Global aktiviert ist, werden alle clientversionsrichtlinien, die Sie direkt wirksam wird, wenn Benutzer versuchen, melden Sie sich. Sie können die globale clientversionskonfiguration deaktivieren, wenn keine clientversionskontrolle erfolgen soll.
ms.openlocfilehash: 3b91ca6b9c3d3f801a8a247eef5641673dc86556
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883207"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="e5a1b-106">Clientversionskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="e5a1b-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="e5a1b-107">Konfigurationseinstellungen für Clientversionen dienen zum Aktivieren oder deaktivieren Sie die Versionskontrolle für Clients.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="e5a1b-108">Die globale clientversionskonfiguration mit Skype für Business Server installiert und wird zum Aktivieren oder Deaktivieren der clientversionskontrolle für die gesamte serverbereitstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="e5a1b-109">Wenn die Konfiguration Global aktiviert ist, werden alle clientversionsrichtlinien, die Sie direkt wirksam wird, wenn Benutzer versuchen, melden Sie sich.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="e5a1b-110">Sie können die globale clientversionskonfiguration deaktivieren, wenn keine clientversionskontrolle erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="e5a1b-p103">Sie können auch standortspezifische Clientversionskonfigurationen erstellen, um die Clientversionskontrolle pro Standort aktivieren und deaktivieren zu können. Standortspezifische Konfigurationen haben Vorrang vor der globalen Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e5a1b-113">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="e5a1b-113">Tasks you can perform</span></span>

<span data-ttu-id="e5a1b-114">Auf der Seite **Neue Clientversionskonfiguration erstellen** oder **Clientversionskonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="e5a1b-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="e5a1b-115">Hinzufügen oder Ändern des Namens der Clientversionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="e5a1b-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="e5a1b-116">Aktivieren und Deaktivieren der Clientversionskontrolle global oder für einen bestimmten Standort</span><span class="sxs-lookup"><span data-stu-id="e5a1b-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="e5a1b-117">Hinzufügen oder Ändern der Standardaktion für die Clientversionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="e5a1b-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e5a1b-118">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="e5a1b-118">UI Reference</span></span>

<span data-ttu-id="e5a1b-119">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="e5a1b-120">**Bereich** Gibt den Bereich (Global oder Standort) der clientversionskonfiguration an.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="e5a1b-121">**Name** Sie können hinzufügen oder Ändern des Namens der clientversionskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="e5a1b-122">**Versionskontrolle aktivieren** Sie können aktivieren oder Deaktivieren der clientversionskontrolle global oder für den Standort, je nach der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="e5a1b-123">**Standardaktion** Sie können die Standardaktion auswählen, die angewendet werden, wenn ein Benutzer versucht, melden Sie sich unter Verwendung einer Clientanwendung keine bestimmte clientversionsrichtlinie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="e5a1b-124">Sie haben folgende Optionen:</span><span class="sxs-lookup"><span data-stu-id="e5a1b-124">You have the following options:</span></span>

  - <span data-ttu-id="e5a1b-125">**Zulassen** Ermöglicht den Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="e5a1b-126">**Blockieren** Verhindert, dass die Clients anmelden, wenn die Clientversion keinem Filter in der Liste nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="e5a1b-127">**Mit URL blockieren** Verhindert, dass die Clients anmelden, wenn die Clientversion keinem Filter in der Liste stimmt nicht überein, und enthält eine Fehlermeldung, die mit einer URL, in dem eine neuere heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="e5a1b-128">**Mit URL zulassen** Ermöglicht den Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste stimmt nicht überein, und eine Fehlermeldung enthält, die eine URL enthält, in dem eine neuere heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="e5a1b-129">**URL** Wenn Sie **mit URL blockieren** oder **mit URL zulassen**ausgewählt haben, können Sie die URL zum Einschließen in die Fehlermeldung angeben.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="e5a1b-130">Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e5a1b-130">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="e5a1b-131">Ausführliche Informationen zur Verwendung von Clientversionskonfigurationen finden Sie in der Betriebsdokumentation unter [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx).</span><span class="sxs-lookup"><span data-stu-id="e5a1b-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

