---
title: Konfigurieren von Partneranwendungen in lync Server 2013 und Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad815a67dafea510513e334c910a5dbb8a2e82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="2791f-102">Konfigurieren von Partneranwendungen in Microsoft lync Server 2013 und Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="2791f-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2791f-103">_**Letztes Änderungsdatum des Themas:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="2791f-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="2791f-104">Die Server-zu-Server-Authentifizierung umfasst in der Regel drei Entitäten: die beiden Server, die miteinander kommunizieren müssen, und einen Sicherheitstoken-Server eines Drittanbieters.</span><span class="sxs-lookup"><span data-stu-id="2791f-104">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server.</span></span> <span data-ttu-id="2791f-105">Wenn zwei Server (beispielsweise Server A und Server B) kommunizieren müssen, beginnen diese beiden Server in der Regel mit einem tokenserver, und Sie erhalten ein gegenseitig vertrauenswürdiges Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="2791f-105">If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token.</span></span> <span data-ttu-id="2791f-106">Server a stellen Sie dann dieses Sicherheitstoken auf Server B (und umgekehrt) als eine Möglichkeit dar, um seine Authentizität und Zuverlässigkeit zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="2791f-106">Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="2791f-107">Das ist jedoch eine allgemeine Regel.</span><span class="sxs-lookup"><span data-stu-id="2791f-107">However, that's a general rule.</span></span> <span data-ttu-id="2791f-108">Lync Server 2013, Microsoft Exchange Server 2013 und Microsoft SharePoint Server 2013 müssen keinen tokenserver eines Drittanbieters verwenden, wenn Sie miteinander kommunizieren. Das liegt daran, dass diese Serverprodukte Sicherheitstoken erstellen können, die voneinander akzeptiert werden können, ohne dass ein separater tokenserver erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2791f-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="2791f-109">(Diese Funktion steht nur in lync Server 2013, Exchange 2013 und SharePoint Server 2013 zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2791f-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="2791f-110">Wenn Sie die Server-zu-Server-Authentifizierung für andere Server, einschließlich anderer Microsoft-Serverprodukte, einrichten müssen, müssen Sie dies unter Verwendung eines tokenserver eines Drittanbieters tun.)</span><span class="sxs-lookup"><span data-stu-id="2791f-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="2791f-111">Damit Sie die Server-zu-Server-Authentifizierung zwischen lync Server und Exchange einrichten können, müssen Sie zwei Schritte ausführen: 1) Sie müssen jedem Server die entsprechenden Zertifikate zuweisen. und 2) Sie müssen jeden Server als Partneranwendung des anderen Servers konfigurieren: Dies bedeutet, dass Sie lync Server 2013 so konfigurieren müssen, dass es sich um eine Partneranwendung für Exchange 2013 handelt, und Sie müssen Exchange 2013 so konfigurieren, dass es sich um eine Partneranwendung für lync Server 2013 handelt.</span><span class="sxs-lookup"><span data-stu-id="2791f-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="2791f-112">Konfigurieren von lync Server 2013 als Partner Anwendung für Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="2791f-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="2791f-113">Die einfachste Möglichkeit, lync Server 2013 auf eine Partneranwendung mit Exchange 2013 zu konfigurieren, besteht darin, das configure-EnterprisePartnerApplication. ps1-Skript auszuführen, ein Windows PowerShell-Skript, das mit Exchange 2013 ausgeliefert wird.</span><span class="sxs-lookup"><span data-stu-id="2791f-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="2791f-114">Um dieses Skript ausführen zu können, müssen Sie die URL für das Dokument für die lync Server-authentifizierungsmetadaten angeben. Dies ist in der Regel der vollqualifizierte Domänenname des lync Server 2013-Pools, gefolgt vom Suffix/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="2791f-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="2791f-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2791f-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="2791f-116">Wenn Sie lync Server als Partneranwendung konfigurieren möchten, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen ähnlichen Befehl aus (vorausgesetzt, Exchange wurde auf Laufwerk C: installiert und verwendet den Standardordnerpfad):</span><span class="sxs-lookup"><span data-stu-id="2791f-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="2791f-117">Nachdem Sie die Partneranwendung konfiguriert haben, empfiehlt es sich, Internet Informationsdienste (IIS) auf Ihrem Exchange-Postfach und den Clientzugriffsservern zu beenden und neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="2791f-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="2791f-118">Sie können IIS neu starten, indem Sie einen ähnlichen Befehl verwenden, mit dem der Dienst auf dem Computer "ATL-Exchange-001" neu gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="2791f-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="2791f-119">Dieser Befehl kann in der Exchange-Verwaltungsshell oder in einem anderen Befehlsfenster ausgeführt werden, das unter Administratorprivilegien ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2791f-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="2791f-120">Konfigurieren von Exchange 2013 als Partner Anwendung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2791f-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="2791f-121">Nachdem Sie lync Server 2013 als Partneranwendung für Exchange 2013 konfiguriert haben, müssen Sie Exchange so konfigurieren, dass es sich um eine Partneranwendung für lync Server handelt.</span><span class="sxs-lookup"><span data-stu-id="2791f-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="2791f-122">Dies kann mithilfe der lync Server-Verwaltungsshell und dem Angeben des Dokuments für die authentifizierungsmetadaten für Exchange erfolgen. Dies ist in der Regel der URI des Exchange-AutoErmittlungsdiensts, gefolgt vom Suffix/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="2791f-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="2791f-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2791f-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="2791f-124">In lync Server werden Partneranwendungen mithilfe des Cmdlets [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2791f-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="2791f-125">Zusätzlich zur Angabe des Metadaten-URIs sollten Sie auch die Vertrauensebene der Anwendung auf Full festlegen. Dadurch kann Exchange sowohl sich selbst als auch alle autorisierten Benutzer im Bereich darstellen.</span><span class="sxs-lookup"><span data-stu-id="2791f-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="2791f-126">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2791f-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="2791f-127">Sie können eine Partneranwendung auch erstellen, indem Sie den Skriptcode, der in der Dokumentation zur Server-zu-Server-Authentifizierung von lync Server 2013 gefunden wurde, kopieren und ändern.</span><span class="sxs-lookup"><span data-stu-id="2791f-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="2791f-128">Weitere Informationen finden Sie im Artikel [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .</span><span class="sxs-lookup"><span data-stu-id="2791f-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="2791f-129">Wenn Sie erfolgreich Partneranwendungen für lync Server und Exchange konfiguriert haben, bedeutet dies, dass Sie auch die Server-zu-Server-Authentifizierung zwischen den beiden Produkten erfolgreich konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="2791f-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="2791f-130">Lync Server 2013 enthält ein Windows PowerShell-Cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), mit dem Sie überprüfen können, ob die Server-zu-Server-Authentifizierung ordnungsgemäß konfiguriert wurde und der lync Server-Speicherdienst eine Verbindung mit Exchange herstellen kann. 2013.</span><span class="sxs-lookup"><span data-stu-id="2791f-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="2791f-131">Das Cmdlet führt dazu eine Verbindung mit dem Postfach eines Exchange 2013-Benutzers, wobei ein Element in den Ordner "Konversations Verlauf" für diesen Benutzer geschrieben wird, und dann optional das Element gelöscht.</span><span class="sxs-lookup"><span data-stu-id="2791f-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="2791f-132">Um die Integration von lync Server 2013 und Exchange 2013 zu testen, führen Sie in der lync Server-Verwaltungsshell einen ähnlichen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="2791f-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="2791f-133">Im vorangehenden Befehl stellt der SipUri die SIP-Adresse eines Benutzers mit einem Konto in Exchange 2013 dar; Ihr Befehl schlägt fehl, da es sich nicht um ein gültiges Benutzerkonto handelt.</span><span class="sxs-lookup"><span data-stu-id="2791f-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="2791f-134">Wenn der Test erfolgreich war und die Verbindung hergestellt ist, können Sie mit der Konfiguration optionaler Funktionen (z. B. der Integration der Archivierung und des einheitlichen Kontaktspeichers) fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2791f-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

