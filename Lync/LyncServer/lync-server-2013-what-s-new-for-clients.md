---
title: 'Lync Server 2013: Neuerungen für Clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9035ace6a3cfbb65c8effb786bcd6a7568f92252
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="1d908-102">Neuerungen für Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d908-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d908-103">_**Letztes Änderungsstand des Themas:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="1d908-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="1d908-104">Microsoft lync 2013 verfügt über eine neu gestaltete Benutzeroberfläche und wichtige neue Features.</span><span class="sxs-lookup"><span data-stu-id="1d908-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="1d908-105">Für Administratoren ist der Client jetzt im Office-Setupprogramm enthalten und bietet einen optimierten Ansatz für die Bereitstellung von Office und das Anpassen von Clients in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="1d908-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d908-106">Eine illustrierte Ansicht der lync 2013 Updates der Benutzeroberfläche finden Sie unter "What es New in lync 2013 <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>" unter.</span><span class="sxs-lookup"><span data-stu-id="1d908-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="1d908-107">Integration in das Setup von Office</span><span class="sxs-lookup"><span data-stu-id="1d908-107">Integration with Office Setup</span></span>

<span data-ttu-id="1d908-108">Der lync 2013-Client und das Online-Besprechungs-Add-in für lync 2013, das die Besprechungsverwaltung über den Outlook-Client für Messaging und Zusammenarbeit unterstützt, sind jetzt sowohl im Office 2013-Setup Programm enthalten.</span><span class="sxs-lookup"><span data-stu-id="1d908-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="1d908-109">In früheren Versionen von lync und Office Communicator konnten Sie die Windows Installer-Eigenschaften verwenden, um die Office-Installation anzupassen und zu steuern.</span><span class="sxs-lookup"><span data-stu-id="1d908-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="1d908-110">Da lync 2013 in Office Setup integriert ist, können Sie die folgenden Methoden zum Anpassen lync 2013 Setups verwenden:</span><span class="sxs-lookup"><span data-stu-id="1d908-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="1d908-111">Verwenden des Office-Anpassungstools</span><span class="sxs-lookup"><span data-stu-id="1d908-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="1d908-112">Verwenden der Datei "config.xml" zur Durchführung von Installationsaufgaben</span><span class="sxs-lookup"><span data-stu-id="1d908-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="1d908-113">Verwenden der Befehlszeilenoptionen für das Setup</span><span class="sxs-lookup"><span data-stu-id="1d908-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d908-114">Mit dem Setupprogramm für lync 2013 werden frühere Versionen von lync oder Office Communicator nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="1d908-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="1d908-115">Der lync 2013 Client wird nebeneinander mit anderen lync-oder Office Communicator-Clients installiert.</span><span class="sxs-lookup"><span data-stu-id="1d908-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="1d908-116">Ausführliche Informationen finden Sie unter [Deploying lync Clients in lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="1d908-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="1d908-117">Bereitstellung von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1d908-117">Group Policy Deployment</span></span>

<span data-ttu-id="1d908-118">Da lync 2013 jetzt in Office Setup enthalten ist, wurde die Methode zum Bereitstellen von lync-Gruppenrichtlinieneinstellungen geändert.</span><span class="sxs-lookup"><span data-stu-id="1d908-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="1d908-119">In früheren Versionen von lync und Office Communicator konnten Sie die Communicator. adm zum Definieren von Gruppenrichtlinieneinstellungen verwenden, während Sie in lync 2013 jetzt die administrativen Vorlagen für lync ADMX und ADML verwenden können, die zusammen mit der Office-Gruppenrichtlinie bereitgestellt werden. Administrative Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="1d908-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="1d908-120">Ausführliche Informationen finden Sie unter [Gruppenrichtlinieneinstellungen für lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="1d908-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="1d908-121">Updates für das Planungs-Add-In von Outlook</span><span class="sxs-lookup"><span data-stu-id="1d908-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="1d908-122">Das Online-Besprechungs-Add-in für lync 2013 umfasst die Anpassung von Besprechungseinladungen und neue Besprechungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="1d908-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="1d908-123">Administratoren können die Besprechungseinladungen ihrer Organisation durch Hinzufügen eines Logos, einer Support-URL, einer URL für den rechtlichen Haftungsausschluss oder eines benutzerdefinierten Fußzeilentexts anpassen.</span><span class="sxs-lookup"><span data-stu-id="1d908-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="1d908-124">Ausführliche Informationen finden Sie unter [Anpassen des Online Besprechungs-Add-Ins in lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="1d908-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="1d908-125">Neue Teilnehmersteuerelemente ermöglichen Besprechungsorganisatoren das Planen von Konferenzen, in denen die Audio- und Videofunktionen von Teilnehmern standardmäßig stummgeschaltet sind.</span><span class="sxs-lookup"><span data-stu-id="1d908-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="1d908-126">Virtual Desktop Infrastructure-Plug-In</span><span class="sxs-lookup"><span data-stu-id="1d908-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="1d908-127">Der lync 2013-Client unterstützt jetzt Audio und Video in einer VDI-Umgebung (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="1d908-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="1d908-128">Ein Benutzer kann ein Audio- oder Videogerät (z. B. ein Headset oder eine Kamera) mit dem lokalen Computer verbinden (z. B. einem Thin-Client oder einem Computer mit neuem Zweck).</span><span class="sxs-lookup"><span data-stu-id="1d908-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="1d908-129">Der Benutzer kann eine Verbindung mit dem virtuellen Computer herstellen, sich beim lync 2013 Client anmelden, der auf dem virtuellen Computer aktiv ist, und an der Echtzeitübertragung von Audio und Video teilnehmen, als ob der Client lokal betrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1d908-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="1d908-130">Die folgenden Features werden in einer virtuellen Desktopumgebung unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1d908-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="1d908-131">Geräteintegration für Audio- und Videofunktionen, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="1d908-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="1d908-132">Anrufsteuerung mit dem Gerät</span><span class="sxs-lookup"><span data-stu-id="1d908-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="1d908-133">Anwesenheitsintegration auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="1d908-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="1d908-134">Unterstützung mehrerer HIDs (Human Interface Device, Eingabegeräte)</span><span class="sxs-lookup"><span data-stu-id="1d908-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="1d908-135">Unterstützung von Standort- und Notrufdiensten</span><span class="sxs-lookup"><span data-stu-id="1d908-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="1d908-136">Unterstützung für alle lync-Modalitäten, einschließlich Chat, Audio, Video, Anwendungsfreigabe, Desktopfreigabe, PowerPoint-Freigabe, Whiteboard und Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="1d908-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="1d908-137">Audio- und Videounterstützung bei Einzel- und Konferenzanrufen</span><span class="sxs-lookup"><span data-stu-id="1d908-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="1d908-138">Informationen zum Bereitstellen des VDI-Plug-Ins finden Sie unter [Deploying the lync VDI Plug-in in lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="1d908-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="1d908-139">Videoerweiterungen</span><span class="sxs-lookup"><span data-stu-id="1d908-139">Video Enhancements</span></span>

<span data-ttu-id="1d908-140">Die Videoerfahrung für Konferenzteilnehmer wurde durch die Einführung neuer Funktionen signifikant verbessert.</span><span class="sxs-lookup"><span data-stu-id="1d908-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="1d908-141">Dank Gesichtserkennung und des intelligenten Framings kann sich das Videofenster des Teilnehmers an Bewegungen anpassen, und der Benutzer bleibt im Mittelpunkt.</span><span class="sxs-lookup"><span data-stu-id="1d908-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="1d908-p107">High-Definition-Videos werden jetzt in Anrufen mit zwei Teilnehmern und in Konferenzen mit mehreren Teilnehmern mit einer Auflösung bis HD 1080P unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1d908-p107">High-definition video is now supported in two-party calls and multiparty conferences. Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="1d908-144">Teilnehmer können auch unterschiedlichen Besprechungslayouts auswählen: Galerienansicht (zeigt Bilder oder Videos aller Teilnehmer an), Sprecheransicht (zeigt den Besprechungsinhalt und nur das Bild oder Video des aktuellen Sprechers an), Präsentationsansicht (zeigt nur den Besprechungsinhalt an), Kompaktansicht (zeigt nur die Besprechungssteuerelemente an).</span><span class="sxs-lookup"><span data-stu-id="1d908-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="1d908-p108">In der neuen Galerieansicht können Benutzer mehrere Videofeeds gleichzeitig anzeigen. Bei Konferenzen mit mehr als fünf Teilnehmern, werden nur die Videofeeds der aktivsten Teilnehmer in der obersten Zeile angezeigt, die anderen Teilnehmer werden jeweils mit einem Bild angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d908-p108">With the new Gallery feature, participants can see multiple video feeds at the same time. If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="1d908-147">Teilnehmer können Videos auch verankern, sodass einer oder mehrere Videofeeds die ganze Zeit über angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1d908-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="1d908-148">Referenten können mithilfe einer Spotlightfunktion den Videofeed einer bestimmten Version auswählen, sodass alle Teilnehmer in der Besprechung nur diesen Teilnehmer sehen.</span><span class="sxs-lookup"><span data-stu-id="1d908-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="1d908-149">Chatroomintegration</span><span class="sxs-lookup"><span data-stu-id="1d908-149">Chat Room Integration</span></span>

<span data-ttu-id="1d908-150">Lync 2013 integriert nun die Funktionen, die zuvor von lync 2010 Gruppen Chat bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="1d908-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="1d908-151">Ein separater Client für Gruppenchats ist nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1d908-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="1d908-152">In lync 2013 können Benutzer nach Chatrooms suchen, Ihren Kontakten Chatrooms hinzufügen, Chatroom-Aktivitäten überwachen sowie Nachrichten lesen und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="1d908-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="1d908-153">Benutzer können Themenfeeds erstellen, um benachrichtigt zu werden, wenn in einem ihrer Chatrooms ein Beitrag mit bestimmten Stichwörtern veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="1d908-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="1d908-154">Die neue Seite mit Optionen für den **Beständigen Chat** ermöglicht Benutzern das Festlegen von Benachrichtigungen und akustischen Signalen, wenn andere Benutzer Nachrichten in ihren Chatrooms veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="1d908-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="1d908-155">Lync Web App Updates</span><span class="sxs-lookup"><span data-stu-id="1d908-155">Lync Web App Updates</span></span>

<span data-ttu-id="1d908-156">Lync Web App ist der webbasierte Konferenz Client für lync Server 2013-Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="1d908-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="1d908-157">In dieser Version bietet das Hinzufügen von Computer-Audio-und-Video zu lync Web App eine umfassende Besprechungs Erfahrung für alle Benutzer, die keinen lync-Client lokal installiert haben.</span><span class="sxs-lookup"><span data-stu-id="1d908-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="1d908-158">Besprechungsteilnehmer können auf alle Funktionen für die Zusammenarbeit und Freigabe sowie auf alle Besprechungssteuerelemente des Referenten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1d908-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="1d908-159">Wenn ein Benutzer versucht, einer Besprechung beizutreten, jedoch keinen lokal installierten Client hat, wird lync Web App geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1d908-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="1d908-160">Wenn Sie zusätzliche Optionen für die Teilnahme an der Besprechung zulassen möchten, können Sie die Seite für den besprechungsbeitritt konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren der Seite für den besprechungsbeitritt in lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1d908-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="1d908-161">Aufgrund der Verbesserungen an lync Web App ist eine aktualisierte Version von Attendee für lync Server 2013 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1d908-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="1d908-162">Lync Web App ist der bevorzugte Client für Teilnehmer außerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="1d908-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="1d908-163">Es ist keine lokale Clientinstallation erforderlich, auch wenn für Audio-, Video-und Freigabefunktionen ein Plug-in bei der ersten Verwendung installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="1d908-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="1d908-164">Lync 2013 für Updates für mobile Clients</span><span class="sxs-lookup"><span data-stu-id="1d908-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="1d908-165">Neben erweiterten Anwesenheitsinformationen, Kontakten und Chatfunktionen bieten lync 2013 Mobile Clients jetzt sprach-und Videoanrufe über das Internet und Mobilfunkdaten Verbindungen an.</span><span class="sxs-lookup"><span data-stu-id="1d908-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="1d908-166">Mit einem einzigen Klick auf den Besprechungslink in einem Kalenderelement können mobile Benutzer an lync-sprach-und-Videobesprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="1d908-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="1d908-167">Weitere Informationen zu lync 2013 mobilen Clients finden Sie unter [Planning for Mobile Clients in lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="1d908-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="1d908-168">Lync 2013 Updates der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="1d908-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="1d908-169">Updates für die Eingabehilfen</span><span class="sxs-lookup"><span data-stu-id="1d908-169">Accessibility Updates</span></span>

<span data-ttu-id="1d908-170">Lync 2013 enthält mehrere neue Barrierefreiheitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="1d908-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="1d908-171">Lync 2013 unterstützt eine hohe dpi-Auflösung, sodass Benutzer Text und Grafiken für 125% und 150% dots per inch skalieren können.</span><span class="sxs-lookup"><span data-stu-id="1d908-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="1d908-172">Lync bietet Unterstützung mit hohem Kontrast, sodass die Benutzeroberfläche bei Verwendung von Designs mit hohem Kontrast in Windows voll funktionsfähig bleibt.</span><span class="sxs-lookup"><span data-stu-id="1d908-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="1d908-173">Lync bietet mehr als 100 Tastenkombinationen, damit Benutzer ohne Maus auf wichtige Funktionen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1d908-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="1d908-174">Beispielsweise kann ein Anruf durch Drücken der ALT-TASTE+C angenommen werden, und mit ALT-TASTE+I können Anrufe ignoriert werden, dabei ist es nicht erforderlich die TAB-TASTE zu betätigen oder den Fokus zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1d908-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="1d908-175">Mit der ALT-TASTE+Q wird ein Anruf beendet, mit der STRG-TASTE+N wird OneNote gestartet, und die ALT-TASTE+T öffnet das Menü "Extras".</span><span class="sxs-lookup"><span data-stu-id="1d908-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="1d908-176">Umfangreiche Sprachausgabe Unterstützung in lync 2013 stellt sicher, dass alle Benachrichtigungen, eingehenden Anforderungen und Chatnachrichten laut gelesen werden, wenn eine Sprachausgabe aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1d908-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="1d908-177">Anwesenheit bei Freigabe</span><span class="sxs-lookup"><span data-stu-id="1d908-177">Presence While Sharing</span></span>

<span data-ttu-id="1d908-178">Wenn lync erkennt, dass ein Benutzer freigegeben wird, weist lync dem Benutzer automatisch einen Präsentations Anwesenheitsstatus zu.</span><span class="sxs-lookup"><span data-stu-id="1d908-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="1d908-179">Dieser Status blockiert die gesamte eingehende Kommunikation, es sei denn, dem Absender wird der Status "Beschäftigt" zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1d908-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="1d908-180">Wenn der Benutzer das Freigabefeature vollständig auf einem sekundären Monitor verwendet, weist lync keinen Präsentations Anwesenheitsstatus zu.</span><span class="sxs-lookup"><span data-stu-id="1d908-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="1d908-181">Updates für das Fenster "Unterhaltung"</span><span class="sxs-lookup"><span data-stu-id="1d908-181">Conversation Window Updates</span></span>

<span data-ttu-id="1d908-182">Das neu gestaltete Fenster "Unterhaltung" bietet jetzt noch schnelleren Zugriff auf wichtige Funktionen.</span><span class="sxs-lookup"><span data-stu-id="1d908-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="1d908-p116">Dank der neuen Unterhaltungsfunktion mit Registerkarten können Benutzer jetzt alle Sofortnachrichten und Chatrooms in einem Unterhaltungsfenster nutzen. Die Registerkarten werden an der linken Seite des Fensters "Unterhaltung" angezeigt und ermöglichen eine schnelle und bequeme Navigation zwischen allen aktiven Unterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="1d908-p116">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window. The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="1d908-p117">Benutzer können eine individuelle Unterhaltung in ein separates Fenster ausgliedern und anschließend die Größe dieses Fensters anpassen. Das Fenster kann außerdem wieder in das Fenster "Unterhaltung" eingegliedert werden.</span><span class="sxs-lookup"><span data-stu-id="1d908-p117">Users can pop out an individual conversation into a separate window, and then resize the window. They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="1d908-187">Lync 2013 öffnet die Unterhaltungen eines Benutzers erneut, wenn der Benutzer sich abmeldet und sich an lync anmeldet.</span><span class="sxs-lookup"><span data-stu-id="1d908-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="1d908-188">Benutzer können jeder Unterhaltung umgehend Sofortnachrichten, Videos, Programmfreigaben, Desktopfreigaben oder Webkonferenztools (Whiteboards, Besprechungsnotizen, Notizbuchfreigaben und Anlagen) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1d908-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="1d908-189">In einer Besprechung, in der Videos oder Inhalte geteilt werden, können Benutzer die Videos oder Inhalte in ein separates Fenster ausgliedern und die Größe dieses Fensters anpassen.</span><span class="sxs-lookup"><span data-stu-id="1d908-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="1d908-190">Updates des lync-Hauptfensters</span><span class="sxs-lookup"><span data-stu-id="1d908-190">Lync Main Window Updates</span></span>

<span data-ttu-id="1d908-191">Der neue und modernisierte Look ermöglicht auch weiterhin den Zugriff auf bekannte Funktionen wie das Feld **Notiz eingeben**, die Statusauswahl und die Auswahl **Standort festlegen**.</span><span class="sxs-lookup"><span data-stu-id="1d908-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="1d908-192">Wenn Chatrooms aktiviert sind, wird den Benutzern auf der lync-Hauptseite ein neues Symbol für **Chatrooms** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d908-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="1d908-193">Über das Symbol **Chatrooms** können Benutzer rasch auf ihre Chatrooms und Filter zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1d908-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="1d908-194">Durch Klicken auf die Ansichtssymbole können Benutzer zwischen der Ansicht **Kontakte**, der Ansicht **Chatrooms**, der Ansicht **Konversationen** und der Ansicht **Telefon** wechseln.</span><span class="sxs-lookup"><span data-stu-id="1d908-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="1d908-195">Wenn Benutzer zu Exchange 2013 migriert wurden, können Sie ein Bild mit hoher Auflösung hochladen.</span><span class="sxs-lookup"><span data-stu-id="1d908-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="1d908-196">Updates für die Ansicht "Kontakte" und die Visitenkarte</span><span class="sxs-lookup"><span data-stu-id="1d908-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="1d908-197">Lync 2013 bietet Benutzern unterschiedliche Möglichkeiten zum Anzeigen von Kontakten und Gruppen in der **Kontakt** Ansicht.</span><span class="sxs-lookup"><span data-stu-id="1d908-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="1d908-198">Nachdem die lync-Kontakte von Benutzern zu Exchange 2013 migriert wurden, können die Benutzer mit dem neuen einheitlichen Kontaktspeicher über lync 2013, Outlook oder Outlook Web App auf Ihre Kontakte zugreifen und diese verwalten, und Ihre Favoriten bleiben synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="1d908-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="1d908-199">Wenn ein Benutzer beispielsweise einen Kontakt zu den Favoriten in Outlook hinzufügt, wird der Kontakt in der Gruppe Favoriten in lync 2013 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d908-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="1d908-200">Wenn Sie den XMPP-Proxy und das XMPP-Gateway hinzugefügt und konfiguriert haben, können Benutzer Kontakte von XMPP-basierten Partnern für Sofortnachrichten- und Präsenzfunktionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1d908-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="1d908-201">Mit der neuen Funktion **Kontakt außerhalb der Organisation hinzufügen** können Benutzer auf einfache Weise andere Benutzer außerhalb ihrer Organisation hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1d908-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="1d908-202">Die neue Funktion **Favoriten** ermöglicht Benutzern das Erstellen einer Liste von Personen, die am häufigsten von Benutzern kontaktiert werden, um schnell darauf zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="1d908-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="1d908-p120">Auf der neuen Optionsseite **Kontaktliste** können Benutzer angeben, wie Benutzer sortiert und angezeigt werden sollen. Zur Auswahl stehen eine erweiterte zweizeilige Ansicht mit Kontaktbildern oder eine kompakte einzeilige Ansicht. Die Liste kann alphabetisch oder nach Verfügbarkeit sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="1d908-p120">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts. Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view. Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="1d908-206">Updates für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="1d908-206">Conferencing Updates</span></span>

<span data-ttu-id="1d908-207">Lync 2013 bietet mehrere Verbesserungen an den Konferenzfunktionen.</span><span class="sxs-lookup"><span data-stu-id="1d908-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="1d908-p121">In Abhängigkeit vom Besprechungstyp können Benutzer jetzt das Publikum stummschalten und die Videofreigabe zulassen oder blockieren, wenn sie die Besprechung planen. Diese Optionen sind auf der Seite **Besprechungsoptionen** verfügbar und sollten bei großen Besprechungen ab 20 Personen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d908-p121">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting. These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="1d908-210">Benutzerfreundliche Audiosteuerelemente im Besprechungsraum ermöglichen Benutzern das Kontrollieren der Audiooptionen wie "Stummschalten", "Stummschaltung aufheben" oder "Gerät ändern".</span><span class="sxs-lookup"><span data-stu-id="1d908-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="1d908-211">Beim Freigeben von Programmen können Benutzer bei Bedarf mehrere Programme für eine Freigabe auswählen.</span><span class="sxs-lookup"><span data-stu-id="1d908-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="1d908-212">Benutzer können jetzt Präsentationen mit Videoclips hochladen, indem Sie die entsprechende PowerPoint-Datei hochladen und mit der Maus auf die Folie zeigen, um die Videosteuerelemente wie Wiedergabe oder Pause und die Audiosteuerelemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1d908-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="1d908-213">Benutzer können aus Besprechungen heraus eine andere geöffnete Unterhaltung mit der Besprechung zusammenführen, indem sie die Option **Diesen Anruf zusammenführen mit** im Menü **Weitere Optionen** (**…**) verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d908-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="1d908-214">Benutzer können mit der Maus auf die Schaltfläche **Teilnehmer anzeigen** zeigen, um die Namen der Teilnehmer anzuzeigen. Benutzer können auch auf **Teilnehmerliste anzeigen** klicken, um den Bereich in der Besprechung zu verankern.</span><span class="sxs-lookup"><span data-stu-id="1d908-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="1d908-215">In Abhängigkeit vom Besprechungstyp können Benutzer aus mehreren Inhalts- und Teilnehmeransichten auswählen.</span><span class="sxs-lookup"><span data-stu-id="1d908-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="1d908-p122">Besprechungen werden automatisch in einem Format aufgezeichnet, das im Windows Media Player wiedergegeben werden kann (MP4). Aufgezeichnete Dateien können auf einfache Weise mit anderen Benutzern geteilt werden. Mithilfe der Funktion **Veröffentlichen** im Aufzeichnungs-Manager können Aufzeichnungen darüber hinaus an freigegebenen Speicherorten abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1d908-p122">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4). Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="1d908-p123">OneNote bietet neue Wege der Zusammenarbeit in einer Besprechung. Während der Besprechung können sich Benutzer mit OneNote Notizen machen. Ferner besteht die Möglichkeit, freigegebene Notizbücher zu verwenden, in die auch andere Besprechungsteilnehmer ihre Notizen in Echtzeit eintragen können. Alle Teammitglieder können auf die freigegebenen Notizen zugreifen und Informationen ergänzen, eigene Ideen einbringen oder die Notizbuchseiten als virtuelles Whiteboard nutzen. Personen und freigegebene Inhalte in der Besprechung werden automatisch den Notizen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1d908-p123">OneNote enables new ways to collaborate in a meeting. During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time. All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard. People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="1d908-p124">Mit der Funktion **Inhalt freigeben und Besprechungsaktivitäten leiten** unten im Besprechungsraum können Benutzer zwischen den einzelnen Inhaltstypen wechseln. Darüber hinaus können Benutzer im Menü **Präsentationsinhalt verwalten** die Inhalte auswählen, die sie freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="1d908-p124">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room. Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d908-224">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d908-224">See Also</span></span>


[<span data-ttu-id="1d908-225">Planen von Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d908-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

