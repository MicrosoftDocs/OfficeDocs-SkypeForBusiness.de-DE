---
title: 'Lync Server 2013: Überprüfen der Konfiguration von Office-webapps Server'
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
ms.openlocfilehash: 0a33a5e9bb93371bdccac3c88b7a1c080e3efaa8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503682"
---
# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="b4cbc-102">Überprüfen der Konfiguration von Office-webapps Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4cbc-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4cbc-103">_**Letztes Änderungsstand des Themas:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="b4cbc-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="b4cbc-104">Nachdem Office webapps Server zur Topologie hinzugefügt wurde und diese Topologie veröffentlicht wurde, sollten im lync Server Ereignisprotokoll zwei neue Ereignisprotokoll Ereignisse angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b4cbc-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="b4cbc-105">Zunächst sollte ein ls Data MCU-Ereignis (Ereigniskennung 41034) hinzugefügt werden; Dieses Ereignis meldet, dass der Office-webapps-Server erkannt wurde:</span><span class="sxs-lookup"><span data-stu-id="b4cbc-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="b4cbc-106">**Webkonferenzserver Office-webapps-Server wird ermittelt, PowerPoint-Inhalte sind aktiviert.**</span><span class="sxs-lookup"><span data-stu-id="b4cbc-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="b4cbc-107">Darüber hinaus sollte ein weiteres ls Data MCU-Ereignis (Ereigniskennung 41032) angezeigt werden, das Office-webapps-Server-URLs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b4cbc-107">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs.</span></span> <span data-ttu-id="b4cbc-108">Beispielsweise sollten Sie etwas Ähnliches sehen:</span><span class="sxs-lookup"><span data-stu-id="b4cbc-108">For example, you should see something similar to this:</span></span>

<span data-ttu-id="b4cbc-109">**Die Office-webapps-Server Ermittlung für den Webkonferenzserver ist erfolgreich.**</span><span class="sxs-lookup"><span data-stu-id="b4cbc-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="b4cbc-110">**Interne Office-webapps-Server-Referenten Seite: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="b4cbc-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="b4cbc-111">**Office-webapps-Server-interne Teilnehmerseite: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="b4cbc-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="b4cbc-112">**Externe Referenten Seite von Office-webapps Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="b4cbc-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="b4cbc-113">**Office-webapps-Server-interne Teilnehmerseite: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="b4cbc-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="b4cbc-114">Wenn ein ls Data MCU-Ereignis mit der Ereignis-ID 41033 angezeigt wird, bedeutet dies, dass die Ermittlung von Office-webapps-Servern fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="b4cbc-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="b4cbc-115">In diesem Fall versucht Microsoft lync Server 2013 so oft wie erforderlich, den neu konfigurierten Office-webapps-Server zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="b4cbc-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="b4cbc-116">Wenn der Ermittlungsprozess wiederholt fehlschlägt, sollten Sie Office-webappsserver aus Ihrem Topologie-Dokument entfernen, die aktualisierte Topologie veröffentlichen und dann Office-webapps-Server wieder der Topologie hinzufügen, nachdem die Verbindungsprobleme behoben wurden.</span><span class="sxs-lookup"><span data-stu-id="b4cbc-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="b4cbc-117">Wenn Office-webapps-Server anscheinend ordnungsgemäß konfiguriert ist und durch den Ermittlungsprozess erkannt wurde, können Sie sicherstellen, dass Office-webapps Server wie erwartet funktioniert, indem Sie eine PowerPoint-Präsentation zwischen einem Paar Microsoft lync 2013 Clients freigeben.</span><span class="sxs-lookup"><span data-stu-id="b4cbc-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="b4cbc-118">Wenn Benutzer a die PowerPoint-Präsentation laden und anzeigen kann und wenn Benutzer B dann an der Besprechung teilnehmen und diese Präsentation sehen kann, funktioniert Office-webapps-Server.</span><span class="sxs-lookup"><span data-stu-id="b4cbc-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="b4cbc-119">Selbst wenn Office-webapps-Server anscheinend ordnungsgemäß konfiguriert ist, könnten Sie möglicherweise die Fehlermeldung "einige Freigabefunktionen sind aufgrund von Server Verbindungsproblemen nicht verfügbar" erhalten, wenn Sie versuchen, eine PowerPoint-Präsentation freizugeben.</span><span class="sxs-lookup"><span data-stu-id="b4cbc-119">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="b4cbc-120">Wenn Sie diese Fehlermeldung erhalten, sollten Sie den Front-End-Server (oder Server) neu starten, der dem neuen Office-webapps-Server zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b4cbc-120">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

