---
title: 'Lync Server 2013: Erstellen oder Ändern einer Agentengruppe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b60ba1c402a629c0a85b2bd99dc4819da3455660
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="d3877-102">Erstellen oder Ändern einer Agentengruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3877-102">Create or modify an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3877-103">_**Letztes Änderungsstand des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="d3877-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="d3877-104">Verwenden Sie eines der folgenden Verfahren, um eine Agentengruppe zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d3877-104">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d3877-105">Ein Administrator (beispielsweise CsVoiceAdministrator) muss Benutzer für Enterprise-VoIP und-lync Server aktivieren, bevor die Benutzeragenten Gruppen zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="d3877-105">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="d3877-106">Wenn Sie einer der Delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Agentgruppen erstellen und die Agentengruppen in den von Ihnen verwalteten Workflows verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3877-106">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3877-p102">Wenn Sie Benutzer als Reaktionsgruppenagents zuweisen, weisen Sie diese darauf hin, dass sie bei aktiviertem Datenschutzmodus nach "RGS-Anwesenheitsmonitor"-Kontakten suchen und sie ihrer Kontaktliste hinzufügen müssen. Agents, deren Datenschutzmodus aktiviert ist, die jedoch "RGS-Anwesenheitsmonitor" nicht in ihre Kontaktliste aufgenommen haben, können keine Anrufe bei der Reaktionsgruppe annehmen. Agents, deren Datenschutzmodus nicht aktiviert ist, sind davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="d3877-p102">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="d3877-110">So verwenden Sie lync Server-Systemsteuerung zum Erstellen oder Ändern einer Agentgruppe</span><span class="sxs-lookup"><span data-stu-id="d3877-110">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="d3877-111">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d3877-111">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d3877-112">Wenn Sie einer der Delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Gruppen erstellen und in den von Ihnen verwalteten Workflows verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3877-112">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="d3877-113">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d3877-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d3877-114">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d3877-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d3877-115">Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="d3877-115">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="d3877-116">Führen Sie auf der Seite **Gruppe** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d3877-116">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d3877-117">Klicken Sie auf **neu**, um eine neue Agentengruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d3877-117">To create a new agent group, click **New**.</span></span> <span data-ttu-id="d3877-118">Geben Sie in das Suchfeld **Dienst auswählen** den vollständigen oder Teil des Namens des **ApplicationServer** -Diensts ein, dem Sie die Gruppe hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="d3877-118">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group.</span></span> <span data-ttu-id="d3877-119">Klicken Sie in der Dienstliste auf den gewünschten Dienst, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3877-119">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="d3877-120">Zum Ändern einer vorhandenen Agentgruppe geben Sie den Namen der Agentgruppe ganz oder teilweise in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="d3877-120">To modify an existing agent group, type all or part of the name of the agent group in the search field.</span></span> <span data-ttu-id="d3877-121">Klicken Sie in der resultierenden Liste auf die gewünschte Gruppe, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d3877-121">In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d3877-122">Geben Sie unter **Name**einen identifizierenden Namen für die Agentengruppe ein.</span><span class="sxs-lookup"><span data-stu-id="d3877-122">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="d3877-123">Geben Sie in **Beschreibung** eine Beschreibung für die Gruppe ein.</span><span class="sxs-lookup"><span data-stu-id="d3877-123">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="d3877-124">Wählen Sie unter **Beteiligungsrichtlinie** eine der folgenden Einstellungen aus, um das Anmeldeverhalten für die Gruppe einzurichten:</span><span class="sxs-lookup"><span data-stu-id="d3877-124">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="d3877-125">Wählen Sie **Informell**, um anzugeben, dass Agents in der Gruppe sich bei der Gruppe weder an- noch abmelden müssen.</span><span class="sxs-lookup"><span data-stu-id="d3877-125">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="d3877-126">Agents werden bei der Anmeldung bei lync Server 2013 automatisch bei der Gruppe angemeldet.</span><span class="sxs-lookup"><span data-stu-id="d3877-126">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="d3877-127">klicken Sie auf **Formell**, um festzulegen, dass sich die Agents der Gruppe bei der Gruppe an- oder abmelden müssen.</span><span class="sxs-lookup"><span data-stu-id="d3877-127">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="d3877-128">Wenn Sie diese Option auswählen, klicken Agents auf ein Menüelement in lync, um Internet Explorer zu öffnen und eine Webseiten Konsole zum ein-und Ausloggen der Gruppe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d3877-128">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="d3877-129">Geben Sie im Feld **Agentwarnungszeit (Sekunden)** an, wie lange das Telefon eines Agents klingelt, bevor der Anruf an den nächsten verfügbaren Agent übergeben wird (die Standardeinstellung ist 20 Sekunden).</span><span class="sxs-lookup"><span data-stu-id="d3877-129">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d3877-130">Die Einstellung für die Agent-Warnungszeit darf 180 Sekunden nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="d3877-130">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="d3877-131">Wenn die Agent-Warnungszeit 180 Sekunden überschreitet, lehnt die Clientanwendung den Anruf ab, da der SIP-Transaktionszeitgeber seine maximale Wartezeit erreicht.</span><span class="sxs-lookup"><span data-stu-id="d3877-131">If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="d3877-132">Wählen Sie unter **Routingmethode** aus, wie Anrufe an die Agents in der Gruppe weitergeleitet werden:</span><span class="sxs-lookup"><span data-stu-id="d3877-132">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="d3877-133">Klicken Sie auf **Längster Leerlauf**, um einen neuen Anruf zuerst dem Agent anzubieten, der am längsten im Leerlauf war ( **verfügbar** oder **inaktiv** in lync Server der längste).</span><span class="sxs-lookup"><span data-stu-id="d3877-133">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="d3877-p109">Klicken Sie auf **Parallel**, um einen neuen Anruf simultan allen verfügbaren Agents anzubieten. Der Anruf wird an den ersten Agent übergeben, der diesen annimmt.</span><span class="sxs-lookup"><span data-stu-id="d3877-p109">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="d3877-136">Wenn Sie einen neuen Anruf den einzelnen Agents nacheinander anbieten möchten, klicken Sie auf **Roundrobin**.</span><span class="sxs-lookup"><span data-stu-id="d3877-136">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="d3877-137">Wenn Sie einen neuen Anruf den Agents immer in der Reihenfolge anbieten möchten, in der sie auf der Registerkarte **Agent** aufgeführt sind, klicken Sie auf **Seriell**.</span><span class="sxs-lookup"><span data-stu-id="d3877-137">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="d3877-138">Wenn Sie einen neuen Anruf für alle Agents anbieten möchten, die sich unabhängig von Ihrer aktuellen Anwesenheit bei lync Server 2013 und dem Reaktionsgruppenanwendung angemeldet haben, klicken Sie auf **Attendant**.</span><span class="sxs-lookup"><span data-stu-id="d3877-138">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="d3877-139">Lync 2010 Attendant Benutzer, die als Agents konfiguriert sind, können alle Anrufe sehen, die warten, und wartende Anrufe in beliebiger Reihenfolge beantworten.</span><span class="sxs-lookup"><span data-stu-id="d3877-139">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="d3877-140">Der Anruf wird an den ersten Agent gesendet, der ihn akzeptiert, nach dem die anderen lync 2010 Attendant Benutzer den Anruf nicht mehr sehen.</span><span class="sxs-lookup"><span data-stu-id="d3877-140">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="d3877-141">Geben Sie auf der Registerkarte **Agents** an, wie Sie Ihre Agentliste erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="d3877-141">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="d3877-142">Um eine benutzerdefinierte Liste von Agents zu verwenden, klicken Sie auf **benutzerdefinierte Gruppe von Agents definieren**, und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d3877-142">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="d3877-143">Klicken Sie zum Hinzufügen eines Benutzers zur Gruppe Agent auf **auswählen**, und geben Sie dann im Suchfeld **Agents auswählen** den vollständigen oder Teil des Namens des Benutzers ein, den Sie dieser Gruppe hinzufügen möchten, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="d3877-143">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**.</span></span> <span data-ttu-id="d3877-144">Klicken Sie in der resultierenden Liste der Agents auf den Benutzer, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3877-144">In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="d3877-145">Wenn Sie einen Benutzer aus der Gruppe Agent entfernen möchten, klicken Sie in der Liste der Agents auf den Benutzer, den Sie entfernen möchten, und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="d3877-145">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="d3877-146">Um die Reihenfolge zu ändern, in der Agents in Gruppen angeboten werden, die entweder Round Robin-Routing oder serielles Routing verwenden, klicken Sie in der Liste der Agents auf einen Benutzer, und klicken Sie dann auf den nach-oben-oder nach-unten-Pfeil.</span><span class="sxs-lookup"><span data-stu-id="d3877-146">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="d3877-147">Wenn Sie eine Exchange Server Verteilerliste als Agentgruppe verwenden möchten, klicken Sie auf **vorhandene e-Mail-Verteilerliste verwenden**, und geben Sie dann in **Verteilerlisten Adresse**die e-Mail-Adresse der Verteilerliste ein (beispielsweise NetworkSupport@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d3877-147">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="d3877-148">Wenn Sie eine E-Mail-Verteilerliste verwenden, gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="d3877-148">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="d3877-p112">Sie können für die Agentgruppe nicht mehrere Verteilerlisten auswählen. Jede Gruppe unterstützt nur eine Verteilerliste.</span><span class="sxs-lookup"><span data-stu-id="d3877-p112">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="d3877-151">Falls die Verteilerliste eine oder mehrere Verteilerlisten enthält, werden die Mitglieder der verschachtelten Verteilerlisten nicht der Agentliste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d3877-151">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="d3877-152">Wenn Serial oder Round Robin Routing ausgewählt ist, bietet der Server einen eingehenden Anruf an den entsprechenden Agent entsprechend der Routingmethode und entsprechend der Reihenfolge, in der Agents in der Verteilerliste aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="d3877-152">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="d3877-153">Wenn die Verteilerliste Benutzer enthält, für die lync Server 2010 aktiviert ist, Enterprise-VoIP jedoch nicht aktiviert ist, werden Sie als dysfunktionale Agents der Gruppe Agent hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d3877-153">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="d3877-154">Stellen Sie sicher, dass für alle Mitglieder der Verteilerliste Enterprise-VoIP für ihre Benutzerkonten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d3877-154">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="d3877-155">Wenn Sie eine e-Mail-Verteilerliste verwenden, werden ausgeblendete Mitgliedschaften oder ausgeblendete Listen möglicherweise für den Administrator oder die Benutzer der Reaktionsgruppe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3877-155">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="d3877-156">Verborgene Mitgliedschaften oder Listen werden unter den folgenden Umständen sichtbar:</span><span class="sxs-lookup"><span data-stu-id="d3877-156">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="d3877-157">Wenn eine Verteilerliste so konfiguriert wurde, dass die Mitgliedschaft ausgeblendet ist und der Reaktionsgruppen Administrator die Verteilerliste der Agentliste zuordnet, können Benutzer die Gruppe aufrufen, um herauszufinden, wer die Mitglieder sind.</span><span class="sxs-lookup"><span data-stu-id="d3877-157">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="d3877-158">Wenn eine Verteilerliste so konfiguriert wurde, dass Sie in der globalen Exchange-Adressliste ausgeblendet ist, kann der Reaktionsgruppen Administrator möglicherweise die Verteilerliste anzeigen und Sie der Liste Agent zuweisen, wenn der Reaktionsgruppen Prozess über die entsprechenden Benutzerrechte verfügt und Berechtigungen, auch wenn der Administrator nicht über die entsprechenden Benutzerrechte und-Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="d3877-158">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="d3877-159">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d3877-159">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="d3877-160">So verwenden Sie Windows PowerShell zum Erstellen oder Ändern einer Agentgruppe</span><span class="sxs-lookup"><span data-stu-id="d3877-160">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="d3877-161">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d3877-161">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="d3877-162">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d3877-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d3877-163">Verwenden Sie **New-CsRgsAgentGroup** , um eine neue Agentengruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d3877-163">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="d3877-164">Verwenden Sie zum Ändern einer vorhandenen Agentgruppe die Datei " **CsRgsAgentGroup** ".</span><span class="sxs-lookup"><span data-stu-id="d3877-164">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="d3877-165">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="d3877-165">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="d3877-166">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d3877-166">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d3877-167">Die Einstellung für die Agent-Warnungszeit darf 180 Sekunden nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="d3877-167">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="d3877-168">Wenn die Agent-Warnungszeit größer als 180 Sekunden ist, lehnt die Clientanwendung den Anruf ab, da der SIP-Transaktionszeitgeber seine maximale Wartezeit erreicht.</span><span class="sxs-lookup"><span data-stu-id="d3877-168">If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="d3877-169">Vergewissern Sie sich, dass die Agentgruppe erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d3877-169">Confirm that the agent group is created.</span></span> <span data-ttu-id="d3877-170">Ausführen</span><span class="sxs-lookup"><span data-stu-id="d3877-170">Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d3877-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3877-171">See Also</span></span>


[<span data-ttu-id="d3877-172">Löschen einer Agentengruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3877-172">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="d3877-173">Verwalten von Reaktionsgruppen-Agentgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3877-173">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="d3877-174">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="d3877-174">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="d3877-175">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="d3877-175">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="d3877-176">Gruppe-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="d3877-176">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="d3877-177">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="d3877-177">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

