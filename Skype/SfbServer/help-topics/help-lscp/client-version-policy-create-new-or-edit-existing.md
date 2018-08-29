---
title: Clientversionsrichtlinie Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: Sie können die Versionen von Clients angeben, die in Ihrer Umgebung unterstützt werden sollen. Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden. Die größte Nutzung der Features in Skype für Business Server 2015 und zur Verbesserung der benutzerfreundlichkeit können den clientversionsfilter Sie um die Clientversionen, die verwendet werden in Ihrer Umgebung zu beschränken. Mit dem Clientversionsfilter können Sie außerdem die Kosten senken, die aufgrund der Unterstützung mehrerer Clientversionen anfallen.
ms.openlocfilehash: 9b69b3dd52665c01e42d12f7aed2790064cb6688
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261147"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="bc69f-106">Clientversionsrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="bc69f-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="bc69f-107">Sie können die Versionen von Clients angeben, die in Ihrer Umgebung unterstützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bc69f-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="bc69f-108">Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="bc69f-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="bc69f-109">Die größte Nutzung der Features in Skype für Business Server 2015 und zur Verbesserung der benutzerfreundlichkeit können den clientversionsfilter Sie um die Clientversionen, die verwendet werden in Ihrer Umgebung zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="bc69f-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="bc69f-110">Mit dem Clientversionsfilter können Sie außerdem die Kosten senken, die aufgrund der Unterstützung mehrerer Clientversionen anfallen.</span><span class="sxs-lookup"><span data-stu-id="bc69f-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc69f-p103">Filter werden anhand ihrer Rangfolge aufgelistet. Beispiel: Sie verfügen über einen Filter, der die Ausführung von Clientversion 1.5 zulässt, gefolgt von einem Filter, der Clients mit früheren Versionen als Version 2.0 blockiert. In diesem Fall hat der erste Filter Vorrang und Clients mit Version 1.5 können eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="bc69f-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="bc69f-113">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="bc69f-113">Tasks you can perform</span></span>

<span data-ttu-id="bc69f-114">Auf der Seite **Neue Clientversionsrichtlinie** bzw. **Clientversionsrichtlinie bearbeiten** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="bc69f-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="bc69f-115">Hinzufügen oder Ändern des Namens oder der Beschreibung der Clientversionsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="bc69f-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="bc69f-116">Hinzufügen oder Ändern der Clientversionsregeln für die Clientversionsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="bc69f-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="bc69f-117">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="bc69f-117">UI Reference</span></span>

<span data-ttu-id="bc69f-118">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc69f-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="bc69f-119">**Bereich** Gibt den Bereich (Standort, Pool oder Benutzer) der clientversionsrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="bc69f-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="bc69f-120">**Name** Sie können hinzufügen oder Ändern des Namens der clientversionsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="bc69f-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="bc69f-121">**Beschreibung** Sie können eine Beschreibung, die Hilfe bei der Identifizierung der Richtlinie in der Liste auf der Seite Clientversionsrichtlinie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bc69f-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="bc69f-122">**Neue** Sie können die Richtlinie eine neue clientversionsregel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bc69f-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="bc69f-123">**Details anzeigen** Diese Option öffnet ein Dialogfeld, in dem Sie die Optionen für eine clientversionsregel ändern können.</span><span class="sxs-lookup"><span data-stu-id="bc69f-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="bc69f-124">**Entfernen** Diese Option wird die ausgewählte clientversionsregel aus der Richtlinie entfernt.</span><span class="sxs-lookup"><span data-stu-id="bc69f-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="bc69f-125">**Weisenden Pfeile** Diese Option wird die ausgewählte clientversionsregel nach oben oder unten im Feld Priorität verschoben.</span><span class="sxs-lookup"><span data-stu-id="bc69f-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="bc69f-126">Die Regeln werden in der angezeigten Reihenfolge verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="bc69f-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="bc69f-127">Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="bc69f-127">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="bc69f-128">Ausführliche Informationen zur Verwendung von clientversionsrichtlinien finden Sie unter [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="bc69f-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

