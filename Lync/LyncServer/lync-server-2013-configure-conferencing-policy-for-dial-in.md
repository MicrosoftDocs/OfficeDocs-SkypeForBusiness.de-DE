---
title: 'Lync Server 2013: Konfigurieren von Konferenzrichtlinien für die Einwahl'
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
ms.openlocfilehash: 107c5fcf4b341c652cd4044fe47f4b650cf5adb4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="ad526-102">Konfigurieren von Konferenzrichtlinien für die Einwahl in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad526-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad526-103">_**Letztes Änderungsdatum des Themas:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="ad526-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="ad526-p101">Die Konferenzrichtlinie ist eine Benutzerkontoeinstellung, die die Konferenzmöglichkeiten für Teilnehmer festlegt. Sie können Konferenzrichtlinien auf Standort- oder Benutzerebene erstellen. Konferenzrichtlinieneinstellungen umfassen viele Aspekte der Konferenzplanung und -teilnahme. Mehrere Konferenzrichtlinieneinstellungen unterstützen Einwahlkonferenzen für Teilnehmer. Bei der Konfiguration von Einwahlkonferenzen sollten Sie sicherstellen, dass diese Felder für Ihre Organisation angemessen festgelegt sind, und sie bei Bedarf bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ad526-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="ad526-109">Überprüfen Sie die folgenden Felder in ihrer konferenzrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="ad526-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="ad526-110">**Teilnehmern erlauben, anonyme Benutzer**   einzuladen diese Einstellung ermöglicht es Besprechungsorganisatoren, anonyme (nicht authentifizierte) Teilnehmer zu Besprechungen einzuladen.</span><span class="sxs-lookup"><span data-stu-id="ad526-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="ad526-111">Diese Einstellung ist für Einwahlkonferenzen optional.</span><span class="sxs-lookup"><span data-stu-id="ad526-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="ad526-112">Diese Einstellung ist standardmäßig in der globalen Standard konferenzrichtlinie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ad526-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="ad526-113">**Aktivieren von PSTN-Einwahlkonferenzen**   mit dieser Einstellung können Benutzer am Audioteil einer Konferenz teilnehmen, indem Sie sich über das PSTN einwählen.</span><span class="sxs-lookup"><span data-stu-id="ad526-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="ad526-114">Diese Einstellung ist für Einwahlkonferenzen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ad526-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="ad526-115">Diese Einstellung ist standardmäßig in der globalen Standard konferenzrichtlinie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ad526-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="ad526-116">**Anonyme Teilnehmer erlauben, sich**   zu wählen diese Einstellung ermöglicht anonymen Benutzern, die bereits der Besprechung beigetreten sind, eine Telefonnummer zu wählen, um an dem Audioteil der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ad526-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="ad526-117">Diese Einstellung ist für Einwahlkonferenzen optional.</span><span class="sxs-lookup"><span data-stu-id="ad526-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="ad526-118">Diese Einstellung ist in der standardmäßigen globalen konferenzrichtlinie nicht standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ad526-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="ad526-119">**Teilnehmern, die für Enterprise-VoIP nicht aktiviert sind, erlauben,**   diese Einstellung zu wählen, ermöglicht es Besprechungsteilnehmern und Organisatoren, die nicht für Enterprise-VoIP aktiviert sind, eine Telefonnummer zu wählen, um am Audioteil der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ad526-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="ad526-120">Der Wähl Anruf ist basierend auf der zugewiesenen VoIP-Richtlinie des Organisators autorisiert.</span><span class="sxs-lookup"><span data-stu-id="ad526-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="ad526-121">Diese Einstellung ist in der standardmäßigen globalen konferenzrichtlinie nicht standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ad526-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="ad526-122">Der Standardwert für die Einstellung ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ad526-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad526-123">Um diese Funktion zu aktivieren, sollte einem Besprechungsorganisator, der für Enterprise-VoIP nicht aktiviert ist, eine entsprechende VoIP-Richtlinie zugewiesen werden, um die Auswahl einer von diesem Benutzer organisierten Konferenz zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="ad526-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="ad526-124">Eine VoIP-Richtlinie kann einem Benutzer zugewiesen werden, der in der lync Server-Verwaltungsshell nicht für Enterprise-VoIP aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ad526-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="ad526-125">Wenn dem Benutzer nicht explizit eine VoIP-Richtlinie zugewiesen ist, wird die Richtlinie für die Sprachausgabe verwendet, um die Auswähl Anforderung zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="ad526-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="ad526-126">Wenn keine Website VoIP-Richtlinie vorhanden ist, wird die globale VoIP-Richtlinie verwendet.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="ad526-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="ad526-127">In diesem Abschnitt wird erläutert, wie Konferenzrichtlinien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ad526-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="ad526-128">Details zum Konfigurieren aller Einstellungen, die die Teilnehmer Erfahrung in der Standard konferenzrichtlinie definieren, finden Sie unter [erstellen oder Ändern einer Sammlung von Einstellungen für die besprechungskonfiguration in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ad526-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="ad526-129">Details zum Erstellen einer konferenzrichtlinie für einen bestimmten Benutzer oder eine Benutzergruppe finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="ad526-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="ad526-130">Eine Liste aller verfügbaren konferenzrichtlinieneinstellungen finden Sie unter [Konferenzrichtlinien Einstellungsreferenz für lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="ad526-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="ad526-131">So ändern Sie die konferenzrichtlinie für die Einwahl</span><span class="sxs-lookup"><span data-stu-id="ad526-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="ad526-132">Melden Sie sich bei dem Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der Rolle **CS-ServerAdministrator** oder **CsAdministrator** an.</span><span class="sxs-lookup"><span data-stu-id="ad526-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="ad526-133">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ad526-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ad526-134">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ad526-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ad526-135">Klicken Sie in der linken Navigationsleiste auf **Konferenz**.</span><span class="sxs-lookup"><span data-stu-id="ad526-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="ad526-136">Doppelklicken Sie auf der Registerkarte **konferenzrichtlinie** auf einen Konferenzrichtlinien Namen, um das Dialogfeld **konferenzrichtlinie bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ad526-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="ad526-137">Überprüfen Sie, ob die Felder für Einwahlkonferenzen für Ihre Organisation geeignet sind, und ändern Sie bei Bedarf die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ad526-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="ad526-138">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ad526-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

