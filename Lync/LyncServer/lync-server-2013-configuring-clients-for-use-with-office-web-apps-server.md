---
title: 'Lync Server 2013: Konfigurieren von Clients für die Verwendung mit Office-webapps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10ec5ddaca5a8409a18504cb73912d107c9a6455
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="76d22-102">Konfigurieren von Clients von lync Server 2013 für die Verwendung mit Office-webapps Server</span><span class="sxs-lookup"><span data-stu-id="76d22-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76d22-103">_**Letztes Änderungsstand des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="76d22-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="76d22-104">Wenn Sie möchten, dass Benutzer die vollständigen Funktionen von Office-Webanwendungs Server nutzen können, sollten Sie diese Benutzer auf Microsoft lync 2013 aktualisieren. nur Benutzer von lync 2013 können beispielsweisedurch PowerPoint-Folien unabhängig von der tatsächlichen PowerPoint-Präsentation scrollen.</span><span class="sxs-lookup"><span data-stu-id="76d22-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="76d22-105">(Das bedeutet, dass diese Benutzer jederzeit auf jeder Folie in der Präsentation suchen können, ohne die tatsächliche Präsentation in irgendeiner Weise zu stören.) Benutzer, die lync 2013 nicht verwenden, können weiterhin Online Konferenzen beitreten und die PowerPoint-Präsentation anzeigen; Sie können jedoch nicht unabhängig voneinander durch die Folien scrollen, Sie können auch keine Folienübergänge sehen oder eingebettete Videos anzeigen.</span><span class="sxs-lookup"><span data-stu-id="76d22-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="76d22-106">Beachten Sie, dass diese Funktionen immer für Benutzer von lync 2013 zur Verfügung stehen. Dies gilt auch dann, wenn der PowerPoint-Referent Microsoft lync 2010 ausführt.</span><span class="sxs-lookup"><span data-stu-id="76d22-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="76d22-107">Wenn eine PowerPoint-Präsentation von einem Benutzer gehostet wird, der lync 2010 ausführt, wird lync Server 2013 mit Office-webapps Server koordinieren, um sicherzustellen, dass lync 2013 Benutzer die Office-webapps-Server Version dieser Präsentation anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="76d22-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="76d22-108">Office webapps Server stellt keine PowerPoint-Dienste für Benutzer bereit, die andere Clients als lync 2013 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="76d22-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="76d22-109">Diese Benutzer stellen stattdessen eine Verbindung mit dem Konferenzserver Dienst her und zeigen PowerPoint-Präsentationen auf die gleiche Weise wie in Microsoft lync Server 2010 an.</span><span class="sxs-lookup"><span data-stu-id="76d22-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="76d22-110">Dies bedeutet auch, dass diese Benutzer nur Zugriff auf die mehr begrenzten Funktionen haben, die von lync Server 2010 angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="76d22-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="76d22-111">Obwohl für Office-webapps Server keine Clientkonfiguration erforderlich ist (andere als das Upgrade von Benutzern auf lync 2013), wird empfohlen, dass die Konferenzteilnehmer ein Upgrade auf Internet Explorer 9 durchführen.</span><span class="sxs-lookup"><span data-stu-id="76d22-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="76d22-112">Obwohl auf Konferenzen mit Internet Explorer 8 zugegriffen werden kann, gibt es einige Einschränkungen bei der Verwendung dieses Webbrowsers.</span><span class="sxs-lookup"><span data-stu-id="76d22-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="76d22-113">Beispielsweise können Benutzer von Internet Explorer 8 nicht die Größe der PowerPoint-Stufe auf eine benutzerdefinierte Größe anpassen. Stattdessen sind Sie auf die Verwendung einer von drei vordefinierten Bühnengrößen limitiert.</span><span class="sxs-lookup"><span data-stu-id="76d22-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="76d22-114">Ebenso können Internet Explorer 8 Benutzer keine Mediendateien wiedergeben.</span><span class="sxs-lookup"><span data-stu-id="76d22-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

