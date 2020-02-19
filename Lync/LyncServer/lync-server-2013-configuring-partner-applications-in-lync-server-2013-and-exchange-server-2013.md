---
title: Konfigurieren von Partneranwendungen in lync Server 2013 und Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fca5fe648ecfb00c7ef7bcb84948a68e4386bbf3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="3bb62-102">Konfigurieren von Partneranwendungen in Microsoft lync Server 2013 und Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bb62-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bb62-103">_**Letztes Änderungsstand des Themas:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="3bb62-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="3bb62-p101">An einer Authentifizierung zwischen Servern sind üblicherweise drei Entitäten beteiligt: Die beiden Server, die miteinander kommunizieren müssen, und ein Sicherheitstokenserver eines Drittanbieters. Wenn zwei Server (z. B. Server A und Server B) miteinander kommunizieren müssen, beginnen beide Server in der Regel damit, dass sie einen Tokenserver kontaktieren und ein gegenseitig als vertrauenswürdig eingestuftes Sicherheitstoken erhalten. Server A präsentiert das Sicherheitstoken dann Server B (und umgekehrt), womit beide ihre Authentizität und Vertrauenswürdigkeit nachweisen.</span><span class="sxs-lookup"><span data-stu-id="3bb62-p101">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server. If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token. Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="3bb62-107">Dies ist jedoch eine allgemeine Regel.</span><span class="sxs-lookup"><span data-stu-id="3bb62-107">However, that's a general rule.</span></span> <span data-ttu-id="3bb62-108">Lync Server 2013, Microsoft Exchange Server 2013 und Microsoft SharePoint Server 2013 müssen bei der Kommunikation miteinander keinen tokenserver eines Drittanbieters verwenden. Das liegt daran, dass diese Serverprodukte Sicherheitstoken erstellen können, die miteinander akzeptiert werden können, ohne dass ein separater tokenserver erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3bb62-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="3bb62-109">(Diese Funktion steht nur in lync Server 2013, Exchange 2013 und SharePoint Server 2013 zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3bb62-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="3bb62-110">Wenn Sie die Server-zu-Server-Authentifizierung für andere Server, einschließlich anderer Microsoft-Serverprodukte, einrichten müssen, müssen Sie dies mit einem Drittanbieter-tokenserver tun.)</span><span class="sxs-lookup"><span data-stu-id="3bb62-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="3bb62-111">Um die Server-zu-Server-Authentifizierung zwischen lync Server und Exchange einzurichten, müssen Sie zwei Dinge tun: 1) Sie müssen jedem Server die entsprechenden Zertifikate zuweisen. und, 2) Sie müssen jeden Server als Partneranwendung des anderen Servers konfigurieren: das heißt, Sie müssen lync Server 2013 als Partneranwendung für Exchange 2013 konfigurieren, und Sie müssen Exchange 2013 als Partneranwendung für lync Server 2013 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3bb62-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="3bb62-112">Konfigurieren von lync Server 2013 als Partner Anwendung für Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="3bb62-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="3bb62-113">Am einfachsten können Sie lync Server 2013 als Partneranwendung mit Exchange 2013 konfigurieren, indem Sie das configure-EnterprisePartnerApplication. ps1-Skript ausführen, ein Windows PowerShelles Skript, das mit Exchange 2013 ausgeliefert wird.</span><span class="sxs-lookup"><span data-stu-id="3bb62-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="3bb62-114">Um dieses Skript auszuführen, müssen Sie die URL für das Dokument lync Server authentifizierungsmetadaten angeben. Dabei handelt es sich normalerweise um den vollqualifizierten Domänennamen des lync Server 2013 Pools gefolgt vom Suffix/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="3bb62-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="3bb62-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3bb62-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="3bb62-116">Wenn Sie lync Server als Partneranwendung konfigurieren möchten, öffnen Sie das Exchange-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus (vorausgesetzt, dass Exchange auf Laufwerk C: installiert wurde und der Standardordnerpfad verwendet wird):</span><span class="sxs-lookup"><span data-stu-id="3bb62-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="3bb62-117">Nach dem Konfigurieren der Partneranwendung wird empfohlen, Internet Information Services (IIS) auf Ihrem Exchange-Postfach und den Clientzugriffsservern zu beenden und neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="3bb62-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="3bb62-118">Sie können IIS mithilfe eines Befehls, der dem folgenden ähnelt, neu starten, um den Dienst auf dem Computer mit ATL-Exchange-001 neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="3bb62-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="3bb62-119">Dieser Befehl kann in der Exchange-Verwaltungsshell oder in einem anderen Befehlsfenster ausgeführt werden, das unter Administratorrechten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3bb62-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="3bb62-120">Konfigurieren von Exchange 2013 als Partner Anwendung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bb62-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="3bb62-121">Nachdem Sie lync Server 2013 als Partneranwendung für Exchange 2013 konfiguriert haben, müssen Sie Exchange als Partneranwendung für lync Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3bb62-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="3bb62-122">Hierzu können Sie die lync Server-Verwaltungsshell verwenden und das Dokument "authentifizierungsmetadaten" für Exchange angeben. Dies ist normalerweise der URI des Exchange-AutoErmittlungsdiensts, gefolgt vom Suffix/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="3bb62-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="3bb62-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3bb62-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="3bb62-124">In lync Server werden Partneranwendungen mithilfe des [New-cspartnerapplication "-](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) Cmdlets konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="3bb62-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="3bb62-125">Zusätzlich zur Angabe des Metadaten-URI sollten Sie auch die Vertrauensebene der Anwendung auf Full festlegen. Dadurch kann Exchange sowohl sich selbst als auch alle autorisierten Benutzer im Bereich darstellen.</span><span class="sxs-lookup"><span data-stu-id="3bb62-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="3bb62-126">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3bb62-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="3bb62-127">Alternativ können Sie eine Partneranwendung erstellen, indem Sie den Skriptcode kopieren und ändern, der in der Dokumentation lync Server 2013 Server-zu-Server-Authentifizierung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3bb62-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="3bb62-128">Weitere Informationen finden Sie im Artikel [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .</span><span class="sxs-lookup"><span data-stu-id="3bb62-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="3bb62-129">Wenn Sie Partneranwendungen sowohl für lync Server als auch für Exchange erfolgreich konfiguriert haben, bedeutet dies, dass Sie die Server-zu-Server-Authentifizierung zwischen den beiden Produkten erfolgreich konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="3bb62-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="3bb62-130">Lync Server 2013 enthält ein Windows PowerShell-Cmdlet, [Test-csexstorageconnectivity "](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), mit dem Sie sicherstellen können, dass die Server-zu-Server-Authentifizierung ordnungsgemäß konfiguriert wurde und dass der lync Server-Speicherdienst eine Verbindung mit Exchange 2013 herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="3bb62-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="3bb62-131">Das Cmdlet tut dies, indem eine Verbindung mit dem Postfach eines Exchange 2013 Benutzers hergestellt wird, ein Element in den Ordner Unterhaltungsverlauf für diesen Benutzer geschrieben wird und dann optional das Element gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="3bb62-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="3bb62-132">Um die Integration von lync Server 2013 und Exchange 2013 zu testen, führen Sie einen Befehl wie den folgenden aus der lync Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="3bb62-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="3bb62-133">Im vorherigen Befehl stellt die SipUri die SIP-Adresse eines Benutzers mit einem Konto auf Exchange 2013 dar; der Befehl schlägt fehl, da es sich nicht um ein gültiges Benutzerkonto handelt.</span><span class="sxs-lookup"><span data-stu-id="3bb62-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="3bb62-134">Wenn der Test erfolgreich war und die Verbindung hergestellt ist, können Sie mit der Konfiguration optionaler Funktionen, wie der Integration der Archivierung und dem einheitlichen Kontaktspeicher fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3bb62-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

