---
title: Erstellen einer Anrufwarteschlange
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie das Telefon System für Anrufwarteschlangen mit Microsoft Teams einrichten, die eine Grußnachricht, Musik, Anrufumleitung und andere Funktionen enthalten.
ms.openlocfilehash: 31826d1090835a073551e3639cb6105feb16d650
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48793534"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="ff34e-103">Erstellen einer Anrufwarteschlange</span><span class="sxs-lookup"><span data-stu-id="ff34e-103">Create a call queue</span></span>

<span data-ttu-id="ff34e-104">Anrufwarteschlangen bieten eine Methode zum Weiterleiten von Anrufern an Personen in Ihrer Organisation, die mit einem bestimmten Problem oder einer bestimmten Frage helfen können.</span><span class="sxs-lookup"><span data-stu-id="ff34e-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="ff34e-105">Anrufe werden einzeln an die Personen in der Warteschlange verteilt (die als *Agents* bezeichnet werden).</span><span class="sxs-lookup"><span data-stu-id="ff34e-105">Calls are distributed one at a time to the people in the queue (who are known as *agents* ).</span></span> 

<span data-ttu-id="ff34e-106">Anrufwarteschlangen bieten Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ff34e-106">Call queues provide:</span></span>

- <span data-ttu-id="ff34e-107">Eine Grußnachricht.</span><span class="sxs-lookup"><span data-stu-id="ff34e-107">A greeting message.</span></span>

- <span data-ttu-id="ff34e-108">Musik, während die Leute in einer Warteschleife warten.</span><span class="sxs-lookup"><span data-stu-id="ff34e-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="ff34e-109">Anrufweiterleitung-in *First Out* (FIFO)-Auftrags-zu-Agents</span><span class="sxs-lookup"><span data-stu-id="ff34e-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="ff34e-110">Behandlungsoptionen für Warteschlangen Überlauf und-Timeout</span><span class="sxs-lookup"><span data-stu-id="ff34e-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="ff34e-111">Stellen Sie sicher, dass Sie den [Plan für automatische Team-Telefonzentralen und-Warteschlangen](plan-auto-attendant-call-queue.md) gelesen haben, und folgen Sie den [Schritten unter erste](plan-auto-attendant-call-queue.md#getting-started) Schritte, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="ff34e-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="ff34e-112">Zum Einrichten einer Anrufwarteschlange erweitern Sie im Team Admin Center die **Sprache** , klicken Sie auf **Anrufwarteschlangen** , und klicken Sie dann auf **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="ff34e-112">To set up a call queue, in the Teams admin center, expand **Voice** , click **Call queues** , and then click **Add** .</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="ff34e-113">Ressourcenkonto und-Sprache</span><span class="sxs-lookup"><span data-stu-id="ff34e-113">Resource account and language</span></span>

![](media/call-queue-name-language.png)

1. <span data-ttu-id="ff34e-114">Geben Sie einen Namen für die Anrufwarteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="ff34e-114">Type a name for the call queue.</span></span> <span data-ttu-id="ff34e-115">Agents sehen diesen Namen, wenn ein eingehender Anruf von der Warteschlange empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="ff34e-115">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="ff34e-116">Klicken Sie auf **Konten hinzufügen** , suchen Sie nach dem Ressourcenkonto, das Sie für diese Anrufwarteschlange verwenden möchten, klicken Sie auf **hinzu** fügen, und klicken Sie dann auf **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="ff34e-116">Click **Add accounts** , search for the resource account that you want to use with this call queue, click **Add** , and then click **Add** .</span></span>

3. <span data-ttu-id="ff34e-117">Wählen Sie eine Sprache aus.</span><span class="sxs-lookup"><span data-stu-id="ff34e-117">Choose a language.</span></span> <span data-ttu-id="ff34e-118">Diese Sprache wird für System generierte Sprachansagen und Voicemail-Transkription verwendet (wenn Sie Sie aktivieren).</span><span class="sxs-lookup"><span data-stu-id="ff34e-118">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-hold-music"></a><span data-ttu-id="ff34e-119">Grüßen und halten von Musik</span><span class="sxs-lookup"><span data-stu-id="ff34e-119">Greetings and hold music</span></span>

<span data-ttu-id="ff34e-120">Geben Sie an, ob Sie einen Gruß an Anrufer wiedergeben möchten, wenn Sie in der Warteschlange ankommen.</span><span class="sxs-lookup"><span data-stu-id="ff34e-120">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="ff34e-121">Sie müssen eine MP3-, WAV-oder WMA-Datei hochladen, die die Ansage enthält, die Sie wiedergeben möchten.</span><span class="sxs-lookup"><span data-stu-id="ff34e-121">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="ff34e-122">Teams stellt Anrufern Standardmusik zur Verfügung, während Sie in einer Warteschlange gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="ff34e-122">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="ff34e-123">Wenn Sie eine bestimmte Audiodatei wiedergeben möchten, wählen Sie **Audiodatei wiedergeben** aus, und laden Sie eine MP3-, WAV-oder WMA-Datei hoch.</span><span class="sxs-lookup"><span data-stu-id="ff34e-123">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="ff34e-124">Die hochgeladene Aufzeichnung darf nicht größer als 5 MB sein.</span><span class="sxs-lookup"><span data-stu-id="ff34e-124">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="ff34e-125">Die Standardmusik, die in Teams-Anrufwarteschlangen bereitgestellt wird, ist von den von Ihrer Organisation zu zahlenden Gebühren befreit.</span><span class="sxs-lookup"><span data-stu-id="ff34e-125">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="ff34e-126">Anruf-Agents</span><span class="sxs-lookup"><span data-stu-id="ff34e-126">Call agents</span></span>

<span data-ttu-id="ff34e-127">Ausgewählte Anruf-Agents müssen eine der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="ff34e-127">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="ff34e-128">Online-Benutzer mit einer Telefon System Lizenz und Enterprise-VoIP aktiviert</span><span class="sxs-lookup"><span data-stu-id="ff34e-128">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="ff34e-129">Online Benutzer mit einem Anrufplan</span><span class="sxs-lookup"><span data-stu-id="ff34e-129">Online users with a Calling Plan</span></span>
- <span data-ttu-id="ff34e-130">Lokale Skype for Business Server-Benutzer</span><span class="sxs-lookup"><span data-stu-id="ff34e-130">On-premises Skype for Business Server users</span></span>
- <span data-ttu-id="ff34e-131">Wenn Ihre Agents die Microsoft Teams-App für Anruf Warteschlangen Anrufe verwenden, müssen Sie sich im TeamsOnly-Modus befinden.</span><span class="sxs-lookup"><span data-stu-id="ff34e-131">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

![](media/call-queue-users-groups.png)

<span data-ttu-id="ff34e-132">Sie können bis zu 20 Agents einzeln und bis zu 200-Agents über Gruppen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ff34e-132">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="ff34e-133">Wenn Sie der Warteschlange einen Benutzer hinzufügen möchten, klicken Sie auf **Benutzer hinzufügen** , suchen Sie nach dem Benutzer, klicken Sie auf **hinzu** fügen, und klicken Sie dann auf **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="ff34e-133">To add a user to the queue, click **Add users** , search for the user, click **Add** , and then click **Add** .</span></span>

<span data-ttu-id="ff34e-134">Wenn Sie der Warteschlange eine Gruppe hinzufügen möchten, klicken Sie auf **Gruppen hinzufügen** , suchen Sie nach der Gruppe, klicken Sie auf **hinzu** fügen, und klicken Sie dann auf **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="ff34e-134">To add a group to the queue, click **Add groups** , search for the group, click **Add** , and then click **Add** .</span></span> <span data-ttu-id="ff34e-135">Sie können Verteilerlisten, Sicherheitsgruppen und Microsoft 365-Gruppen oder Microsoft Teams-Teams verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff34e-135">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="ff34e-136">Neue Benutzer, die zu einer Gruppe hinzugefügt wurden, können bis zu acht Stunden dauern, bis Ihr erster Anruf eingeht.</span><span class="sxs-lookup"><span data-stu-id="ff34e-136">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="ff34e-137">Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="ff34e-137">Call routing</span></span>

![](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="ff34e-138">Der **Konferenzmodus** verringert erheblich die Zeitdauer, die ein Anrufer mit einem Agenten verbunden sein muss, nachdem der Agent den Anruf angenommen hat.</span><span class="sxs-lookup"><span data-stu-id="ff34e-138">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="ff34e-139">Damit der Konferenzmodus funktioniert, müssen die Agents in der Anrufwarteschlange einen der folgenden Clients verwenden:</span><span class="sxs-lookup"><span data-stu-id="ff34e-139">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="ff34e-140">Die neueste Version des Microsoft Teams-Desktop Clients, der Android-App oder der IOS-App</span><span class="sxs-lookup"><span data-stu-id="ff34e-140">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="ff34e-141">Microsoft Teams Phone Version 1449/1.0.94.2020051601 oder höher</span><span class="sxs-lookup"><span data-stu-id="ff34e-141">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="ff34e-142">Die Konten von Agenten Teams müssen auf "nur für Teams" eingestellt sein.</span><span class="sxs-lookup"><span data-stu-id="ff34e-142">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="ff34e-143">Agents, die die Anforderungen nicht erfüllen, werden nicht in die Anruf Weiterleitungsliste aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="ff34e-143">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="ff34e-144">Es wird empfohlen, den Konferenzmodus für Ihre Anrufwarteschlangen zu aktivieren, wenn Ihre Agents alle kompatible Clients verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff34e-144">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="ff34e-145">Busy on Busy wird vom Konferenzmodus nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ff34e-145">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="ff34e-146">Agents in Warteschlangen anrufen, die keine Anrufwarteschlange sind, werden möglicherweise weiterhin mit einem Anruf Warteschlangen Anruf angezeigt, wenn Anwesenheits basiertes Routing nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ff34e-146">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="ff34e-147">Die **Routing Methode** bestimmt die Reihenfolge, in der die Agents Anrufe aus der Warteschlange empfangen.</span><span class="sxs-lookup"><span data-stu-id="ff34e-147">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="ff34e-148">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="ff34e-148">Choose from these options:</span></span>

- <span data-ttu-id="ff34e-149">**Attendant-Routing** klingelt alle Agents in der Warteschlange zur gleichen Zeit.</span><span class="sxs-lookup"><span data-stu-id="ff34e-149">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="ff34e-150">Der Anruf wird vom ersten Anruf Agenten abgeholt.</span><span class="sxs-lookup"><span data-stu-id="ff34e-150">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="ff34e-151">Das **serielle Routing** klingelt alle Anruf-Agents einzeln in der Reihenfolge, die in der Liste der **Anruf-Agents** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ff34e-151">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="ff34e-152">Wenn ein Agent einen Anruf abschließt oder nicht annimmt, klingelt der Anruf beim nächsten Agenten und versucht alle Agenten, bis er abgeholt wird oder ein Timeout annimmt.</span><span class="sxs-lookup"><span data-stu-id="ff34e-152">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="ff34e-153">**Round Robin** balanciert die Weiterleitung eingehender Anrufe, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält.</span><span class="sxs-lookup"><span data-stu-id="ff34e-153">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="ff34e-154">Dies kann in einer eingehenden Vertriebsumgebung wünschenswert sein, um die Chancengleichheit zwischen allen Anruf Agenten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="ff34e-154">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="ff34e-155">**Längster Leerlauf** leitet jeden Anruf an den Agenten weiter, der die längste Zeit inaktiv war.</span><span class="sxs-lookup"><span data-stu-id="ff34e-155">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="ff34e-156">Ein Agent gilt als im Leerlauf, wenn sein Anwesenheitsstatus verfügbar ist oder wenn sein Anwesenheitsstatus für weniger als 10 Minuten abwesend war.</span><span class="sxs-lookup"><span data-stu-id="ff34e-156">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="ff34e-157">Agents, deren Anwesenheitsstatus für mehr als 10 Minuten abwesend war, werden nicht als im Leerlauf betrachtet und sind nicht berechtigt, Anrufe entgegenzunehmen, bis Sie deren Anwesenheit in verfügbar ändern.</span><span class="sxs-lookup"><span data-stu-id="ff34e-157">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![](media/call-queue-presence-agents-time.png)


<span data-ttu-id="ff34e-158">Bei **Anwesenheits basiertem Routing** wird der Verfügbarkeitsstatus von Anruf-Agents verwendet, um zu ermitteln, ob ein Agent in die Anruf Weiterleitungsliste für die ausgewählte Routingmethode aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff34e-158">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="ff34e-159">Anruf-Agents, deren Verfügbarkeitsstatus auf **verfügbar** festgesetzt ist, sind in der Anruf Weiterleitungsliste enthalten und können Anrufe empfangen.</span><span class="sxs-lookup"><span data-stu-id="ff34e-159">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="ff34e-160">Agents, deren Verfügbarkeitsstatus auf einen beliebigen anderen Status festgesetzt ist, werden aus der Anruf Weiterleitungsliste ausgeschlossen und empfangen keine Anrufe, bis sich der Verfügbarkeitsstatus wieder in **verfügbar** ändert.</span><span class="sxs-lookup"><span data-stu-id="ff34e-160">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available** .</span></span> 

<span data-ttu-id="ff34e-161">Sie können das anwesenheitsbasierte Anrufrouting mit einer der Routingmethoden aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ff34e-161">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="ff34e-162">Wenn sich ein Agent für das Abrufen von Anrufen entscheidet, wird er nicht in die Anruf Weiterleitungsliste aufgenommen, unabhängig davon, auf welchen Verfügbarkeitsstatus er festgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="ff34e-162">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="ff34e-163">Agents, die den Skype for Business-Client verwenden, sind in der Anruf Weiterleitungsliste nicht enthalten, wenn Anwesenheits basiertes Routing aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ff34e-163">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="ff34e-164">Wenn Sie über Agenten verfügen, die Skype for Business verwenden, aktivieren Sie das anwesenheitsbasierte Anrufrouting nicht.</span><span class="sxs-lookup"><span data-stu-id="ff34e-164">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="ff34e-165">**Agent-Warnungszeit** gibt an, wie lange das Telefon eines Agenten klingelt, bevor die Warteschlange den Anruf an den nächsten Agenten weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="ff34e-165">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="ff34e-166">Für Warteschlangen mit großem Datenaufkommen empfehlen wir die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ff34e-166">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="ff34e-167">**Konferenzmodus** für **Auto**</span><span class="sxs-lookup"><span data-stu-id="ff34e-167">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="ff34e-168">**Routingmethode** für das **Attendant-Routing**</span><span class="sxs-lookup"><span data-stu-id="ff34e-168">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="ff34e-169">**Anwesenheits basiertes Routing** auf **ein**</span><span class="sxs-lookup"><span data-stu-id="ff34e-169">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="ff34e-170">**Agent-Warnungszeit:** bis **20 Sekunden**</span><span class="sxs-lookup"><span data-stu-id="ff34e-170">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="ff34e-171">Anruf Überlauf Behandlung</span><span class="sxs-lookup"><span data-stu-id="ff34e-171">Call overflow handling</span></span>

![](media/call-queue-overflow-handling.png)

<span data-ttu-id="ff34e-172">**Maximale Anrufe in der Warteschlange** geben die maximale Anzahl von Anrufen an, die zu einem beliebigen Zeitpunkt in der Warteschlange warten können.</span><span class="sxs-lookup"><span data-stu-id="ff34e-172">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="ff34e-173">Der Standardwert ist 50, aber er kann zwischen 0 und 200 liegen.</span><span class="sxs-lookup"><span data-stu-id="ff34e-173">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="ff34e-174">Wenn dieser Grenzwert erreicht ist, wird der Anruf so gehandhabt, wie er durch das festgelegt wird, **Wenn die maximale Anzahl von Anrufen erreicht ist** .</span><span class="sxs-lookup"><span data-stu-id="ff34e-174">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="ff34e-175">Sie können wählen, ob Sie den Anruf trennen oder ihn an eines der Anruf Weiterleitungs Ziele weiterleiten möchten.</span><span class="sxs-lookup"><span data-stu-id="ff34e-175">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="ff34e-176">So können Sie beispielsweise den Anrufer für die Agents in der Warteschlange eine Sprachnachricht hinterlassen.</span><span class="sxs-lookup"><span data-stu-id="ff34e-176">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span>

> [!NOTE]
> <span data-ttu-id="ff34e-177">Wenn die maximale Anzahl von Anrufen auf 0 festgesetzt wird, wird die Ansage nicht wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="ff34e-177">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="ff34e-178">Anruf Timeout Behandlung</span><span class="sxs-lookup"><span data-stu-id="ff34e-178">Call timeout handling</span></span>

![](media/call-queue-timeout-handling.png)

<span data-ttu-id="ff34e-179">**Anruf Timeout: maximale Wartezeit** gibt an, wie lange ein Anruf maximal in der Warteschlange gehalten werden kann, bevor er umgeleitet oder getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="ff34e-179">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="ff34e-180">Sie können einen Wert von 15 Sekunden bis 45 Minuten angeben.</span><span class="sxs-lookup"><span data-stu-id="ff34e-180">You can specify a value from 15 seconds to 45 minutes.</span></span>

<span data-ttu-id="ff34e-181">Sie können wählen, ob Sie den Anruf trennen oder ihn an eines der Anruf Weiterleitungs Ziele weiterleiten möchten.</span><span class="sxs-lookup"><span data-stu-id="ff34e-181">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="ff34e-182">So können Sie beispielsweise den Anrufer für die Agents in der Warteschlange eine Sprachnachricht hinterlassen.</span><span class="sxs-lookup"><span data-stu-id="ff34e-182">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span>

<span data-ttu-id="ff34e-183">Wenn Sie die Optionen für das Anruf Timeout ausgewählt haben, klicken Sie auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="ff34e-183">When you have selected your call timeout options, click **Save** .</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="ff34e-184">Rufnummernanzeige für ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="ff34e-184">Caller ID for outbound calls</span></span>

<span data-ttu-id="ff34e-185">Da sich die Agents in einer Anrufwarteschlange möglicherweise auswählen, um einen Kundenanruf zurückzugeben, sollten Sie in der Lage sein, die Rufnummernanzeige für Mitglieder einer Anrufwarteschlange auf die Dienstnummer einer entsprechenden automatischen Telefonzentrale festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ff34e-185">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="ff34e-186">Weitere Informationen finden Sie unter [Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams](caller-id-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="ff34e-186">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="ff34e-187">Unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="ff34e-187">Supported clients</span></span>

- <span data-ttu-id="ff34e-188">Die folgenden Clients werden für Anruf-Agents in einer Anrufwarteschlange unterstützt:</span><span class="sxs-lookup"><span data-stu-id="ff34e-188">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="ff34e-189">Skype for Business-Desktop Client 2016 (32-Bit-und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="ff34e-189">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="ff34e-190">Lync-Desktop Client 2013 (32-Bit-und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="ff34e-190">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="ff34e-191">Alle IP-Telefonmodelle, die für Microsoft Teams unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="ff34e-191">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="ff34e-192">Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="ff34e-192">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="ff34e-193">Mac Skype for Business-Client (Version 16.8.196 und höher)</span><span class="sxs-lookup"><span data-stu-id="ff34e-193">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="ff34e-194">Android Skype for Business-Client (Version 6.16.0.9 und höher)</span><span class="sxs-lookup"><span data-stu-id="ff34e-194">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="ff34e-195">iPhone Skype for Business-Client (Version 6.16.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="ff34e-195">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="ff34e-196">Mac Skype for Business-Client (Version 6.16.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="ff34e-196">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="ff34e-197">Microsoft Teams Windows-Client (32-Bit-und 64-Bit-Versionen)</span><span class="sxs-lookup"><span data-stu-id="ff34e-197">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="ff34e-198">Microsoft Teams Mac-Client</span><span class="sxs-lookup"><span data-stu-id="ff34e-198">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="ff34e-199">Microsoft Teams-iPhone-App</span><span class="sxs-lookup"><span data-stu-id="ff34e-199">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="ff34e-200">Microsoft Teams Android-App</span><span class="sxs-lookup"><span data-stu-id="ff34e-200">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="ff34e-201">Anrufwarteschlangen, denen eine direkte Routingnummer zugewiesen ist, unterstützen keine Skype for Business-Clients, lync-Clients oder Skype for Business-IP-Telefone als Agents.</span><span class="sxs-lookup"><span data-stu-id="ff34e-201">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="ff34e-202">Cmdlets für Anrufwarteschleifen</span><span class="sxs-lookup"><span data-stu-id="ff34e-202">Call queue cmdlets</span></span>

<span data-ttu-id="ff34e-203">Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ff34e-203">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="ff34e-204">Hier sind die Cmdlets, mit denen Sie eine Anrufwarteschlange verwalten.</span><span class="sxs-lookup"><span data-stu-id="ff34e-204">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="ff34e-205">Neu – CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="ff34e-205">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="ff34e-206">Satz-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="ff34e-206">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="ff34e-207">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="ff34e-207">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="ff34e-208">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="ff34e-208">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

## <a name="related-topics"></a><span data-ttu-id="ff34e-209">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ff34e-209">Related topics</span></span>

[<span data-ttu-id="ff34e-210">Das Telefonsystem bietet Ihnen Folgendes</span><span class="sxs-lookup"><span data-stu-id="ff34e-210">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="ff34e-211">Abrufen von Diensttelefonnummern</span><span class="sxs-lookup"><span data-stu-id="ff34e-211">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="ff34e-212">Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen</span><span class="sxs-lookup"><span data-stu-id="ff34e-212">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="ff34e-213">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="ff34e-213">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="ff34e-214">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ff34e-214">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
