---
title: Clientversionsrichtlinie Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: Sie können die Version von Clients angeben, die in Ihrer Umgebung unterstützt werden. Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden.
ms.openlocfilehash: 5648d96e69869171d78a3a28634bdb2b0221a234
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216403"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="8b4ab-104">Clientversionsrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="8b4ab-104">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="8b4ab-105">Sie können die Version von Clients angeben, die in Ihrer Umgebung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="8b4ab-106">Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="8b4ab-107">Die größte Nutzung der Features in Skype für Business Server und zur Verbesserung der benutzerfreundlichkeit können den clientversionsfilter Sie um die Clientversionen, die verwendet werden in Ihrer Umgebung zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="8b4ab-108">Mit dem Clientversionsfilter können Sie außerdem die Kosten senken, die aufgrund der Unterstützung mehrerer Clientversionen anfallen.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b4ab-p103">Filter werden anhand ihrer Rangfolge aufgelistet. Beispiel: Sie verfügen über einen Filter, der die Ausführung von Clientversion 1.5 zulässt, gefolgt von einem Filter, der Clients mit früheren Versionen als Version 2.0 blockiert. In diesem Fall hat der erste Filter Vorrang und Clients mit Version 1.5 können eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="8b4ab-111">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="8b4ab-111">Tasks you can perform</span></span>

<span data-ttu-id="8b4ab-112">Auf der Seite **Neue Clientversionsrichtlinie** bzw. **Clientversionsrichtlinie bearbeiten** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="8b4ab-112">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="8b4ab-113">Hinzufügen oder Ändern des Namens oder der Beschreibung der Clientversionsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="8b4ab-113">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="8b4ab-114">Hinzufügen oder Ändern der Clientversionsregeln für die Clientversionsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="8b4ab-114">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="8b4ab-115">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="8b4ab-115">UI Reference</span></span>

<span data-ttu-id="8b4ab-116">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="8b4ab-117">**Bereich** Gibt den Bereich (Standort, Pool oder Benutzer) der clientversionsrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-117">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="8b4ab-118">**Name** Sie können hinzufügen oder Ändern des Namens der clientversionsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-118">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="8b4ab-119">**Beschreibung** Sie können eine Beschreibung, die Hilfe bei der Identifizierung der Richtlinie in der Liste auf der Seite Clientversionsrichtlinie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-119">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="8b4ab-120">**Neue** Sie können die Richtlinie eine neue clientversionsregel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-120">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="8b4ab-121">**Details anzeigen** Diese Option öffnet ein Dialogfeld, in dem Sie die Optionen für eine clientversionsregel ändern können.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-121">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="8b4ab-122">**Entfernen** Diese Option wird die ausgewählte clientversionsregel aus der Richtlinie entfernt.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-122">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="8b4ab-123">**Weisenden Pfeile** Diese Option wird die ausgewählte clientversionsregel nach oben oder unten im Feld Priorität verschoben.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-123">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="8b4ab-124">Die Regeln werden in der angezeigten Reihenfolge verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8b4ab-124">Rules are processed in the order listed.</span></span>

<span data-ttu-id="8b4ab-125">Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client-Interoperabilität](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx).</span><span class="sxs-lookup"><span data-stu-id="8b4ab-125">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx).</span></span> <span data-ttu-id="8b4ab-126">Ausführliche Informationen zur Verwendung von Clientversionsrichtlinien finden Sie in der Betriebsdokumentation unter [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx).</span><span class="sxs-lookup"><span data-stu-id="8b4ab-126">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

