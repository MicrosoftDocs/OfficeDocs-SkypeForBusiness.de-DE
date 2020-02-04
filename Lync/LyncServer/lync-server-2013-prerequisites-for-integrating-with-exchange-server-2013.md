---
title: 'Lync Server 2013: Voraussetzungen für die Integration in Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a381f765c9c91e9c5e218d66320d542a11bf878
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="27dd1-102">Voraussetzungen für die Integration von Microsoft lync Server 2013 und Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="27dd1-102">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27dd1-103">_**Letztes Änderungsdatum des Themas:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="27dd1-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="27dd1-104">Bevor Sie Microsoft lync Server 2013 und Microsoft Exchange Server 2013 integrieren können, müssen Sie sicherstellen, dass alle erforderlichen Schritte abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="27dd1-104">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="27dd1-105">Wie Sie vielleicht erwarten, kann die Integration erst dann erfolgen, wenn Exchange 2013 und lync Server 2013 vollständig installiert sind und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="27dd1-105">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="27dd1-106">Details zur Installation von Exchange finden Sie in [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)der Dokumentation zur Planung und Bereitstellung von Exchange 2013 unter.</span><span class="sxs-lookup"><span data-stu-id="27dd1-106">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="27dd1-107">Details zur Installation von lync Server 2013 finden Sie in [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)der Dokumentation zur Planung und Bereitstellung unter.</span><span class="sxs-lookup"><span data-stu-id="27dd1-107">For details about installing Lync Server 2013, see the planning and deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="27dd1-108">Nachdem die Server eingerichtet und ausgeführt wurden, müssen Sie Server-zu-Server-Authentifizierungszertifikate sowohl für lync Server 2013 als auch Exchange 2013 zuweisen. Mithilfe dieser Zertifikate können lync Server und Exchange Informationen austauschen und miteinander kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="27dd1-108">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="27dd1-109">Wenn Sie Exchange 2013 installieren, wird ein selbstsigniertes Zertifikat mit dem Namen Microsoft Exchange Server auth-Zertifikat für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="27dd1-109">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="27dd1-110">Dieses Zertifikat, das sich im Zertifikatspeicher des lokalen Computers befindet, sollte für die Server-zu-Server-Authentifizierung in Exchange 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27dd1-110">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="27dd1-111">Details zum Zuweisen von Zertifikaten in Exchange 2013 finden Sie unter "Konfigurieren des Nachrichtenflusses und des Client [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)Zugriffs" unter.</span><span class="sxs-lookup"><span data-stu-id="27dd1-111">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="27dd1-112">Für lync Server 2013 können Sie ein vorhandenes lync Server-Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden. Beispielsweise kann Ihr Standardzertifikat auch als OAuthTokenIssuer-Zertifikat verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27dd1-112">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="27dd1-113">Mit lync Server 2013 können Sie ein beliebiges Webserverzertifikat als Zertifikat für die Server-zu-Server-Authentifizierung verwenden, vorausgesetzt, dass:</span><span class="sxs-lookup"><span data-stu-id="27dd1-113">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="27dd1-114">Das Zertifikat enthält den Namen der SIP-Domäne im Feld „Betreff“.</span><span class="sxs-lookup"><span data-stu-id="27dd1-114">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="27dd1-115">Dasselbe Zertifikat ist als „OAuthTokenIssuer“-Zertifikat auf allen Front-End-Servern konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="27dd1-115">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="27dd1-116">Das Zertifikat hat eine Länge von mindestens 2048 Bits.</span><span class="sxs-lookup"><span data-stu-id="27dd1-116">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="27dd1-117">Details zu Server-zu-Server-Authentifizierungszertifikaten für Microsoft lync Server 2013 finden Sie unter [Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Microsoft lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="27dd1-117">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="27dd1-118">Nachdem die Zertifikate zugewiesen wurden, müssen Sie den AutoErmittlungsdienst in Exchange 2013 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="27dd1-118">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="27dd1-119">In Exchange 2013 konfiguriert der AutoErmittlungsdienst Benutzerprofile und bietet Zugriff auf Exchange-Dienste, wenn Benutzer sich am System anmelden.</span><span class="sxs-lookup"><span data-stu-id="27dd1-119">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="27dd1-120">Die Benutzer geben im AutoErmittlungsdienst ihre E-Mail-Adresse und ihr Kennwort ein, und der Dienst stellt ihnen im Gegenzug folgende Informationen bereit:</span><span class="sxs-lookup"><span data-stu-id="27dd1-120">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="27dd1-121">Verbindungsinformationen für interne und externe Verbindungen zu Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="27dd1-121">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="27dd1-122">Den Standort des Postfachservers des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="27dd1-122">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="27dd1-123">URLs für Outlook-Features wie etwa Frei/Gebucht-Informationen, Unified Messaging und das Offlineadressbuch.</span><span class="sxs-lookup"><span data-stu-id="27dd1-123">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="27dd1-124">Servereinstellungen für Outlook Anywhere.</span><span class="sxs-lookup"><span data-stu-id="27dd1-124">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="27dd1-125">Der AutoErmittlungsdienst muss konfiguriert sein, bevor Sie lync Server 2013 und Exchange 2013 integrieren können.</span><span class="sxs-lookup"><span data-stu-id="27dd1-125">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="27dd1-126">Sie können überprüfen, ob der AutoErmittlungsdienst konfiguriert wurde, indem Sie den folgenden Befehl aus der Exchange-Verwaltungsshell ausführen und den Wert der AutoDiscoverServiceInternalUri-Eigenschaft überprüfen:</span><span class="sxs-lookup"><span data-stu-id="27dd1-126">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="27dd1-p106">Wenn dieser Wert leer ist, müssen Sie dem AutoErmittlungsdienst einen URI zuweisen. Dieser URI sieht in der Regel so aus:</span><span class="sxs-lookup"><span data-stu-id="27dd1-p106">If this value is blank, you must assign a URI to the autodiscover service. Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="27dd1-129">Sie können den URI für den AutoErmittlungsdienst zuweisen, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="27dd1-129">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="27dd1-130">Details zum AutoErmittlungsdienst finden Sie unter "Grundlegendes zum Auto Ermittlungs [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)Dienst" unter.</span><span class="sxs-lookup"><span data-stu-id="27dd1-130">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="27dd1-131">Nachdem der AutoErmittlungsdienst konfiguriert wurde, müssen Sie die lync Server OAuth-Konfigurationseinstellungen ändern. Dadurch wird sichergestellt, dass lync Server weiß, wo der AutoErmittlungsdienst zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="27dd1-131">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="27dd1-132">Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus, um die OAuth-Konfigurationseinstellungen in lync Server 2013 zu ändern.</span><span class="sxs-lookup"><span data-stu-id="27dd1-132">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="27dd1-133">Wenn Sie diesen Befehl ausführen, stellen Sie sicher, dass Sie den URI für den AutoErmittlungsdienst angeben, der auf Ihrem Exchange-Server ausgeführt wird, und dass Sie **autodiscover. svc** verwenden, um auf den Dienst Speicherort zu verweisen, anstatt auf **autodiscover. XML** (der auf die vom Dienst verwendete XML-Datei verweist):</span><span class="sxs-lookup"><span data-stu-id="27dd1-133">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="27dd1-134">Der Parameter Identity im vorhergehenden Befehl ist optional; Das liegt daran, dass lync Server Ihnen nur eine einzige globale Sammlung von OAuth-Konfigurationseinstellungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="27dd1-134">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="27dd1-135">Das bedeutet unter anderem, dass Sie die URL für den AutoErmittlungsdienst mit diesem etwas einfacheren Befehl konfigurieren können:</span><span class="sxs-lookup"><span data-stu-id="27dd1-135">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="27dd1-136">Satz-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span><span class="sxs-lookup"><span data-stu-id="27dd1-136">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="27dd1-p109">Wenn Sie mit der Technologie noch nicht so vertraut sind, ist „OAuth“ ein Standardautorisierungsprotokoll, das von vielen wichtigen Websites verwendet wird. Bei „OAuth“ werden Benutzeranmeldeinformationen und -kennwörter nicht von einem Computer zum anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstokens. Diese Tokens erteilen für einen bestimmte Zeitspanne Zugriff auf einen bestimmten Satz von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="27dd1-p109">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites. With OAuth, user credentials and passwords are not passed from one computer to another. Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="27dd1-140">Zusätzlich zum Konfigurieren des AutoErmittlungsdiensts müssen Sie auch einen DNS-Eintrag für den Dienst erstellen, der auf Ihren Exchange-Server verweist.</span><span class="sxs-lookup"><span data-stu-id="27dd1-140">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="27dd1-141">Wenn sich der AutoErmittlungsdienst beispielsweise unter autodiscover.litwareinc.com befindet, müssen Sie einen DNS-Eintrag für autodiscover.litwareinc.com erstellen, der in den vollqualifizierten Domänennamen Ihres Exchange-Servers aufgelöst wird (beispielsweise ATL-Exchange-001.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="27dd1-141">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

