---
title: 'Lync Server 2013: Unterstützung für große Besprechungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19359dd785b846fa765e72adb810ccd255c2bd2e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523922"
---
# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="2f53a-102">Unterstützen großer Besprechungen mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f53a-102">Supporting large meetings using Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f53a-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="2f53a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="2f53a-104">Große Besprechungen folgen nicht dem im vorherigen Abschnitt beschriebenen Testmodell, da Sie die folgenden Merkmale aufweisen:</span><span class="sxs-lookup"><span data-stu-id="2f53a-104">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="2f53a-105">Das Besprechungs Format ist eine 1: n-Präsentation.</span><span class="sxs-lookup"><span data-stu-id="2f53a-105">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="2f53a-106">Ein oder mehrere Benutzer sind Referenten, und alle anderen Personen sind nur als Teilnehmer beteiligt.</span><span class="sxs-lookup"><span data-stu-id="2f53a-106">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="2f53a-107">PowerPoint-Präsentations Freigabe ist die Hauptaktivität der Datenzusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="2f53a-107">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="2f53a-108">Audio ist erforderlich, und Video kann auch verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2f53a-108">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="2f53a-109">Eine dedizierte Person, in der Regel entweder der Besprechungsorganisator oder ein Assistent des Organisators, richtet die Besprechung rechtzeitig im Voraus ein.</span><span class="sxs-lookup"><span data-stu-id="2f53a-109">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="2f53a-110">Dedizierte Mitarbeiter (nicht die Referenten) führen die Besprechung aus, einschließlich der Verbindung mit einer Onlinebesprechung, der Überprüfung, ob Audio-, Video-und Folien Freigaben ausgeführt werden, die Verwaltung von Lobby-und Benutzerrollen, das stumm schalten und das stumm schalten von Teilnehmern, das nehmen von Fragen und das Verwalten von Aufzeichnungen, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="2f53a-110">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="2f53a-111">Die Unterstützung großer Besprechungen mit bis zu 1000 Benutzern erfordert die Behebung der Probleme im Zusammenhang mit dem freigegebenen Hardwaremodell und dem nicht Reservierungs Modell.</span><span class="sxs-lookup"><span data-stu-id="2f53a-111">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="2f53a-112">Um über ausreichende CPU-und Arbeitsspeicherressourcen für Besprechungen mit bis zu 1000 Benutzern verfügen zu können, sollten die hostenden Front-End-Server keine anderen Chatnachrichten und Anwesenheits-oder Enterprise-VoIP-Arbeitslasten hosten.</span><span class="sxs-lookup"><span data-stu-id="2f53a-112">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="2f53a-113">Es sollte auch keine anderen Besprechungen hosten, unabhängig von der Größe der anderen Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="2f53a-113">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="2f53a-114">Dies bedeutet, dass das Hosten von Besprechungen mit bis zu 1000 Benutzern einen separaten lync Server Pool einrichten muss, der für das Hosten großer Besprechungen mit bis zu 1000 Benutzern vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="2f53a-114">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="2f53a-115">Ein lync Server Pool, der für das Hosten großer Besprechungen vorgesehen ist, sollte nur eine Besprechung mit bis zu 1000 Benutzern gleichzeitig hosten, sodass Besprechungszeiten vorab über einen Out-of-Band-Planungsprozess reserviert werden müssen, um den dedizierten Support von den Front-End-Servern sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="2f53a-115">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="2f53a-116">Zur gleichzeitigen Unterstützung mehrerer großer Besprechungen wird empfohlen, mehrere dedizierte große Besprechungs Pools einzurichten.</span><span class="sxs-lookup"><span data-stu-id="2f53a-116">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="2f53a-117">Es wird empfohlen, dass eine dedizierte Person den Online Teil einer großen Besprechung ausführt und überwacht.</span><span class="sxs-lookup"><span data-stu-id="2f53a-117">We recommend that a dedicated person run and monitor the online portion of a large meeting.</span></span> <span data-ttu-id="2f53a-118">Diese Person ist möglicherweise der Organisator, Stellvertreter des Organisators oder Referenten oder ein Mitglied des Support Teams für große Besprechungen, je nach den Einstellungen der Organisation.</span><span class="sxs-lookup"><span data-stu-id="2f53a-118">This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="2f53a-119">In den folgenden Abschnitten wird beschrieben, wie Sie einen dedizierten Pool für große Besprechungen implementieren, einschließlich bewährter Methoden für die Verwendung von lync Server 2013 zur Unterstützung großer Besprechungs Szenarien.</span><span class="sxs-lookup"><span data-stu-id="2f53a-119">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2f53a-120">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2f53a-120">In This Section</span></span>

  - [<span data-ttu-id="2f53a-121">Einrichten der Unterstützung für große Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f53a-121">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="2f53a-122">Verwalten großer Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f53a-122">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

