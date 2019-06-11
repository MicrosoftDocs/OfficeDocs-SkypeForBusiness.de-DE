---
title: 'Lync Server 2013: unterstützen von umfangreichen Besprechungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4e8c37c5498702e893da803497177c086a39a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="e9318-102">Unterstützen von umfangreichen Besprechungen mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9318-102">Supporting large meetings using Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9318-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e9318-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e9318-104">Große Besprechungen folgen nicht dem im vorherigen Abschnitt beschriebenen Testmodell, da Sie die folgenden Merkmale aufweisen:</span><span class="sxs-lookup"><span data-stu-id="e9318-104">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="e9318-105">Das Besprechungsformat entspricht einem 1:n-Format.</span><span class="sxs-lookup"><span data-stu-id="e9318-105">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="e9318-106">Ein oder wenige Benutzer fungieren als Referenten, und alle anderen Benutzer sind Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="e9318-106">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="e9318-107">Die Freigabe von PowerPoint-Präsentationen stellt die Hauptaktivität hinsichtlich der Datenzusammenarbeit dar.</span><span class="sxs-lookup"><span data-stu-id="e9318-107">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="e9318-108">Die Übertragung von Audiosignalen ist erforderlich, Videobilder können ebenfalls übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="e9318-108">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="e9318-109">Eine dedizierte Person, im Allgemeinen entweder der Besprechungsorganisator oder ein Assistent des Organisators, richtet die Besprechung rechtzeitig ein.</span><span class="sxs-lookup"><span data-stu-id="e9318-109">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="e9318-110">Spezielle Mitarbeiter (nicht die Referenten) führen durch die Besprechung, kümmern sich um das Herstellen von Verbindungen zu Onlinebesprechungen, stellen sicher, dass das Teilen von Audio-, Video- und Folieninhalten funktioniert, verwalten den Wartebereich und die Benutzerrollen, schalten Teilnehmer stumm bzw. heben deren Stummschaltung auf, nehmen Fragen entgegen und verwalten Aufzeichnungen nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="e9318-110">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="e9318-111">Zur Unterstützung von umfangreichen Besprechungen mit bis zu 1000 Benutzern müssen die Probleme im Zusammenhang mit dem freigegebenen Hardwaremodell und dem nicht Reservierungs Modell behoben werden.</span><span class="sxs-lookup"><span data-stu-id="e9318-111">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="e9318-112">Um ausreichende Speicherressourcen sowie die erforderliche CPU-Leistung für Besprechungen mit bis zu 1.000 Teilnehmern bereitstellen zu können, sollten auf dem Front-End-Server, der als Host fungiert, keine anderen Sofortnachrichten-, Anwesenheits- oder Enterprise-VoIP-Arbeitslasten verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e9318-112">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="e9318-113">Es sollte auch keine anderen Besprechungen hosten, unabhängig von der Größe der anderen Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="e9318-113">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="e9318-114">Das bedeutet, dass für das Hosten von Besprechungen mit bis zu 1000 Benutzern ein separater lync Server-Pool eingerichtet werden muss, der für das Hosten von umfangreichen Besprechungen mit bis zu 1000 Benutzern dediziert ist.</span><span class="sxs-lookup"><span data-stu-id="e9318-114">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="e9318-115">Ein lync-Server Pool, der für das Hosten von umfangreichen Besprechungen dediziert ist, sollte nur eine Besprechung mit bis zu 1000 Benutzern gleichzeitig hosten, sodass Besprechungszeiten im Voraus über einen Out-of-Band-Planungsprozess reserviert werden müssen, um eine dedizierte Unterstützung vom Front-End-Serv zu gewährleisten. ERS.</span><span class="sxs-lookup"><span data-stu-id="e9318-115">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="e9318-116">Wenn Sie mehrere große Besprechungen gleichzeitig unterstützen möchten, empfiehlt es sich, mehrere dedizierte große Besprechungs Pools einzurichten.</span><span class="sxs-lookup"><span data-stu-id="e9318-116">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="e9318-117">Wir empfehlen, dass eine dedizierte Person den Online-Teil einer groß Besprechung ausführt und überwacht.</span><span class="sxs-lookup"><span data-stu-id="e9318-117">We recommend that a dedicated person run and monitor the online portion of a large meeting.</span></span> <span data-ttu-id="e9318-118">Diese Person kann je nach den Einstellungen des Unternehmens der Organisator, die Stellvertretung des Organisators oder Referenten oder ein Mitglied des dedizierten Teams für große Besprechungen sein.</span><span class="sxs-lookup"><span data-stu-id="e9318-118">This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="e9318-119">In den folgenden Abschnitten wird beschrieben, wie Sie einen dedizierten Pool für umfangreiche Besprechungen implementieren, einschließlich bewährter Methoden für die Verwendung von lync Server 2013 zur Unterstützung großer Besprechungs Szenarien.</span><span class="sxs-lookup"><span data-stu-id="e9318-119">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9318-120">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e9318-120">In This Section</span></span>

  - [<span data-ttu-id="e9318-121">Einrichten der Unterstützung für umfangreiche Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9318-121">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="e9318-122">Verwalten von umfangreichen Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9318-122">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

