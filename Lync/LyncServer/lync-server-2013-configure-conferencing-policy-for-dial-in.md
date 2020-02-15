---
title: 'Lync Server 2013: Konfigurieren der konferenzrichtlinie für die Einwahl'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56faf9cb55312beec0714eb84757d92989b1b3ad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="5a60e-102">Konfigurieren von Konferenzrichtlinien für die Einwahl in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a60e-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a60e-103">_**Letztes Änderungsstand des Themas:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="5a60e-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="5a60e-p101">Die Konferenzrichtlinie ist eine Benutzerkontoeinstellung, die die Konferenzmöglichkeiten für Teilnehmer festlegt. Sie können Konferenzrichtlinien auf Standort- oder Benutzerebene erstellen. Konferenzrichtlinieneinstellungen umfassen viele Aspekte der Konferenzplanung und -teilnahme. Mehrere Konferenzrichtlinieneinstellungen unterstützen Einwahlkonferenzen für Teilnehmer. Bei der Konfiguration von Einwahlkonferenzen sollten Sie sicherstellen, dass diese Felder für Ihre Organisation angemessen festgelegt sind, und sie bei Bedarf bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a60e-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="5a60e-109">Überprüfen Sie in Ihrer Konferenzrichtlinie die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="5a60e-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="5a60e-110">**Teilnehmer dürfen anonyme Benutzer**   einladen mit dieser Einstellung können Besprechungsorganisatoren anonyme (nicht authentifizierte) Teilnehmer zu Besprechungen einladen.</span><span class="sxs-lookup"><span data-stu-id="5a60e-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="5a60e-111">Diese Einstellung ist für Einwahlkonferenzen optional.</span><span class="sxs-lookup"><span data-stu-id="5a60e-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="5a60e-112">Diese Einstellung ist in der globalen Standardkonferenzrichtlinie standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="5a60e-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="5a60e-113">**PSTN-Einwahlkonferenzen**   aktivieren mit dieser Einstellung können Benutzer am Audioteil einer Konferenz teilnehmen, indem Sie sich über das PSTN einwählen.</span><span class="sxs-lookup"><span data-stu-id="5a60e-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="5a60e-114">Diese Einstellung ist für Einwahlkonferenzen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5a60e-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="5a60e-115">Diese Einstellung ist in der globalen Standardkonferenzrichtlinie standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="5a60e-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="5a60e-116">**Anonymen Teilnehmern**   das auswählen erlauben diese Einstellung ermöglicht es anonymen Benutzern, die sich bereits mit der Besprechung verbunden haben,, eine Telefonnummer für die Teilnahme am Audioteil der Konferenz zu wählen.</span><span class="sxs-lookup"><span data-stu-id="5a60e-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="5a60e-117">Diese Einstellung ist für Einwahlkonferenzen optional.</span><span class="sxs-lookup"><span data-stu-id="5a60e-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="5a60e-118">Diese Einstellung ist in der globalen Standardkonferenzrichtlinie standardmäßig nicht ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="5a60e-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="5a60e-119">**Teilnehmern, die nicht für Enterprise-VoIP aktiviert sind,**   das auswählen erlauben mit dieser Einstellung können Besprechungsteilnehmer und Organisatoren, die nicht für Enterprise-VoIP aktiviert sind, eine Telefonnummer für die Teilnahme am Audioteil der Konferenz wählen.</span><span class="sxs-lookup"><span data-stu-id="5a60e-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="5a60e-120">Der ausgehende Anruf wird auf der Grundlage der dem Organisator zugewiesenen VoIP-Richtlinie autorisiert.</span><span class="sxs-lookup"><span data-stu-id="5a60e-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="5a60e-121">Diese Einstellung ist in der globalen Standardkonferenzrichtlinie standardmäßig nicht ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="5a60e-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="5a60e-122">Diese Einstellung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5a60e-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a60e-123">Um diese Funktion zu aktivieren, sollte einem Besprechungsorganisator, der nicht für Enterprise-VoIP aktiviert ist, eine entsprechende VoIP-Richtlinie zugewiesen sein, um alle Auswahlen einer von diesem Benutzer organisierten Konferenz zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="5a60e-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="5a60e-124">Eine VoIP-Richtlinie kann einem Benutzer zugewiesen werden, der nicht für Enterprise-VoIP aus dem lync Server-Verwaltungsshell aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5a60e-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="5a60e-125">Wenn dem Benutzer keine VoIP-Richtlinie explizit zugewiesen wurde, wird die VoIP-Richtlinie verwendet, um die Auswähl Anforderung zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="5a60e-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="5a60e-126">Wenn keine VoIP-Richtlinie für Websites vorhanden ist, wird die globale VoIP-Richtlinie verwendet.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="5a60e-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="5a60e-127">Das in diesem Abschnitt beschriebene Verfahren erläutert, wie die Konferenzrichtlinie geändert wird.</span><span class="sxs-lookup"><span data-stu-id="5a60e-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="5a60e-128">Ausführliche Informationen zum Konfigurieren aller Einstellungen, die die Teilnehmer Erfahrung in der Standard konferenzrichtlinie definieren, finden Sie unter [erstellen oder Ändern einer Sammlung von Besprechungs Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="5a60e-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="5a60e-129">Ausführliche Informationen zum Erstellen einer konferenzrichtlinie für einen bestimmten Benutzer oder eine bestimmte Gruppe von Benutzern finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="5a60e-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="5a60e-130">Eine Liste aller verfügbaren konferenzrichtlinieneinstellungen finden Sie unter [Conferencing Policy Settings Reference for lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="5a60e-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="5a60e-131">So ändern Sie die Konferenzrichtlinie für die Einwahl</span><span class="sxs-lookup"><span data-stu-id="5a60e-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="5a60e-132">Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.</span><span class="sxs-lookup"><span data-stu-id="5a60e-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="5a60e-133">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5a60e-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5a60e-134">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5a60e-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5a60e-135">Klicken Sie in der linken Navigationsleiste auf **Konferenz**.</span><span class="sxs-lookup"><span data-stu-id="5a60e-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="5a60e-136">Doppelklicken Sie auf der Registerkarte **Konferenzrichtlinie** auf den Namen einer Konferenzrichtlinie, um das Dialogfeld **Konferenzrichtlinie bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5a60e-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="5a60e-137">Stellen Sie sicher, dass die Felder für Einwahlkonferenzen für Ihre Organisation angemessen eingestellt sind, und ändern Sie die Einstellungen bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="5a60e-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="5a60e-138">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="5a60e-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

