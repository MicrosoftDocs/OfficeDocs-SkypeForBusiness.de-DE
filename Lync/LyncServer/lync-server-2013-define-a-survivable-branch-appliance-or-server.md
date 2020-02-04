---
title: 'Lync Server 2013: Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df5577ff0211afd005feb8fea4788598a03d536e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="d3008-102">Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3008-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3008-103">_**Letztes Änderungsdatum des Themas:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="d3008-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="d3008-104">Führen Sie dieses Verfahren am zentralen Standort aus, wenn Sie die Survivable Branch-Appliance oder den Server nicht definiert haben, als Sie Sie zu Ihrer Topologie hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="d3008-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="d3008-105">So definieren Sie eine Survivable Branch-Appliance oder einen Überlebenden Branch-Server</span><span class="sxs-lookup"><span data-stu-id="d3008-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="d3008-106">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="d3008-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d3008-107">Erweitern Sie in der Konsolenstruktur die zentrale Website, erweitern Sie **Verzweigungs Standorte**, und erweitern Sie dann den Namen der Zweigstelle, auf der Sie die Survivable Branch-Appliance oder den Survivable Branch-Server bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d3008-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="d3008-108">Klicken Sie mit der rechten Maustaste auf **Survival Branch Appliances**, und klicken Sie dann auf **neue Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="d3008-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d3008-109">Überlebensfähige <STRONG>Branch-Appliances</STRONG> definieren Sie Survival-Branch-Server und Survivable Branch-Appliances.</span><span class="sxs-lookup"><span data-stu-id="d3008-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="d3008-110">Klicken Sie im Dialogfeld **Survivable Branch-Appliance definieren** auf **FQDN**, geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der Survivable Branch Appliance oder des Survivable Branch-Servers ein, den Sie an dieser Zweigstelle bereitstellen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="d3008-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d3008-111">Wenn Sie eine Survivable-Branch-Appliance definieren, muss der Name, den Sie in <STRONG>FQDN</STRONG> eingeben, dem Überlebenden Branch Appliance-FQDN entsprechen, den Sie dem <STRONG>servicePrincipalName</STRONG> -Attribut zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="d3008-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="d3008-112">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Hinzufügen einer Survivable Branch-Appliance zu Active Directory in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d3008-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="d3008-113">Klicken Sie auf **Front-End-Pool**, klicken Sie auf den Front-End-Server (User Services Pool) an der zentralen Website, mit der die überlebensfähige Branch-Appliance oder der Survivable Branch-Server eine Verbindung herstellen soll, und klicken Sie dann auf **weiter**</span><span class="sxs-lookup"><span data-stu-id="d3008-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="d3008-114">Klicken Sie auf **Edgeserver**, klicken Sie auf den Edge-Pool, der von dieser Survivable Branch Appliance oder einem Überlebenden Verzweigungs Server hergestellt wird, um die PSTN-Konnektivität für Remotebenutzer der Zweigstelle bereitzustellen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="d3008-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="d3008-115">Klicken Sie auf **Gateway-FQDN oder IP-Adresse**, und geben Sie dann den FQDN oder die IP-Adresse des Gateway-Peers ein, dem die Survivable Branch-Appliance oder der Survivable Branch-Server zugeordnet ist, um eingehende oder ausgehende PSTN-Anrufe weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="d3008-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d3008-116">Wenn Sie eine Survivable Branch-Appliance definieren, ist dies das Gateway, auf das der Vermittlungs Server innerhalb der Survivable Branch-Appliance für PSTN-Konnektivität zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="d3008-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="d3008-117">Klicken Sie auf **Überwachungs Port für IP/PSTN-Gateway**, und übernehmen Sie den Standardport.</span><span class="sxs-lookup"><span data-stu-id="d3008-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="d3008-118">Klicken Sie im **SIP-Transportprotokoll**auf das Transport Protokoll, das von der Survivable Branch-Appliance oder dem Survivable Branch-Server verwendet wird, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d3008-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d3008-119">Aus Sicherheitsgründen empfehlen wir dringend, TLS (Transport Layer Security) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3008-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="d3008-120">Wenn Sie eine Survivable Branch-Appliance definieren, lesen Sie in der Dokumentation Ihres Survivable Branch Appliance-Herstellers nach, ob Ihre Survivable Branch-Appliance das TLS-Protokoll unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d3008-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="d3008-121">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf die neue Survivable Branch-Appliance oder den neuen Server, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="d3008-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="d3008-122">**Nächster Schritt**: [Bereitstelleneiner überlebensfähigen Branch-Appliance oder eines Servers mit lync Server 2013-Branch Site-Aufgabe](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="d3008-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

