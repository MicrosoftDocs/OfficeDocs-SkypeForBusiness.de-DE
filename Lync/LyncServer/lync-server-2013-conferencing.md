---
title: Lync Server 2013 Konferenzen
description: Lync Server 2013 Konferenzen.
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
ms.openlocfilehash: 7d4a5f1ca1edc6246aace56c8a4bfa5b5215c4bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555951"
---
# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="d169e-103">Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d169e-103">Conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d169e-104">_**Letztes Änderungsstand des Themas:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="d169e-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="d169e-105">Mit einheitlichen Konferenzen in lync Server 2013 können Benutzer zusammenarbeiten, Informationen austauschen und ihre Bemühungen in Echtzeit koordinieren.</span><span class="sxs-lookup"><span data-stu-id="d169e-105">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="d169e-106">Alle Benutzer können die vollständige Bandbreite der Funktionen zur spontanen Zusammenarbeit und zu geplanten Besprechungen sowie die Besprechungstools nutzen.</span><span class="sxs-lookup"><span data-stu-id="d169e-106">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="d169e-107">VoIP- und Videokonferenzfunktionen können an jedem Ort mit Internetverbindung eingesetzt werden, und Benutzer, denen kein Computer zur Verfügung steht, können durch Einwahl über ein Festnetztelefon (PSTN) an Audiokonferenzen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="d169e-107">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="d169e-108">In Outlook integrierte Besprechungstools ermöglichen Organisatoren das Planen einer Besprechung oder das Starten einer spontanen Konferenz mit einem einzigen Mausklick und machen es den Teilnehmern ebenso leicht, sich anzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d169e-108">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="d169e-109">Ein WebClient erweitert umfangreiche Konferenzfunktionen auf Teilnehmer, die nicht die Desktop Version von lync betreiben.</span><span class="sxs-lookup"><span data-stu-id="d169e-109">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="d169e-110">Audio- und Videokonferenzen</span><span class="sxs-lookup"><span data-stu-id="d169e-110">Audio and Video Conferencing</span></span>

<span data-ttu-id="d169e-111">Lync Server bietet eine Benutzeroberfläche, die Benutzern herkömmlicher Audio Bridge-Dienste vertraut ist, einschließlich PSTN-Einwahl Diensten mit Tonwahlbefehlen für die Anrufsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d169e-111">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="d169e-112">Gleichzeitig sind leistungsfähige Planungs-, Teilnahme- und Verwaltungsfunktionen integriert, die nur mit einer integrierten Unified Communications-Plattform verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d169e-112">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="d169e-113">Mit einem einzigen Mausklick können Benutzer eine Besprechung in Outlook planen.</span><span class="sxs-lookup"><span data-stu-id="d169e-113">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="d169e-114">Details wie Besprechungszeit, Ort und Teilnehmer befolge die vertraute Outlook-Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d169e-114">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="d169e-115">Außerdem werden zum Konferenzanruf gehörende Informationen (z. B. die Einwahlnummer, Besprechungs-IDs und PIN-Erinnerungen (Personal Identification Number)) automatisch mit Daten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="d169e-115">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="d169e-116">Um sicherzustellen, dass nur die autorisierten Personen an einem Anruf teilnehmen, bietet lync Server mehrere Authentifizierungsstufen für Teilnehmer an.</span><span class="sxs-lookup"><span data-stu-id="d169e-116">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="d169e-117">Benutzer, die sich mit lync anmelden, werden bereits vom Active Directory-Domänendienste authentifiziert und müssen keine PIN, keinen Passcode oder keine Besprechungs-ID eingeben.</span><span class="sxs-lookup"><span data-stu-id="d169e-117">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="d169e-118">Lync vereinfacht die Benutzeroberfläche für Videokonferenzen, indem Video in den Unified Client integriert wird, sodass das Planen einer Besprechung mit Video oder die spontane Weiterleitung an Video nahtlos und einfach ist.</span><span class="sxs-lookup"><span data-stu-id="d169e-118">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="d169e-119">Lync Server vereinfacht das Hinzufügen von Videos zu einem Standardtelefon Anruf mit nur einem Mausklick.</span><span class="sxs-lookup"><span data-stu-id="d169e-119">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="d169e-120">Wenn es mehrere Teilnehmer bei einem Videoanruf oder einer Videokonferenz gibt, kann jeder Benutzer bis zu fünf andere Teilnehmer sehen, oder ein Referent legt eine einzige Videoquelle fest, die allen anderen Teilnehmern eingeblendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d169e-120">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="d169e-121">High-Definition-Video (Auflösung 1270 x 720; Seitenverhältnis 16:9) und VGA-Video (Auflösung 640 x 480; Seitenverhältnis 4:3) werden für Peer-zu-Peer-Anrufe zwischen Benutzern unterstützt, die lync auf High-End-Computern betreiben.</span><span class="sxs-lookup"><span data-stu-id="d169e-121">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="d169e-122">Jedem Teilnehmer kann das Bild in einer anderen Auflösung angezeigt werden, je nach der Leistungsfähigkeit seiner Videohardware.</span><span class="sxs-lookup"><span data-stu-id="d169e-122">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="d169e-p108">IT-Administratoren können Richtlinien festlegen, um High-Definition- oder VGA-Video auf Clients einzuschränken und zu deaktivieren. Dabei spielen die Computerfunktionen, die Netzwerkbandbreite und das Vorhandensein einer Kamera, die die gewünschte Auflösung bieten kann, eine Rolle. Diese Richtlinien werden durch eine In-Band-Bereitstellung durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="d169e-p108">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution. These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="d169e-125">Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="d169e-125">Web conferencing</span></span>

<span data-ttu-id="d169e-126">Lync Server integriert Features für die Konferenz Freigabe wie Desktop, Anwendung, Anlage, Whiteboard, Poll und PowerPoint in das optimierte lync.</span><span class="sxs-lookup"><span data-stu-id="d169e-126">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="d169e-127">Zusammen mit Audio- und Videokonferenzfunktionen bietet dies Möglichkeiten zu einer optimalen Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="d169e-127">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="d169e-128">Um die Gesamterfahrung von Benutzern zu verbessern, die PowerPoint-Präsentationen präsentieren oder anzeigen, verwendet lync Server 2013 Office-Webanwendungen zur Behandlung von PowerPoint-Präsentationen.</span><span class="sxs-lookup"><span data-stu-id="d169e-128">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="d169e-129">Benutzer können ein Bild freigeben oder Text mithilfe eines Whiteboards in der lync-Besprechung kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="d169e-129">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="d169e-130">Referenten können Umfragen in der lync-Besprechung durchführen, um Feedback von den Teilnehmern anzufordern.</span><span class="sxs-lookup"><span data-stu-id="d169e-130">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="d169e-131">Mit der Desktopfreigabe können Referenten beliebige Grafiken, Anwendungen, Webseiten, Dokumente, Software oder einen Teil Ihrer Desktops an Remote-Teilnehmer in Echtzeit direkt von lync aus übertragen.</span><span class="sxs-lookup"><span data-stu-id="d169e-131">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="d169e-132">Die Zuschauer können die Mausbewegungen und Tastatureingaben verfolgen.</span><span class="sxs-lookup"><span data-stu-id="d169e-132">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="d169e-133">Referenten können ihren gesamten Bildschirm oder nur einen Teilbereich freigeben.</span><span class="sxs-lookup"><span data-stu-id="d169e-133">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="d169e-134">Durch Freigabe ihres Desktops können Referenten ihren Zuhörern interaktive Produkt- oder Softwaredemos von jedem beliebigen Ort aus vorführen.</span><span class="sxs-lookup"><span data-stu-id="d169e-134">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="d169e-p112">Mit der Anwendungsfreigabe können Referenten die Steuerung von Software auf ihrem Desktop freigeben, ohne das Feedback oder Textfragen von Teilnehmern aus dem Blick zu verlieren. Referenten können die Steuerung der Anwendung auch an Besprechungsteilnehmer übertragen.</span><span class="sxs-lookup"><span data-stu-id="d169e-p112">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions. Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="d169e-137">Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="d169e-137">Dial-in Conferencing</span></span>

<span data-ttu-id="d169e-138">Für Benutzer, die keinen Personal Computer verwenden, stehen verschiedene Methoden für die Teilnahme an einer lync Server-Telefonkonferenz zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d169e-138">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="d169e-139">Ein PSTN-Benutzer kann eine Zugriffsnummer wählen, auf die Besprechungs Brücke zugreifen und dann die Besprechungs-ID eingeben.</span><span class="sxs-lookup"><span data-stu-id="d169e-139">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="d169e-140">Für sicherere Besprechungen kann der Benutzer auch aufgefordert werden, seine PIN zur Authentifizierung bei Active Directory einzugeben.</span><span class="sxs-lookup"><span data-stu-id="d169e-140">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="d169e-141">Lync Server unterstützt auch lync Phone Edition-Geräte, bei denen es sich um eigenständige IP-Telefongeräte handelt, die von Microsoft-Partnern bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d169e-141">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

