---
title: 'Lync Server 2013: Konfigurieren von Unified Messaging für Exchange Server für die Verwendung von lync Server'
description: 'Lync Server 2013: Konfigurieren von Unified Messaging für Exchange Server für die Verwendung von lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53c303f0ae659536aafcbdfcd829ed236e35a0ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548241"
---
# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="0f482-103">Konfigurieren von Unified Messaging für Exchange Server zum Arbeiten mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f482-103">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f482-104">_**Letztes Änderungsstand des Themas:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="0f482-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0f482-105">Wenn Sie Exchange Unified Messaging (um) verwenden möchten, um Mailboxansage, Outlook Voice Access oder automatische Telefonzentralendienste für Enterprise-VoIP-Benutzer bereitzustellen, lesen Sie <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planen der Integration von Exchange Unified Messaging in lync Server 2013</A> in der Planungsdokumentation, und befolgen Sie dann die Anweisungen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="0f482-105">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="0f482-106">Um Exchange Unified Messaging (um) für die Zusammenarbeit mit Enterprise-VoIP zu konfigurieren, müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="0f482-106">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="0f482-107">Konfigurieren von Zertifikaten auf dem Server mit Exchange Unified Messaging (um) Diensten</span><span class="sxs-lookup"><span data-stu-id="0f482-107">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f482-108">Fügen Sie alle Client Zugriffs-und Postfachserver allen um-SIP-URI-Wählplänen hinzu.</span><span class="sxs-lookup"><span data-stu-id="0f482-108">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="0f482-109">Wenn dies nicht der Fall ist, funktioniert das Routing für ausgehende Anrufe nicht wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="0f482-109">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="0f482-110">Erstellen Sie bei Bedarf einen oder mehrere um-SIP-URI-Wählpläne zusammen mit den Telefonnummern für den Teilnehmerzugriff, und erstellen Sie dann entsprechende lync Server Wählpläne.</span><span class="sxs-lookup"><span data-stu-id="0f482-110">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="0f482-111">Verwenden Sie das **exchucutil.ps1** -Skript:</span><span class="sxs-lookup"><span data-stu-id="0f482-111">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="0f482-112">Erstellen von UM-IP-Gateways</span><span class="sxs-lookup"><span data-stu-id="0f482-112">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="0f482-113">Erstellen von UM-Sammelanschlüssen</span><span class="sxs-lookup"><span data-stu-id="0f482-113">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="0f482-114">Erteilen Sie lync Server 2013 Berechtigung zum Lesen von um-Active Directory-Domänendienste Objekten.</span><span class="sxs-lookup"><span data-stu-id="0f482-114">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="0f482-115">Erstellen Sie ein um-Objekt der automatischen Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="0f482-115">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="0f482-116">Erstellen eines Teilnehmerzugriffs Objekts.</span><span class="sxs-lookup"><span data-stu-id="0f482-116">Create a subscriber access object.</span></span>

  - <span data-ttu-id="0f482-117">Erstellen Sie einen SIP-URI für jeden Benutzer, und verknüpfen Sie Benutzer mit einem um-SIP-URI-Wählplan.</span><span class="sxs-lookup"><span data-stu-id="0f482-117">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="0f482-118">Anforderungen und Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="0f482-118">Requirements and Recommendations</span></span>

<span data-ttu-id="0f482-119">Bevor Sie beginnen, wird in der Dokumentation in diesem Abschnitt davon ausgegangen, dass Sie die folgenden Exchange 2013 Rollen bereitgestellt haben: Client Zugriff und Postfach.</span><span class="sxs-lookup"><span data-stu-id="0f482-119">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="0f482-120">In Microsoft Exchange Server 2013 wird Exchange um als Dienst auf diesen Servern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0f482-120">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="0f482-121">Ausführliche Informationen zum Bereitstellen von Exchange 2013 finden Sie in der Exchange 2013 TechNet-Bibliothek unter [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="0f482-121">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="0f482-122">Beachten Sie auch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0f482-122">Also note the following:</span></span>

  - <span data-ttu-id="0f482-123">Wenn Exchange um in mehreren Gesamtstrukturen installiert ist, müssen die Exchange Server Integrationsschritte für jede um-Gesamtstruktur ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0f482-123">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="0f482-124">Darüber hinaus muss jede um-Gesamtstruktur so konfiguriert werden, dass Sie der Gesamtstruktur vertraut, in der lync Server 2013 bereitgestellt wird, und die Gesamtstruktur, in der lync Server 2013 bereitgestellt wird, muss so konfiguriert sein, dass jeder um-Gesamtstruktur vertraut wird.</span><span class="sxs-lookup"><span data-stu-id="0f482-124">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="0f482-125">Integrationsschritte werden sowohl für die Exchange Server Rollen, in denen Unified Messaging-Dienste ausgeführt werden, als auch auf dem Server ausgeführt, auf dem lync Server 2013 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0f482-125">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="0f482-126">Sie sollten die Exchange Server Unified Messaging-Integrationsschritte durchführen, bevor Sie die lync Server 2013 Integrationsschritte durchführen.</span><span class="sxs-lookup"><span data-stu-id="0f482-126">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f482-127">Informationen dazu, welche Integrationsschritte auf welchen Servern und mit welchen Administratorrollen ausgeführt werden, finden Sie unter <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment Process for Integration on-premises Unified Messaging and lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0f482-127">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="0f482-128">Die folgenden Tools müssen auf jedem Server mit Exchange um verfügbar sein:</span><span class="sxs-lookup"><span data-stu-id="0f482-128">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="0f482-129">Exchange-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="0f482-129">Exchange Management Shell</span></span>

  - <span data-ttu-id="0f482-130">Das Skript **exchucutil.ps1**, mit dem die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="0f482-130">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="0f482-131">Erstellt ein um-IP-Gateway für jeden lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f482-131">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="0f482-132">Erstellen eines Sammelanschlusses für jedes Gateway.</span><span class="sxs-lookup"><span data-stu-id="0f482-132">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="0f482-133">Die Pilot-ID jedes Sammelanschlusses gibt die um-SIP-URI-Wähleinstellungen an, die von der Front-End-Pool oder Standard Edition-Server verwendet werden, die dem Gateway zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0f482-133">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="0f482-134">Erteilt lync Server 2013 Berechtigung zum Lesen von Exchange um-Objekten in Active Directory-Domänendienste.</span><span class="sxs-lookup"><span data-stu-id="0f482-134">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0f482-135">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0f482-135">In This Section</span></span>

  - [<span data-ttu-id="0f482-136">Konfigurieren von Zertifikaten auf dem Server, auf dem Exchange Server Unified Messaging läuft</span><span class="sxs-lookup"><span data-stu-id="0f482-136">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="0f482-137">Konfigurieren von Unified Messaging für Microsoft Exchange für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f482-137">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

