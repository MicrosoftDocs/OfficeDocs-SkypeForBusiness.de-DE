---
title: 'Lync Server 2013: Überprüfen der Konnektivität für externe Benutzer'
description: 'Lync Server 2013: Überprüfen der Konnektivität für externe Benutzer.'
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
ms.openlocfilehash: 50ef728157d01b93e7d0b8420442ce083a42b5b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547091"
---
# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="abe58-103">Überprüfen der Konnektivität für externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe58-103">Verify connectivity for external users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abe58-104">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="abe58-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="abe58-105">Zum Überprüfen der Konnektivität für externe Benutzer müssen Sie sicherstellen, dass sich die Benutzer mit dem Server und mit dem Port für den Zugriffs-Edgedienst verbinden können.</span><span class="sxs-lookup"><span data-stu-id="abe58-105">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="abe58-106">Eine wertvolle Ressource für die Bestätigung Ihrer Konfiguration und die Möglichkeit zum Verbinden, senden und empfangen der richtigen Nachrichten für die Szenarien, die der externe Benutzer Zugriff benötigt, ist die Remote Connectivity Analyzer-Website ( <http://www.testocsconnectivity.com> ).</span><span class="sxs-lookup"><span data-stu-id="abe58-106">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="abe58-107">Die Website wird vom Microsoft-Support verwaltet und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="abe58-107">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="abe58-108">Um die Remoteverbindungsanalyse zu verwenden, öffnen Sie die Website in einem Browser, und folgen Sie den Anweisungen zum Auswählen des Szenarios.</span><span class="sxs-lookup"><span data-stu-id="abe58-108">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="abe58-109">Testen der Konnektivität externer Benutzer und des externen Zugriffs</span><span class="sxs-lookup"><span data-stu-id="abe58-109">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="abe58-110">Tests für den Zugriff durch externe Benutzer sollten sämtliche Typen von externen Benutzern umfassen, die von Ihrer Organisation unterstützt werden. Dazu können die folgenden Typen zählen:</span><span class="sxs-lookup"><span data-stu-id="abe58-110">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="abe58-111">Benutzer aus mindestens einer Partnerdomäne sowie Testen von IM-, Anwesenheits-, A/V-Funktionen und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="abe58-111">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="abe58-112">Benutzer öffentlicher IM-Dienstanbieter, die von Ihrer Organisation unterstützt werden (und für welche die Bereitstellung abgeschlossen wurde).</span><span class="sxs-lookup"><span data-stu-id="abe58-112">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="abe58-113">Anonyme Benutzer.</span><span class="sxs-lookup"><span data-stu-id="abe58-113">Anonymous users.</span></span>

  - <span data-ttu-id="abe58-114">Benutzer innerhalb Ihrer Organisation, die sich remote bei Lync anmelden, jedoch kein VPN verwenden.</span><span class="sxs-lookup"><span data-stu-id="abe58-114">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="abe58-115">Mithilfe dieser Tests wird ermittelt, ob Ihr Edgeserver folgende Aufgaben ausführt:</span><span class="sxs-lookup"><span data-stu-id="abe58-115">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="abe58-116">Überwachen der erforderlichen Ports durch Verwendung eines telnet-Clients außerhalb Ihres Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="abe58-116">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="abe58-117">Beispiel: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="abe58-117">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="abe58-118">Ausführen des vorstehenden Tests für Ports, die Sie abhängig von Ihrer Bereitstellung auf dem Edgeserver oder Edgeserverpool verwenden.</span><span class="sxs-lookup"><span data-stu-id="abe58-118">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="abe58-119">Ausführen einer präzisen externen DNS-Auflösung.</span><span class="sxs-lookup"><span data-stu-id="abe58-119">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="abe58-p102">Senden Sie von außerhalb Ihres Netzwerks ein Pingsignal an jeden externen FQDN Ihres Edgeservers oder Edgeserverpools. Selbst wenn das Pingen nicht erfolgreich ist, werden die IP-Adressen angezeigt, die Sie mit den von Ihnen zugewiesenen Adressen vergleichen können.</span><span class="sxs-lookup"><span data-stu-id="abe58-p102">From outside your network ping each of the external FQDN’s of your Edge or Edge pool. Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

