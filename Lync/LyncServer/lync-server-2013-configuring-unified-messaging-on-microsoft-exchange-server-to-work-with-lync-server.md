---
title: 'Lync Server 2013: Konfigurieren von Unified Messaging auf Microsoft Exchange Server für die Zusammenarbeit mit Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461d822862e837879f1feb2d3f980b816aae5280
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="0b74c-102">Konfigurieren von Unified Messaging auf Microsoft Exchange Server für die Zusammenarbeit mit Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b74c-102">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b74c-103">_**Letztes Änderungsdatum des Themas:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="0b74c-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0b74c-104">Wenn Sie Exchange Unified Messaging (um) zum Bereitstellen von Anrufbeantwortung, Outlook Voice Access oder automatischen Telefonzentralen Diensten für Enterprise-VoIP-Benutzer verwenden möchten, lesen Sie <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planen der Exchange Unified Messaging-Integration in lync Server 2013</A> in der Planung. Dokumentation, und folgen Sie dann den Anweisungen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="0b74c-104">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="0b74c-105">Um Exchange Unified Messaging (um) für die Arbeit mit Enterprise-VoIP zu konfigurieren, müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="0b74c-105">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="0b74c-106">Konfigurieren von Zertifikaten auf dem Server mit Exchange Unified Messaging (um)-Diensten</span><span class="sxs-lookup"><span data-stu-id="0b74c-106">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0b74c-107">Fügen Sie allen um-SIP-URI-Wählplänen alle Client Zugriffs-und Postfachserver hinzu.</span><span class="sxs-lookup"><span data-stu-id="0b74c-107">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="0b74c-108">Wenn dies nicht der Fall ist, funktioniert das Routing für ausgehende Anrufe nicht wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="0b74c-108">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="0b74c-109">Erstellen Sie bei Bedarf einen oder mehrere um-SIP-URI-Wählpläne zusammen mit den Telefonnummern für den Abonnenten Zugriff, und erstellen Sie dann entsprechende lync Server-Wählpläne.</span><span class="sxs-lookup"><span data-stu-id="0b74c-109">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="0b74c-110">Verwenden Sie das **exchucutil. ps1-** Skript für folgende Zwecke:</span><span class="sxs-lookup"><span data-stu-id="0b74c-110">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="0b74c-111">Erstellen von um-IP-Gateways</span><span class="sxs-lookup"><span data-stu-id="0b74c-111">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="0b74c-112">Erstellen von um-Sammelanschlüssen</span><span class="sxs-lookup"><span data-stu-id="0b74c-112">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="0b74c-113">Erteilen der lync Server 2013-Berechtigung zum Lesen von um-Active Directory-Domänendienste-Objekten</span><span class="sxs-lookup"><span data-stu-id="0b74c-113">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="0b74c-114">Erstellen Sie ein Objekt der automatischen UM-Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="0b74c-114">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="0b74c-115">Erstellen Sie ein Teilnehmerzugriffs Objekt.</span><span class="sxs-lookup"><span data-stu-id="0b74c-115">Create a subscriber access object.</span></span>

  - <span data-ttu-id="0b74c-116">Erstellen Sie einen SIP-URI für jeden Benutzer, und verknüpfen Sie Benutzer mit einem um-SIP-URI-Wählplan.</span><span class="sxs-lookup"><span data-stu-id="0b74c-116">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="0b74c-117">Anforderungen und Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="0b74c-117">Requirements and Recommendations</span></span>

<span data-ttu-id="0b74c-118">Bevor Sie beginnen, wird in der in diesem Abschnitt aufgeführten Dokumentation davon ausgegangen, dass Sie die folgenden Exchange 2013-Rollen bereitgestellt haben: Client Zugriff und Postfach.</span><span class="sxs-lookup"><span data-stu-id="0b74c-118">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="0b74c-119">In Microsoft Exchange Server 2013 wird Exchange um als Dienst auf diesen Servern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0b74c-119">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="0b74c-120">Ausführliche Informationen zum Bereitstellen von Exchange 2013 finden Sie in der Exchange 2013 TechNet-Bibliothek unter[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="0b74c-120">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="0b74c-121">Beachten Sie außerdem Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0b74c-121">Also note the following:</span></span>

  - <span data-ttu-id="0b74c-122">Wenn Exchange um in mehreren Gesamtstrukturen installiert ist, müssen die Exchange Server-Integrationsschritte für jede um-Gesamtstruktur ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0b74c-122">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="0b74c-123">Darüber hinaus muss jede um-Gesamtstruktur so konfiguriert werden, dass Sie der Gesamtstruktur vertraut, in der lync Server 2013 bereitgestellt wird, und die Gesamtstruktur, in der lync Server 2013 bereitgestellt wird, muss so konfiguriert sein, dass Sie jeder um-Gesamtstruktur vertraut.</span><span class="sxs-lookup"><span data-stu-id="0b74c-123">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="0b74c-124">Die Integrationsschritte erfolgen sowohl für die Exchange-Serverrollen, auf denen Unified Messaging-Dienste ausgeführt werden, als auch auf dem Server, auf dem lync Server 2013 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b74c-124">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="0b74c-125">Sie sollten die Exchange Server Unified Messaging-Integrationsschritte ausführen, bevor Sie die lync Server 2013-Integrationsschritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="0b74c-125">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0b74c-126">Informationen dazu, welche Integrationsschritte für welche Server und welche Administratorrollen ausgeführt werden, finden Sie unter <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Bereitstellungsprozess für die Integration von lokalen Unified Messaging und lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0b74c-126">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="0b74c-127">Die folgenden Tools müssen auf jedem Server mit Exchange um verfügbar sein:</span><span class="sxs-lookup"><span data-stu-id="0b74c-127">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="0b74c-128">Exchange-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="0b74c-128">Exchange Management Shell</span></span>

  - <span data-ttu-id="0b74c-129">Das Skript **exchucutil. ps1**, in dem die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="0b74c-129">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="0b74c-130">Erstellt ein um-IP-Gateway für jeden lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b74c-130">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="0b74c-131">Erstellt einen Sammelanschluss für jedes Gateway.</span><span class="sxs-lookup"><span data-stu-id="0b74c-131">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="0b74c-132">Die Pilotkennung der einzelnen Sammelanschlüsse gibt den um-SIP-URI-Wählplan an, der vom Front-End-Pool oder Standard Edition-Server verwendet wird, der dem Gateway zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0b74c-132">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="0b74c-133">Erteilt lync Server 2013 die Berechtigung zum Lesen von Exchange um-Objekten in Active Directory-Domänendiensten.</span><span class="sxs-lookup"><span data-stu-id="0b74c-133">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0b74c-134">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0b74c-134">In This Section</span></span>

  - [<span data-ttu-id="0b74c-135">Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0b74c-135">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="0b74c-136">Konfigurieren von Unified Messaging in Microsoft Exchange für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b74c-136">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

