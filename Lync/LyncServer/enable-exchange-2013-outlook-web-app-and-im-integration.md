---
title: Aktivieren der Integration von Exchange 2013 Outlook Web App und Chatnachrichten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da4289f663d62d1638c0f669e17a5e318e0788d3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="d4c0f-102">Aktivieren der Integration von Exchange 2013 Outlook Web App und Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="d4c0f-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4c0f-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d4c0f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d4c0f-104">Um die Integration von Exchange 2013 Outlook Web Access (OWA) und Instant Messaging (Chat) mit lync Server 2013 zu ermöglichen, müssen Sie den Exchange 2013 Client Zugriffsserver (CAS) der lync Server 2013 Topologie als vertrauenswürdigen Anwendungsserver hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="d4c0f-105">So erstellen Sie einen vertrauenswürdigen Anwendungspool</span><span class="sxs-lookup"><span data-stu-id="d4c0f-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="d4c0f-106">Starten Sie die lync Server 2013 Management-Shell.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="d4c0f-107">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="d4c0f-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="d4c0f-108">Damit wird die "siteIP" für den "siteName" zurückgegeben, unter dem Sie den Pool erstellen.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="d4c0f-109">Ausführliche Informationen finden Sie unter [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in der Dokumentation zur lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="d4c0f-110">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="d4c0f-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="d4c0f-111">Ausführliche Informationen finden Sie unter [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in der Dokumentation zur lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="d4c0f-112">Der Exchange Server-FQDN sollte als Antragstellername oder alternativer Antragstellername des Exchange OWA-Zertifikats konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="d4c0f-113">Überprüfen Sie in Exchange OWA, ob der FQDN des Pools ebenfalls vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d4c0f-114">Wenn sich der CAS-Server <EM>nicht</EM> auf demselben Server befindet, auf dem Exchange 2013 Unified Messaging (um) ausgeführt wird, überspringen Sie die verbleibenden Schritte in diesem Verfahren, und führen Sie das Verfahren "Erstellen einer vertrauenswürdigen Anwendung für den Exchange 2013-CAS-Server" weiter unten in diesem Thema aus.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="d4c0f-115">Wenn sich der CAS-Server auf demselben Server befindet, auf dem Exchange 2013 Unified Messaging (um) ausgeführt wird, führen Sie die Schritte in diesem Verfahren aus, und führen Sie das Verfahren "Erstellen einer vertrauenswürdigen Anwendung für den Exchange 2013-CAS-Server" weiter unten in diesem Thema aus.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="d4c0f-116">Führen Sie **Enable-CsTopology** aus.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="d4c0f-117">Öffnen Sie den Topologie-Generator, und laden Sie die bestehende Topologie herunter.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="d4c0f-118">Erweitern Sie im linken Bereich die Struktur bis hinunter zu **Vertrauenswürdige Anwendungsserver**.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="d4c0f-119">Erweitern Sie den Knoten **Vertrauenswürdige Anwendungsserver**.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="d4c0f-120">Der Exchange 2013 CAS-Server sollte jetzt als vertrauenswürdiger Anwendungsserver aufgeführt sein.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="d4c0f-121">So erstellen Sie eine vertrauenswürdige Anwendung für den Exchange 2013 CAS-Server</span><span class="sxs-lookup"><span data-stu-id="d4c0f-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="d4c0f-122">Starten Sie die lync Server 2013 Management-Shell.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="d4c0f-123">Wenn sich der CAS-Server *nicht* auf demselben Server befindet, auf dem Exchange 2013 Unified Messaging (um) ausgeführt wird, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="d4c0f-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="d4c0f-124">Ausführliche Informationen finden Sie im Thema [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in der Dokumentation zur lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="d4c0f-125">Führen Sie **Enable-CsTopology** aus.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="d4c0f-126">Erweitern Sie im linken Bereich des Topologie-Generators die Struktur bis hinunter zu **Vertrauenswürdige Anwendungsserver**.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="d4c0f-127">Erweitern Sie den Knoten **Vertrauenswürdige Anwendungsserver**.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="d4c0f-128">Der Exchange 2013 CAS-Server sollte jetzt als vertrauenswürdiger Anwendungsserver aufgeführt sein.</span><span class="sxs-lookup"><span data-stu-id="d4c0f-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

