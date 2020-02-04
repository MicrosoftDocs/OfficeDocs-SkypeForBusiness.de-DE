---
title: 'Lync Server 2013: Erstellen oder Ändern einer konferenzrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f3dd712b94838382f6022de888383c0f47bee6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="11c2a-102">Erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11c2a-102">Create or modify a conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11c2a-103">_**Letztes Änderungsdatum des Themas:** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="11c2a-103">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="11c2a-104">Führen Sie die folgenden Schritte aus, um eine konferenzrichtlinie auf Benutzerebene oder auf Websiteebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="11c2a-104">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="11c2a-105">Ausführliche Informationen zum Zuweisen einer Richtlinie auf Benutzerebene zu einem Benutzer finden Sie unter [Zuweisen einer konferenzrichtlinie für einzelne Benutzer in lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="11c2a-105">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="11c2a-106">Eine Liste aller verfügbaren konferenzrichtlinieneinstellungen finden Sie unter [Konferenzrichtlinien Einstellungsreferenz für lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="11c2a-106">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="11c2a-107">So erstellen Sie einen neuen Benutzer oder eine neue Website Richtlinie</span><span class="sxs-lookup"><span data-stu-id="11c2a-107">To create a new user or site policy</span></span>

1.  <span data-ttu-id="11c2a-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="11c2a-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11c2a-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="11c2a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="11c2a-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="11c2a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="11c2a-111">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und klicken Sie dann auf **konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="11c2a-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="11c2a-112">Klicken Sie auf **Neu** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="11c2a-112">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="11c2a-p103">Klicken Sie auf **Hinzufügen**, um eine Richtlinie auf Benutzerebene zu erstellen. Geben Sie im Abschnitt **Neue Konferenzrichtlinie** bei **Name** einen beschreibenden Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p103">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="11c2a-p104">Klicken Sie auf **Standortrichtlinie**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie eine Richtlinie erstellen möchten. Klicken Sie in der Liste der Standorte auf den gewünschten Standort und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="11c2a-118">Der Websitename wird zum Namen der konferenzrichtlinie und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="11c2a-118">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="11c2a-119">Geben Sie bei **Beschreibung** eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="11c2a-119">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="11c2a-p105">Geben Sie bei **Richtlinie für Organisatoren** unter **Maximale Besprechungsgröße** die Höchstzahl an Benutzern ein, die für eine Besprechung zugelassen werden sollen. Der maximale Besprechungsumfang ist standardmäßig auf 250 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p105">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="11c2a-122">Um Benutzer daran zu hindern, anonyme Benutzer zu Besprechungen einzuladen, deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen anonyme Benutzer einladen**.</span><span class="sxs-lookup"><span data-stu-id="11c2a-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="11c2a-123">Anonyme Benutzer sind Benutzer, die keine Anmeldeinformationen in den Active Directory-Domänendiensten Ihrer Organisation haben und daher nicht authentifiziert sind.</span><span class="sxs-lookup"><span data-stu-id="11c2a-123">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="11c2a-124">In der Standardeinstellung können Benutzer anonyme Benutzer zu Besprechungen einladen.</span><span class="sxs-lookup"><span data-stu-id="11c2a-124">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="11c2a-125">Führen Sie im Abschnitt **Aufzeichnung** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="11c2a-125">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="11c2a-p107">Klicken Sie auf **Keine**, um Teilnehmer an der Aufzeichnung von Besprechungen zu hindern. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p107">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
      - <span data-ttu-id="11c2a-128">Klicken Sie auf **Aufzeichnung aktivieren**, um Teilnehmern die Aufzeichnung von Besprechungen zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="11c2a-128">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="11c2a-p108">Um externen Teilnehmern das Aufzeichnen von Besprechungen zu erlauben, aktivieren Sie das Kontrollkästchen **Partnerteilnehmern und anonymen Teilnehmern das Aufzeichnen gestatten**. In der Standardeinstellung werden externe Teilnehmer an der Aufzeichnung von Besprechungen gehindert.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p108">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="11c2a-131">Führen Sie im Abschnitt **Audio/Video** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="11c2a-131">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="11c2a-132">Klicken Sie auf **Keine**, um die Verwendung von Audio und Video zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="11c2a-132">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="11c2a-133">Klicken Sie auf **IP-Audio aktivieren**, um die Verwendung von Audio, nicht jedoch von Video, zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="11c2a-133">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="11c2a-p109">Klicken Sie auf **IP-Audio/Video aktivieren**, um die Verwendung von Audio und Video zuzulassen. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p109">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>

11. <span data-ttu-id="11c2a-136">Wenn Sie die Verwendung von Audio im Abschnitt **Audio/Video** zulassen, führen Sie eine der folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="11c2a-136">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="11c2a-p110">Wenn Sie Benutzer daran hindern möchten, per Einwahl an einer Besprechung teilzunehmen, deaktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p110">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="11c2a-p111">Wenn Sie Benutzern die Einwahl in Besprechungen gestatten und nicht authentifizierten (anonymen) Benutzern die Teilnahme an Besprechungen über eine ausgehende Telefonverbindung erlauben möchten, aktivieren Sie das Kontrollkästchen **Anonyme Teilnehmer dürfen ausgehende Verbindungen herstelle**. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an und der Benutzer nimmt das Gespräch an, um an der Besprechung teilzunehmen. In der Standardeinstellung können anonyme Benutzer nicht über ausgehende Telefonverbindungen an Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p111">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="11c2a-142">Wenn Sie die Verwendung von Video in **Audio/Video**zulassen ausgewählt haben, aktivieren Sie **mehrere Videostreams zulassen** .</span><span class="sxs-lookup"><span data-stu-id="11c2a-142">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="11c2a-143">Führen Sie im Abschnitt **Datenzusammenarbeit** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="11c2a-143">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="11c2a-144">Wenn Sie keine Datenzusammenarbeit zulassen möchten, klicken Sie auf **Keine**.</span><span class="sxs-lookup"><span data-stu-id="11c2a-144">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="11c2a-p112">Zum Zulassen einer Datenzusammenarbeit klicken Sie auf **Datenzusammenarbeit aktivieren**. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p112">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>

14. <span data-ttu-id="11c2a-147">Wenn Sie die Datenzusammenarbeit im Abschnitt **Datenzusammenarbeit** zulassen, führen Sie eine der folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="11c2a-147">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="11c2a-p113">Deaktivieren Sie das Kontrollkästchen **Partnerteilnehmer und anonyme Teilnehmer dürfen Inhalte herunterladen**. In der Standardeinstellung können externe Benutzer Inhalte herunterladen.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p113">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
      - <span data-ttu-id="11c2a-p114">Deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen Dateien übertragen**, um Dateiübertragungen zu verhindern. In der Standardeinstellung können Dateien übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p114">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="11c2a-152">Deaktivieren Sie das Kontrollkästchen **Anmerkungen aktivieren**, um die Verwendung von Anmerkungen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="11c2a-152">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="11c2a-153">Wenn Sie Anmerkungen in PowerPoint-Präsentationen verwenden möchten, deaktivieren Sie die **Option PowerPoint-Anmerkungen aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="11c2a-153">To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="11c2a-154">In der Standardeinstellung sind Anmerkungen zulässig.</span><span class="sxs-lookup"><span data-stu-id="11c2a-154">By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="11c2a-p116">Deaktivieren Sie das Kontrollkästchen **Abstimmungen aktivieren**, um die Verwendung von Abstimmungen zu verhindern. In der Standardeinstellung sind Abstimmungen zulässig.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p116">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>

15. <span data-ttu-id="11c2a-157">Führen Sie im Abschnitt **Anwendungsfreigabe** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="11c2a-157">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="11c2a-158">Klicken Sie auf **Anwendungsfreigabe deaktivieren**, um die Verwendung der Anwendungsfreigabe zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="11c2a-158">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="11c2a-p117">Klicken Sie auf **Anwendungsfreigabe aktivieren**, um die Verwendung der Anwendungsfreigabe zuzulassen. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p117">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>

16. <span data-ttu-id="11c2a-161">Wenn Sie die Anwendungsfreigabe im Abschnitt **Anwendungsfreigabe** zulassen, führen Sie eine der folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="11c2a-161">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="11c2a-p118">Deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen die Steuerung übernehmen**, um Teilnehmer an der Übernahme der Steuerung für die Anwendungsfreigabe zu hindern. In der Standardeinstellung können Teilnehmer die Steuerung für die Anwendungsfreigabe übernehmen.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p118">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="11c2a-p119">Wenn Sie Besprechungsteilnehmern die Übernahme der Steuerung für die Anwendungsfreigabe ermöglichen möchten, aktivieren Sie das Kontrollkästchen **Partnerteilnehmer und anonyme Teilnehmer dürfen die Steuerung übernehmen**, um externen Benutzern die Übernahme der Steuerung für die Anwendungsfreigabe zu erlauben. In der Standardeinstellung können externe Benutzer die Steuerung für die Anwendungsfreigabe nicht übernehmen.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p119">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="11c2a-166">Führen Sie unter **Richtlinie für Teilnehmer** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="11c2a-166">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="11c2a-167">Klicken Sie auf **Anwendungs- und Desktopfreigabe deaktivieren**, um sowohl eine Anwendungsfreigabe als auch die Freigabe des Desktops zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="11c2a-167">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="11c2a-168">Klicken Sie auf **Anwendungsfreigabe aktivieren**, um eine Anwendungsfreigabe, nicht jedoch die Freigabe des Desktops zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="11c2a-168">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="11c2a-p120">Klicken Sie auf **Anwendungs- und Desktopfreigabe aktivieren**, um sowohl eine Anwendungsfreigabe als auch die Freigabe des Desktops zuzulassen. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p120">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>

18. <span data-ttu-id="11c2a-p121">Deaktivieren Sie das Kontrollkästchen **Peer-zu-Peer-Dateiübertragung aktivieren**, um Peer-zu-Peer-Dateiübertragungen zu verhindern. In der Standardeinstellung sind Peer-zu-Peer-Dateiübertragungen zulässig.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p121">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="11c2a-p122">Aktivieren Sie das Kontrollkästchen **Peer-zu-Peer-Aufzeichnung aktivieren**, um eine Peer-zu-Peer-Aufzeichnung zuzulassen. In der Standardeinstellung sind Peer-zu-Peer-Aufzeichnungen unzulässig.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p122">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="11c2a-p123">Aktivieren Sie das Kontrollkästchen **Teilnahme mit mehreren Videostreams aktivieren**, um die Teilnahme mit mehreren Videostreams zuzulassen. In der Standardeinstellung sind mehrere Videostreams zulässig.</span><span class="sxs-lookup"><span data-stu-id="11c2a-p123">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="11c2a-177">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="11c2a-177">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="11c2a-178">So ändern Sie einen vorhandenen Benutzer oder eine Website Richtlinie</span><span class="sxs-lookup"><span data-stu-id="11c2a-178">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="11c2a-179">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="11c2a-179">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11c2a-180">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="11c2a-180">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="11c2a-181">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="11c2a-181">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="11c2a-182">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und klicken Sie dann auf **konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="11c2a-182">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="11c2a-183">Klicken Sie in der Liste mit den Konferenzrichtlinien auf die Richtlinie, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="11c2a-183">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="11c2a-184">Ändern Sie im Abschnitt **Konferenzrichtlinie bearbeiten** eine beliebige der Richtlinieneinstellungen. Hiervon ausgenommen ist der Richtlinienname, dieser kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="11c2a-184">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="11c2a-185">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="11c2a-185">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

