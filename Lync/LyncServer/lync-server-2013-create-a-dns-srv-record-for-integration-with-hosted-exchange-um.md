---
title: Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange UM-Dienste
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f96b8873e7d83b7025b43b111312185b8e5d5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="7f0fc-102">Erstellen eines DNS-SRV-Eintrags für die Integration in gehostete Exchange UM-Dienste</span><span class="sxs-lookup"><span data-stu-id="7f0fc-102">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f0fc-103">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="7f0fc-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="7f0fc-104">In diesem Thema wird beschrieben, wie Sie den DNS-SRV-Eintrag (Domain Name System) konfigurieren, der für einen lync Server 2013-Edgeserver zur Weiterleitung an einen gehosteten Exchange-Dienst wie Microsoft Exchange Online erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-104">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="7f0fc-105">So erstellen Sie einen externen DNS-SRV-Eintrag für den gehosteten Exchange-Dienst</span><span class="sxs-lookup"><span data-stu-id="7f0fc-105">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="7f0fc-106">Melden Sie sich beim externen DNS-Server als Mitglied der DnsAdmins-Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-106">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="7f0fc-107">Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-107">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="7f0fc-108">Erweitern Sie in der Konsolenstruktur ihrer SIP-Domäne **Forward-Lookupzonen**, und wählen Sie die SIP-Domäne aus, in der lync Server 2013 installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-108">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="7f0fc-109">Sie müssen den DNS-SRV-Eintrag in der SIP-Domäne erstellen, in der lync Server installiert ist oder installiert wird.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-109">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed.</span></span> <span data-ttu-id="7f0fc-110">Wenn Sie den SRV-Eintrag erstellen, muss der für den Host mit diesem Dienst Feld verwendete FQDN der externe FQDN des Edge-Pools sein.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-110">When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool.</span></span> <span data-ttu-id="7f0fc-111">Wenn beispielsweise der externe FQDN Ihres Edge-Pools Edge01.contoso.net lautet, geben Sie diesen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-111">For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value.</span></span> <span data-ttu-id="7f0fc-112">Dieser muss sich ebenfalls in der gleichen Domäne wie der DNS-Hosteintrag (A) befinden.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-112">This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="7f0fc-113">Klicken Sie mit der rechten Maustaste auf die ausgewählte Domäne, und klicken Sie dann auf **Weitere neue Einträge**.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-113">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="7f0fc-114">Klicken Sie unter **Ressourceneintragstyp**auf **Dienststandort (SRV)**, und klicken Sie dann auf **Datensatz erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-114">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="7f0fc-115">Klicken Sie im **neuen Ressourceneintrag**auf **Dienst**, und geben \*\* \_Sie sipfederationtls\*\*ein.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-115">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="7f0fc-116">Klicken Sie auf **Protokoll**, und \*\* \_\*\* geben Sie dann TCP ein.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-116">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="7f0fc-117">Klicken Sie auf **Portnummer** und geben Sie **5061** ein.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-117">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="7f0fc-118">Klicken Sie auf **Host mit diesem Dienst**, und geben Sie dann den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des lync Server 2013-Edge-Pools ein, der Zugriff auf Ihr lync Server 2013-System für vertrauenswürdige externe Clients bietet.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-118">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7f0fc-119">Die Domäne muss auch als autorisierende, akzeptierte Domäne in Ihren Exchange Online-Einstellungen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-119">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="7f0fc-120">Ausführliche Informationen finden Sie unter Erstellen von akzeptierten Domänen unter <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-120">For details, see Create Accepted Domains at <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="7f0fc-121">Klicken Sie auf **OK** und dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="7f0fc-122">So überprüfen Sie, ob der DNS-SRV-Eintrag erfolgreich erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="7f0fc-122">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="7f0fc-123">Melden Sie sich bei einem Clientcomputer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-123">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="7f0fc-124">Klicken Sie auf  \*\*Start \*\* und dann auf  **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="7f0fc-125">Führen Sie an der Eingabeaufforderung den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7f0fc-125">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="7f0fc-126">Überprüfen Sie, ob Sie eine Antwort erhalten, die in die entsprechende IP-Adresse für den FQDN aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7f0fc-126">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f0fc-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f0fc-127">See Also</span></span>


[<span data-ttu-id="7f0fc-128">Erstellen von DNS-Einträgen für Reverseproxyserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f0fc-128">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

