---
title: Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange um
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c30164813619a271f2321db3ff3e8019067193c0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="f7d10-102">Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange um</span><span class="sxs-lookup"><span data-stu-id="f7d10-102">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7d10-103">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f7d10-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f7d10-104">In diesem Thema wird beschrieben, wie Sie den Domain Name System (DNS) SRV-Eintrag konfigurieren, der erforderlich ist, damit ein lync Server 2013 Edgeserver an einen gehosteten Exchange-Dienst wie Microsoft Exchange Online weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="f7d10-104">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="f7d10-105">So erstellen Sie einen externen DNS-SRV-Eintrag für den gehosteten Exchange-Dienst</span><span class="sxs-lookup"><span data-stu-id="f7d10-105">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="f7d10-106">Melden Sie sich am externen DNS-Server als Mitglied der Gruppe "DnsAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="f7d10-106">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="f7d10-107">Klicken Sie auf **Start**, auf **Verwaltung** und anschließend auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f7d10-107">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="f7d10-108">Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen**, und wählen Sie die SIP-Domäne aus, in der lync Server 2013 installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7d10-108">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="f7d10-p101">Sie müssen den DNS-SRV-Eintrag in der SIP-Domäne erstellen, in der Lync Server installiert ist oder wird. Wenn Sie den SRV-Eintrag erstellen, muss für das Feld "Host, der diesen Dienst anbietet" der externe FQDN des Edgepools verwendet werden. Wenn beispielsweise der externe FQDN des Edgepools "edge01.contoso.net" ist, geben Sie diesen Wert in das Feld ein. Der FQDN muss sich auch in derselben Domäne wie der DNS-A-Eintrag (Hosts) befinden.</span><span class="sxs-lookup"><span data-stu-id="f7d10-p101">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed. When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool. For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value. This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="f7d10-113">Klicken Sie mit der rechten Maustaste auf die ausgewählte Domäne, und klicken Sie dann auf **Andere neue Einträge**.</span><span class="sxs-lookup"><span data-stu-id="f7d10-113">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="f7d10-114">Klicken Sie In **Ressourceneintragstyp** auf **Dienstidentifizierung (SRV)**, und klicken Sie dann auf **Eintrag erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f7d10-114">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="f7d10-115">Klicken Sie unter **neuer Ressourceneintrag**auf **Dienst**, und geben \*\* \_Sie sipfederationtls\*\*.</span><span class="sxs-lookup"><span data-stu-id="f7d10-115">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="f7d10-116">Klicken Sie auf **Protokoll**, und \*\* \_\*\* geben Sie dann TCP ein.</span><span class="sxs-lookup"><span data-stu-id="f7d10-116">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="f7d10-117">Klicken Sie auf **Portnummer**, und geben Sie **5061** ein.</span><span class="sxs-lookup"><span data-stu-id="f7d10-117">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="f7d10-118">Klicken Sie auf Host, der **diesen Dienst anbietet**, und geben Sie dann den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des lync Server 2013 Edgepool ein, der Zugriff auf das lync Server 2013 System für vertrauenswürdige externe Clients bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f7d10-118">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f7d10-119">Die Domäne muss auch als autorisierende akzeptierte Domäne in den Exchange Online-Einstellungen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="f7d10-119">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="f7d10-120">Ausführliche Informationen finden Sie unter CREATE Accepted <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>Domains at.</span><span class="sxs-lookup"><span data-stu-id="f7d10-120">For details, see Create Accepted Domains at <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="f7d10-121">Klicken Sie auf **OK** und dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="f7d10-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="f7d10-122">So stellen Sie sicher, dass der DNS-SRV-Eintrag erfolgreich erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="f7d10-122">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="f7d10-123">Melden Sie sich an einem Clientcomputer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="f7d10-123">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="f7d10-124">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f7d10-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="f7d10-125">Führen Sie an der Eingabeaufforderung den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f7d10-125">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="f7d10-126">Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="f7d10-126">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7d10-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7d10-127">See Also</span></span>


[<span data-ttu-id="f7d10-128">Erstellen von DNS-Einträgen für Reverse-Proxy Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7d10-128">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

