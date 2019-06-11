---
title: Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4cdfd80c368558ee034369eba0ca0cb9e89ecea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a><span data-ttu-id="ae0ae-102">Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae0ae-102">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae0ae-103">_**Letztes Änderungsdatum des Themas:** 2015-05-14_</span><span class="sxs-lookup"><span data-stu-id="ae0ae-103">_**Topic Last Modified:** 2015-05-14_</span></span>

<span data-ttu-id="ae0ae-104">Microsoft lync Server 2013 muss sicher und nahtlos mit anderen Anwendungen und Server Produkten kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-104">Microsoft Lync Server 2013 must be able to securely, and seamlessly, communicate with other applications and server products.</span></span> <span data-ttu-id="ae0ae-105">So können Sie beispielsweise lync Server 2013 so konfigurieren, dass Kontaktdaten und/oder Archivierungsdaten in Microsoft Exchange Server 2013 gespeichert werden. Dies kann jedoch nur erfolgen, wenn lync Server und Exchange sicher miteinander kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-105">For example, you can configure Lync Server 2013 so that contact data and/or archiving data is stored in Microsoft Exchange Server 2013; however, this can only be done if Lync Server and Exchange are able to securely communicate with one another.</span></span> <span data-ttu-id="ae0ae-106">Ebenso können Sie eine lync Server-Konferenz in Microsoft SharePoint Server planen. Dies kann jedoch nur erfolgen, wenn sich die beiden Server (SharePoint und lync Server) gegenseitig vertrauen.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-106">Likewise, you can schedule a Lync Server conference from within Microsoft SharePoint Server; again, however, this can only be done if the two servers (SharePoint and Lync Server) trust one another.</span></span> <span data-ttu-id="ae0ae-107">Obwohl es möglich ist, einen Authentifizierungsmechanismus für die Kommunikation zwischen lync und Exchange sowie einen separaten Mechanismus für die Kommunikation zwischen lync und SharePoint zu verwenden, besteht ein besserer und effizienterer Ansatz darin, eine standardisierte Methode für alle Server-zu-Server-Zwecke zu verwenden. Authentifizierung und Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-107">Although it's possible to use one authentication mechanism for Lync-to-Exchange communication and a separate mechanism for Lync-to-SharePoint communication, a better and more efficient approach is to use a standardized method for all server-to-server authentication and authorization.</span></span>

<span data-ttu-id="ae0ae-108">Die Verwendung einer einzelnen standardisierten Methode für die Server-zu-Server-Authentifizierung ist der von lync Server 2013 getroffene Ansatz.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-108">Using a single, standardized method for server-to-server authentication is the approach taken by Lync Server 2013.</span></span> <span data-ttu-id="ae0ae-109">Für die 2013-Version unterstützen lync Server 2013 (sowie andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und Microsoft SharePoint Server) das OAuth (Open Authorization)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-109">For the 2013 release, Lync Server 2013 (as well as other Microsoft Server products, including Exchange 2013 and Microsoft SharePoint Server) support the OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="ae0ae-110">Bei OAuth wird ein Standard Autorisierungs Protokoll, das von einer Reihe von Hauptwebsites, Benutzeranmeldeinformationen und Kennwörtern verwendet wird, nicht von einem Computer an einen anderen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-110">With OAuth, a standard authorization protocol used by a number of major websites, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="ae0ae-111">Stattdessen basiert Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstokens; Diese Token gewähren für einen bestimmten Zeitraum Zugriff auf eine bestimmte Gruppe von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-111">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>

<span data-ttu-id="ae0ae-112">Die OAuth-Authentifizierung umfasst in der Regel drei Parteien: einen einzelnen autorisierungsserver und die beiden Realms, die miteinander kommunizieren müssen.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-112">OAuth authentication typically involves three parties: a single authorization server and the two realms that need to communicate with one another.</span></span> <span data-ttu-id="ae0ae-113">(Sie können auch eine Server-zu-Server-Authentifizierung ausführen, ohne einen autorisierungsserver zu verwenden, ein Prozess, der später in diesem Dokument erläutert wird.) Sicherheitstoken werden von dem autorisierungsserver (auch als Sicherheitstokenserver bezeichnet) für die beiden Bereiche ausgestellt, die kommuniziert werden müssen. Diese Token stellen sicher, dass die Kommunikation, die von einem Bereich stammt, vom anderen Bereich als vertrauenswürdig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-113">(You can also do server-to-server authentication without using an authorization server, a process that will be discussed later in this document.) Security tokens are issued by the authorization server (also known as a security token server) to the two realms that need to communicate; these tokens verify that communications originating from one realm should be trusted by the other realm.</span></span> <span data-ttu-id="ae0ae-114">Beispielsweise kann der autorisierungsserver Token ausgeben, mit denen sichergestellt wird, dass Benutzer aus einem bestimmten lync Server-2013-Bereich auf einen bestimmten Exchange 2013-Bereich zugreifen können, und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-114">For example, the authorization server might issue tokens that verify that users from a specific Lync Server 2013 realm are able to access a specified Exchange 2013 realm, and vice-versa.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ae0ae-115">Ein Bereich ist einfach ein Sicherheitscontainer.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-115">A realm is simply a security container.</span></span> <span data-ttu-id="ae0ae-116">Standardmäßig verwendet lync Server 2013 Ihre SIP-Standarddomäne als OAuth-Bereich.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-116">By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</span></span> <span data-ttu-id="ae0ae-117">Weitere SIP-Namespaces werden der Liste mit alternativen Antragstellernamen im OAuth-Zertifikat hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-117">Additional SIP namespaces are added to the Subject Alternate Name list in the OAuth certificate.</span></span>



</div>

<span data-ttu-id="ae0ae-118">Lync Server 2013 unterstützt drei Szenarien für die Server-zu-Server-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-118">Lync Server 2013 supports three server-to-server authentication scenarios.</span></span> <span data-ttu-id="ae0ae-119">Mit lync Server 2013 können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="ae0ae-119">With Lync Server 2013 you can:</span></span>

  - <span data-ttu-id="ae0ae-120">Konfigurieren Sie die Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von lync Server 2013 und einer lokalen Installation von Exchange 2013 und/oder Microsoft SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-120">Configure server-to-server authentication between an on-premise installation of Lync Server 2013 and an on-premises installation of Exchange 2013 and/or Microsoft SharePoint Server.</span></span>

  - <span data-ttu-id="ae0ae-121">Konfigurieren Sie die Server-zu-Server-Authentifizierung zwischen zwei Office 365-Komponenten (beispielsweise zwischen Microsoft Exchange und Microsoft lync Server oder zwischen Microsoft lync Server und Microsoft SharePoint).</span><span class="sxs-lookup"><span data-stu-id="ae0ae-121">Configure server-to-server authentication between a pair of Office 365 components (for example, between Microsoft Exchange and Microsoft Lync Server, or between Microsoft Lync Server and Microsoft SharePoint).</span></span>

  - <span data-ttu-id="ae0ae-122">Konfigurieren Sie die Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung (Server-zu-Server-Authentifizierung zwischen einem lokalen Server und einer Office 365-Komponente).</span><span class="sxs-lookup"><span data-stu-id="ae0ae-122">Configure server-to-server authentication in a cross-premises environment (that is, server-to-server authentication between an on-premises server and an Office 365 component).</span></span>

<span data-ttu-id="ae0ae-123">Beachten Sie, dass zu diesem Zeitpunkt nur Exchange 2013, SharePoint Server und lync Server 2013 die Server-zu-Server-Authentifizierung unterstützen. Wenn Sie einen dieser Server nicht ausführen, können Sie die OAuth-Authentifizierung nicht vollständig implementieren.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-123">Note that, at this point in time, only Exchange 2013, SharePoint Server, and Lync Server 2013 support server-to-server authentication; if you are not running one of these servers then you will not be able to fully implement OAuth authentication.</span></span>

<span data-ttu-id="ae0ae-124">Es sollte auch darauf hingewiesen werden, dass Sie die Server-zu-Server-Authentifizierung nicht verwenden müssen: die Server-zu-Server-Authentifizierung ist nicht erforderlich, um lync Server 2013 bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-124">It should also be pointed out that you do not need to use server-to-server authentication: server-to-server authentication is not required in order to deploy Lync Server 2013.</span></span> <span data-ttu-id="ae0ae-125">Wenn lync Server 2013 nicht mit anderen Servern (wie Exchange 2013) kommunizieren muss, wird die Server-zu-Server-Authentifizierung nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-125">If Lync Server 2013 does not need to communicate with other servers (such as Exchange 2013) then server-to-server authentication is not needed.</span></span>

<span data-ttu-id="ae0ae-126">Die Server-zu-Server-Authentifizierung ist jedoch erforderlich, wenn Sie einige der neuen Funktionen von lync Server verwenden möchten, beispielsweise den "Unified Contact Store".</span><span class="sxs-lookup"><span data-stu-id="ae0ae-126">However, server-to-server authentication is required if you want to use some of Lync Server's new features, such as the "unified contact store."</span></span> <span data-ttu-id="ae0ae-127">Mit dem Unified Contact Store werden die lync Server 2013-Kontaktinformationen in Exchange 2013 statt in lync Server gespeichert. Dadurch können Benutzer über einen einzigen Satz Kontakte verfügen, auf die in lync, Microsoft Outlook oder Microsoft Outlook Web Access problemlos zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-127">With unified contact store, Lync Server 2013 contact information is stored in Exchange 2013 instead of in Lync Server; this enables users to have a single set of contacts that is readily accessible from within Lync, Microsoft Outlook, or Microsoft Outlook Web Access.</span></span> <span data-ttu-id="ae0ae-128">Da für den Unified Contact Store lync Server 2013 zum Freigeben von Informationen für Exchange 2013 erforderlich ist, müssen Sie die Server-zu-Server-Authentifizierung verwenden, um das Feature bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-128">Because the unified contact store requires Lync Server 2013 to share information with Exchange 2013, you must use server-to-server authentication in order to deploy the feature.</span></span> <span data-ttu-id="ae0ae-129">Die Server-zu-Server-Authentifizierung ist auch erforderlich, wenn Sie die Exchange-Archivierung verwenden möchten, in der die Protokolle von Chatsitzungen als Exchange 2013-e-Mails und nicht als einzelne Datenbankeinträge gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-129">Server-to-server authentication is also required if you choose to use Exchange archiving, in which the transcripts of instant messaging sessions are saved as Exchange 2013 emails rather than as individual database records.</span></span>

<span data-ttu-id="ae0ae-130">Damit die Office 365-Version von lync Server mit dem Exchange-Pendant kommuniziert, muss lync Server 2013 zuerst ein Sicherheitstoken vom autorisierungsserver abrufen.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-130">For the Office 365 version of Lync Server to communicate with its Exchange counterpart, Lync Server 2013 must first obtain a security token from the authorization server.</span></span> <span data-ttu-id="ae0ae-131">Lync Server verwendet dann dieses Sicherheitstoken, um sich selbst für Exchange zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-131">Lync Server then uses that security token to identify itself to Exchange.</span></span> <span data-ttu-id="ae0ae-132">Die Office 365-Version von Exchange muss denselben Vorgang durchlaufen, um mit lync Server 2013 zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-132">The Office 365 version of Exchange must go through the same process in order to communicate with Lync Server 2013.</span></span>

<span data-ttu-id="ae0ae-133">Für eine lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern muss kein Drittanbieter-Tokenserver verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-133">However, for on-premises server-to-server authentication between two Microsoft servers there is no need to use a third-party token server.</span></span> <span data-ttu-id="ae0ae-134">Serverprodukte wie lync Server 2013 und Exchange 2013 verfügen über einen integrierten tokenserver, der für Authentifizierungszwecke mit anderen Microsoft-Servern (wie SharePoint Server) verwendet werden kann, die die Server-zu-Server-Authentifizierung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-134">Server products such as Lync Server 2013 and Exchange 2013 have a built-in token server that can be used for authentication purposes with other Microsoft servers (such as SharePoint server) that support server-to-server authentication.</span></span> <span data-ttu-id="ae0ae-135">Mit lync Server 2013 können Sie beispielsweise ein Sicherheitstoken selbst ausgeben und Signieren und dann dieses Token für die Kommunikation mit Exchange 2013 verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-135">For example, Lync Server 2013 can issue and sign a security token by itself, then use that token to communicate with Exchange 2013.</span></span> <span data-ttu-id="ae0ae-136">In einem solchen Fall ist kein Drittanbieter-Tokenserver erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-136">In a case like this, there is no need for a third-party token server.</span></span>

<span data-ttu-id="ae0ae-137">Um die Server-zu-Server-Authentifizierung für eine lokale Implementierung von lync Server 2013 zu konfigurieren, müssen Sie zwei Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ae0ae-137">In order to configure server-to-server authentication for an on-premises implementation of Lync Server 2013 you must do two things:</span></span>

  - <span data-ttu-id="ae0ae-138">Weisen Sie dem in lync Server integrierten Token-Aussteller ein Zertifikat zu.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-138">Assign a certificate to Lync Server's built-in token issuer.</span></span>

  - <span data-ttu-id="ae0ae-139">Konfigurieren Sie den Server, mit dem lync Server 2013 kommuniziert, als "Partneranwendung".</span><span class="sxs-lookup"><span data-stu-id="ae0ae-139">Configure the server that Lync Server 2013 will communicate with to be a "partner application."</span></span> <span data-ttu-id="ae0ae-140">Wenn lync Server 2013 beispielsweise mit Exchange 2013 kommunizieren muss, müssen Sie Exchange so konfigurieren, dass es sich um eine Partneranwendung handelt.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-140">For example, if Lync Server 2013 needs to communicate with Exchange 2013 then you will need to configure Exchange to be a partner application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ae0ae-141">Eine "Partneranwendung" ist eine beliebige Anwendung, mit der lync Server 2013 Sicherheitstoken direkt austauschen kann, ohne dass ein Sicherheits tokenserver eines Drittanbieters durchlaufen werden muss.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-141">A "partner application" is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server.</span></span>



</div>

<span data-ttu-id="ae0ae-142">Beachten Sie, dass OAuth eine Kernkomponente des Produkts ist und weder deaktiviert noch entfernt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ae0ae-142">Note that OAuth is a core part of the product and cannot be disabled or removed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ae0ae-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae0ae-143">See Also</span></span>


[<span data-ttu-id="ae0ae-144">Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae0ae-144">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[<span data-ttu-id="ae0ae-145">Konfigurieren von Microsoft lync Server 2013 in einer standortübergreifenden Umgebung</span><span class="sxs-lookup"><span data-stu-id="ae0ae-145">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

