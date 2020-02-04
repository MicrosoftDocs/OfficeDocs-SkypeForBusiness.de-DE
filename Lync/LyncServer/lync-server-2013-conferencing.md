---
title: 'Lync Server 2013: Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f14a9f23617c55f1c09abc4daf29b5849b3bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="9bdcd-102">Konferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bdcd-102">Conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bdcd-103">_**Letztes Änderungsdatum des Themas:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="9bdcd-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="9bdcd-104">Mit Unified Conferencing in lync Server 2013 können Benutzer zusammenarbeiten, Informationen austauschen und ihre Bemühungen in Echtzeit koordinieren.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="9bdcd-105">Alle Ihre Benutzer können die gesamte Bandbreite an spontaner Zusammenarbeit, geplanten Besprechungen und Besprechungstools verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="9bdcd-106">Funktionen für Sprach-und Videokonferenzen können von jedem Ort mit einer Internet Verbindung verwendet werden, und Benutzer, die sich nicht an einem Computer befinden, können an Audiokonferenzen teilnehmen, indem Sie sich mit einem PSTN-Telefon (Public Switched Telephone Network) einwählen.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="9bdcd-107">In Outlook integrierte Besprechungstools ermöglichen es den Organisatoren, eine Besprechung zu planen oder eine spontane Konferenz mit nur einem Mausklick zu starten, und es ist auch für Teilnehmer genauso einfach, teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="9bdcd-108">Ein WebClient erweitert Rich-Konferenzfeatures auf Teilnehmer, die nicht die Desktop Version von lync ausführen.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="9bdcd-109">Audio- und Videokonferenzen</span><span class="sxs-lookup"><span data-stu-id="9bdcd-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="9bdcd-110">Lync Server bietet eine Benutzeroberfläche, die für die Benutzer herkömmlicher Audio Bridge-Dienste wie PSTN-Einwahldienste mit Befehlen zur Anrufsteuerung mit Tonwahl vertraut ist.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="9bdcd-111">Gleichzeitig beinhaltet Sie leistungsfähige Planungs-, Verbindungs-und Verwaltungsfunktionen, die nur mit einer integrierten Unified Communications-Plattform zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="9bdcd-112">Mit nur einem Mausklick können Benutzer eine Besprechung aus Outlook planen.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="9bdcd-113">Details wie Besprechungszeit, Ort und Teilnehmer folgen der vertrauten Outlook-Vorlage.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="9bdcd-114">Darüber hinaus werden Konferenzanruf spezifische Informationen wie Einwahlnummer, Besprechungs-IDs und PIN-Erinnerung (persönliche Identifikationsnummer) automatisch ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="9bdcd-115">Um sicherzustellen, dass nur autorisierte Personen an einem Anruf teilnehmen, bietet lync Server mehrere Authentifizierungsstufen für Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="9bdcd-116">Benutzer, die mit lync teilnehmen, werden bereits von den Active Directory-Domänendiensten authentifiziert und müssen keine PIN, keinen Passcode oder keine Besprechungs-ID eingeben.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="9bdcd-117">Lync vereinfacht die Videokonferenz-Benutzererfahrung, indem es Video in den Unified Client einbindet, damit die Planung einer Besprechung mit Video oder die spontane Weiterleitung an Videos nahtlos und einfach ist.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="9bdcd-118">Mit lync Server ist es einfach, mit nur einem Mausklick Video zu einem Standard-Telefonanruf hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="9bdcd-119">Wenn in einem Videoanruf oder einer Konferenz mehrere Teilnehmer vorhanden sind, kann jeder Benutzer Video von bis zu fünf anderen Benutzern gleichzeitig sehen, oder ein Referent kann nur eine Videoquelle auswählen, die nur von jedem angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="9bdcd-120">HD-Video (Auflösung 1270 x 720; Seitenverhältnis 16:9) und VGA-Video (Auflösung 640 x 480; Seitenverhältnis 4:3) werden für Peer-to-Peer-Anrufe zwischen Benutzern unterstützt, die lync auf Highend-Computern ausführen.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="9bdcd-121">Die Auflösung, die von jedem Teilnehmer in einer einzelnen Unterhaltung angezeigt wird, kann je nach den Videofunktionen der jeweiligen Hardware des Benutzers unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="9bdcd-122">IT-Administratoren können abhängig von der Computerfunktion, der Netzwerkbandbreite und dem vorhanden sein einer Kamera, die die erforderliche Auflösung liefern kann, Richtlinien festlegen, um HD-oder VGA-Video auf Clients zu beschränken oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-122">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution.</span></span> <span data-ttu-id="9bdcd-123">Diese Richtlinien werden durch die in-Band-Bereitstellung erzwungen.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-123">These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="9bdcd-124">Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="9bdcd-124">Web conferencing</span></span>

<span data-ttu-id="9bdcd-125">Lync Server integriert Konferenz Freigabefeatures wie Desktop, Anwendung, Anlage, Whiteboard, Poll und PowerPoint in die optimierte lync-Version.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="9bdcd-126">In Kombination mit Audio-oder Videokonferenzen entsteht eine äußerst immersive und kollaborative Sitzung, die einfach zu vereinfachen ist.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="9bdcd-127">Zur Verbesserung der allgemeinen Benutzerfreundlichkeit von Benutzern, die PowerPoint-Präsentationen präsentieren oder anzeigen, verwendet lync Server 2013 Office Web Apps zur Behandlung von PowerPoint-Präsentationen.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="9bdcd-128">Benutzer können ein Bild freigeben oder Text mithilfe eines Whiteboards in der lync-Besprechung kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="9bdcd-129">Referenten können Umfragen in der lync-Besprechung durchführen, um Feedback von den Teilnehmern anzufordern.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="9bdcd-130">Die Desktopfreigabe ermöglicht es Referenten, visuelle Elemente, Anwendungen, Webseiten, Dokumente, Software oder einen Teil Ihrer Desktops an Remote-Teilnehmer in Echtzeit zu übertragen, direkt von lync aus.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="9bdcd-131">Teilnehmer können mit Mausbewegungen und Tastatureingaben folgen.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="9bdcd-132">Referenten können auswählen, ob Sie den gesamten Bildschirm oder nur einen Teil freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="9bdcd-133">Durch die Freigabe Ihrer Desktops können Referenten in interaktiven Produkt-oder Software-Demos von jedem Ort aus mit Ihren Zielgruppen kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="9bdcd-134">Die Anwendungsfreigabe ermöglicht es Referenten, die Steuerung von Software auf ihren Desktops freizugeben, ohne das Feedback von Teilnehmern oder Text Fragen aus den Augen zu verlieren.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-134">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions.</span></span> <span data-ttu-id="9bdcd-135">Referenten können die Steuerung der Anwendung auch an Besprechungsteilnehmer delegieren.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-135">Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="9bdcd-136">Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="9bdcd-136">Dial-in Conferencing</span></span>

<span data-ttu-id="9bdcd-137">Für Benutzer, die keinen Personal Computer verwenden, stehen verschiedene Methoden für die Teilnahme an einem lync Server-Konferenzanruf zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="9bdcd-138">Ein PSTN-Benutzer kann eine Zugriffsnummer wählen, auf die Besprechungs Brücke zugreifen und dann die Besprechungs-ID eingeben.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="9bdcd-139">Für sicherere Besprechungen kann der Benutzer auch dazu aufgefordert werden, seine PIN einzugeben, um sich bei Active Directory zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="9bdcd-140">Lync Server unterstützt auch lync Phone Edition-Geräte, bei denen es sich um eigenständige IP-Telefongeräte handelt, die von Microsoft-Partnern bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9bdcd-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

