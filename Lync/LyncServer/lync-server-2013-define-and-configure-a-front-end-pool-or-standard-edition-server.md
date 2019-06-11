---
title: Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ac840cb40da71f81a24501f3d9caa53fb316e86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="6a10d-102">Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a10d-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a10d-103">_**Letztes Änderungsdatum des Themas:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="6a10d-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="6a10d-104">Für dieses Verfahren ist keine Mitgliedschaft in einem lokalen Administrator oder einer privilegierten Domänengruppe erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6a10d-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="6a10d-105">Melden Sie sich als Standardbenutzer an einem Computer an.</span><span class="sxs-lookup"><span data-stu-id="6a10d-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="6a10d-106">Wenn Sie einen Enterprise-Server bereitstellen, muss immer eine Mindestanzahl an Front-End-Servern in einem Pool ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6a10d-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="6a10d-107">In der folgenden Tabelle werden diese Anforderungen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="6a10d-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a10d-108">Gesamtzahl der Front-End-Server im Pool</span><span class="sxs-lookup"><span data-stu-id="6a10d-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="6a10d-109">Anzahl der Server, die aktiv sein müssen, damit der Pool funktioniert</span><span class="sxs-lookup"><span data-stu-id="6a10d-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a10d-110">1-2</span><span class="sxs-lookup"><span data-stu-id="6a10d-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="6a10d-111">1</span><span class="sxs-lookup"><span data-stu-id="6a10d-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a10d-112">3-4</span><span class="sxs-lookup"><span data-stu-id="6a10d-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="6a10d-113">2</span><span class="sxs-lookup"><span data-stu-id="6a10d-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a10d-114">5-6</span><span class="sxs-lookup"><span data-stu-id="6a10d-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="6a10d-115">3</span><span class="sxs-lookup"><span data-stu-id="6a10d-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a10d-116">7-8</span><span class="sxs-lookup"><span data-stu-id="6a10d-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="6a10d-117">4</span><span class="sxs-lookup"><span data-stu-id="6a10d-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a10d-118">9-10</span><span class="sxs-lookup"><span data-stu-id="6a10d-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="6a10d-119">5</span><span class="sxs-lookup"><span data-stu-id="6a10d-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a10d-120">11-12</span><span class="sxs-lookup"><span data-stu-id="6a10d-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="6a10d-121">6</span><span class="sxs-lookup"><span data-stu-id="6a10d-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="6a10d-122">Bei lync Server 2013 müssen Sie jedes Mal, wenn Sie einen Front-End-Server aus dem Pool hinzufügen oder entfernen, Dienste neu starten.</span><span class="sxs-lookup"><span data-stu-id="6a10d-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="6a10d-123">Das Entfernen und Hinzufügen von Servern sollte als separate Vorgänge erfolgen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="6a10d-124">Wenn Sie beispielsweise zwei Front-End-Server hinzufügen und zwei Front-End-Server entfernen möchten, verwenden Sie den folgenden Prozess:</span><span class="sxs-lookup"><span data-stu-id="6a10d-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="6a10d-125">Entfernen Sie die beiden Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="6a10d-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="6a10d-126">Veröffentlichen Sie die Topologie, und aktivieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="6a10d-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="6a10d-127">Starten Sie die Dienste neu</span><span class="sxs-lookup"><span data-stu-id="6a10d-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="6a10d-128">Fügen Sie die beiden Front-End-Server hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a10d-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="6a10d-129">Veröffentlichen Sie die Topologie, und aktivieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="6a10d-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="6a10d-130">Starten Sie die Dienste neu.</span><span class="sxs-lookup"><span data-stu-id="6a10d-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="6a10d-131">Nachdem Sie Ihre Topologie definiert haben, gehen Sie wie folgt vor, um einen Front-End-Pool für Ihre Website zu definieren.</span><span class="sxs-lookup"><span data-stu-id="6a10d-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="6a10d-132">Details zum Definieren der Topologie finden Sie unter [definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="6a10d-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="6a10d-133">So definieren Sie einen Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="6a10d-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="6a10d-134">Klicken Sie im Assistenten zum Definieren eines neuen Front-End-Pools auf der Seite **Neues Front-End-Pool definieren** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6a10d-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="6a10d-135">Geben Sie auf der Seite **FQDN des Front-End-Pools definieren** einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den zu erstellenden Pool ein, klicken Sie auf **Enterprise Edition-Front-End-Pool**, und klicken Sie dann auf **weiter**</span><span class="sxs-lookup"><span data-stu-id="6a10d-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="6a10d-136">Geben Sie auf der Seite **Computer auf diesem Pool definieren** einen Computer-FQDN für den ersten Front-End-Server im Pool ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6a10d-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="6a10d-137">Wiederholen Sie diesen Schritt für alle weiteren Computer (bis zu zwölf), die Sie dem Pool hinzufügen möchten, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6a10d-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="6a10d-138">Aktivieren Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die in diesem Front-End-Pool angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="6a10d-139">Wenn Sie beispielsweise nur Chat-und Anwesenheitsfeatures bereitstellen, aktivieren Sie das Kontrollkästchen **Konferenzen** , um mehrteiligen Chat zu ermöglichen, aber nicht die **Einwahl (PSTN)-Konferenz**, **Enterprise-VoIP**oder \*\* \*\*Kontrollkästchen für die Anrufsteuerung, da Sie die Features für sprach-, Video-und kollaborative Konferenzen darstellen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="6a10d-140">**Konferenzen**   diese Auswahl bietet eine Reihe von Funktionen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="6a10d-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="6a10d-141">Chatten mit mehr als zwei Teilnehmer in einer Chatsitzung.</span><span class="sxs-lookup"><span data-stu-id="6a10d-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="6a10d-142">Konferenz, die Zusammenarbeit in Dokumenten, Anwendungsfreigabe und Desktopfreigabe umfasst.</span><span class="sxs-lookup"><span data-stu-id="6a10d-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="6a10d-143">A/v-Konferenzen, mit denen Benutzer in Echtzeit Audio/Video-Konferenzen (a/v) führen können, ohne externe Dienste wie den Live Meeting-Dienst oder eine Audio-Bridge eines Drittanbieters zu benötigen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="6a10d-144">**Durch Einwahlkonferenzen**   (PSTN) können Benutzer an einem Audioteil einer lync Server 2013-Konferenz teilnehmen, indem Sie ein PSTN-Telefon (Public Switched Telephone Network) verwenden, ohne einen Audiokonferenz-Anbieter zu benötigen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="6a10d-145">**Enterprise Voice**   Enterprise-VoIP ist die VoIP-Lösung (Voice over IP) in lync Server 2013, mit der Benutzer Telefonanrufe tätigen und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="6a10d-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="6a10d-146">Sie würden dieses Feature bereitstellen, wenn Sie beabsichtigen, lync Server 2013 für Sprachanrufe, Voicemail und andere Funktionen zu verwenden, die ein Hardwaregerät oder einen Software Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a10d-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="6a10d-147">**Anrufannahme Steuerung (CAC)**   CAC ermittelt basierend auf der verfügbaren Netzwerkbandbreite, ob Echt Zeit Kommunikationssitzungen wie Sprach-oder Videoanrufe eingerichtet werden können.</span><span class="sxs-lookup"><span data-stu-id="6a10d-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="6a10d-148">Wenn Sie nur Chat und Anwesenheit bereitgestellt haben, ist CAC nicht erforderlich, da keine dieser beiden Features CAC verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a10d-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="6a10d-149">**Die Archivierungs**   Archivierung bietet eine Möglichkeit zum Archivieren von Chat Inhalten, Konferenz (Besprechungs-) Inhalten oder beidem, die über lync Server 2013 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="6a10d-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="6a10d-150">**Monitoring**   Monitoring Server ermöglicht Ihnen, numerische Daten zu sammeln, die die Medienqualität in Ihrem Netzwerk und Endpunkten beschreiben, Nutzungsinformationen zu VoIP-Anrufen, Chatnachrichten, A/V-Unterhaltungen, Besprechungen, Anwendungsfreigabe und Datei Übertragungen und Anruf Fehler sowie Informationen zur Problembehandlung bei fehlgeschlagenen anrufen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6a10d-151">Wenn Sie CAC in Ihrer Bereitstellung aktivieren möchten, müssen Sie CAC in genau einem Pool pro zentralen Standort aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6a10d-151">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site.</span></span> <span data-ttu-id="6a10d-152">CAC wird empfohlen, wenn Sie Sprachfeatures oder A/V-Konferenzen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-152">CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="6a10d-153">In der folgenden Tabelle sind die verfügbaren Funktionen (oben) und die den Benutzern angebotenen Funktionen (links) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a10d-153">The following table shows the available features (top) and the functions offered to users (left).</span></span> <span data-ttu-id="6a10d-154">Die Auswahl in der Tabelle ist das, was Sie auswählen sollten, um diese Features für Ihre Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6a10d-154">The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th><span data-ttu-id="6a10d-155">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="6a10d-155">Conferencing</span></span></th>
    <th><span data-ttu-id="6a10d-156">Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="6a10d-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="6a10d-157">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="6a10d-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="6a10d-158">Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="6a10d-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="6a10d-159">Chat und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="6a10d-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="6a10d-160">X</span><span class="sxs-lookup"><span data-stu-id="6a10d-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6a10d-161">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="6a10d-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="6a10d-162">X</span><span class="sxs-lookup"><span data-stu-id="6a10d-162">X</span></span></p></td>
    <td><p><span data-ttu-id="6a10d-163">X</span><span class="sxs-lookup"><span data-stu-id="6a10d-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6a10d-164">A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="6a10d-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="6a10d-165">X</span><span class="sxs-lookup"><span data-stu-id="6a10d-165">X</span></span></p></td>
    <td><p><span data-ttu-id="6a10d-166">X</span><span class="sxs-lookup"><span data-stu-id="6a10d-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="6a10d-167">X</span><span class="sxs-lookup"><span data-stu-id="6a10d-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6a10d-168">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="6a10d-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="6a10d-169">X</span><span class="sxs-lookup"><span data-stu-id="6a10d-169">X</span></span></p></td>
    <td><p><span data-ttu-id="6a10d-170">X</span><span class="sxs-lookup"><span data-stu-id="6a10d-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="6a10d-171">Auf der Seite **"Serverrollen auswählen** " können Sie den Vermittlungsserver auf dem Front-End-Server collocate oder als eigenständigen Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="6a10d-172">Sie können den Vermittlungs Server im Front-End-Pool collocate.</span><span class="sxs-lookup"><span data-stu-id="6a10d-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="6a10d-173">Wenn Sie beabsichtigen, den Vermittlungs Server im Front-End-Pool der Enterprise Edition collocate, stellen Sie sicher, dass das Kontrollkästchen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6a10d-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="6a10d-174">Die Serverrolle wird auf den Servern im Pool bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6a10d-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="6a10d-175">Wenn Sie den Vermittlungsserver als eigenständigen Server bereitstellen möchten, deaktivieren Sie das entsprechende Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="6a10d-176">Nachdem Sie den Front-End-Server vollständig bereitgestellt haben, werden Sie den Vermittlungsserver in einem separaten Bereitstellungsschritt bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6a10d-177">Wir empfehlen, dass Sie den Vermittlungs Server nach Möglichkeit collocate.</span><span class="sxs-lookup"><span data-stu-id="6a10d-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="6a10d-178">Ausführliche Informationen zur Unterstützung für sich selbst oder eigenständige Vermittlungsserver finden Sie unter <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Komponenten und Topologien für Mediation Server in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6a10d-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="6a10d-179">Mit der Seite **Serverrollen mit diesem Front-End-Pool verknüpfen** können Sie Serverrollen mit dem Front-End-Pool definieren und zuordnen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="6a10d-180">Die folgende Rolle ist verfügbar:</span><span class="sxs-lookup"><span data-stu-id="6a10d-180">The following role is available:</span></span>
    
    <span data-ttu-id="6a10d-181">**Aktivieren eines Edge-Pools**   definiert und ordnet einen einzelnen Edgeserver oder einen Pool von Edgeserver zu.</span><span class="sxs-lookup"><span data-stu-id="6a10d-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="6a10d-182">Ein Edgeserver vereinfacht die Kommunikation und Zusammenarbeit zwischen Benutzern innerhalb der Organisation und Personen außerhalb der Organisation, einschließlich Verbundbenutzern.</span><span class="sxs-lookup"><span data-stu-id="6a10d-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="6a10d-183">Es gibt zwei mögliche Szenarien, mit denen Sie die Serverrollen bereitstellen und zuordnen können:</span><span class="sxs-lookup"><span data-stu-id="6a10d-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="6a10d-184">In Szenario 1 definieren Sie eine neue Topologie für eine Neuinstallation.</span><span class="sxs-lookup"><span data-stu-id="6a10d-184">For scenario one, you are defining a new topology for a new installation.</span></span> <span data-ttu-id="6a10d-185">Sie können sich der Installation auf eine von zwei Arten nähern:</span><span class="sxs-lookup"><span data-stu-id="6a10d-185">You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="6a10d-186">Deaktivieren Sie das Kontrollkästchen, und fahren Sie mit dem Definieren der Topologie fort.</span><span class="sxs-lookup"><span data-stu-id="6a10d-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="6a10d-187">Nachdem Sie den Front-End-Server und den Back-End-Server veröffentlicht, konfiguriert und getestet haben, können Sie den Topologie-Generator erneut ausführen, um die Rollenserver zur Topologie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="6a10d-188">Mit dieser Strategie können Sie den Front-End-Pool und den Server, auf dem SQL Server ausgeführt wird, ohne zusätzliche Komplikationen durch zusätzliche Rollen testen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="6a10d-189">Wenn Sie die anfänglichen Tests abgeschlossen haben, können Sie den Topologie-Generator zur Auswahl der erforderlichen Rollen erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="6a10d-190">Wählen Sie die Rollen aus, die installiert werden müssen, und richten Sie anschließend die Hardware für die ausgewählten Rollen ein.</span><span class="sxs-lookup"><span data-stu-id="6a10d-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="6a10d-191">Für Szenario zwei verfügen Sie über eine vorhandene Bereitstellung, und ihre Infrastruktur ist für neue Rollen bereit, oder Sie müssen vorhandene Rollen einem neuen Front-End-Server zuordnen:</span><span class="sxs-lookup"><span data-stu-id="6a10d-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="6a10d-192">In diesem Fall wählen Sie die Rollen aus, die Sie dem neuen Front-End-Server bereitstellen oder zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="6a10d-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="6a10d-193">In beiden Fällen fahren Sie mit der Definition der Rollen fort, richten gegebenenfalls erforderliche Hardware ein und führen die Installation aus.</span><span class="sxs-lookup"><span data-stu-id="6a10d-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="6a10d-194">Führen Sie auf der Seite **SQL Store definieren** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6a10d-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="6a10d-195">Zum Verwenden eines SQL Server-Speichers, der bereits in Ihrer Topologie definiert wurde, wählen Sie eine Instanz unter **SQL-Speicher** aus.</span><span class="sxs-lookup"><span data-stu-id="6a10d-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="6a10d-196">Wenn Sie eine neue SQL Server-Instanz zum Speichern von Poolinformationen definieren möchten, klicken Sie auf **neu** , und geben Sie dann den **SQL Server-FQDN**im Dialogfeld **neuen SQL-Speicher definieren** ein.</span><span class="sxs-lookup"><span data-stu-id="6a10d-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="6a10d-197">Zum Angeben des Namens einer SQL Server-Instanz wählen Sie **Benannte Instanz** und geben Sie anschließend den Namen der Instanz an.</span><span class="sxs-lookup"><span data-stu-id="6a10d-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="6a10d-198">Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a10d-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="6a10d-199">Wenn Sie die SQL-Spiegelung verwenden möchten, wählen Sie **SQL-Spiegelung aktivieren** aus, und wählen Sie eine vorhandene Instanz aus, oder erstellen Sie eine neue Instanz.</span><span class="sxs-lookup"><span data-stu-id="6a10d-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="6a10d-200">Führen Sie auf der Seite " **Dateifreigabe definieren** " eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6a10d-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="6a10d-201">Zum Verwenden einer Dateifreigabe, die bereits in Ihrer Topologie definiert wurde, wählen Sie **Zuvor definierte Dateifreigabe verwenden**.</span><span class="sxs-lookup"><span data-stu-id="6a10d-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="6a10d-202">Zum Definieren einer neuen Dateifreigabe wählen Sie **Neue Dateifreigabe definieren**, geben Sie im Feld **Dateiserver-FQDN** den vollqualifizierten Domänennamen des vorhandenen Dateiservers ein, auf dem sich die Dateifreigabe befinden soll, und geben Sie anschließend einen Namen für die Dateifreigabe in das Feld **Dateifreigabe** ein.</span><span class="sxs-lookup"><span data-stu-id="6a10d-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="6a10d-203">Die Dateifreigabe für lync Server 2013 kann nicht auf dem Front-End-Server gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="6a10d-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="6a10d-204">Beachten Sie, dass sich die Dateifreigabe in diesem Beispiel auf dem auf SQL Server basierenden Back-End-Server befand.</span><span class="sxs-lookup"><span data-stu-id="6a10d-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="6a10d-205">Dies ist möglicherweise kein optimaler Ort für die Anforderungen Ihrer Organisation, und ein Dateiserver ist möglicherweise eine bessere Wahl.</span><span class="sxs-lookup"><span data-stu-id="6a10d-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="6a10d-206">Sie können die Dateifreigabe definieren, ohne sie erstellt zu haben.</span><span class="sxs-lookup"><span data-stu-id="6a10d-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="6a10d-207">Sie müssen die Dateifreigabe am definierten Speicherort erstellen, bevor Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="6a10d-208">Führen Sie auf der Seite **Geben Sie die Webdienste-URL** an eine oder beide der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6a10d-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="6a10d-209">Die Basis-URL ist die Webdienstidentität der URL ohne https://.</span><span class="sxs-lookup"><span data-stu-id="6a10d-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="6a10d-210">Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet https://pool01.contoso.net, lautet die Basis-URL pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="6a10d-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="6a10d-211">Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN für externe Webdienste eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="6a10d-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="6a10d-212">Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a10d-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="6a10d-213">Wenn Sie den DNS-Lastenausgleich konfigurieren, aktivieren Sie das Kontrollkästchen Interner FQDN des Webdienste- **Pools außer Kraft setzen** , geben Sie die interne Basis-URL ein (die sich vom FQDN des Pools unter\<scheiden muss und\>beispielsweise Internal-ihre Basis-URL sein kann) in \*\* Interne Basis-URL\*\*.</span><span class="sxs-lookup"><span data-stu-id="6a10d-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="6a10d-214">Wenn Sie sich entscheiden, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="6a10d-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="6a10d-215"><STRONG>Verwenden Sie nur Standardzeichen</STRONG> (A – Z, a – z, 0 – 9 und Bindestriche), wenn Sie URLs oder vollqualifizierte Domänennamen definieren.</span><span class="sxs-lookup"><span data-stu-id="6a10d-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="6a10d-216">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="6a10d-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="6a10d-217">Nicht-Standardzeichen in einem URL oder vollqualifizierten Domänennamen (FQDN) werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn die URL oder der FQDN dem Antragstellernamen oder dem alternativen Antragstellernamen im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6a10d-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="6a10d-218">Optional können Sie die externe Basis-URL in der **externen Basis-URL**eingeben.</span><span class="sxs-lookup"><span data-stu-id="6a10d-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="6a10d-219">Sie würden die externe Basis-URL eingeben, um Sie von ihrer internen Domänen Namensgebung zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="6a10d-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="6a10d-220">Beispielsweise ist Ihre interne Domäne contoso.net, aber ihr externer Domänenname lautet contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6a10d-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="6a10d-221">Sie würden die URL mit dem contoso.com-Domänennamen definieren.</span><span class="sxs-lookup"><span data-stu-id="6a10d-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="6a10d-222">Dies ist auch im Fall eines Reverseproxys wichtig.</span><span class="sxs-lookup"><span data-stu-id="6a10d-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="6a10d-223">Der Domänenname der externen Basis-URL würde dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="6a10d-224">Für Sofortnachrichten und Anwesenheitsinformationen ist der HTTP-Zugriff auf den Front-End-Pool erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6a10d-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6a10d-225">Wenn Sie den DNS-Lastenausgleich verwenden möchten, müssen Sie die entsprechenden DNS-Einträge erstellen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="6a10d-226">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-dns-for-load-balancing.md">Konfigurieren von DNS für den Lastenausgleich in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6a10d-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="6a10d-227">Wenn Sie auf der Seite **"Features auswählen** " **Konferenzen** ausgewählt haben, wählen Sie auf der Seite Wählen Sie **eine Office Web Apps Server** aus die Option **Pool mit einem Office Web Apps-Server verknüpfen** aus, und klicken Sie dann auf **neu** (oder wählen Sie eine vorhandene Office Web Apps aus. Server aus der Dropdownliste).</span><span class="sxs-lookup"><span data-stu-id="6a10d-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="6a10d-228">Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.</span><span class="sxs-lookup"><span data-stu-id="6a10d-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="6a10d-229">Wenn der Office Web Apps-Server lokal und in derselben Netzwerkzone wie lync Server 2013 installiert ist, sollte die Option **Office Web Apps Server in einem externen Netzwerk bereitgestellt werden (also Umkreis/Internet)** , nicht ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="6a10d-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="6a10d-230">Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.</span><span class="sxs-lookup"><span data-stu-id="6a10d-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6a10d-231">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration in Office Web Apps Server und lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6a10d-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="6a10d-232">Wählen Sie auf der Seite **Archivierungs-SQL-Speicher definieren** eine vorhandene Instanz oder SQL Server aus, oder definieren Sie eine neue Instanz zum Speichern der Daten, die mit den Archivierungsdaten verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="6a10d-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="6a10d-233">Wählen Sie auf der Seite **Definieren der Überwachung des SQL Stores** eine vorhandene Instanz oder SQL Server aus, oder definieren Sie eine neue Instanz zum Speichern der Daten, die mit Überwachungsdaten verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="6a10d-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="6a10d-234">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6a10d-234">Click **Next**.</span></span> <span data-ttu-id="6a10d-235">Wenn Sie auf der Seite **Serverrollen mit diesem Front-End-Pool zuordnen** andere Rollen Server definiert haben, werden die Seiten des Assistenten für die Rollenkonfiguration separat geöffnet, damit Sie die Serverrollen konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="6a10d-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="6a10d-236">Ausführliche Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="6a10d-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="6a10d-237">Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a10d-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="6a10d-238">Wenn Sie keine zusätzlichen Serverrollen zum Konfigurieren und Bereitstellen ausgewählt haben oder wenn Sie die Konfiguration der zusätzlichen Rollen Server abgeschlossen haben, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="6a10d-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

