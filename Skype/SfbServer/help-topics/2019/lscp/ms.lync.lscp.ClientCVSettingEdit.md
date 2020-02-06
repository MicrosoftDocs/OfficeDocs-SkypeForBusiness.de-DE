---
title: Client-Versions Konfiguration neues erstellen oder vorhandenes bearbeiten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: Client Version-Konfigurationseinstellungen werden verwendet, um die Client Versionskontrolle zu aktivieren oder zu deaktivieren. Die Konfiguration der globalen Client Version wird mit Skype for Business Server installiert und wird verwendet, um die Client Versionskontrolle für die gesamte Server Bereitstellung zu aktivieren oder zu deaktivieren. Wenn die globale Konfiguration aktiviert ist, werden alle von Ihnen eingerichteten clientversionsrichtlinien wirksam, wenn Benutzer versuchen, sich anzumelden. Sie können die Konfiguration der globalen Client Version deaktivieren, wenn keine Client Versionskontrolle erfolgen soll.
ms.openlocfilehash: c0225947f3346e129768fc6e61dc9484e916be75
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794574"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="e4be2-106">Clientversionskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="e4be2-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="e4be2-107">Client Version-Konfigurationseinstellungen werden verwendet, um die Client Versionskontrolle zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e4be2-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="e4be2-108">Die Konfiguration der globalen Client Version wird mit Skype for Business Server installiert und wird verwendet, um die Client Versionskontrolle für die gesamte Server Bereitstellung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e4be2-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="e4be2-109">Wenn die globale Konfiguration aktiviert ist, werden alle von Ihnen eingerichteten clientversionsrichtlinien wirksam, wenn Benutzer versuchen, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="e4be2-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="e4be2-110">Sie können die Konfiguration der globalen Client Version deaktivieren, wenn keine Client Versionskontrolle erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="e4be2-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="e4be2-p103">Sie können auch standortspezifische Clientversionskonfigurationen erstellen, um die Clientversionskontrolle pro Standort aktivieren und deaktivieren zu können. Standortspezifische Konfigurationen haben Vorrang vor der globalen Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e4be2-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e4be2-113">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="e4be2-113">Tasks you can perform</span></span>

<span data-ttu-id="e4be2-114">Auf der Seite **Neue Clientversionskonfiguration erstellen** oder **Clientversionskonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="e4be2-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="e4be2-115">Hinzufügen oder Ändern des Namens der Clientversionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="e4be2-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="e4be2-116">Aktivieren und Deaktivieren der Clientversionskontrolle global oder für einen bestimmten Standort</span><span class="sxs-lookup"><span data-stu-id="e4be2-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="e4be2-117">Hinzufügen oder Ändern der Standardaktion für die Clientversionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="e4be2-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e4be2-118">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="e4be2-118">UI Reference</span></span>

<span data-ttu-id="e4be2-119">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e4be2-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="e4be2-120">**Bereich** Identifiziert den Bereich (Global oder Website) der Client Versions Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e4be2-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="e4be2-121">**Name** Sie können den Namen der Client Versions Konfiguration hinzufügen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="e4be2-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="e4be2-122">**Aktivieren der Versionskontrolle** Je nach dem Umfang der Konfiguration können Sie die Client Versionskontrolle Global oder für die Website aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e4be2-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="e4be2-123">**Standardaktion** Sie können die Standardaktion auswählen, die angewendet werden soll, wenn ein Benutzer versucht, sich mit einer Clientanwendung anzumelden, für die es keine spezifische clientversionsrichtlinie gibt.</span><span class="sxs-lookup"><span data-stu-id="e4be2-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="e4be2-124">Sie haben folgende Optionen:</span><span class="sxs-lookup"><span data-stu-id="e4be2-124">You have the following options:</span></span>

  - <span data-ttu-id="e4be2-125">**Zulassen** Ermöglicht es dem Client, sich anzumelden, wenn die Client Version keinem Filter in der Liste der clientversionsrichtlinien entspricht.</span><span class="sxs-lookup"><span data-stu-id="e4be2-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="e4be2-126">**Blockieren** Verhindert, dass der Client sich anmeldet, wenn die Client Version keinem Filter in der Liste der clientversionsrichtlinien entspricht.</span><span class="sxs-lookup"><span data-stu-id="e4be2-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="e4be2-127">**Block mit URL** Verhindert, dass der Client sich anmeldet, wenn die Client Version keinem Filter in der Liste der clientversionsrichtlinien entspricht und eine Fehlermeldung mit einer URL enthält, in der ein neuerer Client heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4be2-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="e4be2-128">**Mit URL zulassen** Ermöglicht es dem Client, sich anzumelden, wenn die Client Version keinem Filter in der Liste der clientversionsrichtlinien entspricht und eine Fehlermeldung mit einer URL enthält, in der ein neuerer Client heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4be2-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="e4be2-129">**URL** Wenn Sie **Block mit URL** oder **Allow with URL**ausgewählt haben, können Sie die Client Download-URL angeben, die in die Fehlermeldung aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e4be2-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="e4be2-130">Details zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperabilität](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e4be2-130">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="e4be2-131">Ausführliche Informationen zur Verwendung von Clientversionskonfigurationen finden Sie in der Betriebsdokumentation unter [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx).</span><span class="sxs-lookup"><span data-stu-id="e4be2-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

