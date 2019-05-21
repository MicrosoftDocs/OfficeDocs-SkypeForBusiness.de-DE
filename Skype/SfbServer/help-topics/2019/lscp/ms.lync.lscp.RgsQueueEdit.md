---
title: Antwortgruppen-Warteschlange "neue erstellen" oder "vorhandene bearbeiten"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: Warteschlangen für Reaktionsgruppen halten Anrufe an eine Reaktionsgruppe, bis ein Agent den Anruf annimmt.
ms.openlocfilehash: 20a2066cbbece953e8f050919d8531f887f676ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292605"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="c5c1c-103">Reaktionsgruppenwarteschleife: Erstellen einer neuen oder Bearbeiten einer vorhandenen Reaktionsgruppenwarteschleife</span><span class="sxs-lookup"><span data-stu-id="c5c1c-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="c5c1c-104">Warteschlangen für Reaktionsgruppen halten Anrufe an eine Reaktionsgruppe, bis ein Agent den Anruf annimmt.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c5c1c-105">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="c5c1c-105">UI Reference</span></span>

<span data-ttu-id="c5c1c-106">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c5c1c-107">**Name** Jede Warteschlange muss einen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="c5c1c-108">Geben Sie einen beschreibenden Namen für die Warteschleife ein.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="c5c1c-109">**Beschreibung** Dieses Feld ist optional.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-109">**Description** This field is optional.</span></span> <span data-ttu-id="c5c1c-110">Geben Sie darin zusätzliche Details zur Warteschleife an.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="c5c1c-111">**Gruppen** Wählen Sie die Agentengruppen aus, die Sie der Warteschlange zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="c5c1c-112">Klicken Sie auf **Auswählen**, um der Liste Agentgruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="c5c1c-113">Klicken Sie auf **Entfernen**, um die ausgewählte Agentgruppe aus der Liste zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="c5c1c-114">Mit den Pfeilschaltflächen können Sie eine ausgewählte Agentgruppe in der Liste nach oben oder unten verschieben.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="c5c1c-115">Die Reihenfolge der Agentengruppen wirkt sich auf die Reihenfolge aus, in der der Skype for Business-Server nach einem verfügbaren Agenten sucht.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="c5c1c-116">Die erste Gruppe in der Liste wird also zuerst nach einem verfügbaren Agent durchsucht, dann die zweite Gruppe usw.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="c5c1c-117">**Aktivieren des warteschlangentimeouts** Aktivieren Sie dieses Kontrollkästchen, um eine maximale Zeitdauer anzugeben, die ein Anrufer warten muss, bevor ein Agent den Anruf beantwortet.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="c5c1c-118">Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="c5c1c-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="c5c1c-119">**Timeoutzeitraum (Sekunden)** Wählen oder geben Sie die maximale Anzahl von Sekunden ein, die ein Anrufer warten kann, bevor ein Agent den Anruf beantwortet.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="c5c1c-120">**Anrufaktion** Wählen Sie die Aktion aus, die beim Timeout eines Anrufs eintritt. Ihre Auswahlmöglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="c5c1c-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="c5c1c-121">**Verbindung trennen**</span><span class="sxs-lookup"><span data-stu-id="c5c1c-121">**Disconnect**</span></span>

  - <span data-ttu-id="c5c1c-122">**Weiterleiten an Voicemail** Wenn Sie diese Option auswählen, geben Sie unter **SIP-Adresse**im Format SIP<username> @ <domainname> : (beispielsweise SIP:Bob@contoso.com) eine Voicemail-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="c5c1c-123">**Weiterleitung an Telefonnummer** Wenn Sie diese Option auswählen, geben Sie in **SIP Address** die Telefonnummer im Format SIP:<number> @ <domainname> ein (beispielsweise SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c5c1c-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="c5c1c-124">**An SIP-Adresse weiterleiten** Wählen Sie diese Option aus, um den Anruf an einen anderen Benutzer weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="c5c1c-125">Geben Sie in **SIP-Adresse**den URI für den Benutzer im Format SIP:<username>@<domainname>ein.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="c5c1c-126">**Weiterleiten an eine andere Warteschlange** Wenn Sie diese Option auswählen, navigieren Sie zu der Warteschlange, in der Anrufe empfangen werden, wenn das Zeitlimit für Anrufe abläuft.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="c5c1c-127">**Aktivieren des Warteschlangen Überlaufs** Aktivieren Sie dieses Kontrollkästchen, um die maximale Anzahl von Anrufen anzugeben, die in der Warteschlange enthalten sein können.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="c5c1c-128">Wenn Sie diese Option auswählen, müssen Sie auch Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="c5c1c-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="c5c1c-129">**Maximale Anzahl von Anrufen** Wählen Sie die maximale Anzahl von Anrufen aus, die die Warteschlange aufnehmen kann, oder geben Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="c5c1c-130">**Weiterleiten des Anrufs** Wählen Sie aus, welche Aktion durchführen soll, wenn der Schwellenwert für den Warteschlangen Überlauf erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="c5c1c-131">**Anrufaktion** Wählen Sie die Aktion aus, die auftritt, wenn der Schwellenwert für den Warteschlangen Überlauf erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="c5c1c-132">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="c5c1c-132">Your choices are:</span></span>

  - <span data-ttu-id="c5c1c-133">**Verbindung trennen**</span><span class="sxs-lookup"><span data-stu-id="c5c1c-133">**Disconnect**</span></span>

  - <span data-ttu-id="c5c1c-134">**Weiterleiten an Voicemail** Wenn Sie diese Option auswählen, geben Sie unter **SIP-Adresse**im Format SIP<username> @ <domainname> : (beispielsweise SIP:Bob@contoso.com) eine Voicemail-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="c5c1c-135">**Weiterleitung an Telefonnummer** Wenn Sie diese Option auswählen, geben Sie in **SIP Address** die Telefonnummer im Format SIP:<number> @ <domainname> ein (beispielsweise SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c5c1c-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="c5c1c-136">**An SIP-Adresse weiterleiten** Wählen Sie diese Option aus, um den Anruf an einen anderen Benutzer weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="c5c1c-137">Geben Sie in **SIP-Adresse**den URI für den Benutzer im Format SIP:<username>@<domainname>ein.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="c5c1c-138">**Weiterleiten an eine andere Warteschlange** Wenn Sie diese Option auswählen, navigieren Sie zu der Warteschlange, die Anrufe empfangen soll, wenn der Schwellenwert für den Warteschlangen Überlauf erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="c5c1c-139">Ausführliche Informationen zu den Features und Funktionen der Reaktionsgruppe finden Sie unter [Planen der reaktionsgruppenanwendung in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c5c1c-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="c5c1c-140">Ausführliche Informationen zur Verwendung von Warteschleifen finden Sie in der Betriebsdokumentation unter [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx).</span><span class="sxs-lookup"><span data-stu-id="c5c1c-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


