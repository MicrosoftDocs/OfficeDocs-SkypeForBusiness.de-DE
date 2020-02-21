---
title: 'Lync Server 2013: Konfigurieren von DNS für die Edge-Unterstützung'
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
ms.openlocfilehash: d7b3dcb9693ed6ab58d2828570e81ef05709867e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="df772-102">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df772-102">Configure DNS for edge support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df772-103">_**Letztes Änderungsstand des Themas:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="df772-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="df772-104">Sie müssen DNS-Einträge (Domain Name System) für interne und externe Edgeschnittstellen konfigurieren, sowohl für Edgeserver- als auch für Reverseproxyschnittstellen.</span><span class="sxs-lookup"><span data-stu-id="df772-104">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="df772-105">Edgeserver sind standardmäßig nicht Mitglied einer Domäne und haben keinen vollqualifizierten Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="df772-105">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="df772-106">Der Edgeserver wird nur durch den kurzen Computernamen bezeichnet und nicht durch einen vollqualifizierten Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="df772-106">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="df772-107">Der Topologie-Generator verwendet jedoch FQDNs und keine Kurznamen.</span><span class="sxs-lookup"><span data-stu-id="df772-107">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="df772-108">Der Name der Edgeserver muss mit dem FQDN übereinstimmen, der vom Topologie-Generator verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="df772-108">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="df772-109">Hierzu definieren Sie ein DNS-Suffix, das, wenn es mit dem Computernamen kombiniert wird, den erwarteten FQDN ergibt.</span><span class="sxs-lookup"><span data-stu-id="df772-109">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="df772-110">Nutzen Sie das unter "So fügen Sie das DNS-Suffix zum Computernamen eines Edgeservers hinzu, der nicht Mitglied einer Domäne ist" beschriebene Verfahren, um das DNS-Suffix zum Computernamen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="df772-110">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df772-111">Standardmäßig verwendet DNS einen Round Robin-Algorithmus, um die Reihenfolge der Ressourcendatensatz Daten zu drehen, die in Abfrage Antworten zurückgegeben werden, wenn mehrere Ressourceneinträge desselben Typs für einen abgefragten DNS-Domänennamen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="df772-111">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="df772-112">Lync Server 2013 DNS-Lastenausgleich hängt vom DNS-Roundrobin als Teil des DNS-Lastenausgleichsmechanismus ab.</span><span class="sxs-lookup"><span data-stu-id="df772-112">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="df772-113">Stellen Sie sicher, dass die Roundrobin-Einstellung nicht deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="df772-113">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="df772-114">Wenn Sie einen DNS-Server verwenden, auf dem kein Windows-Betriebssystem installiert ist, stellen Sie sicher, dass die Reihenfolge der Round Robin-Ressourceneinträge aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="df772-114">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="df772-115">Erstellen und überprüfen Sie einen DNS-SRV-Eintrag entsprechend dem Verfahren **So erstellen Sie einen DNS-SRV-Eintrag**.</span><span class="sxs-lookup"><span data-stu-id="df772-115">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="df772-116">Definieren Sie die für den Zugriff externer Benutzer erforderlichen DNS-A-Einträge nach dem unter **So erstellen Sie einen DNS-A-Eintrag** beschriebenen Verfahren.</span><span class="sxs-lookup"><span data-stu-id="df772-116">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="df772-117">Unter **So überprüfen Sie einen DNS-Eintrag** erfahren Sie in diesem Thema, wie Sie prüfen können, ob die Einträge richtig konfiguriert sind und funktionieren.</span><span class="sxs-lookup"><span data-stu-id="df772-117">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="df772-118">Ausführliche Informationen zu jedem Datensatz, der für die Unterstützung des Zugriffs durch externe Benutzer erforderlich ist, finden Sie unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df772-118">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="df772-119">So fügen Sie das DNS-Suffix zum Computernamen auf einem Edgeserver hinzu, der nicht Mitglied einer Domäne ist</span><span class="sxs-lookup"><span data-stu-id="df772-119">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="df772-120">Klicken Sie auf dem Computer auf **Start**, klicken Sie mit der rechten Maustaste auf **Arbeitsplatz**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="df772-120">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="df772-121">Klicken Sie unter **Einstellungen für Computernamen, Domäne und Arbeitsgruppe** auf **Einstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="df772-121">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="df772-122">Klicken Sie auf der Registerkarte **Computername** auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="df772-122">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="df772-123">Klicken Sie in **Ändern des Computernamens bzw. der Domäne** auf **Mehr**.</span><span class="sxs-lookup"><span data-stu-id="df772-123">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="df772-124">Geben Sie in **DNS-Suffix und NetBIOS-Computername** unter **Primäres DNS-Suffix des Computers** den Namen Ihrer internen Domäne (z. B. corp.contoso.com) ein, und klicken Sie dann dreimal auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="df772-124">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="df772-125">Starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="df772-125">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="df772-126">So erstellen Sie einen DNS-SRV-Eintrag</span><span class="sxs-lookup"><span data-stu-id="df772-126">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="df772-127">Klicken Sie auf dem geeigneten DNS-Server nacheinander auf **Start**, **Systemsteuerung**, **Verwaltung** und dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="df772-127">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="df772-128">Sie müssen DNS so konfigurieren, dass es: 1) externe DNS-Einträge für externe DNS-Lookups von Remotebenutzern und Partnerverbund Partnern gibt; 2) Einträge für DNS-Lookups zur Verwendung durch die Edgeserver innerhalb des Umkreisnetzwerks (auch bekannt als DMZ, demilitarisierte Zone und überwachtes Subnetz), einschließlich einer Datensätze für die internen Server mit lync Server 2013; und 3) interne DNS-Einträge für Nachschlagevorgänge von den internen Clients und Servern mit lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df772-128">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="df772-129">Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="df772-129">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="df772-130">Klicken Sie auf **Neue Datensätze**.</span><span class="sxs-lookup"><span data-stu-id="df772-130">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="df772-131">Klicken Sie unter **Wählen Sie einen Ressourceneintragstyp** auf **Dienstidentifizierung (SRV)** und dann auf **Eintrag erstellen**.</span><span class="sxs-lookup"><span data-stu-id="df772-131">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="df772-132">Stellen Sie alle erforderlichen Informationen für den DNS-SRV-Eintrag bereit.</span><span class="sxs-lookup"><span data-stu-id="df772-132">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="df772-133">So erstellen Sie einen DNS-A-Eintrag</span><span class="sxs-lookup"><span data-stu-id="df772-133">To create a DNS A record</span></span>

1.  <span data-ttu-id="df772-134">Klicken Sie auf dem DNS-Server nacheinander auf **Start**, **Systemsteuerung**, **Verwaltung** und dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="df772-134">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="df772-135">Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="df772-135">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="df772-136">Klicken Sie auf **Neuer Host (A)**.</span><span class="sxs-lookup"><span data-stu-id="df772-136">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="df772-137">Stellen Sie alle erforderlichen Informationen für den DNS-SRV-Eintrag bereit.</span><span class="sxs-lookup"><span data-stu-id="df772-137">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="df772-138">So überprüfen Sie einen DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="df772-138">To verify a DNS record</span></span>

1.  <span data-ttu-id="df772-139">Melden Sie sich bei einem Clientcomputer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="df772-139">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="df772-140">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="df772-140">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="df772-141">Führen Sie an der Eingabeaufforderung den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="df772-141">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="df772-142">Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="df772-142">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df772-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df772-143">See Also</span></span>


[<span data-ttu-id="df772-144">Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange um</span><span class="sxs-lookup"><span data-stu-id="df772-144">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="df772-145">Bestimmen der DNS-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df772-145">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

