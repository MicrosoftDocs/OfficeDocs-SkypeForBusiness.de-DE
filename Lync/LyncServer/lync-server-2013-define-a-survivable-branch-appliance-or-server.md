---
title: 'Lync Server 2013: Definieren eines Survivable Branch Appliance oder Servers'
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
ms.openlocfilehash: ee83a532f3e378cf0beb0d9d09a08e935cf56247
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516372"
---
# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="b8e36-102">Definieren einer Survivable Branch Appliance oder eines Servers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8e36-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8e36-103">_**Letztes Änderungsstand des Themas:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="b8e36-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="b8e36-104">Führen Sie das vorliegende Verfahren am zentralen Standort aus, wenn Sie die Survivable Branch Appliance oder den Survivable Branch Server nicht beim Hinzufügen zu Ihrer Topologie definiert haben.</span><span class="sxs-lookup"><span data-stu-id="b8e36-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="b8e36-105">So definieren Sie eine Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="b8e36-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="b8e36-106">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="b8e36-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b8e36-107">Erweitern Sie in der Konsolenstruktur den zentralen Standort, erweitern Sie **Zweigstellenstandorte**, und erweitern Sie dann den Namen des Zweigstellen Standorts, an dem die Survivable Branch Appliance oder Survivable Branch Server bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b8e36-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="b8e36-108">Klicken Sie mit der rechten Maustaste auf **Survivable Branch Appliances**, und klicken Sie dann auf **neue Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="b8e36-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b8e36-109"><STRONG>Survivable Branch Appliances</STRONG> ist der Ort, an dem Sie Survivable Branch-Server und Survivable Branch Appliances definieren.</span><span class="sxs-lookup"><span data-stu-id="b8e36-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="b8e36-110">Klicken Sie im Dialogfeld **Survivable Branch Appliance definieren** auf **FQDN**, geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der Survivable Branch Appliance oder Survivable Branch Server an, die Sie an dieser Zweigstelle bereitstellen möchten, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b8e36-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b8e36-111">Wenn Sie eine Survivable Branch Appliance definieren, muss der Name, den Sie in <STRONG>FQDN</STRONG> eingeben, mit dem Survivable Branch Appliance FQDN identisch sein, den Sie dem <STRONG>servicePrincipalName</STRONG> -Attribut zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="b8e36-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="b8e36-112">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b8e36-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="b8e36-113">Klicken Sie auf **Front-End-Pool**, klicken Sie auf den Front-End-Server (User Services Pool) am zentralen Standort, zu dem diese Survivable Branch Appliance oder Survivable Branch Server eine Verbindung herstellen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b8e36-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="b8e36-114">Klicken Sie auf **Edgeserver**, klicken Sie auf das Edgepool, mit dem diese Survivable Branch Appliance oder Survivable Branch Server eine Verbindung herstellen, um die PSTN-Konnektivität für Remotebenutzer des Zweigstellen Standorts bereitzustellen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="b8e36-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="b8e36-115">Klicken Sie auf **Gateway-FQDN oder IP-Adresse**, und geben Sie dann den FQDN oder die IP-Adresse des Gateway-Peers ein, dem der Survivable Branch Appliance oder der Survivable Branch Server für das Weiterleiten von eingehenden oder ausgehenden PSTN-anrufen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b8e36-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b8e36-116">Beim Definieren einer Survivable Branch Appliance ist dies das Gateway, mit dem sich der Vermittlungsserver in der Survivable Branch Appliance für PSTN-Verbindungen verbindet.</span><span class="sxs-lookup"><span data-stu-id="b8e36-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="b8e36-117">Klicken Sie auf **Überwachungsport für das IP/PSTN-Gateway**, und akzeptieren Sie den Standardport.</span><span class="sxs-lookup"><span data-stu-id="b8e36-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="b8e36-118">Klicken Sie im **SIP-Transport Protokoll**auf das Transportprotokoll, das von Survivable Branch Appliance oder Survivable Branch Server verwendet wird, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b8e36-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8e36-119">Aus Sicherheitsgründen wird der Einsatz von TLS (Transport Layer Security) ausdrücklich empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b8e36-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="b8e36-120">Konsultieren Sie beim Definieren einer Survivable Branch Appliance die Dokumentation des Herstellers, um sicherzustellen, dass die Survivable Branch Appliance das TLS-Protokoll unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b8e36-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="b8e36-121">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf die neue Survivable Branch Appliance oder den Survivable Branch Server, klicken Sie auf **Topologie** und anschließend auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="b8e36-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="b8e36-122">**Nächster Schritt**: [Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013-Branch-Standort Aufgabe](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="b8e36-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

