---
title: Clientversionsrichtlinie
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: Sie können die Versionen von Clients angeben, die in Ihrer Umgebung unterstützt werden sollen. Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden. Die größte Nutzung der Features in Skype für Business Server 2015 und zur Verbesserung der benutzerfreundlichkeit können den clientversionsfilter Sie um die Clientversionen, die verwendet werden in Ihrer Umgebung zu beschränken. Mit dem Clientversionsfilter können Sie außerdem die Kosten senken, die aufgrund der Unterstützung mehrerer Clientversionen anfallen.
ms.openlocfilehash: cdba87f684af4a0bac4f36e9a856957a70499840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-policy"></a><span data-ttu-id="15f90-106">Clientversionsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="15f90-106">Client Version Policy</span></span>
 
<span data-ttu-id="15f90-107">Sie können die Versionen von Clients angeben, die in Ihrer Umgebung unterstützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="15f90-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="15f90-108">Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="15f90-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="15f90-109">Die größte Nutzung der Features in Skype für Business Server 2015 und zur Verbesserung der benutzerfreundlichkeit können den clientversionsfilter Sie um die Clientversionen, die verwendet werden in Ihrer Umgebung zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="15f90-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="15f90-110">Mit dem Clientversionsfilter können Sie außerdem die Kosten senken, die aufgrund der Unterstützung mehrerer Clientversionen anfallen.</span><span class="sxs-lookup"><span data-stu-id="15f90-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="15f90-111">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="15f90-111">Tasks you can perform</span></span>

<span data-ttu-id="15f90-112">Auf der Seite **Clientversionsrichtlinie** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="15f90-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>
  
- <span data-ttu-id="15f90-113">Bearbeiten Sie die Standardeinstellung ( **Global**) clientversionsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="15f90-113">Edit the default ( **Global**) client version policy.</span></span>
    
- <span data-ttu-id="15f90-114">Erstellen von Clientversionsrichtlinien für einen bestimmten Standort oder Pool</span><span class="sxs-lookup"><span data-stu-id="15f90-114">Create client version policies for a particular site or pool.</span></span>
    
- <span data-ttu-id="15f90-115">Erstellen von Clientversionsrichtlinien, die einzelnen Benutzern zugewiesen werden können</span><span class="sxs-lookup"><span data-stu-id="15f90-115">Create client version policies that can be assigned to individual users.</span></span>
    
> [!NOTE]
> <span data-ttu-id="15f90-116">Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="15f90-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span> 
  
## <a name="ui-reference"></a><span data-ttu-id="15f90-117">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="15f90-117">UI Reference</span></span>

<span data-ttu-id="15f90-118">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15f90-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="15f90-119">**Neue** Sie können eine oder mehrere der folgenden clientversionsrichtlinien erstellen:</span><span class="sxs-lookup"><span data-stu-id="15f90-119">**New** You can create one or more of each of the following client version policies:</span></span>
    
  - <span data-ttu-id="15f90-120">Standortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="15f90-120">Site policy</span></span>
    
  - <span data-ttu-id="15f90-121">Poolrichtlinie</span><span class="sxs-lookup"><span data-stu-id="15f90-121">Pool policy</span></span>
    
  - <span data-ttu-id="15f90-122">Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="15f90-122">User policy</span></span>
    
- <span data-ttu-id="15f90-123">**Bearbeiten** Sie können die Optionen aller clientversionsrichtlinien ändern.</span><span class="sxs-lookup"><span data-stu-id="15f90-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="15f90-124">Mit dieser Option haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="15f90-124">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="15f90-125">**Details anzeigen** Diese Option öffnet ein Dialogfeld, in dem Sie die Optionen für eine clientversionsrichtlinie ändern können.</span><span class="sxs-lookup"><span data-stu-id="15f90-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>
    
  - <span data-ttu-id="15f90-126">**Wählen Sie alle** Diese Option werden alle clientversionsrichtlinien der Liste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="15f90-126">**Select All** This option selects all client version policies in the list.</span></span>
    
  - <span data-ttu-id="15f90-127">**Löschen** Diese Option werden alle ausgewählten clientversionsrichtlinien gelöscht.</span><span class="sxs-lookup"><span data-stu-id="15f90-127">**Delete** This option deletes all selected client version policies.</span></span>
    
- <span data-ttu-id="15f90-128">**Aktualisieren** Sie können die Liste Client Version Richtlinie zum Überprüfen des Status der Optionen aller clientversionsrichtlinien aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="15f90-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>
    
<span data-ttu-id="15f90-129">Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="15f90-129">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="15f90-130">Ausführliche Informationen zur Verwendung von clientversionsrichtlinien finden Sie unter [Specify the Client Versions Supported in Your Organization](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="15f90-130">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

