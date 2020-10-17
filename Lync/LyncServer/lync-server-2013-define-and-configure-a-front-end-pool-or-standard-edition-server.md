---
title: Definieren und Konfigurieren eines Front-End-Pool oder Standard Edition-Server
description: Definieren und Konfigurieren eines Front-End-Pool oder Standard Edition-Servers.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd632564f0a5afd1f899ee8487f633c4685d12a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569981"
---
# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="457f8-103">Definieren und Konfigurieren eines Front-End-Pool oder Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457f8-103">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="457f8-104">_**Letztes Änderungsstand des Themas:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="457f8-104">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="457f8-p101">Für dieses Verfahren ist keine Mitgliedschaft in einer lokalen Administratorgruppe oder einer Domänengruppe mit besonderen Rechten erforderlich. Melden Sie sich als Standardbenutzer bei einem Computer an.</span><span class="sxs-lookup"><span data-stu-id="457f8-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="457f8-107">Wenn Sie einen Enterprise-Server bereitstellen, muss immer eine Mindestanzahl von Front-End-Servern in einem Pool installiert sein.</span><span class="sxs-lookup"><span data-stu-id="457f8-107">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="457f8-108">Eine Übersicht über diese Mindestanzahl finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="457f8-108">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="457f8-109">Gesamtanzahl der Front-End-Server im Pool</span><span class="sxs-lookup"><span data-stu-id="457f8-109">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="457f8-110">Anzahl der Server, die für die korrekte Funktionsweise des Pools ausgeführt werden müssen</span><span class="sxs-lookup"><span data-stu-id="457f8-110">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="457f8-111">1-2</span><span class="sxs-lookup"><span data-stu-id="457f8-111">1-2</span></span></p></td>
<td><p><span data-ttu-id="457f8-112">1</span><span class="sxs-lookup"><span data-stu-id="457f8-112">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="457f8-113">3-4</span><span class="sxs-lookup"><span data-stu-id="457f8-113">3-4</span></span></p></td>
<td><p><span data-ttu-id="457f8-114">2</span><span class="sxs-lookup"><span data-stu-id="457f8-114">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="457f8-115">5-6</span><span class="sxs-lookup"><span data-stu-id="457f8-115">5-6</span></span></p></td>
<td><p><span data-ttu-id="457f8-116">3</span><span class="sxs-lookup"><span data-stu-id="457f8-116">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="457f8-117">7-8</span><span class="sxs-lookup"><span data-stu-id="457f8-117">7-8</span></span></p></td>
<td><p><span data-ttu-id="457f8-118">4 </span><span class="sxs-lookup"><span data-stu-id="457f8-118">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="457f8-119">9-10</span><span class="sxs-lookup"><span data-stu-id="457f8-119">9-10</span></span></p></td>
<td><p><span data-ttu-id="457f8-120">5 </span><span class="sxs-lookup"><span data-stu-id="457f8-120">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="457f8-121">11-12</span><span class="sxs-lookup"><span data-stu-id="457f8-121">11-12</span></span></p></td>
<td><p><span data-ttu-id="457f8-122">6 </span><span class="sxs-lookup"><span data-stu-id="457f8-122">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="457f8-123">Für lync Server 2013 müssen Sie bei jedem Hinzufügen oder Entfernen eines Front-End-Server aus dem Pool Dienste neu starten.</span><span class="sxs-lookup"><span data-stu-id="457f8-123">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="457f8-124">Das Entfernen und Hinzufügen von Servern sollte als separate Vorgänge erfolgen.</span><span class="sxs-lookup"><span data-stu-id="457f8-124">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="457f8-125">Wenn Sie beispielsweise zwei Front-End-Server hinzufügen und zwei Front-End-Server entfernen möchten, verwenden Sie den folgenden Prozess:</span><span class="sxs-lookup"><span data-stu-id="457f8-125">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="457f8-126">Entfernen Sie die beiden Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="457f8-126">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="457f8-127">Veröffentlichen Sie die Topologie, und aktivieren Sie sie erneut.</span><span class="sxs-lookup"><span data-stu-id="457f8-127">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="457f8-128">Starten Sie die Dienste neu.</span><span class="sxs-lookup"><span data-stu-id="457f8-128">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="457f8-129">Fügen Sie die beiden Front-End-Server hinzu.</span><span class="sxs-lookup"><span data-stu-id="457f8-129">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="457f8-130">Veröffentlichen Sie die Topologie, und aktivieren Sie sie erneut.</span><span class="sxs-lookup"><span data-stu-id="457f8-130">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="457f8-131">Starten Sie die Dienste neu.</span><span class="sxs-lookup"><span data-stu-id="457f8-131">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="457f8-132">Nachdem Sie Ihre Topologie definiert haben, verwenden Sie das folgende Verfahren, um eine Front-End-Pool für Ihre Website zu definieren.</span><span class="sxs-lookup"><span data-stu-id="457f8-132">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="457f8-133">Ausführliche Informationen zum Definieren der Topologie finden Sie unter [definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="457f8-133">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="457f8-134">So definieren Sie eine Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="457f8-134">To define a Front End pool</span></span>

1.  <span data-ttu-id="457f8-135">Klicken Sie im Assistenten zum Definieren eines neuen Front-End-Pools auf der Seite **Neuen Front-End-Pool definieren** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="457f8-135">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="457f8-136">Geben Sie auf der Seite **Front-End-Pool FQDN definieren** einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool ein, den Sie erstellen möchten, klicken Sie auf **Enterprise Edition Front-End-Pool**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="457f8-136">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="457f8-137">Geben Sie auf der Seite **Computer in diesem Pool definieren** einen Computer-FQDN für den ersten Front-End-Server im Pool ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="457f8-137">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="457f8-138">Wiederholen Sie diesen Schritt für alle weiteren Computer (bis zu zwölf), die Sie dem Pool hinzufügen möchten, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="457f8-138">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="457f8-139">Aktivieren Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die in diesem Front-End-Pool werden sollen.</span><span class="sxs-lookup"><span data-stu-id="457f8-139">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="457f8-140">Wenn Sie beispielsweise nur Instant Messaging-und Anwesenheitsfunktionen bereitstellen, aktivieren Sie das Kontrollkästchen **Konferenzen** , um mehrteiligen Chat zu ermöglichen, aber nicht die Kontrollkästchen **Einwahlkonferenzen**, **Enterprise-VoIP**oder **Anrufsteuerung** auswählen, da Sie die Features für VoIP, Video und gemeinschaftliche Konferenzen darstellen.</span><span class="sxs-lookup"><span data-stu-id="457f8-140">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="457f8-141">**Konferenzen**     Diese Auswahl ermöglicht eine umfangreiche Palette von Features, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="457f8-141">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="457f8-142">Sofortnachrichten mit mehr als zwei Teilnehmern in einer Sofortnachrichtenfunktionsitzung</span><span class="sxs-lookup"><span data-stu-id="457f8-142">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="457f8-143">Konferenzfunktionen, u. a. Dokumentzusammenarbeit, Anwendungsfreigabe und Desktopfreigabe</span><span class="sxs-lookup"><span data-stu-id="457f8-143">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="457f8-144">A/v-Konferenzen, die es Benutzern ermöglichen, Echtzeit-Audio/Video-Konferenzen (a/v) zu haben, ohne externe Dienste wie den Live Meeting-Dienst oder eine Audio-Bridge eines Drittanbieters zu benötigen.</span><span class="sxs-lookup"><span data-stu-id="457f8-144">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="457f8-145">**Einwahlkonferenzen**     (PSTN) Ermöglicht Benutzern die Teilnahme am Audioteil einer lync Server 2013 Konferenz mithilfe eines PSTN-Telefons (Public Switched Telephone Network), ohne dass ein Anbieter für Audiokonferenzen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="457f8-145">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="457f8-146">**Enterprise-VoIP**     Enterprise-VoIP ist die VoIP-Lösung (Voice over IP) in lync Server 2013, mit der Benutzer Telefonanrufe tätigen und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="457f8-146">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="457f8-147">Sie möchten dieses Feature bereitstellen, wenn Sie lync Server 2013 für Sprachanrufe, Voicemail und andere Funktionen verwenden möchten, die ein Hardwaregerät oder einen Software Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="457f8-147">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="457f8-148">**Anrufsteuerung (Call Admission Control, CAC)**     Bei der Anrufsteuerung wird basierend auf der verfügbaren Netzwerkbandbreite festgelegt, ob Echt Zeit Kommunikationssitzungen wie Sprach-oder Videoanrufe eingerichtet werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="457f8-148">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="457f8-149">Wenn Sie lediglich Sofortnachrichten- und Anwesenheitsfunktionen bereitgestellt haben, wird die Anrufsteuerung nicht benötigt, da diese Funktionen die Anrufsteuerung nicht nutzen.</span><span class="sxs-lookup"><span data-stu-id="457f8-149">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="457f8-150">**Archivierung**     Die Archivierung bietet Ihnen die Möglichkeit, Chatinhalte, Konferenzinhalte (Besprechungen) oder beides zu archivieren, die über lync Server 2013 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="457f8-150">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="457f8-151">**Überwachung**     Mit Monitoring Server können Sie numerische Daten erfassen, die die Medienqualität in Ihrem Netzwerk und Endpunkten, Nutzungsinformationen im Zusammenhang mit VoIP-Anrufen, Chatnachrichten, A/V-Unterhaltungen, Besprechungen, Anwendungsfreigabe und Dateiübertragungen sowie Anruf Fehler-und Problembehandlungsinformationen für fehlgeschlagene Anrufe beschreiben.</span><span class="sxs-lookup"><span data-stu-id="457f8-151">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="457f8-p109">Zum Aktivieren der Anrufsteuerung in Ihrer Bereitstellung müssen Sie diese Funktion in genau einem Pool pro zentralem Standort aktivieren. Die Anrufsteuerung wird empfohlen, wenn Sie VoIP-Funktionen oder die A/V-Konferenzfunktion bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="457f8-p109">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site. CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="457f8-p110">In der folgenden Tabelle sind die verfügbaren Funktionen (oben) sowie die für die Benutzer bereitgestellten Funktionen (links) aufgeführt. Um diese Funktionen für Ihre Organisation zu aktivieren, treffen Sie die in der Tabelle gezeigte Auswahl.</span><span class="sxs-lookup"><span data-stu-id="457f8-p110">The following table shows the available features (top) and the functions offered to users (left). The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
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
    <th><span data-ttu-id="457f8-156">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="457f8-156">Conferencing</span></span></th>
    <th><span data-ttu-id="457f8-157">Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="457f8-157">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="457f8-158">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="457f8-158">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="457f8-159">Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="457f8-159">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="457f8-160">Sofortnachrichten und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="457f8-160">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="457f8-161">X</span><span class="sxs-lookup"><span data-stu-id="457f8-161">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="457f8-162">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="457f8-162">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="457f8-163">X</span><span class="sxs-lookup"><span data-stu-id="457f8-163">X</span></span></p></td>
    <td><p><span data-ttu-id="457f8-164">X</span><span class="sxs-lookup"><span data-stu-id="457f8-164">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="457f8-165">A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="457f8-165">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="457f8-166">X</span><span class="sxs-lookup"><span data-stu-id="457f8-166">X</span></span></p></td>
    <td><p><span data-ttu-id="457f8-167">X</span><span class="sxs-lookup"><span data-stu-id="457f8-167">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="457f8-168">X</span><span class="sxs-lookup"><span data-stu-id="457f8-168">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="457f8-169">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="457f8-169">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="457f8-170">X</span><span class="sxs-lookup"><span data-stu-id="457f8-170">X</span></span></p></td>
    <td><p><span data-ttu-id="457f8-171">X</span><span class="sxs-lookup"><span data-stu-id="457f8-171">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="457f8-172">Auf der Seite verbundene **Serverrollen auswählen** können Sie die Vermittlungsserver im Front-End-Server collocate oder als eigenständigen Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="457f8-172">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="457f8-173">Sie können die Vermittlungsserver im Front-End-Pool collocate.</span><span class="sxs-lookup"><span data-stu-id="457f8-173">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="457f8-174">Wenn Sie beabsichtigen, die Vermittlungsserver im Enterprise Edition-Front-End-Pool collocate, stellen Sie sicher, dass das Kontrollkästchen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="457f8-174">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="457f8-175">Die Serverrolle wird auf den Poolservern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="457f8-175">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="457f8-176">Wenn Sie die Vermittlungsserver als eigenständigen Server bereitstellen möchten, deaktivieren Sie das entsprechende Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="457f8-176">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="457f8-177">Sie werden Vermittlungsserver in einem separaten Bereitstellungsschritt bereitstellen, nachdem Sie die Front-End-Server vollständig bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="457f8-177">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="457f8-178">Es wird empfohlen, wenn möglich den Vermittlungsserver zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="457f8-178">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="457f8-179">Ausführliche Informationen zur Unterstützung für verbundene oder eigenständige Vermittlungsserver finden Sie unter <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and Topologies for Vermittlungsserver in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="457f8-179">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="457f8-180">Auf der Seite **Serverrollen mit dieser Front-End-Pool zuordnen** können Sie Serverrollen mit dem Front-End-Pool definieren und zuordnen.</span><span class="sxs-lookup"><span data-stu-id="457f8-180">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="457f8-181">Die folgende Rolle ist verfügbar:</span><span class="sxs-lookup"><span data-stu-id="457f8-181">The following role is available:</span></span>
    
    <span data-ttu-id="457f8-182">**Aktivieren eines Edgepool**     Definiert und ordnet einem einzelnen Edgeserver oder einem Pool von Edgeserver zu.</span><span class="sxs-lookup"><span data-stu-id="457f8-182">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="457f8-183">Eine Edgeserver erleichtert die Kommunikation und Zusammenarbeit zwischen Benutzern innerhalb der Organisation und Personen außerhalb der Organisation, einschließlich Verbundbenutzern.</span><span class="sxs-lookup"><span data-stu-id="457f8-183">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="457f8-184">Für die Bereitstellung und Zuordnung der Serverrollen sind zwei Szenarien möglich:</span><span class="sxs-lookup"><span data-stu-id="457f8-184">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="457f8-p116">In Szenario 1 definieren Sie eine neue Topologie für eine Neuinstallation. Die Installation kann über zwei Methoden ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="457f8-p116">For scenario one, you are defining a new topology for a new installation. You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="457f8-187">Lassen Sie das Kontrollkästchen deaktiviert, und fahren Sie mit der Topologiedefinition fort.</span><span class="sxs-lookup"><span data-stu-id="457f8-187">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="457f8-188">Nachdem Sie die Front-End-und Back-End-Server Rollen veröffentlicht, konfiguriert und getestet haben, können Sie den Topologie-Generator erneut ausführen, um die Rollen Server zur Topologie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="457f8-188">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="457f8-189">Mit dieser Strategie können Sie die Front-End-Pool und den Server, auf dem SQL Server läuft, ohne zusätzliche Komplikationen durch zusätzliche Rollen testen.</span><span class="sxs-lookup"><span data-stu-id="457f8-189">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="457f8-190">Nachdem Sie die ersten Tests abgeschlossen haben, können Sie den Topologie-Generator erneut ausführen, um die Rollen auszuwählen, die Sie bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="457f8-190">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="457f8-191">Wählen Sie die Rollen aus, die installiert werden müssen, und richten Sie anschließend die Hardware für die ausgewählten Rollen ein.</span><span class="sxs-lookup"><span data-stu-id="457f8-191">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="457f8-192">Für Szenario 2 verfügen Sie über eine vorhandene Bereitstellung, und ihre Infrastruktur ist bereit für neue Rollen, oder Sie müssen vorhandene Rollen einer neuen Front-End-Server zuordnen:</span><span class="sxs-lookup"><span data-stu-id="457f8-192">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="457f8-193">In diesem Fall wählen Sie die Rollen aus, die Sie dem neuen Front-End-Server bereitstellen oder zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="457f8-193">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="457f8-194">In beiden Fällen fahren Sie mit der Definition der Rollen fort, richten gegebenenfalls erforderliche Hardware ein und führen die Installation aus.</span><span class="sxs-lookup"><span data-stu-id="457f8-194">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="457f8-195">Führen Sie auf der Seite **SQL-Speicher definieren** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="457f8-195">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="457f8-196">Zum Verwenden eines vorhandenen SQL Server-Speichers, der bereits in Ihrer Topologie definiert wurde, wählen Sie eine Instanz unter **SQL-Speicher** aus.</span><span class="sxs-lookup"><span data-stu-id="457f8-196">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="457f8-197">Zum Definieren einer neuen SQL Server Instanz zum Speichern von Poolinformationen klicken Sie auf **neu** , und geben Sie dann im Dialogfeld **neuen SQL-Speicher definieren** den **FQDN SQL Server**an.</span><span class="sxs-lookup"><span data-stu-id="457f8-197">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="457f8-198">Zum Angeben des Namens einer SQL Server-Instanz wählen Sie **Benannte Instanz**, und geben Sie anschließend den Namen der Instanz an.</span><span class="sxs-lookup"><span data-stu-id="457f8-198">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="457f8-199">Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="457f8-199">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="457f8-200">Zum Verwenden der SQL-Spiegelung wählen Sie **SQL-Spiegelung aktivieren** aus, und wählen Sie dann eine vorhandene Instanz aus, oder erstellen Sie eine neue Instanz.</span><span class="sxs-lookup"><span data-stu-id="457f8-200">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="457f8-201">Führen Sie auf der Seite **Dateifreigabe definieren** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="457f8-201">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="457f8-202">Zum Verwenden einer Dateifreigabe, die bereits in Ihrer Topologie definiert wurde, wählen Sie **Zuvor definierte Dateifreigabe verwenden**.</span><span class="sxs-lookup"><span data-stu-id="457f8-202">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="457f8-203">Zum Definieren einer neuen Dateifreigabe wählen Sie **Neue Dateifreigabe definieren**, geben Sie im Feld **Dateiserver-FQDN** den vollqualifizierten Domänennamen des vorhandenen Dateiservers ein, auf dem sich die Dateifreigabe befinden soll, und geben Sie anschließend einen Namen für die Dateifreigabe in das Feld **Dateifreigabe** ein.</span><span class="sxs-lookup"><span data-stu-id="457f8-203">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="457f8-204">Die Dateifreigabe für lync Server 2013 kann sich nicht auf dem Front-End-Server befinden.</span><span class="sxs-lookup"><span data-stu-id="457f8-204">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="457f8-205">Beachten Sie, das die Dateifreigabe in diesem Beispiel auf dem SQL Server-basierten Back-End-Server platziert wurde.</span><span class="sxs-lookup"><span data-stu-id="457f8-205">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="457f8-206">Möglicherweise ist dies nicht der optimale Speicherort für die Anforderungen Ihrer Organisation, und ein Dateiserver wäre die bessere Wahl.</span><span class="sxs-lookup"><span data-stu-id="457f8-206">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="457f8-207">Sie können die Dateifreigabe definieren, ohne dass die Dateifreigabe erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="457f8-207">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="457f8-208">Sie müssen die Dateifreigabe am definierten Speicherort erstellen, bevor Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="457f8-208">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="457f8-209">Führen Sie auf der Seite **Webdienste-URL angeben** einen oder mehrere der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="457f8-209">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="457f8-210">Die Basis-URL ist die Webdienstidentität der URL ohne https://.</span><span class="sxs-lookup"><span data-stu-id="457f8-210">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="457f8-211">Wenn beispielsweise die vollständige URL für die Webdienste des Pools ist https://pool01.contoso.net , lautet die Basis-URL pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="457f8-211">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="457f8-212">Wenn Sie mehr als eine Front-End-Pool oder Front-End-Server haben, muss der FQDN für externe Webdienste eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="457f8-212">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="457f8-213">Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Server als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für eine andere Front-End-Pool oder Front-End-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="457f8-213">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="457f8-214">Wenn Sie den DNS-Lastenausgleich konfigurieren, aktivieren Sie das Kontrollkästchen **internen Webdienste Pool-FQDN außer Kraft setzen** , geben Sie die interne Basis-URL (die sich vom Pool-FQDN unterscheiden muss und beispielsweise Internal sein kann \<your base URL\> ) in die **interne Basis-URL**ein.</span><span class="sxs-lookup"><span data-stu-id="457f8-214">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="457f8-215">Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="457f8-215">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="457f8-216"><STRONG>Verwenden Sie nur Standardzeichen</STRONG> (einschließlich a – z, a – z, 0 – 9 und Bindestriche), wenn Sie URLs oder vollqualifizierte Domänennamen definieren.</span><span class="sxs-lookup"><span data-stu-id="457f8-216"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="457f8-217">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="457f8-217">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="457f8-218">Nicht Standardzeichen in einer URL oder einem FQDN werden von externen DNS-und öffentlichen CAS häufig nicht unterstützt (das heißt, wenn die URL oder der FQDN dem Antragstellernamen oder dem alternativen Antragstellernamen im Zertifikat zugewiesen werden muss).</span><span class="sxs-lookup"><span data-stu-id="457f8-218">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="457f8-219">Optional geben Sie die externe Basis-URL im Feld **Externe Basis-URL** ein.</span><span class="sxs-lookup"><span data-stu-id="457f8-219">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="457f8-220">Die externe Basis-URL wird zur Unterscheidung dieser URL von Ihrer internen Domänenbenennung eingegeben.</span><span class="sxs-lookup"><span data-stu-id="457f8-220">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="457f8-221">Beispiel: der Name Ihrer internen Domäne lautet "contoso.net", der Name Ihrer externen Domäne lautet "contoso.com".</span><span class="sxs-lookup"><span data-stu-id="457f8-221">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="457f8-222">Zur Definition der URL würden Sie den Domänennamen "contoso.com" verwenden.</span><span class="sxs-lookup"><span data-stu-id="457f8-222">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="457f8-223">Dies ist auch im Fall eines Reverseproxys wichtig.</span><span class="sxs-lookup"><span data-stu-id="457f8-223">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="457f8-224">Der Domänenname der externen Basis-URL würde dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen.</span><span class="sxs-lookup"><span data-stu-id="457f8-224">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="457f8-225">Für Chatnachrichten und Anwesenheitsinformationen ist der HTTP-Zugriff auf die Front-End-Pool erforderlich.</span><span class="sxs-lookup"><span data-stu-id="457f8-225">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="457f8-226">Zur Verwendung des DNS-Lastenausgleichs müssen Sie die entsprechenden DNS-Einträge erstellen.</span><span class="sxs-lookup"><span data-stu-id="457f8-226">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="457f8-227">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-dns-for-load-balancing.md">Konfigurieren von DNS für den Lastenausgleich in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="457f8-227">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="457f8-228">Wenn Sie auf der Seite **Features auswählen** die Option **Konferenzen** ausgewählt haben, wählen Sie auf der Seite **Office-webappsserver auswählen** die Option **Pool mit einem Office-webappsserver zuordnen** aus, und klicken Sie dann auf **neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office-webapps-Server aus).</span><span class="sxs-lookup"><span data-stu-id="457f8-228">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="457f8-229">Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.</span><span class="sxs-lookup"><span data-stu-id="457f8-229">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="457f8-230">Wenn der Office Web Apps-Server lokal und in der gleichen Netzwerkzone wie lync Server 2013 installiert ist, sollte die Option **Office Web Apps Server in einem externen Netzwerk bereitgestellt werden (d. "Perimeter/Internet")** sollte nicht ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="457f8-230">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="457f8-231">Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.</span><span class="sxs-lookup"><span data-stu-id="457f8-231">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="457f8-232">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration mit Office-webapps Server und lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="457f8-232">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="457f8-233">Wählen Sie auf der Seite **Archivierungs-SQL-Speicher definieren** eine vorhandene Instanz von SQL Server aus, oder definieren Sie eine neue Instanz, um die Daten zu speichern, die den Archivierungsdaten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="457f8-233">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="457f8-234">Wählen Sie auf der Seite **Monitoring-SQL-Speicher definieren** eine vorhandene Instanz von SQL Server aus, oder definieren Sie eine neue Instanz, um die Daten zu speichern, die den Überwachungsdaten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="457f8-234">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="457f8-235">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="457f8-235">Click **Next**.</span></span> <span data-ttu-id="457f8-236">Wenn Sie auf der Seite **Serverrollen mit dieser Front-End-Pool zuordnen** andere Rollen Server definiert haben, werden separate Seiten des Rollen Konfigurations-Assistenten geöffnet, über die Sie die Serverrollen konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="457f8-236">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="457f8-237">Ausführliche Informationen finden Sie im Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="457f8-237">For details, see the following:</span></span>
    
    [<span data-ttu-id="457f8-238">Bereitstellen von externem Benutzer Zugriff in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457f8-238">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="457f8-239">Wenn Sie keine zusätzlichen Serverrollen ausgewählt haben, die konfiguriert und bereitgestellt werden sollen, oder wenn Sie die Konfiguration der zusätzlichen Rollenserver abgeschlossen haben, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="457f8-239">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

