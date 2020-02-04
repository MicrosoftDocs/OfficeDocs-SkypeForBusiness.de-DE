---
title: 'Lync Server 2013: Konfigurieren von DNS für die Edgeunterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c905c8fff7a67b26a7df8d2c741ce0a16fddce6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="88307-102">Konfigurieren von DNS für die Edgeunterstützung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88307-102">Configure DNS for edge support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88307-103">_**Letztes Änderungsdatum des Themas:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="88307-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="88307-104">Sie müssen DNS-Einträge (Domain Name System) für interne und externe Edge-Schnittstellen konfigurieren, einschließlich der Edge-Server-und Reverse-Proxy-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="88307-104">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="88307-105">Edgeserver sind standardmäßig nicht mit einer Domäne verbunden und verfügen nicht über einen vollqualifizierten Domänennamen (vollständig qualifizierter Domänenname).</span><span class="sxs-lookup"><span data-stu-id="88307-105">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="88307-106">Der Edgeserver wird nur mit dem kurzen Namen (Computer) und nicht mit einem vollqualifizierten Domänennamen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="88307-106">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="88307-107">Der Topologie-Generator verwendet jedoch FQDNs und keine kurzen Namen.</span><span class="sxs-lookup"><span data-stu-id="88307-107">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="88307-108">Der Name des Edgeserver muss dem vom Topologie-Generator verwendeten FQDN entsprechen.</span><span class="sxs-lookup"><span data-stu-id="88307-108">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="88307-109">Zu diesem Zweck definieren Sie ein DNS-Suffix, das in Kombination mit dem Computernamen zum erwarteten FQDN führt.</span><span class="sxs-lookup"><span data-stu-id="88307-109">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="88307-110">Gehen Sie wie folgt vor, um das DNS-Suffix zu dem Computernamen auf und dem Edgeserver hinzuzufügen, die nicht zu einer Domäne hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="88307-110">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88307-111">Standardmäßig verwendet DNS einen Round-Robin-Algorithmus, um die Reihenfolge der in Abfrage Antworten zurückgegebenen Ressourceneintragsdaten zu drehen, wenn mehrere Ressourceneinträge desselben Typs für einen abgefragten DNS-Domänennamen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="88307-111">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="88307-112">Der lync Server 2013-DNS-Lastenausgleich hängt vom DNS-Roundrobin als Teil des DNS-Lastenausgleichsmechanismus ab.</span><span class="sxs-lookup"><span data-stu-id="88307-112">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="88307-113">Überprüfen Sie, ob die Roundrobin-Einstellung deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="88307-113">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="88307-114">Wenn Sie einen DNS-Server verwenden, auf dem kein Windows-Betriebssystem ausgeführt wird, stellen Sie sicher, dass die Round-Robin-Ressourceneintrags Reihenfolge aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="88307-114">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="88307-115">Führen Sie die folgenden Verfahren in "**So erstellen Sie einen DNS-SRV-Eintrag**" aus, um jeden DNS-SRV-Eintrag zu erstellen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="88307-115">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="88307-116">Verwenden Sie das Verfahren unter "**So erstellen Sie einen DNS-Eintrag**", um die DNS-a-Einträge zu definieren, die für den Zugriff durch externe Benutzer erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="88307-116">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="88307-117">Wenn Sie sicherstellen möchten, dass die Datensätze konfiguriert sind und ordnungsgemäß funktionieren, lesen Sie "**So überprüfen Sie einen DNS-Eintrag**" in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="88307-117">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="88307-118">Details zu den einzelnen Datensätzen, die für die Unterstützung des Zugriffs externer Benutzer erforderlich sind, finden Sie unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88307-118">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="88307-119">So fügen Sie dem Computernamen auf einem Edgeserver, der nicht zu einer Domäne gehört, das DNS-Suffix hinzu</span><span class="sxs-lookup"><span data-stu-id="88307-119">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="88307-120">Klicken Sie auf dem Computer auf **Start**, klicken Sie mit der rechten Maustaste auf **Computer**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="88307-120">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="88307-121">Klicken Sie unter **Computer Name, Domäne und Arbeitsgruppeneinstellungen**auf **Einstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="88307-121">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="88307-122">Klicken Sie auf der Registerkarte **Computer Name** auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="88307-122">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="88307-123">Klicken Sie unter **Computer Name/domänenänderungen**auf **mehr**.</span><span class="sxs-lookup"><span data-stu-id="88307-123">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="88307-124">Geben Sie unter **DNS-Suffix und NetBIOS-Computername**in **Primäres DNS-Suffix dieses Computers**den Namen Ihrer internen Domäne (beispielsweise Corp.contoso.com) ein, und klicken Sie dann dreimal auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="88307-124">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="88307-125">Starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="88307-125">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="88307-126">So erstellen Sie einen DNS-SRV-Eintrag</span><span class="sxs-lookup"><span data-stu-id="88307-126">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="88307-127">Klicken Sie auf dem entsprechenden DNS-Server auf **Start**, klicken Sie auf **System**Steuerung, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="88307-127">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="88307-128">Sie müssen DNS so konfigurieren, dass: 1) externe DNS-Einträge für externe DNS-Lookups von Remotebenutzern und Verbundpartnern vorhanden sind. 2) Einträge für DNS-Lookups zur Verwendung durch die Edgeserver im Umkreisnetzwerk (auch bekannt als DMZ, demilitarisierte Zone und geschirmtes Subnetz), einschließlich Datensätzen für die internen Server mit lync Server 2013; und 3) interne DNS-Einträge für Lookups von den internen Clients und Servern, auf denen lync Server 2013 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="88307-128">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="88307-129">Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="88307-129">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="88307-130">Klicken Sie auf **andere neue Datensätze**.</span><span class="sxs-lookup"><span data-stu-id="88307-130">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="88307-131">Geben Sie unter **Ressourceneintragstyp auswählen den**Namen **Dienststandort (SRV)** ein, und klicken Sie dann auf **Datensatz erstellen**.</span><span class="sxs-lookup"><span data-stu-id="88307-131">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="88307-132">Geben Sie alle erforderlichen Informationen für den DNS-SRV-Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="88307-132">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="88307-133">So erstellen Sie einen DNS-a-Eintrag</span><span class="sxs-lookup"><span data-stu-id="88307-133">To create a DNS A record</span></span>

1.  <span data-ttu-id="88307-134">Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **System**Steuerung, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="88307-134">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="88307-135">Erweitern Sie in der Konsolenstruktur ihrer SIP-Domäne **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="88307-135">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="88307-136">Klicken Sie auf **neuer Host (a)**.</span><span class="sxs-lookup"><span data-stu-id="88307-136">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="88307-137">Geben Sie alle erforderlichen Informationen für den DNS-SRV-Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="88307-137">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="88307-138">So überprüfen Sie einen DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="88307-138">To verify a DNS record</span></span>

1.  <span data-ttu-id="88307-139">Melden Sie sich bei einem Clientcomputer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="88307-139">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="88307-140">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="88307-140">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="88307-141">Führen Sie an der Eingabeaufforderung den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="88307-141">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="88307-142">Überprüfen Sie, ob Sie eine Antwort erhalten, die in die entsprechende IP-Adresse für den FQDN aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="88307-142">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88307-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88307-143">See Also</span></span>


[<span data-ttu-id="88307-144">Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange UM-Dienste</span><span class="sxs-lookup"><span data-stu-id="88307-144">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="88307-145">Ermitteln von DNS-Anforderungen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88307-145">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

