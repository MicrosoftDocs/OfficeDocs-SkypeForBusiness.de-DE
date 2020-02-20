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
ms.openlocfilehash: 677b657f5bb7dacad6f1379aa4923052ba4ab1c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="852b8-102">Erstellen und Überprüfen von DNS-SRV-Einträgen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="852b8-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="852b8-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="852b8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="852b8-104">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNS-Admins" beim Server oder bei der Domäne angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="852b8-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="852b8-105">In diesem Thema wird beschrieben, wie Sie die Domain Name System (DNS) Datensätze konfigurieren, die Sie in lync Server 2013-Bereitstellungen erstellen müssen und die für die automatische Clientanmeldung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="852b8-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="852b8-106">Wenn Sie eine Front-End-Pool erstellen, erstellt Setup Active Directory Objekte und Einstellungen für den Pool, einschließlich des vollqualifizierten Domänennamens (FQDN) des Pools.</span><span class="sxs-lookup"><span data-stu-id="852b8-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="852b8-107">Für ein Standard Edition-Server werden ähnliche Objekte und Einstellungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="852b8-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="852b8-108">Damit Clients eine Verbindung mit dem Pool oder Standard Edition-Server herstellen können, muss der FQDN des Pools oder Standard Edition-Server in DNS registriert sein.</span><span class="sxs-lookup"><span data-stu-id="852b8-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="852b8-109">Sie müssen DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne erstellen.</span><span class="sxs-lookup"><span data-stu-id="852b8-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="852b8-110">Für diese Vorgehensweise wird davon ausgegangen, dass das interne DNS Zonen für die SIP-Benutzerdomänen aufweist.</span><span class="sxs-lookup"><span data-stu-id="852b8-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="852b8-111">So konfigurieren Sie einen DNS-SRV-Eintrag</span><span class="sxs-lookup"><span data-stu-id="852b8-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="852b8-112">Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="852b8-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="852b8-113">Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die SIP-Domäne, in der lync Server 2013 installiert wird.</span><span class="sxs-lookup"><span data-stu-id="852b8-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="852b8-114">Klicken Sie auf **Neue Datensätze**.</span><span class="sxs-lookup"><span data-stu-id="852b8-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="852b8-115">Klicken Sie unter **Ressourceneintragstyp auswählen**auf **Dienststandort (SRV)**, und klicken Sie dann auf **Datensatz erstellen**.</span><span class="sxs-lookup"><span data-stu-id="852b8-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="852b8-116">Klicken Sie auf **Dienst**, und \*\* \_\*\* geben Sie sipinternaltls.</span><span class="sxs-lookup"><span data-stu-id="852b8-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="852b8-117">Klicken Sie auf **Protokoll**, und \*\* \_\*\* geben Sie dann TCP ein.</span><span class="sxs-lookup"><span data-stu-id="852b8-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="852b8-118">Klicken Sie auf **Portnummer**, und geben Sie **5061** ein.</span><span class="sxs-lookup"><span data-stu-id="852b8-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="852b8-119">Klicken Sie auf Host, der **diesen Dienst anbietet**, und geben Sie dann den FQDN des Pools oder Standard Edition-Server ein.</span><span class="sxs-lookup"><span data-stu-id="852b8-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="852b8-120">Klicken Sie auf **OK** und dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="852b8-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="852b8-121">So überprüfen Sie die Erstellung eines DNS-SRV-Eintrags</span><span class="sxs-lookup"><span data-stu-id="852b8-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="852b8-122">Melden Sie sich bei einem Clientcomputer in der Domäne mit einem Konto an, das Mitglied der Gruppe der authentifizierten Benutzer ist oder über entsprechende Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="852b8-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="852b8-123">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="852b8-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="852b8-124">Geben Sie im Feld **Öffnen** die Zeichenfolge **cmd** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="852b8-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="852b8-125">Geben Sie an der Eingabeaufforderung **nslookup**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="852b8-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="852b8-126">Geben Sie Typ **festlegen = SRV**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="852b8-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="852b8-127">Geben \*\* \_Sie sipinternaltls\_ ein. TCP.contoso.com\*\*, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="852b8-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="852b8-128">Die für den TLS-Eintrag (Transport Layer Security) angezeigte Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="852b8-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="852b8-129">Server: \<DNS-\>Server. contoso.com</span><span class="sxs-lookup"><span data-stu-id="852b8-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="852b8-130">Adresse: \<IP-Adresse des DNS-Servers\></span><span class="sxs-lookup"><span data-stu-id="852b8-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="852b8-131">Nicht autorisierende Antwort:</span><span class="sxs-lookup"><span data-stu-id="852b8-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="852b8-132">\_sipinternaltls. \_Speicherort des TCP.contoso.com-SRV-Diensts:</span><span class="sxs-lookup"><span data-stu-id="852b8-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="852b8-133">Priorität = 0</span><span class="sxs-lookup"><span data-stu-id="852b8-133">priority = 0</span></span>
    
    <span data-ttu-id="852b8-134">Gewichtung = 0</span><span class="sxs-lookup"><span data-stu-id="852b8-134">weight = 0</span></span>
    
    <span data-ttu-id="852b8-135">Port = 5061</span><span class="sxs-lookup"><span data-stu-id="852b8-135">port = 5061</span></span>
    
    <span data-ttu-id="852b8-136">SVR Hostname = Poolname.contoso.com (oder Standard Edition-Server eines Datensatzes)</span><span class="sxs-lookup"><span data-stu-id="852b8-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="852b8-137">Poolname.contoso.com Internet Address = \<virtuelle IP-Adresse des Lastenausgleichs\> oder \<die IP-Adresse eines einzelnen Enterprise Edition-Server für Pools mit nur einem\> Enterprise Edition-Server \<oder einer IP-Adresse des Standard Edition-Server\></span><span class="sxs-lookup"><span data-stu-id="852b8-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="852b8-138">Geben Sie nach Abschluss der Eingabeaufforderung **Exit**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="852b8-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="852b8-139">So überprüfen Sie, ob der FQDN des Front-End-Pools oder Standard Edition-Servers aufgelöst werden kann</span><span class="sxs-lookup"><span data-stu-id="852b8-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="852b8-140">Melden Sie sich an einem Clientcomputer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="852b8-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="852b8-141">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="852b8-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="852b8-142">Geben Sie im Feld **Öffnen** die Zeichenfolge **cmd** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="852b8-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="852b8-143">Geben Sie an der Eingabeaufforderung **nslookup** \<-FQDN des Front-End-Pool\> oder \<FQDN des Standard Edition-Server\>ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="852b8-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="852b8-144">Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="852b8-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

