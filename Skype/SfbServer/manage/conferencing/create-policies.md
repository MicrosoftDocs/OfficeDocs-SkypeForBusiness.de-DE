---
title: Erstellen von Konferenzrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server Konferenzrichtlinien erstellen.'
ms.openlocfilehash: 6fc8145e5f7c4dc0ee4b824a92248e365df56213
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818616"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="eb6f0-103">Erstellen von Konferenzrichtlinien in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eb6f0-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="eb6f0-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie in Skype for Business Server Konferenzrichtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="eb6f0-105">Sie können Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="eb6f0-106">Erstellen von Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="eb6f0-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="eb6f0-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="eb6f0-108">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="eb6f0-109">Klicken Sie auf der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="eb6f0-110">Klicken Sie auf **Neu** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="eb6f0-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="eb6f0-p101">Klicken Sie auf **Hinzufügen**, um eine Richtlinie auf Benutzerebene zu erstellen. Geben Sie im Abschnitt **Neue Konferenzrichtlinie** bei **Name** einen beschreibenden Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p101">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="eb6f0-p102">Klicken Sie auf **Standortrichtlinie**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie eine Richtlinie erstellen möchten. Klicken Sie in der Liste der Standorte auf den gewünschten Standort und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p102">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="eb6f0-116">Der Standortname wird als Name der Konferenzrichtlinie übernommen und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="eb6f0-117">Geben Sie bei **Beschreibung** eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="eb6f0-p103">Geben Sie bei **Richtlinie für Organisatoren** unter **Maximale Besprechungsgröße** die Höchstzahl an Benutzern ein, die für eine Besprechung zugelassen werden sollen. Der maximale Besprechungsumfang ist standardmäßig auf 250 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="eb6f0-120">Um Benutzer daran zu hindern, anonyme Benutzer zu Besprechungen einzuladen, deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen anonyme Benutzer einladen**.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="eb6f0-121">Anonyme Benutzer sind Benutzer, die keine Anmeldeinformationen in den Active Directory-Domänendiensten Ihrer Organisation haben und daher nicht authentifiziert sind.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="eb6f0-122">In der Standardeinstellung können Benutzer anonyme Benutzer zu Besprechungen einladen.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="eb6f0-123">Führen Sie im Abschnitt **Aufzeichnung** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="eb6f0-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="eb6f0-p105">Klicken Sie auf **Keine**, um Teilnehmer an der Aufzeichnung von Besprechungen zu hindern. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="eb6f0-126">Klicken Sie auf **Aufzeichnung aktivieren**, um Teilnehmern die Aufzeichnung von Besprechungen zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="eb6f0-p106">Um externen Teilnehmern das Aufzeichnen von Besprechungen zu erlauben, aktivieren Sie das Kontrollkästchen **Partnerteilnehmern und anonymen Teilnehmern das Aufzeichnen gestatten**. In der Standardeinstellung werden externe Teilnehmer an der Aufzeichnung von Besprechungen gehindert.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="eb6f0-129">Führen Sie im Abschnitt **Audio/Video** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="eb6f0-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="eb6f0-130">Klicken Sie auf **Keine**, um die Verwendung von Audio und Video zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="eb6f0-131">Klicken Sie auf **IP-Audio aktivieren**, um die Verwendung von Audio, nicht jedoch von Video, zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="eb6f0-p107">Klicken Sie auf **IP-Audio/Video aktivieren**, um die Verwendung von Audio und Video zuzulassen. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="eb6f0-134">Wenn Sie die Verwendung von Audio im Abschnitt **Audio/Video** zulassen, führen Sie eine der folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="eb6f0-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="eb6f0-p108">Wenn Sie Benutzer daran hindern möchten, per Einwahl an einer Besprechung teilzunehmen, deaktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="eb6f0-p109">Wenn Sie Benutzern die Einwahl in Besprechungen gestatten und nicht authentifizierten (anonymen) Benutzern die Teilnahme an Besprechungen über eine ausgehende Telefonverbindung erlauben möchten, aktivieren Sie das Kontrollkästchen **Anonyme Teilnehmer dürfen ausgehende Verbindungen herstelle**. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an und der Benutzer nimmt das Gespräch an, um an der Besprechung teilzunehmen. In der Standardeinstellung können anonyme Benutzer nicht über ausgehende Telefonverbindungen an Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="eb6f0-140">Wenn Sie die Verwendung von Video im Abschnitt **Audio/Video** zulassen möchten, aktivieren Sie das Kontrollkästchen **Mehrere Videostreams zulassen**.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="eb6f0-141">Führen Sie im Abschnitt **Datenzusammenarbeit** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="eb6f0-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="eb6f0-142">Wenn Sie keine Datenzusammenarbeit zulassen möchten, klicken Sie auf **Keine**.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="eb6f0-p110">Zum Zulassen einer Datenzusammenarbeit klicken Sie auf **Datenzusammenarbeit aktivieren**. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="eb6f0-145">Wenn Sie die Datenzusammenarbeit im Abschnitt **Datenzusammenarbeit** zulassen, führen Sie eine der folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="eb6f0-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="eb6f0-p111">Deaktivieren Sie das Kontrollkästchen **Partnerteilnehmer und anonyme Teilnehmer dürfen Inhalte herunterladen**. In der Standardeinstellung können externe Benutzer Inhalte herunterladen.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="eb6f0-p112">Deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen Dateien übertragen**, um Dateiübertragungen zu verhindern. In der Standardeinstellung können Dateien übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="eb6f0-p113">Deaktivieren Sie das Kontrollkästchen **Anmerkungen aktivieren**, um die Verwendung von Anmerkungen zu verhindern. Deaktivieren Sie das Kontrollkästchen **PowerPoint-Anmerkungen aktivieren**, um die Verwendung von Anmerkungen in freigegebenen PowerPoint-Präsentationen zu verhindern. In der Standardeinstellung sind Anmerkungen zulässig.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p113">To prevent the use of annotations, clear the **Enable annotations** check box. To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**. By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="eb6f0-p114">Deaktivieren Sie das Kontrollkästchen **Abstimmungen aktivieren**, um die Verwendung von Abstimmungen zu verhindern. In der Standardeinstellung sind Abstimmungen zulässig.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="eb6f0-155">Führen Sie im Abschnitt **Anwendungsfreigabe** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="eb6f0-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="eb6f0-156">Klicken Sie auf **Anwendungsfreigabe deaktivieren**, um die Verwendung der Anwendungsfreigabe zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="eb6f0-p115">Klicken Sie auf **Anwendungsfreigabe aktivieren**, um die Verwendung der Anwendungsfreigabe zuzulassen. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="eb6f0-159">Wenn Sie die Anwendungsfreigabe im Abschnitt **Anwendungsfreigabe** zulassen, führen Sie eine der folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="eb6f0-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="eb6f0-p116">Deaktivieren Sie das Kontrollkästchen **Teilnehmer dürfen die Steuerung übernehmen**, um Teilnehmer an der Übernahme der Steuerung für die Anwendungsfreigabe zu hindern. In der Standardeinstellung können Teilnehmer die Steuerung für die Anwendungsfreigabe übernehmen.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="eb6f0-p117">Wenn Sie Besprechungsteilnehmern die Übernahme der Steuerung für die Anwendungsfreigabe ermöglichen möchten, aktivieren Sie das Kontrollkästchen **Partnerteilnehmer und anonyme Teilnehmer dürfen die Steuerung übernehmen**, um externen Benutzern die Übernahme der Steuerung für die Anwendungsfreigabe zu erlauben. In der Standardeinstellung können externe Benutzer die Steuerung für die Anwendungsfreigabe nicht übernehmen.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="eb6f0-164">Führen Sie unter **Richtlinie für Teilnehmer** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="eb6f0-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="eb6f0-165">Klicken Sie auf **Anwendungs- und Desktopfreigabe deaktivieren**, um sowohl eine Anwendungsfreigabe als auch die Freigabe des Desktops zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="eb6f0-166">Klicken Sie auf **Anwendungsfreigabe aktivieren**, um eine Anwendungsfreigabe, nicht jedoch die Freigabe des Desktops zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="eb6f0-p118">Klicken Sie auf **Anwendungs- und Desktopfreigabe aktivieren**, um sowohl eine Anwendungsfreigabe als auch die Freigabe des Desktops zuzulassen. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="eb6f0-p119">Deaktivieren Sie das Kontrollkästchen **Peer-zu-Peer-Dateiübertragung aktivieren**, um Peer-zu-Peer-Dateiübertragungen zu verhindern. In der Standardeinstellung sind Peer-zu-Peer-Dateiübertragungen zulässig.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="eb6f0-p120">Aktivieren Sie das Kontrollkästchen **Peer-zu-Peer-Aufzeichnung aktivieren**, um eine Peer-zu-Peer-Aufzeichnung zuzulassen. In der Standardeinstellung sind Peer-zu-Peer-Aufzeichnungen unzulässig.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="eb6f0-p121">Aktivieren Sie das Kontrollkästchen **Teilnahme mit mehreren Videostreams aktivieren**, um die Teilnahme mit mehreren Videostreams zuzulassen. In der Standardeinstellung sind mehrere Videostreams zulässig.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-p121">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="eb6f0-175">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="eb6f0-176">Erstellen von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="eb6f0-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="eb6f0-177">Verwenden Sie das Cmdlet **New-CsConferencingPolicy**, um Konferenzrichtlinien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="eb6f0-178">Im folgenden Beispiel wird eine neue konferenzrichtlinie mit dem Identitäts SalesConferencingPolicy erstellt.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="eb6f0-179">Diese Richtlinie verwendet alle Standardwerte für eine Konferenzrichtlinie mit einer Ausnahme: MaxMeetingSize.</span><span class="sxs-lookup"><span data-stu-id="eb6f0-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="eb6f0-180">In diesem Beispiel wird die maximale Besprechungsgröße statt auf den Standardwert 250 auf 50 festgelegt:</span><span class="sxs-lookup"><span data-stu-id="eb6f0-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="eb6f0-181">Weitere Informationen, einschließlich einer vollständigen Syntax Beschreibung und einer Liste von Parametern, finden Sie unter [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="eb6f0-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

