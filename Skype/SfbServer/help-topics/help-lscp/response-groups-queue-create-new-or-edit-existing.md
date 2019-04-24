---
title: Reaktionsgruppenwarteschleife Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Reaktionsgruppenwarteschleifen halten Anrufe an eine reaktionsgruppe, bis ein Agent den Anruf annimmt.
ms.openlocfilehash: d00d43ab50060990341a2071ea68126ebc445a21
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200583"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="44df2-103">Reaktionsgruppenwarteschleife: Erstellen einer neuen oder Bearbeiten einer vorhandenen Reaktionsgruppenwarteschleife</span><span class="sxs-lookup"><span data-stu-id="44df2-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="44df2-104">Reaktionsgruppenwarteschleifen halten Anrufe an eine reaktionsgruppe, bis ein Agent den Anruf annimmt.</span><span class="sxs-lookup"><span data-stu-id="44df2-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="44df2-105">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="44df2-105">UI Reference</span></span>

<span data-ttu-id="44df2-106">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="44df2-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="44df2-107">**Name** Jede Warteschleife muss einen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="44df2-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="44df2-108">Geben Sie einen beschreibenden Namen für die Warteschleife ein.</span><span class="sxs-lookup"><span data-stu-id="44df2-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="44df2-109">**Beschreibung** Dieses Feld ist optional.</span><span class="sxs-lookup"><span data-stu-id="44df2-109">**Description** This field is optional.</span></span> <span data-ttu-id="44df2-110">Geben Sie darin zusätzliche Details zur Warteschleife an.</span><span class="sxs-lookup"><span data-stu-id="44df2-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="44df2-111">**Gruppen** Wählen Sie die agentgruppen, die Sie an die Warteschlange zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="44df2-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="44df2-112">Klicken Sie auf **Auswählen**, um der Liste Agentgruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="44df2-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="44df2-113">Klicken Sie auf **Entfernen**, um die ausgewählte Agentgruppe aus der Liste zu löschen.</span><span class="sxs-lookup"><span data-stu-id="44df2-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="44df2-114">Mit den Pfeilschaltflächen können Sie eine ausgewählte Agentgruppe in der Liste nach oben oder unten verschieben.</span><span class="sxs-lookup"><span data-stu-id="44df2-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="44df2-115">Die Reihenfolge der Agentengruppen wirkt sich auf die Reihenfolge, in der Skype für Business Server nach einem verfügbaren Agent sucht.</span><span class="sxs-lookup"><span data-stu-id="44df2-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="44df2-116">Die erste Gruppe in der Liste wird also zuerst nach einem verfügbaren Agent durchsucht, dann die zweite Gruppe usw.</span><span class="sxs-lookup"><span data-stu-id="44df2-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="44df2-117">**Timeout der Nachrichtenwarteschlange aktivieren** Aktivieren Sie dieses Kontrollkästchen an eine maximale Zeitspanne für ein Anrufer in der Warteschleife warten, bevor ein Agent den Anruf annimmt.</span><span class="sxs-lookup"><span data-stu-id="44df2-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="44df2-118">Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="44df2-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="44df2-119">**Timeout (Sekunden)** Wählen Sie aus, oder geben Sie die maximale Anzahl von Sekunden ein, die ein Anrufer warten kann, bevor ein Agent den Anruf annimmt.</span><span class="sxs-lookup"><span data-stu-id="44df2-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="44df2-120">**Aktion zum Aufrufen eines** Wählen Sie die Aktion, die bei Zeitüberschreitung eines Anrufs. Die folgenden Optionen sind:</span><span class="sxs-lookup"><span data-stu-id="44df2-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="44df2-121">**Verbindung trennen**</span><span class="sxs-lookup"><span data-stu-id="44df2-121">**Disconnect**</span></span>

  - <span data-ttu-id="44df2-122">**An Voicemail weiterleiten** Wenn Sie diese Option in **SIP-Adresse**auswählen, geben Sie eine Voicemail-Adresse im Format Sip:<username> @ <domainname> (beispielsweise sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="44df2-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="44df2-123">**An Telefonnummer weiterleiten** Wenn Sie diese Option auswählen, geben Sie unter **SIP-Adresse** die Telefonnummer im Format Sip:<number> @ <domainname> (beispielsweise sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="44df2-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="44df2-124">**Weiterleiten an SIP-Adresse** Wählen Sie diese Option, um den Anruf an einen anderen Benutzer weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="44df2-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="44df2-125">Geben Sie in der **SIP-Adresse**, den URI für den Benutzer im Format Sip:<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="44df2-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="44df2-126">**Weiterleiten an eine andere Warteschlange** Wenn Sie diese Option auswählen, wechseln Sie zu der Warteschleife, empfangen anruft, während das Timeout für Anrufe.</span><span class="sxs-lookup"><span data-stu-id="44df2-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="44df2-127">**Aktivieren der Warteschlange Overflow (engl.)** Aktivieren Sie dieses Kontrollkästchen, um eine maximale Anzahl der Anrufe anzugeben, die die Warteschleife aufnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="44df2-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="44df2-128">Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="44df2-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="44df2-129">**Maximale Anzahl von Anrufen** Wählen Sie aus, oder geben Sie die maximale Anzahl von Anrufen, die die Warteschleife aufnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="44df2-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="44df2-130">**Den Anruf weiterleiten** Wählen Sie aus, welchen Anruf reagiert werden soll, wenn die für die Warteschlange Überlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="44df2-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="44df2-131">**Aktion zum Aufrufen eines** Wählen Sie die Aktion, die bei der für die Warteschlange Überlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="44df2-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="44df2-132">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="44df2-132">Your choices are:</span></span>

  - <span data-ttu-id="44df2-133">**Verbindung trennen**</span><span class="sxs-lookup"><span data-stu-id="44df2-133">**Disconnect**</span></span>

  - <span data-ttu-id="44df2-134">**An Voicemail weiterleiten** Wenn Sie diese Option in **SIP-Adresse**auswählen, geben Sie eine Voicemail-Adresse im Format Sip:<username> @ <domainname> (beispielsweise sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="44df2-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="44df2-135">**An Telefonnummer weiterleiten** Wenn Sie diese Option auswählen, geben Sie unter **SIP-Adresse** die Telefonnummer im Format Sip:<number> @ <domainname> (beispielsweise sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="44df2-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="44df2-136">**Weiterleiten an SIP-Adresse** Wählen Sie diese Option, um den Anruf an einen anderen Benutzer weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="44df2-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="44df2-137">Geben Sie in der **SIP-Adresse**, den URI für den Benutzer im Format Sip:<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="44df2-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="44df2-138">**Weiterleiten an eine andere Warteschlange** Wenn Sie diese Option auswählen, wechseln Sie zu der Warteschleife, Anrufe, die für die Warteschlange Überlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="44df2-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="44df2-139">Ausführliche Informationen zu Response Group Features und Funktionen finden Sie unter [Planen für die Anwendung "Reaktionsgruppe" in Skype für Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="44df2-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="44df2-140">Ausführliche Informationen zur Verwendung von Warteschleifen finden Sie in der Betriebsdokumentation unter [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx).</span><span class="sxs-lookup"><span data-stu-id="44df2-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


