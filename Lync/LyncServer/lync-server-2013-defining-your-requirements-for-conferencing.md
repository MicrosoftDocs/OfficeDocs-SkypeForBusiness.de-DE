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
ms.openlocfilehash: 19f70df743e03494c0c54e180e2f23f960a752a1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="b2dbe-102">Definieren der Anforderungen für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2dbe-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2dbe-103">_**Letztes Änderungsstand des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="b2dbe-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="b2dbe-p101">Wenn Sie festlegen, welche Konferenzfunktionen bereitgestellt werden sollen, müssen Sie überlegen, welche Funktionen von Ihren Benutzern genutzt werden sollen und welche Netzwerkbandbreite zur Verfügung steht. Die nachfolgenden Fragen führen Sie durch den Konferenzplanungsprozess und helfen Ihnen, herauszufinden, welche Konferenzfunktionen aufgrund der Anforderungen Ihrer Organisation benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-p101">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities. The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="b2dbe-106">**Sollen Webkonferenzfunktionen bereitgestellt werden, die eine gemeinsame Verwendung von Dokumenten und Anwendungen umfassen?**</span><span class="sxs-lookup"><span data-stu-id="b2dbe-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="b2dbe-107">Wenn dies der Fall ist, müssen Sie die Konferenz für Ihre Front-End-Pool im Microsoft lync Server 2013, im Planungs Tool oder im Topologie-Generator aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="b2dbe-108">Durch das Aktivieren von Konferenzen werden sowohl Webkonferenzen als auch A/V-Konferenzen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="b2dbe-109">Bei der Anwendungsfreigabe wird eine höhere Netzwerkbandbreite als bei der Dokumentzusammenarbeit benötigt und belegt.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="b2dbe-110">Lync Server 2013 stellt einen Einschränkungsmechanismus zum Steuern der einzelnen Anwendungsfreigabesitzungen bereit.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="b2dbe-111">In der Standardeinstellung ist für jede Sitzung 1,5 KB/s festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="b2dbe-112">Wenn Sie die Anwendungsfreigabe nicht aktivieren, die Funktion zur Dokumentzusammenarbeit jedoch bereitstellen möchten, können Sie die Konferenzfunktionen aktivieren und die Anwendungsfreigabe mithilfe von Besprechungsrichtlinien deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="b2dbe-113">Ausführliche Informationen zum Konfigurieren von Besprechungsrichtlinien finden Sie unter [Conferencing Policies in lync Server 2013](lync-server-2013-conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b2dbe-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="b2dbe-114">Um Benutzern die Freigabe von PowerPoint-Präsentationen zu ermöglichen, müssen Sie Office-webapps-Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="b2dbe-115">Ausführliche Informationen zum Konfigurieren von Office-webapps Server finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="b2dbe-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="b2dbe-116">**Sollen A/V-Konferenzen aktiviert werden?**</span><span class="sxs-lookup"><span data-stu-id="b2dbe-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="b2dbe-117">Wenn dies der Fall ist, müssen Sie die Konferenz für Ihre Front-End-Pool im lync Server 2013, im Planungs Tool oder im Topologie-Generator aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="b2dbe-118">Durch das Aktivieren von Konferenzen werden sowohl Webkonferenzen als auch A/V-Konferenzen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="b2dbe-p107">Für A/V-Konferenzen ist eine höhere Netzwerkbandbreite erforderlich als für Webkonferenzen (diese umfassen Dokumentzusammenarbeit und Anwendungsfreigabe). Wenn Sie A/V-Konferenzen nicht aktivieren, das Feature für Webkonferenzen jedoch bereitstellen möchten, können Sie die Konferenzfunktionen aktivieren und A/V-Konferenzen mithilfe von Besprechungsrichtlinien deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-p107">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing). If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="b2dbe-p108">Wenn Sie Audiokonferenzen, jedoch keine Videokonferenzen zulassen möchten, können Sie die A/V-Konferenzfunktion aktivieren und Videokonferenzen mithilfe von Besprechungsrichtlinien verhindern. Alternativ können Sie A/V-Konferenzen aktivieren und das Starten von oder Teilnehmen an A/V-Konferenzen nur für bestimmte Benutzer zulassen.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-p108">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences. Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2dbe-123">Enterprise-VoIP ist für die Verwendung von A/V-Konferenzen nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-123">Enterprise Voice is not required for you to use A/V conferencing.</span></span> <span data-ttu-id="b2dbe-124">Wenn Sie a/V-Konferenzen aktivieren, können Ihre Benutzer Ihrer Konferenzen Audiodaten hinzufügen, wenn Sie über Audiogeräte verfügen, selbst wenn Sie eine Nebenstellenanlage für Ihre Telefonlösung verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-124">If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="b2dbe-125">**Sollen Benutzer bei Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen können?**</span><span class="sxs-lookup"><span data-stu-id="b2dbe-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="b2dbe-p110">Wenn ja, stellen Sie Einwahlkonferenzen bereit und aktivieren Sie sie. Eingeladene Benutzer innerhalb und außerhalb Ihrer Organisation können anschließend unter Verwendung eines Festnetztelefons am Audioteil von Konferenzen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="b2dbe-128">**Möchten Sie externen Benutzern mit lync Server 2013 Clients die Teilnahme an den von Ihnen aktivierten Konferenztypen ermöglichen?**</span><span class="sxs-lookup"><span data-stu-id="b2dbe-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="b2dbe-129">Wenn ja, müssen Sie Edgeserver bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="b2dbe-130">Indem Sie externe Teilnahme an Besprechungen ermöglichen, maximieren Sie Ihre Investitionen in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="b2dbe-131">Beispielsweise können Benutzer mit Laptops mit lync Server 2013 an Konferenzen von überall aus teilnehmen – zu Hause, im Flughafen oder an Kundenstandorten.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="b2dbe-132">Wenn Sie Edgeserver bereitstellen, können Sie zudem Partnerverbundbeziehungen mit anderen Organisationen – z. B. Ihren Kunden oder Lieferanten – einrichten, sodass Benutzer dieser Organisationen einfacher mit Ihren Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="b2dbe-133">Ausführliche Informationen zum Bereitstellen von Edgeserver finden Sie unter [Planen des Zugriffs durch externe Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) und [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="b2dbe-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="b2dbe-134">Ausführliche Informationen zum Aktivieren von externem Zugriff für Office-webapps-Server finden Sie unter [Veröffentlichen von Office-webapps Server in lync Server 2013 mithilfe eines Reverse-Proxyservers](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span><span class="sxs-lookup"><span data-stu-id="b2dbe-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="b2dbe-135">**Möchten Sie die Clients steuern, die an lync Server 2013 Besprechungen teilnehmen können?**</span><span class="sxs-lookup"><span data-stu-id="b2dbe-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="b2dbe-136">Wenn ja, wird empfohlen, die Besprechungsseite so zu konfigurieren, dass nur die Clientoptionen ausgewählt werden können, die auch unterstützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="b2dbe-137">Jedes Mal, wenn ein Benutzer auf einen Link klickt, um einer geplanten Besprechung beizutreten, erkennt lync Server 2013, ob ein Client bereits auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="b2dbe-138">Anschließend wird der Standardclient gestartet, und die Seite für den Besprechungsbeitritt wird geöffnet, auf der Links für alternative Clients angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="b2dbe-139">Die Seite für den Besprechungsbeitritt enthält immer die Option zur Verwendung der Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="b2dbe-140">Zusätzlich zu dieser Option können Sie entscheiden, ob Sie Links für Teilnehmer und frühere Versionen von Communicator einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="b2dbe-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="b2dbe-141">Ausführliche Informationen finden Sie unter [Konfigurieren der Seite für den besprechungsbeitritt in lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span><span class="sxs-lookup"><span data-stu-id="b2dbe-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b2dbe-142">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b2dbe-142">In This Section</span></span>

  - [<span data-ttu-id="b2dbe-143">Webkonferenz Anforderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2dbe-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="b2dbe-144">A/V-Konferenz Anforderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2dbe-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="b2dbe-145">Anforderungen für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2dbe-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2dbe-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2dbe-146">See Also</span></span>


[<span data-ttu-id="b2dbe-147">Planen von Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2dbe-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="b2dbe-148">Prüfliste für die Bereitstellung für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2dbe-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

