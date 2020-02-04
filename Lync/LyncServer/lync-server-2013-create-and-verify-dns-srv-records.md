---
title: 'Lync Server 2013: Erstellen und Überprüfen von DNS-SRV-Einträgen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8440d2ae91d535c8c4747c923b1b17dda9bb0f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="4c801-102">Erstellen und Überprüfen von DNS-SRV-Einträgen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c801-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c801-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4c801-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4c801-104">Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie am Server oder in der Domäne minimal als Mitglied der Gruppe der Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="4c801-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="4c801-105">In diesem Thema wird beschrieben, wie Sie die DNS-Einträge (Domain Name System) konfigurieren, die Sie in lync Server 2013-Bereitstellungen erstellen müssen, und die für die automatische Clientanmeldung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4c801-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="4c801-106">Wenn Sie einen Front-End-Pool erstellen, erstellt Setup Active Directory-Objekte und-Einstellungen für den Pool, einschließlich des vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) des Pools.</span><span class="sxs-lookup"><span data-stu-id="4c801-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="4c801-107">Ähnliche Objekte und Einstellungen werden für einen Standard Edition-Server erstellt.</span><span class="sxs-lookup"><span data-stu-id="4c801-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="4c801-108">Damit Clients eine Verbindung mit dem Pool oder dem Standard Edition-Server herstellen können, muss der FQDN des Pools oder Standard Edition-Servers in DNS registriert sein.</span><span class="sxs-lookup"><span data-stu-id="4c801-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="4c801-109">Sie müssen DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c801-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="4c801-110">Bei diesem Verfahren wird davon ausgegangen, dass Ihr interner DNS Zonen für Ihre SIP-Benutzerdomänen aufweist.</span><span class="sxs-lookup"><span data-stu-id="4c801-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="4c801-111">So konfigurieren Sie einen DNS-SRV-Eintrag</span><span class="sxs-lookup"><span data-stu-id="4c801-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="4c801-112">Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="4c801-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="4c801-113">Erweitern Sie in der Konsolenstruktur ihrer SIP-Domäne **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die SIP-Domäne, in der lync Server 2013 installiert wird.</span><span class="sxs-lookup"><span data-stu-id="4c801-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="4c801-114">Klicken Sie auf **andere neue Datensätze**.</span><span class="sxs-lookup"><span data-stu-id="4c801-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="4c801-115">Klicken Sie unter **Wählen Sie einen Ressourceneintragstyp** auf **Dienstidentifizierung (SRV)** und dann auf **Eintrag erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4c801-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="4c801-116">Klicken Sie auf **Dienst**, und \*\* \_\*\* geben Sie sipinternaltls ein.</span><span class="sxs-lookup"><span data-stu-id="4c801-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="4c801-117">Klicken Sie auf **Protokoll**, und \*\* \_\*\* geben Sie dann TCP ein.</span><span class="sxs-lookup"><span data-stu-id="4c801-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="4c801-118">Klicken Sie auf **Portnummer** und geben Sie **5061** ein.</span><span class="sxs-lookup"><span data-stu-id="4c801-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="4c801-119">Klicken Sie auf **Host, der diesen Dienst anbietet** und geben Sie den FQDN des Pools bzw. des Standard Edition-Servers ein.</span><span class="sxs-lookup"><span data-stu-id="4c801-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="4c801-120">Klicken Sie auf **OK** und dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="4c801-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="4c801-121">So überprüfen Sie die Erstellung eines DNS-SRV-Eintrags</span><span class="sxs-lookup"><span data-stu-id="4c801-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="4c801-122">Melden Sie sich mit einem Konto, das Mitglied der Gruppe der authentifizierten Benutzer ist oder über gleichwertige Berechtigungen verfügt, an einem Clientcomputer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="4c801-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="4c801-123">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4c801-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="4c801-124">Geben Sie im Feld **Öffnen** den **Befehl cmd**ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c801-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="4c801-125">Geben Sie an der Eingabeaufforderung **nslookup**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4c801-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="4c801-126">Geben Sie Type **= SRV**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4c801-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="4c801-127">Geben \*\* \_Sie sipinternaltls\_ ein. TCP.contoso.com\*\*, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4c801-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="4c801-128">Die für den TLS-Eintrag (Transport Layer Security) angezeigte Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4c801-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="4c801-129">Server: \<DNS-\>Server. contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c801-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="4c801-130">Adresse: \<IP-Adresse des DNS-Servers\></span><span class="sxs-lookup"><span data-stu-id="4c801-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="4c801-131">Nicht autorisierende Antwort:</span><span class="sxs-lookup"><span data-stu-id="4c801-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="4c801-132">\_sipinternaltls. \_TCP.contoso.com SRV-Dienststandort:</span><span class="sxs-lookup"><span data-stu-id="4c801-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="4c801-133">Priorität = 0</span><span class="sxs-lookup"><span data-stu-id="4c801-133">priority = 0</span></span>
    
    <span data-ttu-id="4c801-134">Gewichtung = 0</span><span class="sxs-lookup"><span data-stu-id="4c801-134">weight = 0</span></span>
    
    <span data-ttu-id="4c801-135">Port = 5061</span><span class="sxs-lookup"><span data-stu-id="4c801-135">port = 5061</span></span>
    
    <span data-ttu-id="4c801-136">SVR Hostname = Poolname.contoso.com (oder Standard Edition Server A Record)</span><span class="sxs-lookup"><span data-stu-id="4c801-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="4c801-137">Poolname.contoso.com Internet Address = \<virtuelle IP-Adresse des Load Balancer\> oder \<IP-Adresse eines einzelnen Enterprise Edition-Servers für Pools mit nur einem\> Enter \<Prise Edition-Server oder einer IP-Adresse des Standard Edition-Servers\></span><span class="sxs-lookup"><span data-stu-id="4c801-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="4c801-138">Wenn Sie die Eingabeaufforderung beendet haben, geben Sie **Exit**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4c801-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="4c801-139">So überprüfen Sie, ob der FQDN des Front-End-Pools oder des Standard Edition-Servers aufgelöst werden kann</span><span class="sxs-lookup"><span data-stu-id="4c801-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="4c801-140">Melden Sie sich bei einem Clientcomputer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="4c801-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="4c801-141">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4c801-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="4c801-142">Geben Sie im Feld **Öffnen** den **Befehl cmd**ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c801-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="4c801-143">Geben Sie an der Eingabeaufforderung **nslookup** \<-FQDN des Front-End\> - \<Pools oder den FQDN des Standard\>Edition-Servers ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4c801-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="4c801-144">Überprüfen Sie, ob Sie eine Antwort erhalten, die in die entsprechende IP-Adresse für den FQDN aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="4c801-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

