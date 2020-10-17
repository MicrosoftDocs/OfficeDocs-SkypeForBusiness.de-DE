---
title: 'Lync Server 2013: Überprüfen der Konfiguration von Office-webapps Server'
description: 'Lync Server 2013: Überprüfen der Konfiguration von Office-webapps Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80c3160dd9a76c129fbb0289929a868b897beb2c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547151"
---
# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="c2d3e-103">Überprüfen der Konfiguration von Office-webapps Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2d3e-103">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2d3e-104">_**Letztes Änderungsstand des Themas:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="c2d3e-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="c2d3e-105">Nachdem Office webapps Server zur Topologie hinzugefügt wurde und diese Topologie veröffentlicht wurde, sollten im lync Server Ereignisprotokoll zwei neue Ereignisprotokoll Ereignisse angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-105">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="c2d3e-106">Zunächst sollte ein ls Data MCU-Ereignis (Ereigniskennung 41034) hinzugefügt werden; Dieses Ereignis meldet, dass der Office-webapps-Server erkannt wurde:</span><span class="sxs-lookup"><span data-stu-id="c2d3e-106">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="c2d3e-107">**Webkonferenzserver Office-webapps-Server wird ermittelt, PowerPoint-Inhalte sind aktiviert.**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-107">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="c2d3e-108">Darüber hinaus sollte ein weiteres ls Data MCU-Ereignis (Ereigniskennung 41032) angezeigt werden, das Office-webapps-Server-URLs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-108">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs.</span></span> <span data-ttu-id="c2d3e-109">Beispielsweise sollten Sie etwas Ähnliches sehen:</span><span class="sxs-lookup"><span data-stu-id="c2d3e-109">For example, you should see something similar to this:</span></span>

<span data-ttu-id="c2d3e-110">**Die Office-webapps-Server Ermittlung für den Webkonferenzserver ist erfolgreich.**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-110">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="c2d3e-111">**Interne Office-webapps-Server-Referenten Seite: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-111">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="c2d3e-112">**Office-webapps-Server-interne Teilnehmerseite: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-112">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="c2d3e-113">**Externe Referenten Seite von Office-webapps Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-113">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="c2d3e-114">**Office-webapps-Server-interne Teilnehmerseite: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="c2d3e-114">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="c2d3e-115">Wenn ein ls Data MCU-Ereignis mit der Ereignis-ID 41033 angezeigt wird, bedeutet dies, dass die Ermittlung von Office-webapps-Servern fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-115">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="c2d3e-116">In diesem Fall versucht Microsoft lync Server 2013 so oft wie erforderlich, den neu konfigurierten Office-webapps-Server zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-116">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="c2d3e-117">Wenn der Ermittlungsprozess wiederholt fehlschlägt, sollten Sie Office-webappsserver aus Ihrem Topologie-Dokument entfernen, die aktualisierte Topologie veröffentlichen und dann Office-webapps-Server wieder der Topologie hinzufügen, nachdem die Verbindungsprobleme behoben wurden.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-117">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="c2d3e-118">Wenn Office-webapps-Server anscheinend ordnungsgemäß konfiguriert ist und durch den Ermittlungsprozess erkannt wurde, können Sie sicherstellen, dass Office-webapps Server wie erwartet funktioniert, indem Sie eine PowerPoint-Präsentation zwischen einem Paar Microsoft lync 2013 Clients freigeben.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-118">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="c2d3e-119">Wenn Benutzer a die PowerPoint-Präsentation laden und anzeigen kann und wenn Benutzer B dann an der Besprechung teilnehmen und diese Präsentation sehen kann, funktioniert Office-webapps-Server.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-119">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="c2d3e-120">Selbst wenn Office-webapps-Server anscheinend ordnungsgemäß konfiguriert ist, könnten Sie möglicherweise die Fehlermeldung "einige Freigabefunktionen sind aufgrund von Server Verbindungsproblemen nicht verfügbar" erhalten, wenn Sie versuchen, eine PowerPoint-Präsentation freizugeben.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-120">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="c2d3e-121">Wenn Sie diese Fehlermeldung erhalten, sollten Sie den Front-End-Server (oder Server) neu starten, der dem neuen Office-webapps-Server zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c2d3e-121">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

