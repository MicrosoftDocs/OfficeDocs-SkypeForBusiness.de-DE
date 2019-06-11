---
title: 'Lync Server 2013: Neue Funktionen für Clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf37f68d0ea11e17a799956f285d8ca82eb2a27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="6e089-102">Neue Funktionen für Clients in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e089-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e089-103">_**Letztes Änderungsdatum des Themas:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="6e089-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="6e089-104">Microsoft lync 2013 verfügt über eine neu gestaltete Benutzeroberfläche und wichtige neue Features.</span><span class="sxs-lookup"><span data-stu-id="6e089-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="6e089-105">Für Administratoren ist der Client jetzt im Office-Setupprogramm enthalten und bietet einen optimierten Ansatz zum Bereitstellen von Office und zum Anpassen von Clients in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="6e089-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e089-106">Eine illustrierte Ansicht der Benutzeroberflächen Updates für lync 2013 finden Sie unter "Neuerungen in lync 2013" <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span><span class="sxs-lookup"><span data-stu-id="6e089-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="6e089-107">Integration in Office-Setup</span><span class="sxs-lookup"><span data-stu-id="6e089-107">Integration with Office Setup</span></span>

<span data-ttu-id="6e089-108">Der lync 2013-Client und das Online Besprechungs-Add-in für lync 2013, das die Besprechungsverwaltung innerhalb des Outlook-Messaging-und-Zusammenarbeits-Clients unterstützt, sind jetzt im Office 2013-Setup Programm enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e089-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="6e089-109">In früheren Versionen von lync und Office Communicator könnten Sie die Windows Installer-Eigenschaften verwenden, um die Office-Installation anzupassen und zu steuern.</span><span class="sxs-lookup"><span data-stu-id="6e089-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="6e089-110">Da lync 2013 in das Office-Setup integriert ist, können Sie die folgenden Methoden zum Anpassen von lync 2013-Setup verwenden:</span><span class="sxs-lookup"><span data-stu-id="6e089-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="6e089-111">Verwenden des Office-Anpassungstools</span><span class="sxs-lookup"><span data-stu-id="6e089-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="6e089-112">Verwenden von "config. xml" zum Ausführen von Installationsaufgaben</span><span class="sxs-lookup"><span data-stu-id="6e089-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="6e089-113">Verwenden von Setup-Befehlszeilenoptionen</span><span class="sxs-lookup"><span data-stu-id="6e089-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e089-114">Das lync 2013-Setupprogramm deinstalliert keine früheren Versionen von lync oder Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="6e089-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="6e089-115">Der lync 2013-Client wird nebeneinander mit anderen lync-oder Office Communicator-Clients installiert</span><span class="sxs-lookup"><span data-stu-id="6e089-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="6e089-116">Ausführliche Informationen finden Sie unter [Bereitstellen von lync-Clients in lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6e089-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="6e089-117">Bereitstellung von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="6e089-117">Group Policy Deployment</span></span>

<span data-ttu-id="6e089-118">Da lync 2013 jetzt in Office-Setup enthalten ist, hat sich die Methode zum Bereitstellen von lync-Gruppenrichtlinieneinstellungen geändert.</span><span class="sxs-lookup"><span data-stu-id="6e089-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="6e089-119">In früheren Versionen von lync und Office Communicator könnten Sie die Gruppenrichtlinieneinstellungen mithilfe von Communicator. adm definieren, während Sie in lync 2013 nun die administrativen Vorlagen für lync und ADML verwenden können, die zusammen mit der Office-Gruppenrichtlinie bereitgestellt werden. Administrative Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="6e089-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="6e089-120">Ausführliche Informationen finden Sie unter [Gruppenrichtlinieneinstellungen für lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="6e089-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="6e089-121">Outlook-Scheduling-Add-in-Updates</span><span class="sxs-lookup"><span data-stu-id="6e089-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="6e089-122">Das Online Besprechungs-Add-in für lync 2013 umfasst Besprechungs Einladungs Anpassungen und neue Besprechungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="6e089-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="6e089-123">Administratoren können die Besprechungseinladungen der Organisation anpassen, indem Sie ein benutzerdefiniertes Logo, eine Support-URL, eine URL für eine rechtliche Verzichtserklärung oder einen benutzerdefinierten Fußzeilentext hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6e089-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="6e089-124">Ausführliche Informationen finden Sie unter [Anpassen des Online Besprechungs-Add-Ins in lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="6e089-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="6e089-125">Mit den Steuerelementen für neue Teilnehmer-stumm Schaltungen können Besprechungsorganisatoren Konferenzen planen, für die Teilnehmer-Audio und-Videostandard mäßig stumm geschaltet sind.</span><span class="sxs-lookup"><span data-stu-id="6e089-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="6e089-126">Plug-in für virtuelle Desktop Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="6e089-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="6e089-127">Der lync 2013-Client unterstützt jetzt Audio und Video in einer VDI-Umgebung (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="6e089-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="6e089-128">Ein Benutzer kann ein Audio-oder Videogerät (beispielsweise ein Headset oder eine Kamera) an den lokalen Computer (beispielsweise einen Thin-Client oder einen neu gezielten Computer) anschließen.</span><span class="sxs-lookup"><span data-stu-id="6e089-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="6e089-129">Der Benutzer kann eine Verbindung mit dem virtuellen Computer herstellen, sich beim lync 2013-Client anmelden, der auf dem virtuellen Computer ausgeführt wird, und an Echtzeit-Audio-und Videokommunikation teilnehmen, als ob der Client lokal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6e089-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="6e089-130">Die folgenden Features werden in einer virtuellen Desktopumgebung unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6e089-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="6e089-131">Geräteintegration für Audio und Video, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="6e089-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="6e089-132">Anrufsteuerungen vom Gerät aus</span><span class="sxs-lookup"><span data-stu-id="6e089-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="6e089-133">Anwesenheitsintegration auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="6e089-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="6e089-134">Mehrere HID-Unterstützung (Human Interface Device)</span><span class="sxs-lookup"><span data-stu-id="6e089-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="6e089-135">Support für Standort und Notfalldienste.</span><span class="sxs-lookup"><span data-stu-id="6e089-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="6e089-136">Unterstützung für alle lync-Modalitäten, einschließlich Chat, Audio, Video, Anwendungsfreigabe, Desktopfreigabe, PowerPoint-Freigabe, Whiteboard und Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="6e089-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="6e089-137">Unterstützung für Audio-und Videoanrufe in persönlichen anrufen und Konferenzgesprächen.</span><span class="sxs-lookup"><span data-stu-id="6e089-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="6e089-138">Informationen zum Bereitstellen des VDI-Plug-Ins finden Sie unter [Bereitstellen des lync-VDI-Plug-ins in lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="6e089-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="6e089-139">Video Verbesserungen</span><span class="sxs-lookup"><span data-stu-id="6e089-139">Video Enhancements</span></span>

<span data-ttu-id="6e089-140">Mehrere neue Features verbessern die Videoqualität für Konferenzteilnehmer erheblich.</span><span class="sxs-lookup"><span data-stu-id="6e089-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="6e089-141">Das Video wird durch die Flächen Erkennung und das intelligente Framing verbessert, sodass das Video eines Teilnehmers verschoben wird, damit es im Rahmen zentriert bleibt.</span><span class="sxs-lookup"><span data-stu-id="6e089-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="6e089-142">HD-Video wird jetzt in zweier-und mehr Parteien-Konferenzen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e089-142">High-definition video is now supported in two-party calls and multiparty conferences.</span></span> <span data-ttu-id="6e089-143">Benutzer können Auflösungen bis zu HD 1080p erleben.</span><span class="sxs-lookup"><span data-stu-id="6e089-143">Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="6e089-144">Teilnehmer können aus verschiedenen Besprechungs Layouts auswählen: in der Katalogansicht werden die Bilder oder Videos aller Teilnehmer angezeigt. Sprecher Ansicht zeigt den Besprechungsinhalt und nur das Video oder Bild des aktuellen Sprechers an; Die Präsentationsansicht zeigt nur den Besprechungsinhalt an. In der Kompaktansicht werden nur die Besprechungs Steuerelemente angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e089-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="6e089-145">Mit dem neuen Katalog Feature können Teilnehmer gleichzeitig mehrere Video-Feeds sehen.</span><span class="sxs-lookup"><span data-stu-id="6e089-145">With the new Gallery feature, participants can see multiple video feeds at the same time.</span></span> <span data-ttu-id="6e089-146">Wenn die Konferenz mehr als fünf Teilnehmer umfasst, werden in der obersten Zeile Video Feeds von nur den aktivsten Teilnehmern angezeigt, und Bilder werden für die anderen Teilnehmer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e089-146">If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="6e089-147">Teilnehmer können die Video Fixierung verwenden, um eine oder mehrere der verfügbaren Video Feeds auszuwählen, damit Sie jederzeit sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="6e089-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="6e089-148">Referenten können die Video-Spotlight-Funktion verwenden, um den Videofeed einer Person auszuwählen, damit jeder Teilnehmer an der Besprechung diesen Teilnehmer nur sieht.</span><span class="sxs-lookup"><span data-stu-id="6e089-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="6e089-149">Chatroom-Integration</span><span class="sxs-lookup"><span data-stu-id="6e089-149">Chat Room Integration</span></span>

<span data-ttu-id="6e089-150">Lync 2013 integriert nun die Features, die zuvor vom lync 2010-Gruppen-Chat bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6e089-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="6e089-151">Ein separater Gruppen-Chat-Client ist nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e089-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="6e089-152">In lync 2013 können Benutzer nach Chatrooms suchen, Chatrooms zu Ihren Kontakten hinzufügen, Chatroom-Aktivitäten überwachen sowie Nachrichten lesen und senden.</span><span class="sxs-lookup"><span data-stu-id="6e089-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="6e089-153">Benutzer können Themen Feeds erstellen, damit Sie benachrichtigt werden, wenn jemand in einem Chatroom einen Beitrag hinzufügt, der bestimmte Stichwörter enthält.</span><span class="sxs-lookup"><span data-stu-id="6e089-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="6e089-154">Auf der Seite neue Optionen für beständigen **Chat** können Benutzer Benachrichtigungs Benachrichtigungen und Sounds festlegen, die gelten, wenn Personen Nachrichten in ihren Chatrooms Posten.</span><span class="sxs-lookup"><span data-stu-id="6e089-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="6e089-155">Lync Web App-Updates</span><span class="sxs-lookup"><span data-stu-id="6e089-155">Lync Web App Updates</span></span>

<span data-ttu-id="6e089-156">Lync Web App ist der webbasierte Konferenz Client für lync Server 2013-Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="6e089-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="6e089-157">In dieser Version bietet das Hinzufügen von Computer-Audio und-Video zu lync Web App eine vollständige Besprechungs Erfahrung für jeden, der keinen lync-Client lokal installiert hat.</span><span class="sxs-lookup"><span data-stu-id="6e089-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="6e089-158">Besprechungsteilnehmer können auf alle Funktionen für die Zusammenarbeit und Freigabe sowie auf alle Besprechungssteuerelemente für Referenten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6e089-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="6e089-159">Wenn ein Benutzer versucht, an einer Besprechung teilzunehmen, aber keinen lokal installierten Client hat, wird lync Web App geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6e089-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="6e089-160">Wenn Sie weitere Optionen für die Teilnahme an der Besprechung zulassen möchten, können Sie die Seite "Besprechungsteilnahme" konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren der Besprechungsteilnahme Seite in lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6e089-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="6e089-161">Aufgrund der Verbesserungen bei lync Web App ist eine aktualisierte Version von Attendee für lync Server 2013 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6e089-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="6e089-162">Lync Web App ist der bevorzugte Client für Teilnehmer außerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="6e089-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="6e089-163">Es ist keine lokale Clientinstallation erforderlich, auch wenn für Audio-, Video-und Freigabefunktionen ein Plug-in bei der ersten Verwendung installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="6e089-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="6e089-164">Updates für lync 2013 für mobile Clients</span><span class="sxs-lookup"><span data-stu-id="6e089-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="6e089-165">Neben erweiterten Anwesenheits-, Kontakt-und Chatfunktionen bieten lync 2013 Mobile-Clients jetzt sprach-und Videoanrufe über das Internet und Mobilfunk-Datenverbindungen.</span><span class="sxs-lookup"><span data-stu-id="6e089-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="6e089-166">Mit einem einzigen Antippen des besprechungslinks in einem Kalenderelement können mobile Benutzer an lync-sprach-und Videobesprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="6e089-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="6e089-167">Weitere Informationen zu mobilen lync 2013-Clients finden Sie unter [Planen mobiler Clients in lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6e089-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="6e089-168">Lync 2013-Benutzeroberflächen Updates</span><span class="sxs-lookup"><span data-stu-id="6e089-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="6e089-169">Updates für Barrierefreiheit</span><span class="sxs-lookup"><span data-stu-id="6e089-169">Accessibility Updates</span></span>

<span data-ttu-id="6e089-170">Lync 2013 umfasst mehrere neue Barrierefreiheitsfeatures.</span><span class="sxs-lookup"><span data-stu-id="6e089-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="6e089-171">Lync 2013 unterstützt eine Auflösung mit einem höheren dpi-Wert, sodass Benutzer Text und Grafiken für 125% und 150% Punkte pro Zoll skalieren können.</span><span class="sxs-lookup"><span data-stu-id="6e089-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="6e089-172">Lync bietet Unterstützung für hohen Kontrast, damit die Benutzeroberfläche bei Verwendung mit Designs mit hohem Kontrast in Windows voll funktionsfähig bleibt.</span><span class="sxs-lookup"><span data-stu-id="6e089-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="6e089-173">Lync bietet mehr als 100 Tastenkombinationen, damit Benutzer ohne Maus auf wichtige Funktionen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="6e089-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="6e089-174">Beispielsweise können Benutzer ALT + C drücken, um einen Anruf anzunehmen, oder ALT + I, um ihn zu ignorieren, ohne die Tab-Taste oder den Fokus setzen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="6e089-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="6e089-175">Durch Drücken von (alt + Q) wird ein Anruf beendet (STRG + N) startet OneNote, und (Alt + T) öffnet das Menü Extras.</span><span class="sxs-lookup"><span data-stu-id="6e089-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="6e089-176">Die umfassende Unterstützung für die Sprachausgabe in lync 2013 stellt sicher, dass alle Benachrichtigungen, eingehenden Anfragen und Sofortnachrichten laut vorgelesen werden, wenn eine Sprachausgabe aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6e089-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="6e089-177">Anwesenheit während der Freigabe</span><span class="sxs-lookup"><span data-stu-id="6e089-177">Presence While Sharing</span></span>

<span data-ttu-id="6e089-178">Wenn lync erkennt, dass ein Benutzer freigegeben wird, weist lync dem Benutzer automatisch einen Präsentations Anwesenheitsstatus zu.</span><span class="sxs-lookup"><span data-stu-id="6e089-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="6e089-179">Dieser Status blockiert alle eingehenden Kommunikationen, es sei denn, dem Absender wird die private Beziehung Arbeitsgruppe zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6e089-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="6e089-180">Wenn der Benutzer die Freigabefunktion vollständig auf einem sekundären Monitor verwendet, weist lync keinen Präsentations Anwesenheitsstatus zu.</span><span class="sxs-lookup"><span data-stu-id="6e089-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="6e089-181">Updates für Unterhaltungsfenster</span><span class="sxs-lookup"><span data-stu-id="6e089-181">Conversation Window Updates</span></span>

<span data-ttu-id="6e089-182">Das neu gestaltete Unterhaltungsfenster bietet schnelleren Zugriff auf wichtige Funktionen.</span><span class="sxs-lookup"><span data-stu-id="6e089-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="6e089-183">Mit dem neuen Feature "Tabbed-Konversationen" können Benutzer nun alle Ihre Chat-und Chatrooms in einem Unterhaltungsfenster aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="6e089-183">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window.</span></span> <span data-ttu-id="6e089-184">Über die Registerkarten auf der linken Seite des Unterhaltungsfensters können Benutzer einfach zwischen allen aktiven Konversationen navigieren.</span><span class="sxs-lookup"><span data-stu-id="6e089-184">The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="6e089-185">Benutzer können eine einzelne Konversation in einem separaten Fenster öffnen und dann die Größe des Fensters ändern.</span><span class="sxs-lookup"><span data-stu-id="6e089-185">Users can pop out an individual conversation into a separate window, and then resize the window.</span></span> <span data-ttu-id="6e089-186">Sie können das Fenster auch wieder in das Haupt Unterhaltungsfenster einbringen.</span><span class="sxs-lookup"><span data-stu-id="6e089-186">They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="6e089-187">Lync 2013 öffnet die Unterhaltungen eines Benutzers erneut, wenn sich der Benutzer anmeldet und sich wieder bei lync anmeldet.</span><span class="sxs-lookup"><span data-stu-id="6e089-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="6e089-188">Benutzer können jeder Unterhaltung Schnellchat-, Video-, Programmfreigabe-, Desktopfreigabe-oder Webkonferenz Tools (Whiteboard, Besprechungsnotizen, freigegebene Notizbücher und Anlagen) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6e089-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="6e089-189">In einer Besprechung, in der Videos oder Inhalte freigegeben werden, können Benutzer das Besprechungs Video oder freigegebene Inhalte herausspringen und dann die Größe des Fensters ändern.</span><span class="sxs-lookup"><span data-stu-id="6e089-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="6e089-190">Updates für das Hauptfenster von lync</span><span class="sxs-lookup"><span data-stu-id="6e089-190">Lync Main Window Updates</span></span>

<span data-ttu-id="6e089-191">Das neue optimierte aussehen behält vertraute Funktionen wie das aktuelle Feature " **What es Happening Today?** ", die Statusauswahl und die **Einstellung "Standort** Auswahl" bei.</span><span class="sxs-lookup"><span data-stu-id="6e089-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="6e089-192">Wenn Chatrooms aktiviert sind, wird den Benutzern auf \*\*\*\* der lync-Hauptseite ein neues Symbol für Chatrooms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e089-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="6e089-193">Mit dem \*\*\*\* Symbol Chatrooms können Benutzer schnell auf Ihre Chatrooms und Filter zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6e089-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="6e089-194">Benutzer können auf die Ansichtssymbole klicken, um zur Ansicht **Kontakte** , **chatroomansicht** , **Konversations** Ansicht oder **Telefon** Ansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="6e089-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="6e089-195">Wenn Benutzer zu Exchange 2013 migriert wurden, können Sie ein Bild mit höherer Auflösung hochladen.</span><span class="sxs-lookup"><span data-stu-id="6e089-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="6e089-196">Kontakte anzeigen und Visitenkarten Updates</span><span class="sxs-lookup"><span data-stu-id="6e089-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="6e089-197">Lync 2013 bietet Benutzern unterschiedliche Möglichkeiten zum Anzeigen von Kontakten und Gruppen in der Ansicht " **Kontakte** ".</span><span class="sxs-lookup"><span data-stu-id="6e089-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="6e089-198">Mit dem neuen Unified Contact Store können die Benutzer nach dem Migrieren der lync-Kontakte von Benutzern zu Exchange 2013 auf Ihre Kontakte aus lync 2013, Outlook oder Outlook Web App zugreifen und diese verwalten, und Ihre Favoriten bleiben synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="6e089-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="6e089-199">Wenn ein Benutzer beispielsweise einen Kontakt zu den Favoriten in Outlook hinzufügt, wird der Kontakt in der Gruppe Favoriten in lync 2013 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e089-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="6e089-200">Wenn Sie den XMPP-Proxy und das XMPP-Gateway hinzugefügt und konfiguriert haben, können Benutzer Kontakte von XMPP-basierten Partnern für Sofortnachrichten und Anwesenheitsinformationen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6e089-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="6e089-201">Ein neuer **Kontakt hinzufügen, der nicht in meiner Organisation enthalten ist** , bietet Benutzern eine einfache Möglichkeit zum Hinzufügen von Personen, die sich außerhalb der Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="6e089-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="6e089-202">Eine neue Gruppe " **Favoriten** " ermöglicht Benutzern das Erstellen einer Liste von Personen, die Benutzer am häufigsten kontaktieren, um schnelleren Zugriff zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6e089-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="6e089-203">Benutzer können die Seite neue **Kontaktlisten** Optionen verwenden, um auszuwählen, wie Benutzer Kontakte sortieren und anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="6e089-203">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts.</span></span> <span data-ttu-id="6e089-204">Benutzer können eine erweiterte, zweizeilige Ansicht auswählen, in der die Bilder von Kontakten angezeigt werden, oder eine verkürzte einzeilige Ansicht.</span><span class="sxs-lookup"><span data-stu-id="6e089-204">Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view.</span></span> <span data-ttu-id="6e089-205">Benutzer können Kontakte auch alphabetisch oder nach Verfügbarkeit sortieren.</span><span class="sxs-lookup"><span data-stu-id="6e089-205">Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="6e089-206">Konferenz Updates</span><span class="sxs-lookup"><span data-stu-id="6e089-206">Conferencing Updates</span></span>

<span data-ttu-id="6e089-207">Lync 2013 bietet mehrere Verbesserungen für Konferenzfeatures.</span><span class="sxs-lookup"><span data-stu-id="6e089-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="6e089-208">Je nach Art der Besprechung können Benutzer die Zielgruppe jetzt stumm schalten und die Videofreigabe beim Planen der Besprechung zulassen oder blockieren.</span><span class="sxs-lookup"><span data-stu-id="6e089-208">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting.</span></span> <span data-ttu-id="6e089-209">Diese Optionen sind auf der Seite " **Besprechungsoptionen** " verfügbar und werden für größere Besprechungen mit mehr als 20 Teilnehmern empfohlen.</span><span class="sxs-lookup"><span data-stu-id="6e089-209">These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="6e089-210">Einfach zu verwendende Audiosteuerungen im Besprechungsraum ermöglichen dem Benutzer die Steuerung von Audiooptionen, wie Stummschaltung, Stummschaltung, Gerätewechsel usw.</span><span class="sxs-lookup"><span data-stu-id="6e089-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="6e089-211">Beim Freigeben von Programmen können Benutzer mehrere Programme auswählen, die Sie freigeben möchten, wenn Sie mit mehr als einem Programm arbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="6e089-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="6e089-212">Benutzer können jetzt Präsentationen mit Videoclips hochladen, indem Sie die PowerPoint-Datei hochladen und mit der Maus auf die Folie zeigen, um Videosteuerelemente wie Wiedergabe-, Pause-und Audiosteuerungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6e089-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="6e089-213">Während einer Besprechung können Benutzer eine andere offene Unterhaltung mit der Besprechung zusammenführen, indem Sie im Menü **Weitere Optionen** (**.**..) die Option **diesen Anruf zusammenführen** verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e089-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="6e089-214">Um die Namen der Teilnehmer anzuzeigen, können Benutzer mit der Maus auf die Schaltfläche **Teilnehmer anzeigen** zeigen oder auf **Teilnehmerliste anzeigen** klicken, um das Panel in der Besprechung anzudocken.</span><span class="sxs-lookup"><span data-stu-id="6e089-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="6e089-215">Je nach Besprechungstyp können Benutzer aus verschiedenen Inhalts-und Teilnehmer Ansichten auswählen.</span><span class="sxs-lookup"><span data-stu-id="6e089-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="6e089-216">Besprechungsaufzeichnungen werden automatisch in einem Format gespeichert, das in Windows Media Player (MP4) wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6e089-216">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4).</span></span> <span data-ttu-id="6e089-217">Benutzer können die Datei ganz einfach für beliebige Personen freigeben oder mithilfe der Funktion " **veröffentlichen** " im Aufzeichnungs-Manager die Aufzeichnung an einem freigegebenen Speicherort Posten.</span><span class="sxs-lookup"><span data-stu-id="6e089-217">Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="6e089-218">OneNote ermöglicht neue Möglichkeiten für die Zusammenarbeit an einer Besprechung.</span><span class="sxs-lookup"><span data-stu-id="6e089-218">OneNote enables new ways to collaborate in a meeting.</span></span> <span data-ttu-id="6e089-219">Während einer Besprechung können Benutzer Notizen mit OneNote für die persönliche Verwendung nach der Besprechung erstellen oder freigegebene Notizbücher und die gemeinsame Bearbeitung mit Besprechungsteilnehmern in Echtzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e089-219">During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time.</span></span> <span data-ttu-id="6e089-220">Alle Teammitglieder können auf die freigegebenen Notizen zugreifen, um Informationen beizusteuern, Ideen zu Brainstorming oder die Notizbuchseiten als virtuelles Whiteboard zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e089-220">All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard.</span></span> <span data-ttu-id="6e089-221">In der Besprechung freigegebene Personen und Inhalte werden den Notizen automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6e089-221">People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="6e089-222">Benutzer können mithilfe von " **Inhalte freigeben" und "Besprechungs Aktivitäten leiten** " am unteren Rand des Besprechungsraums zwischen Inhaltstypen wechseln.</span><span class="sxs-lookup"><span data-stu-id="6e089-222">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room.</span></span> <span data-ttu-id="6e089-223">Benutzer können auch das Menü **Präsentationsinhalte verwalten** verwenden, um auszuwählen, welche Inhalte freigegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6e089-223">Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e089-224">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e089-224">See Also</span></span>


[<span data-ttu-id="6e089-225">Planen von Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e089-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

