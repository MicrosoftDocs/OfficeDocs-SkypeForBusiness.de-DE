---
title: Workflow für Reaktionsgruppen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: Reaktionsgruppen bestehen aus agentgruppen, Warteschlangen und Workflows. Workflows für Reaktionsgruppen definieren die Aktionen, die ausgeführt werden, wenn die Anwendung "Reaktionsgruppe" einen Telefonanruf empfängt.
ms.openlocfilehash: a86b269b59c04c2f954bc212fa437ebc6e387b4b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896529"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="3d0a2-104">Workflow für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="3d0a2-104">Response Groups Workflow</span></span>

<span data-ttu-id="3d0a2-105">Reaktionsgruppen bestehen aus agentgruppen, Warteschlangen und Workflows.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="3d0a2-106">Workflows für Reaktionsgruppen definieren die Aktionen, die ausgeführt werden, wenn die Anwendung "Reaktionsgruppe" einen Telefonanruf empfängt.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="3d0a2-107">Die **Reaktionsgruppen** - **Workflow** -Seite zeigt eine Liste aller Reaktionsgruppe Workflows, die für Ihre Organisation definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="3d0a2-108">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="3d0a2-108">Tasks you can perform</span></span>

<span data-ttu-id="3d0a2-109">Sie können die folgenden Aufgaben ausführen, aus der **Reaktionsgruppen** - **Workflowstatusseite** :</span><span class="sxs-lookup"><span data-stu-id="3d0a2-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="3d0a2-110">Erstellen Sie oder ändern Sie einen Workflow für Sammelanschlüsse</span><span class="sxs-lookup"><span data-stu-id="3d0a2-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="3d0a2-111">Erstellen oder Ändern eines interaktiven Workflows</span><span class="sxs-lookup"><span data-stu-id="3d0a2-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="3d0a2-112">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="3d0a2-112">UI Reference</span></span>

<span data-ttu-id="3d0a2-113">In der folgenden Liste werden die Befehle der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="3d0a2-114">**Erstellen oder Bearbeiten eines Workflows** Öffnet das Konfigurationstool für Reaktionsgruppen zu erstellen oder Bearbeiten eines Workflows.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="3d0a2-115">**Aktualisieren** Aktualisiert die Liste der Workflows.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="3d0a2-116">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="3d0a2-117">**Name** Der eindeutige Name, der dem Workflow zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="3d0a2-118">**Dienst** Der **ApplicationServer** -Dienst, der den Workflow hostet.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="3d0a2-119">**SIP-Adresse** Die SIP-Adresse der Gruppe, die Anrufe beim Workflow entgegennehmen soll.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="3d0a2-120">**Telefon** Die Telefonnummer, die aufgerufen wird, um diese reaktionsgruppe zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="3d0a2-121">**Sprache** Die Sprache, die für die Spracherkennung und die Sprachsynthese verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="3d0a2-122">**IVR** Gibt an, ob der Workflow einen Sammelanschluss oder einen interaktiven Workflow ist.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="3d0a2-123">**Aktiviert** Gibt an, ob der Workflow Anrufe aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="3d0a2-124">Ausführliche Informationen zu Response Group Features und Funktionen finden Sie unter [Planen für die Anwendung "Reaktionsgruppe" in Skype für Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="3d0a2-125">Ausführliche Informationen zur Verwendung von Workflows für Reaktionsgruppen finden Sie unter [Verwalten von Reaktionsgruppenworkflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3d0a2-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


