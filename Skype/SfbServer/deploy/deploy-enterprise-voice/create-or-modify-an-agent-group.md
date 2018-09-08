---
title: Erstellen oder Ändern einer agentgruppe in Skype für Unternehmen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Erstellen oder Ändern einer agentgruppe in Reaktionsgruppe in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 0a88052d8ceba244e6971d1ebeffdffa84388ef6
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882193"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="d0a53-103">Erstellen oder Ändern einer agentgruppe in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d0a53-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="d0a53-104">Erstellen oder Ändern einer agentgruppe in Reaktionsgruppe in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="d0a53-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d0a53-105">Beim Erstellen einer Agentgruppe wählen Sie die Agents aus, die der Gruppe zugewiesen werden. Außerdem geben Sie zusätzliche Gruppeneinstellungen (beispielsweise die Routingmethode) an und legen fest, ob sich ein Agent bei der Gruppe an- und abmelden muss.</span><span class="sxs-lookup"><span data-stu-id="d0a53-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="d0a53-106">Ein Agent, der bei der Gruppe an-oder vom an-und Abmelden Skype für Unternehmen unterscheidet abmelden muss, wird einen formellen Vertreter aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d0a53-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="d0a53-107">Formelle Agents müssen sich bei der Gruppe anmelden, um an die Gruppe weitergeleitete Anrufe empfangen zu können.</span><span class="sxs-lookup"><span data-stu-id="d0a53-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="d0a53-108">Dies kann für Agents nützlich sein, die Anrufe der Gruppe nur zeitweise annehmen.</span><span class="sxs-lookup"><span data-stu-id="d0a53-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="d0a53-109">Formelle Agents melden sich bei ihren Gruppen an-oder durch Klicken auf ein Menüelement in Skype für Unternehmen Windows Internet Explorer als Browser öffnen und Anzeigen einer Webseite-Konsole.</span><span class="sxs-lookup"><span data-stu-id="d0a53-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="d0a53-110">Ein Agent, der nicht an- und Abmelden der Gruppe angemeldet ist, wird als informeller Agent bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d0a53-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="d0a53-111">Informelle Agents werden automatisch der Gruppe angemeldet, bei der Anmeldung zu Skype für Unternehmen und Anmeldung kann nicht aus der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="d0a53-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="d0a53-112">Nur lokale Benutzer können Agents sein.</span><span class="sxs-lookup"><span data-stu-id="d0a53-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="d0a53-113">Wenn ein Agent lokal zu online verschoben wurde, werden nicht reaktionsgruppenanrufe, Vertreter weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d0a53-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="d0a53-114">Verwenden Sie eines der folgenden Verfahren, um eine Agentgruppe zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d0a53-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d0a53-p104">Wenn Sie Benutzer als Reaktionsgruppenagents zuweisen, weisen Sie diese darauf hin, dass sie bei aktiviertem Datenschutzmodus nach „RGS-Anwesenheitsmonitor“-Kontakten suchen und sie ihrer Kontaktliste hinzufügen müssen. Agents, deren Datenschutzmodus aktiviert ist, die jedoch „RGS-Anwesenheitsmonitor“ nicht in ihre Kontaktliste aufgenommen haben, können keine Anrufe bei der Reaktionsgruppe annehmen. Agents, deren Datenschutzmodus nicht aktiviert ist, sind davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="d0a53-p104">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="d0a53-118">Verwenden Sie zum Erstellen oder Ändern einer agentgruppe Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d0a53-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="d0a53-119">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d0a53-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d0a53-120">Wenn Sie einer der delegierten Reaktionsgruppenleiter für einen verwalteten Workflow sind, können Sie Gruppen erstellen und in den von Ihnen verwalteten Workflows verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0a53-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="d0a53-121">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d0a53-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d0a53-122">Klicken Sie auf der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="d0a53-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="d0a53-123">Führen Sie auf der Seite **Gruppe** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d0a53-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="d0a53-p105">Zum Erstellen einer neuen Agentgruppe klicken Sie auf **Neu**. Geben Sie im Suchfeld **Dienst auswählen** den Namen des **ApplicationServer**-Diensts, dem Sie die Gruppe hinzufügen möchten, ganz oder teilweise ein. Klicken Sie in der nun angezeigten Liste der Dienst auf den gewünschten Dienst und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0a53-p105">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="d0a53-p106">Wenn Sie eine vorhandene Agentgruppe ändern möchten, geben Sie im Suchfeld den Namen der Agentgruppe ganz oder teilweise ein. Klicken Sie in der nun angezeigten Liste auf die gewünschte Gruppe, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d0a53-p106">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d0a53-129">Geben Sie im Feld **Name** einen aussagekräftigen Namen für die Agentgruppe ein.</span><span class="sxs-lookup"><span data-stu-id="d0a53-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="d0a53-130">Geben Sie in **Beschreibung** eine Beschreibung für die Gruppe ein.</span><span class="sxs-lookup"><span data-stu-id="d0a53-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="d0a53-131">Wählen Sie unter **Beteiligungsrichtlinie** eine der folgenden Einstellungen aus, um das Anmeldeverhalten für die Gruppe einzurichten:</span><span class="sxs-lookup"><span data-stu-id="d0a53-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="d0a53-132">Wählen Sie **Informell**, um anzugeben, dass Agents in der Gruppe sich bei der Gruppe weder an- noch abmelden müssen.</span><span class="sxs-lookup"><span data-stu-id="d0a53-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="d0a53-133">Agents werden automatisch der Gruppe angemeldet beim Anmelden bei Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="d0a53-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="d0a53-134">Klicken Sie auf **Formell**, um festzulegen, dass sich die Agents der Gruppe bei der Gruppe an- oder abmelden müssen.</span><span class="sxs-lookup"><span data-stu-id="d0a53-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="d0a53-135">Wenn Sie diese Option auswählen, klicken Sie auf Agents ein Menüelement in Skype für Unternehmen, öffnen Sie Internet Explorer und Anzeigen einer Webseite-Konsole für die Anmeldung bei der Gruppe an-oder.</span><span class="sxs-lookup"><span data-stu-id="d0a53-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="d0a53-136">Geben Sie im Feld **Agentwarnungszeit (Sekunden)** an, wie lange das Telefon eines Agents klingelt, bevor der Anruf an den nächsten verfügbaren Agent übergeben wird (die Standardeinstellung ist 20 Sekunden).</span><span class="sxs-lookup"><span data-stu-id="d0a53-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d0a53-p109">Die Einstellung für die Agentwarnungszeit darf 180 Sekunden nicht überschreiten. Andernfalls weist die Clientanwendung den Anruf zurück, weil der Zeitgeber für die SIP-Transaktion die maximale Wartezeit erreicht.</span><span class="sxs-lookup"><span data-stu-id="d0a53-p109">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="d0a53-139">Wählen Sie unter **Routingmethode** aus, wie Anrufe an die Agents in der Gruppe weitergeleitet werden:</span><span class="sxs-lookup"><span data-stu-id="d0a53-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="d0a53-140">Um einen neuen Anruf zuerst dem Agent anbieten möchten, der die längste Zeit untätig war, Leerlaufzeit (Anwesenheitsstatus **verfügbar** oder **inaktiv** in Skype für Unternehmen, das sich am längsten), klicken Sie auf **Längster Leerlauf**.</span><span class="sxs-lookup"><span data-stu-id="d0a53-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="d0a53-p110">Klicken Sie auf **Parallel**, um einen neuen Anruf simultan allen verfügbaren Agents anzubieten. Der Anruf wird an den ersten Agent übergeben, der diesen annimmt.</span><span class="sxs-lookup"><span data-stu-id="d0a53-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="d0a53-143">Wenn Sie einen neuen Anruf den einzelnen Agents nacheinander anbieten möchten, klicken Sie auf **Roundrobin**.</span><span class="sxs-lookup"><span data-stu-id="d0a53-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="d0a53-144">Wenn Sie einen neuen Anruf den Agents immer in der Reihenfolge anbieten möchten, in der sie auf der Registerkarte **Agent** aufgeführt sind, klicken Sie auf **Seriell**.</span><span class="sxs-lookup"><span data-stu-id="d0a53-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="d0a53-145">Klicken Sie auf **automatische Telefonzentrale**, wenn Sie einen neuen Anruf allen Agents anbieten möchten, die in Skype für Unternehmen und die Anwendung "Reaktionsgruppe" zur selben Zeit, unabhängig von ihrer aktuellen Anwesenheit, angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="d0a53-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="d0a53-146">Benutzer, die als Agents konfiguriert sind, können alle wartenden Anrufe sehen und in beliebiger Reihenfolge annehmen.</span><span class="sxs-lookup"><span data-stu-id="d0a53-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="d0a53-147">Der Anruf wird an den ersten Agent übergeben, der den Anruf annimmt, woraufhin er den weiteren Agents nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d0a53-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="d0a53-148">Geben Sie auf der Registerkarte **Agents** an, wie Sie Ihre Agentliste erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="d0a53-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
   - <span data-ttu-id="d0a53-149">Um eine benutzerdefinierte Liste von Agents zu verwenden, klicken Sie auf **Eine benutzerdefinierte Gruppe von Agents definieren**. Führen Sie anschließend einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d0a53-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
   - <span data-ttu-id="d0a53-p112">Zum Hinzufügen eines Benutzers zur Agentgruppe klicken Sie auf **Agents Auswählen** und geben Sie dann im Suchfeld **Agents auswählen** einen Teil oder den vollständigen Namen des Benutzers ein, der zu dieser Gruppe hinzugefügt werden soll. Klicken Sie anschließend auf **Suchen**. Klicken Sie in der Ergebnisliste auf den betreffenden Benutzer und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0a53-p112">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
   - <span data-ttu-id="d0a53-152">Zum Entfernen eines Benutzers aus der Agentgruppe klicken Sie in der Liste der Agents auf den Benutzer, der entfernt werden soll und anschließend auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="d0a53-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="d0a53-153">Zum Ändern der Reihenfolge, in der Agents Anrufe in Gruppen angeboten werden, die entweder Roundrobinrouting oder serielles Routing verwenden, klicken Sie in der Liste der Agents auf einen Benutzer und dann auf den Pfeil nach oben oder den Pfeil nach unten.</span><span class="sxs-lookup"><span data-stu-id="d0a53-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
   - <span data-ttu-id="d0a53-154">Zum Verwenden einer Microsoft Exchange Server-Verteilerliste als Agentgruppe klicken Sie auf **Eine vorhandene E-Mail-Verteilerliste verwenden** und geben Sie dann in **Adresse der Verteilerliste** die E-Mail-Adresse der Verteilerliste an (z. B. NetzwerkSupport@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d0a53-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
     <span data-ttu-id="d0a53-155">Wenn Sie eine E-Mail-Verteilerliste verwenden, gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="d0a53-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
     - <span data-ttu-id="d0a53-p113">Sie können für die Agentgruppe nicht mehrere Verteilerlisten auswählen. Jede Gruppe unterstützt nur eine Verteilerliste.</span><span class="sxs-lookup"><span data-stu-id="d0a53-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
     - <span data-ttu-id="d0a53-158">Falls die Verteilerliste eine oder mehrere Verteilerlisten enthält, werden die Mitglieder der verschachtelten Verteilerlisten nicht der Agentliste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d0a53-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
     - <span data-ttu-id="d0a53-159">Wenn serielles Routing oder Roundrobinrouting ausgewählt ist, leitet der Server einen eingehenden Anruf gemäß Routingmethode und Reihenfolge, in der Agents auf der Verteilerliste angegeben sind, an den geeigneten Agent weiter.</span><span class="sxs-lookup"><span data-stu-id="d0a53-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
     - <span data-ttu-id="d0a53-p114">Wenn die Verteilerliste Benutzer enthält, für die Lync Server 2010 aktiviert, aber Enterprise Voice nicht aktiviert ist, werden diese der Agentgruppe als dysfunktionelle Agents hinzugefügt. Stellen Sie sicher, dass für alle Mitglieder in der Verteilerliste Enterprise Voice für die Benutzerkonten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d0a53-p114">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents. Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d0a53-162">Wenn Sie eine e-Mail-Verteilerliste verwenden, können verborgene Mitgliedschaften oder Listen für die Reaktionsgruppe Administrator oder Benutzer sichtbar werden.</span><span class="sxs-lookup"><span data-stu-id="d0a53-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="d0a53-163">Verborgene Mitgliedschaften oder Listen werden unter den folgenden Umständen sichtbar:</span><span class="sxs-lookup"><span data-stu-id="d0a53-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="d0a53-164">Wenn eine Verteilerliste, damit die Mitgliedschaft ist ausgeblendet, und der Reaktionsgruppe Administrator der Verteilerliste zu der vertreterliste weist konfiguriert wurde, können Benutzer die Gruppe, um zu ermitteln, wer die Member sind aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d0a53-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="d0a53-165">Eine Verteilerliste wurde so konfiguriert, dass er in der globalen Adressliste von Exchange ausgeblendet ist, der Reaktionsgruppe-Administrator möglicherweise finden Sie unter der Verteilung auflisten und der vertreterliste zuweisen, wenn der Reaktionsgruppe Prozess der ausreichenden Benutzerrechte verfügt und Berechtigungen, auch wenn der Administrator nicht über die entsprechenden Benutzerrechte und-Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="d0a53-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="d0a53-166">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d0a53-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="d0a53-167">Verwenden von Skype für Business Server-Verwaltungsshell zum Erstellen oder Ändern einer agentgruppe</span><span class="sxs-lookup"><span data-stu-id="d0a53-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="d0a53-168">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d0a53-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="d0a53-169">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d0a53-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d0a53-170">Verwenden Sie **New-CsRgsAgentGroup** zum Erstellen einer neuen agentgruppe.</span><span class="sxs-lookup"><span data-stu-id="d0a53-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="d0a53-171">Verwenden Sie **Set-CsRgsAgentGroup** , um eine vorhandene agentgruppe zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d0a53-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="d0a53-172">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d0a53-172">At the command line, run:</span></span>
    
   ```
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="d0a53-173">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d0a53-173">For example:</span></span>
    
   ```
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="d0a53-p116">Die Einstellung für die Agentwarnungszeit darf 180 Sekunden nicht überschreiten. Andernfalls weist die Clientanwendung den Anruf zurück, weil der Zeitgeber für die SIP-Transaktion die maximale Wartezeit erreicht.</span><span class="sxs-lookup"><span data-stu-id="d0a53-p116">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="d0a53-p117">Vergewissern Sie sich, dass die Agentgruppe erstellt worden ist. Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d0a53-p117">Confirm that the agent group is created. Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="d0a53-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0a53-178">See also</span></span>

[<span data-ttu-id="d0a53-179">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="d0a53-179">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="d0a53-180">Mit New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="d0a53-180">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="d0a53-181">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="d0a53-181">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="d0a53-182">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="d0a53-182">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)