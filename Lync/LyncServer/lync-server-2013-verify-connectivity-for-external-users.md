---
title: 'Lync Server 2013: Überprüfen der Konnektivität für externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c1f8a9bbda54c596a9ccae8451b15ce7300bffd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="68a43-102">Überprüfen der Konnektivität für externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68a43-102">Verify connectivity for external users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68a43-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="68a43-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="68a43-104">Zum Überprüfen der Konnektivität für externe Benutzer muss die Konnektivität zwischen Benutzern und dem Server und Port für den Access Edge-Dienst sichergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="68a43-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="68a43-105">Eine wertvolle Ressource für die Bestätigung Ihrer Konfiguration und die Möglichkeit zum Verbinden, senden und empfangen der richtigen Nachrichten für die Szenarien, für die der Zugriff durch externe Benutzer erforderlich ist,<http://www.testocsconnectivity.com>ist die Remote Connectivity Analyzer-Website ().</span><span class="sxs-lookup"><span data-stu-id="68a43-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="68a43-106">Die Website wird vom Microsoft-Support verwaltet und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="68a43-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="68a43-107">Zum Erreichen des Remote Connectivity Analyzer öffnen Sie die Website in einem Browser, und folgen Sie den Anweisungen, um das Szenario auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="68a43-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="68a43-108">Testen der Konnektivität externer Benutzer und des externen Zugriffs</span><span class="sxs-lookup"><span data-stu-id="68a43-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="68a43-109">Tests für den Zugriff durch externe Benutzer sollten alle externen Benutzertypen enthalten, die von Ihrer Organisation unterstützt werden, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="68a43-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="68a43-110">Benutzer aus mindestens einer Föderationsdomäne und Test-Chat, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="68a43-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="68a43-111">Benutzer jedes öffentlichen Chat Dienstanbieters, den Ihre Organisation unterstützt (und für die die Bereitstellung abgeschlossen wurde).</span><span class="sxs-lookup"><span data-stu-id="68a43-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="68a43-112">Anonyme Benutzer.</span><span class="sxs-lookup"><span data-stu-id="68a43-112">Anonymous users.</span></span>

  - <span data-ttu-id="68a43-113">Benutzer in Ihrer Organisation, die bei lync Remote angemeldet sind, aber keine VPN-Verbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="68a43-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="68a43-114">Diese Tests bestimmen, ob der Edgeserver wie folgt lautet:</span><span class="sxs-lookup"><span data-stu-id="68a43-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="68a43-115">Überwachen der erforderlichen Ports durch Verwendung eines telnet-Clients außerhalb Ihres Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="68a43-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="68a43-116">Beispiel: Telnet SIP.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="68a43-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="68a43-117">Führen Sie den vorhergehenden Test für Ports aus, die Sie je nach Bereitstellung auf dem Edgeserver oder Edgeserver-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="68a43-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="68a43-118">Ausführen einer präzisen externen DNS-Auflösung.</span><span class="sxs-lookup"><span data-stu-id="68a43-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="68a43-119">Pingen Sie von außerhalb Ihres Netzwerks jeden der externen FQDN des Edge-oder Edge-Pools.</span><span class="sxs-lookup"><span data-stu-id="68a43-119">From outside your network ping each of the external FQDN’s of your Edge or Edge pool.</span></span> <span data-ttu-id="68a43-120">Auch wenn der ping fehlschlägt, werden die IP-Adressen angezeigt, die Sie mit den zugewiesenen vergleichen können.</span><span class="sxs-lookup"><span data-stu-id="68a43-120">Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

