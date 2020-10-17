---
title: 'Lync Server 2013: Konfigurieren von DNS für den Lastenausgleich'
description: 'Lync Server 2013: Konfigurieren von DNS für den Lastenausgleich.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b13db22d65ee67723ebc0a31544137d467d5c6b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553451"
---
# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="c985f-103">Konfigurieren von DNS für den Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c985f-103">Configure DNS for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c985f-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c985f-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c985f-105">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNS-Admins" beim Server oder bei der Domäne angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="c985f-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="c985f-106">Bei Domain Name System (DNS) Lastenausgleich wird der für lync Server 2013 eindeutige Netzwerkdatenverkehr wie SIP-Datenverkehr und Mediendatenverkehr ausgeglichen.</span><span class="sxs-lookup"><span data-stu-id="c985f-106">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="c985f-107">Der DNS-Lastenausgleich wird für Front-End-Pools, Edgeserverpools, Director-Pools und eigenständige Vermittlungsserverpools unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c985f-107">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="c985f-108">Für einen Pool, der für die Verwendung des DNS-Lastenausgleichs konfiguriert ist, müssen zwei vollqualifizierte Domänennamen (FQDNs) definiert sein: der reguläre Pool-FQDN, der vom DNS-Lastenausgleich verwendet wird (beispielsweise pool1.contoso.com) und der in die physischen IPS der Server im Pool aufgelöst wird, sowie einen anderen FQDN für die Webdienste des Pools (beispielsweise web1.contoso.net), der in die virtuelle IP-Adresse des Pools aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c985f-108">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="c985f-109">Ausführliche Informationen zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c985f-109">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c985f-110">Hardwarelastenausgleich ist weiterhin für den HTTPS-Datenverkehr zwischen Client und Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c985f-110">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="c985f-111">Bevor Sie den DNS-Lastenausgleich verwenden können, müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c985f-111">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="c985f-112">Überschreiben Sie den internen FQDN des Webdienste Pools.</span><span class="sxs-lookup"><span data-stu-id="c985f-112">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c985f-113">Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="c985f-113">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="c985f-114">Erstellen Sie DNS-A-Einträge zum Auflösen der Pool-FQDN in die IP-Adressen aller Server im Pool.</span><span class="sxs-lookup"><span data-stu-id="c985f-114">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="c985f-115">Aktivieren Sie zufällige IP-Adressen oder (für Windows Server DNS) Roundrobin.</span><span class="sxs-lookup"><span data-stu-id="c985f-115">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c985f-116">Roundrobin sollte standardmäßig aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c985f-116">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="c985f-117">So setzen Sie den FQDN der internen Webdienste außer Kraft</span><span class="sxs-lookup"><span data-stu-id="c985f-117">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="c985f-118">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="c985f-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="c985f-119">Erweitern Sie in der Konsolenstruktur den Knoten für die Enterprise Edition-Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="c985f-119">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="c985f-120">Klicken Sie mit der rechten Maustaste auf den Pool, klicken Sie auf **Eigenschaften bearbeiten** und dann auf **Webdienste**.</span><span class="sxs-lookup"><span data-stu-id="c985f-120">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="c985f-121">Aktivieren Sie unterhalb von **Interne Webdienste** das Kontrollkästchen **Vollqualifizierten Domänennamen außer Kraft setzen**.</span><span class="sxs-lookup"><span data-stu-id="c985f-121">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="c985f-122">Geben Sie den Pool-FQDN ein, der in die physischen IP-Adressen der Server im Pool aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c985f-122">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="c985f-123">Geben Sie unterhalb von **Externe Webdienste** den externen Pool-FQDN ein, der in die virtuellen IP-Adressen des Pools aufgelöst wird, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c985f-123">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="c985f-124">Klicken Sie in der Konsolenstruktur auf **lync Server 2013**, und klicken Sie dann im Bereich **Aktionen** auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="c985f-124">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="c985f-125">So erstellen Sie DNS-Hosteinträge (A) für alle internen Poolserver</span><span class="sxs-lookup"><span data-stu-id="c985f-125">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="c985f-126">Klicken Sie nacheinander auf **Start**, **Alle Programme**, **Verwaltung** und **DNS**.</span><span class="sxs-lookup"><span data-stu-id="c985f-126">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="c985f-127">Klicken Sie im **DNS Manager** auf den DNS-Server für die Eintragsverwaltung, um diesen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="c985f-127">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="c985f-128">Klicken Sie auf **Forward-Lookupzonen**, um den Knoten zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="c985f-128">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="c985f-129">Klicken Sie mit der rechten Maustaste auf die DNS-Domäne, der Sie Einträge hinzufügen möchten, und klicken Sie dann auf **Neuer Host (A oder AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="c985f-129">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="c985f-130">Geben Sie im Feld **Name** den Namen des Hosteintrags ein (der Domänenname wird automatisch angehängt).</span><span class="sxs-lookup"><span data-stu-id="c985f-130">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="c985f-131">Geben Sie im Feld für die IP-Adresse die IP-Adresse des Front-End-Servers ein, und wählen Sie anschließend **Verknüpften PTR-Eintrag erstellen** oder **Authentifizierte Benutzer können DNS-Einträge mit demselben Besitzernamen aktualisieren**, falls anwendbar.</span><span class="sxs-lookup"><span data-stu-id="c985f-131">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="c985f-132">Fahren Sie mit der Erstellung von Einträgen für alle Front-End-Mitgliedsserver fort, die in den DNS-Lastenausgleich einbezogen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c985f-132">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="c985f-133">Wenn Sie beispielsweise über einen Pool namens "pool1.contoso.com" und drei Front-End-Server verfügen, erstellen Sie die folgenden DNS-Einträge:</span><span class="sxs-lookup"><span data-stu-id="c985f-133">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c985f-134">FQDN</span><span class="sxs-lookup"><span data-stu-id="c985f-134">FQDN</span></span></th>
    <th><span data-ttu-id="c985f-135">Typ</span><span class="sxs-lookup"><span data-stu-id="c985f-135">Type</span></span></th>
    <th><span data-ttu-id="c985f-136">Daten</span><span class="sxs-lookup"><span data-stu-id="c985f-136">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c985f-137">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c985f-137">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="c985f-138">Host (A)</span><span class="sxs-lookup"><span data-stu-id="c985f-138">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="c985f-139">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="c985f-139">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c985f-140">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c985f-140">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="c985f-141">Host (A)</span><span class="sxs-lookup"><span data-stu-id="c985f-141">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="c985f-142">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="c985f-142">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c985f-143">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c985f-143">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="c985f-144">Host (A)</span><span class="sxs-lookup"><span data-stu-id="c985f-144">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="c985f-145">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="c985f-145">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="c985f-146">Ausführliche Informationen zum Erstellen von DNS-Hosteinträgen (A) finden Sie unter [Konfigurieren von DNS-Hosteinträgen für lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span><span class="sxs-lookup"><span data-stu-id="c985f-146">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="c985f-147">So aktivieren Sie Roundrobin für Windows Server</span><span class="sxs-lookup"><span data-stu-id="c985f-147">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="c985f-148">Klicken Sie nacheinander auf **Start**, **Alle Programme**, **Verwaltung** und **DNS**.</span><span class="sxs-lookup"><span data-stu-id="c985f-148">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="c985f-149">Erweitern Sie **DNS**, klicken Sie mit der rechten Maustaste auf den DNS-Server, den Sie konfigurieren möchten, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c985f-149">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="c985f-150">Klicken Sie auf die Registerkarte **Erweitert**, wählen Sie **Roundrobin aktivieren** und **Netzwerkmaskenanforderung aktivieren**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c985f-150">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="c985f-151">![DNS-Roundrobin-Dialogfeld](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS-Roundrobin-Dialogfeld")</span><span class="sxs-lookup"><span data-stu-id="c985f-151">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c985f-152">Diese Funktion sollte standardmäßig aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c985f-152">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c985f-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c985f-153">See Also</span></span>


[<span data-ttu-id="c985f-154">DNS-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c985f-154">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

