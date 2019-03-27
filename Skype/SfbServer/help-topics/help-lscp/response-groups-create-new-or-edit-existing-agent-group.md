---
title: Reaktionsgruppen Erstellen einer neuen oder Bearbeiten von vorhandenen Agentgruppe
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: Mithilfe von Agentgruppen wird definiert, wer Anrufe bei einer Reaktionsgruppe entgegennehmen kann (so genannte Agents). Außerdem werden damit die Einstellungen festgelegt, die für alle Agents der Gruppe gelten.
ms.openlocfilehash: 9dbd8a5d758b9d10ae1d992cd85df91bee19988a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878752"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="e6dc8-103">Reaktionsgruppen: Erstellen einer neuen oder Bearbeiten einer vorhandenen Agentgruppe</span><span class="sxs-lookup"><span data-stu-id="e6dc8-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="e6dc8-104">Mithilfe von Agentgruppen wird definiert, wer Anrufe bei einer Reaktionsgruppe entgegennehmen kann (so genannte Agents). Außerdem werden damit die Einstellungen festgelegt, die für alle Agents der Gruppe gelten.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e6dc8-105">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="e6dc8-105">UI Reference</span></span>

<span data-ttu-id="e6dc8-106">In der folgenden Liste werden die Felder der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="e6dc8-107">**Name** Jeder Agentengruppe erfordert einen eindeutigen Namen.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="e6dc8-108">Verwenden Sie einen beschreibenden Namen, mit dem die Funktion der Gruppe verdeutlicht wird.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="e6dc8-109">Beispiel: Helpdesk.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-109">For example, Help Desk.</span></span>

- <span data-ttu-id="e6dc8-110">**Beschreibung** Dieses Feld ist optional.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-110">**Description** This field is optional.</span></span> <span data-ttu-id="e6dc8-111">Geben Sie darin zusätzliche Details zur Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="e6dc8-112">**Beteiligungsrichtlinie für telefonisten** Geben Sie die Möglichkeit, die Agents zum Anmelden bei der reaktionsgruppe sind:</span><span class="sxs-lookup"><span data-stu-id="e6dc8-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="e6dc8-p103">Wählen Sie **Informell**, um festzulegen, dass sich die Agents der Gruppe nicht an- und abmelden müssen. Informelle Agents werden bei der Anmeldung automatisch bei der Gruppe angemeldet. Die Standardeinstellung ist **Informell**.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-p103">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in. The default is **Informal**.</span></span>

  - <span data-ttu-id="e6dc8-115">Wählen Sie **formelle** um anzugeben, dass die Agents in der Gruppe an-und Abmelden Abmelden müssen. Wenn Sie diese Option auswählen, klicken Sie auf Agents ein Menüelement im-Client auf einen Browser öffnen und Anzeigen von einer Webseite-Konsole für die an-und Abmelden.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="e6dc8-116">**Agentwarnungszeit (Sekunden)** Geben Sie die Anzahl der Sekunden einen Agent angeboten werden soll, bevor der Anruf dem nächsten verfügbaren Vertreter angeboten.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="e6dc8-117">Die Spanne der möglichen Werte reicht von 10 bis weniger als 180 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="e6dc8-118">Die Standardeinstellung ist „20 Sekunden“.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="e6dc8-119">**Routingmethode** Wählen Sie die Methode für die Bestimmung der Reihenfolge, in der Agents Anrufe erhalten:</span><span class="sxs-lookup"><span data-stu-id="e6dc8-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="e6dc8-120">Wählen Sie **Längster Leerlauf**, um den Anruf dem Agent mit der längsten Leerlaufzeit (Anwesenheitsstatus **Verfügbar** oder **Inaktiv**) anzubieten.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="e6dc8-p105">Wählen Sie **Parallel**, um einen neuen Anruf simultan allen verfügbaren Agents anzubieten. Der Anruf wird an den ersten Agent übergeben, der ihn annimmt.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="e6dc8-123">Wählen Sie **Roundrobin**, um einen neuen Anruf den einzelnen Agents nacheinander anzubieten.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="e6dc8-124">Wählen Sie **Seriell**, um einen neuen Anruf den Agents immer in der Reihenfolge anzubieten, in der sie auf der Registerkarte **Agent** aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="e6dc8-125">Wählen Sie **Attendant** , um einen neuen Anruf den alle Support-Mitarbeiter, die angemeldet sind und die Anwendung "Reaktionsgruppe" unabhängig von der aktuellen Anwesenheit gleichzeitig anzubieten.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="e6dc8-126">Um-Telefonzentralen und Clientbenutzer, die konfiguriert werden, wie Agents alle Anrufe sehen können, die darauf warten, und warten Anrufe in beliebiger Reihenfolge beantworten können.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="e6dc8-127">Der Anruf wird an den ersten Agent übergeben, der den Anruf annimmt, und den weiteren Attendants und Benutzern nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="e6dc8-128">**Agents** Wählen Sie die Benutzer-Agents für die reaktionsgruppe in eine der folgenden Arten sein:</span><span class="sxs-lookup"><span data-stu-id="e6dc8-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="e6dc8-129">Wählen Sie **eine vorhandene e-Mail-Verteilerliste verwenden** , um eine Exchange-Verteilerliste verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="e6dc8-130">Geben Sie die E-Mail-Adresse der Verteilerliste unter **Verteilerlistenadresse** ein.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e6dc8-p108">Sie können für eine Agentgruppe nur eine Verteilerliste auswählen. Falls die Verteilerliste verschachtelte Verteilerlisten enthält, werden die verschachtelten Verteilerlisten nicht in die Agentgruppe einbezogen.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e6dc8-133">Die Reihenfolge, in der Agents in der Verteilerliste aufgeführt sind, wirkt sich auf die Reihenfolge aus, in der Agents Anrufe beim Roundrobin- und seriellen Routing angeboten bekommen.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e6dc8-134">Verborgene Mitgliedschaften oder Listen möglicherweise für reaktionsgruppenadministratoren oder Benutzer sichtbar werden.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="e6dc8-135">Weitere Informationen hierzu finden Sie unter [Erstellen oder Ändern einer agentgruppe in Skype für Business 2015](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span><span class="sxs-lookup"><span data-stu-id="e6dc8-135">For details, see [Create or modify an agent group in Skype for Business 2015](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="e6dc8-p110">Wählen Sie **Benutzerdefinierte Gruppe von Agents definieren**, um die Benutzer auszuwählen, die Sie als Agents für die Reaktionsgruppe zuweisen möchten. Klicken Sie auf **Auswählen**, um der Liste einen Agent hinzuzufügen. Klicken Sie auf **Entfernen**, um einen ausgewählten Agent aus der Liste zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="e6dc8-p111">Mit dem Pfeil nach oben bzw. nach unten können Sie einen ausgewählten Agent in der Liste mit den Agents nach oben oder unten verschieben. Die Reihenfolge der Agents in der Liste wirkt sich auf die Reihenfolge aus, in der Agents Anrufe beim Roundrobin- und seriellen Routing angeboten bekommen.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="e6dc8-141">Ausführliche Informationen zu Response Group Features und Funktionen finden Sie unter [Planen für die Anwendung "Reaktionsgruppe" in Skype für Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e6dc8-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="e6dc8-142">Ausführliche Informationen zur Verwendung von Agentgruppen finden Sie in der Betriebsdokumentation unter [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx).</span><span class="sxs-lookup"><span data-stu-id="e6dc8-142">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


