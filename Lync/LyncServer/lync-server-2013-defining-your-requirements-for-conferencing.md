---
title: 'Lync Server 2013: Definieren der Anforderungen für Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c19269ef06fc2aa7ec19e2ede53f406b345536b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="5b237-102">Definieren der Anforderungen für Konferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b237-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b237-103">_**Letztes Änderungsdatum des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="5b237-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="5b237-104">Wenn Sie festlegen, welche Konferenzfunktionen bereitgestellt werden sollen, müssen Sie überlegen, welche Funktionen von Ihren Benutzern genutzt werden sollen und welche Netzwerkbandbreite zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="5b237-104">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities.</span></span> <span data-ttu-id="5b237-105">Die folgende Liste der Fragen führt Sie durch den Konferenz Planungsprozess, um zu ermitteln, welche Features von Konferenzen Sie basierend auf den Anforderungen Ihrer Organisation bereitstellen sollten.</span><span class="sxs-lookup"><span data-stu-id="5b237-105">The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="5b237-106">**Sollen Webkonferenzfunktionen bereitgestellt werden, die eine gemeinsame Verwendung von Dokumenten und Anwendungen umfassen?**</span><span class="sxs-lookup"><span data-stu-id="5b237-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="5b237-107">In diesem Fall müssen Sie die Konferenz für Ihren Front-End-Pool im Microsoft lync Server 2013, Planungs Tool oder im Topologie-Generator aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b237-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="5b237-108">Wenn Sie Konferenzen aktivieren, aktivieren Sie sowohl Webkonferenzen als auch A/V-Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="5b237-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="5b237-109">Bei der Anwendungsfreigabe wird eine höhere Netzwerkbandbreite als bei der Dokumentzusammenarbeit benötigt und belegt.</span><span class="sxs-lookup"><span data-stu-id="5b237-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="5b237-110">Lync Server 2013 bietet einen Drosselungsmechanismus zum Steuern jeder Anwendungsfreigabesitzung.</span><span class="sxs-lookup"><span data-stu-id="5b237-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="5b237-111">In der Standardeinstellung sind für jede Sitzung 1,5 KB/s festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5b237-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="5b237-112">Wenn Sie die Anwendungsfreigabe nicht aktivieren möchten, Sie jedoch die Zusammenarbeit mit Dokumenten verwenden möchten, können Sie Konferenzen aktivieren und Besprechungsrichtlinien verwenden, um die Anwendungsfreigabe zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b237-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="5b237-113">Details zum Konfigurieren von Besprechungsrichtlinien finden Sie unter [Konferenzrichtlinien in lync Server 2013](lync-server-2013-conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5b237-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="5b237-114">Um Benutzern das Freigeben von PowerPoint-Präsentationen zu ermöglichen, müssen Sie den Office Web Apps-Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5b237-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="5b237-115">Weitere Informationen zum Konfigurieren von Office Web Apps Server finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="5b237-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="5b237-116">**Möchten Sie eine/V-Konferenz aktivieren?**</span><span class="sxs-lookup"><span data-stu-id="5b237-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="5b237-117">In diesem Fall müssen Sie die Konferenz für Ihren Front-End-Pool im lync Server 2013, Planungs Tool oder im Topologie-Generator aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b237-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="5b237-118">Wenn Sie Konferenzen aktivieren, aktivieren Sie sowohl Webkonferenzen als auch A/V-Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="5b237-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="5b237-119">A/V-Konferenzen erfordern und verwenden mehr Netzwerkbandbreite als Webkonferenzen (einschließlich Dokument Zusammenarbeit und Anwendungsfreigabe).</span><span class="sxs-lookup"><span data-stu-id="5b237-119">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing).</span></span> <span data-ttu-id="5b237-120">Wenn Sie keine a/v-Konferenzen aktivieren, aber Webkonferenzen aktivieren möchten, können Sie Konferenzen aktivieren und Besprechungsrichtlinien verwenden, um a/v-Konferenzen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b237-120">If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="5b237-121">Wenn Sie Audiokonferenzen, aber keine Videokonferenzen aktivieren möchten, können Sie eine/V-Konferenz aktivieren und mithilfe von Besprechungsrichtlinien Videokonferenzen verhindern.</span><span class="sxs-lookup"><span data-stu-id="5b237-121">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences.</span></span> <span data-ttu-id="5b237-122">Alternativ können Sie A/V-Konferenzen aktivieren und das Starten von oder Teilnehmen an A/V-Konferenzen nur für bestimmte Benutzer zulassen.</span><span class="sxs-lookup"><span data-stu-id="5b237-122">Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b237-p109">Enterprise Voice wird für A/V-Konferenzen nicht benötigt. Wenn Sie A/V-Konferenzen aktivieren, können Benutzer ihren Konferenzen Audiofunktionen hinzufügen, falls sie über entsprechende Geräte verfügen. Dies gilt auch bei Verwendung eines Nebenstellensystems als Telefonlösung.</span><span class="sxs-lookup"><span data-stu-id="5b237-p109">Enterprise Voice is not required for you to use A/V conferencing. If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="5b237-125">**Möchten Sie Benutzern die Teilnahme am Audioteil von Konferenzen ermöglichen, wenn Sie ein PSTN-Telefon verwenden?**</span><span class="sxs-lookup"><span data-stu-id="5b237-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="5b237-p110">Wenn ja, stellen Sie Einwahlkonferenzen bereit und aktivieren Sie sie. Eingeladene Benutzer innerhalb und außerhalb Ihrer Organisation können anschließend unter Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="5b237-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="5b237-128">**Möchten Sie externen Benutzern mit lync Server 2013-Clients ermöglichen, an den von Ihnen aktivierten Konferenztypen teilzunehmen?**</span><span class="sxs-lookup"><span data-stu-id="5b237-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="5b237-129">In diesem Fall sollten Sie Edgeserver bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5b237-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="5b237-130">Indem Sie externe Teilnahme an Besprechungen zulassen, maximieren Sie Ihre Investition in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b237-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="5b237-131">Benutzer mit Laptops mit lync Server 2013 können beispielsweise an Konferenzen teilnehmen, egal, wo Sie sich befinden – zu Hause, im Flughafen oder auf Kunden Websites.</span><span class="sxs-lookup"><span data-stu-id="5b237-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="5b237-132">Darüber hinaus können Sie mit Edgeserver, die bereitgestellt werden, Verbundbeziehungen mit anderen Organisationen wie Ihren Kunden oder Lieferanten erstellen, und Benutzer aus diesen Organisationen können einfacher mit ihren Benutzern zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5b237-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="5b237-133">Details zum Bereitstellen von Edgeserver finden Sie unter [Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) und [Bereitstellen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5b237-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="5b237-134">Details zum Aktivieren von externem Zugriff für Office Web Apps Server finden Sie unter [Veröffentlichen von Office Web Apps Server in lync Server 2013 mit einem Reverse Proxy Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span><span class="sxs-lookup"><span data-stu-id="5b237-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="5b237-135">**Möchten Sie die Clients steuern, die an lync Server 2013-Besprechungen teilnehmen können?**</span><span class="sxs-lookup"><span data-stu-id="5b237-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="5b237-136">Wenn ja, wird empfohlen, die Besprechungsseite so zu konfigurieren, dass nur die Clientoptionen ausgewählt werden können, die auch unterstützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5b237-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="5b237-137">Jedes Mal, wenn ein Benutzer auf einen Link klickt, um an einer geplanten Besprechung teilzunehmen, erkennt lync Server 2013, ob ein Client bereits auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5b237-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="5b237-138">Anschließend wird der Standardclient gestartet, und die Seite für den Besprechungsbeitritt mit Links zu alternativen Clients wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5b237-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="5b237-139">Die Seite "Besprechungsteilnahme" enthält immer die Option, Microsoft lync Web App zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5b237-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="5b237-140">Ferner können Sie entscheiden, ob Links für Teilnehmer und frühere Versionen von Communicator eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5b237-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="5b237-141">Ausführliche Informationen finden Sie unter [Konfigurieren der Besprechungsteilnahme Seite in lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span><span class="sxs-lookup"><span data-stu-id="5b237-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5b237-142">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5b237-142">In This Section</span></span>

  - [<span data-ttu-id="5b237-143">Webkonferenz Anforderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b237-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="5b237-144">A/V-Konferenz Anforderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b237-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="5b237-145">Anforderungen für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b237-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5b237-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b237-146">See Also</span></span>


[<span data-ttu-id="5b237-147">Planen von Konferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b237-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="5b237-148">Prüfliste zur Bereitstellung für Konferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b237-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

