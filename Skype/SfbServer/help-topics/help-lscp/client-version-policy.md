---
title: Clientversionsrichtlinie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: Sie können die Version von Clients angeben, die in Ihrer Umgebung unterstützt werden. Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden. Um die in Skype for Business Server 2015 enthaltenen Funktionen optimal zu nutzen und die allgemeine Benutzerfreundlichkeit zu verbessern, können Sie den Clientversionsfilter verwenden, um die Clientversionen zu beschränken, die in Ihrer Umgebung verwendet werden. Mit dem Clientversionsfilter können Sie außerdem die Kosten senken, die aufgrund der Unterstützung mehrerer Clientversionen anfallen.
ms.openlocfilehash: 50687531fe9622240b8caeb75a61c3ac705fe84a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300007"
---
# <a name="client-version-policy"></a><span data-ttu-id="2ab2f-106">Clientversionsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="2ab2f-106">Client Version Policy</span></span>

<span data-ttu-id="2ab2f-107">Sie können die Version von Clients angeben, die in Ihrer Umgebung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="2ab2f-108">Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="2ab2f-109">Um die in Skype for Business Server 2015 enthaltenen Funktionen optimal zu nutzen und die allgemeine Benutzerfreundlichkeit zu verbessern, können Sie den Clientversionsfilter verwenden, um die Clientversionen zu beschränken, die in Ihrer Umgebung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="2ab2f-110">Mit dem Clientversionsfilter können Sie außerdem die Kosten senken, die aufgrund der Unterstützung mehrerer Clientversionen anfallen.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2ab2f-111">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2ab2f-111">Tasks you can perform</span></span>

<span data-ttu-id="2ab2f-112">Auf der Seite **Clientversionsrichtlinie** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ab2f-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="2ab2f-113">Bearbeiten Sie die standardmäßige clientversionsrichtlinie ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="2ab2f-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="2ab2f-114">Erstellen von Clientversionsrichtlinien für einen bestimmten Standort oder Pool</span><span class="sxs-lookup"><span data-stu-id="2ab2f-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="2ab2f-115">Erstellen von Clientversionsrichtlinien, die einzelnen Benutzern zugewiesen werden können</span><span class="sxs-lookup"><span data-stu-id="2ab2f-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="2ab2f-116">Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2ab2f-117">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="2ab2f-117">UI Reference</span></span>

<span data-ttu-id="2ab2f-118">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="2ab2f-119">**Neu** Sie können eine oder mehrere der folgenden clientversionsrichtlinien erstellen:</span><span class="sxs-lookup"><span data-stu-id="2ab2f-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="2ab2f-120">Standortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="2ab2f-120">Site policy</span></span>

  - <span data-ttu-id="2ab2f-121">Poolrichtlinie</span><span class="sxs-lookup"><span data-stu-id="2ab2f-121">Pool policy</span></span>

  - <span data-ttu-id="2ab2f-122">Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="2ab2f-122">User policy</span></span>

- <span data-ttu-id="2ab2f-123">**Bearbeiten** von Sie können die Optionen für eine der clientversionsrichtlinien ändern.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="2ab2f-124">Mit dieser Option haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="2ab2f-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="2ab2f-125">**Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Optionen für eine clientversionsrichtlinie ändern können.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="2ab2f-126">**Alle auswählen** Mit dieser Option werden alle clientversionsrichtlinien in der Liste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="2ab2f-127">**Löschen** Mit dieser Option werden alle ausgewählten clientversionsrichtlinien gelöscht.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="2ab2f-128">**Aktualisieren** Sie können die Liste der clientversionsrichtlinien aktualisieren, um den Status der Optionen aller clientversionsrichtlinien zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="2ab2f-p104">Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie in der Planungsdokumentation unter [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx). Ausführliche Informationen zur Verwendung von Clientversionsrichtlinien finden Sie in der Betriebsdokumentation unter [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ab2f-p104">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

