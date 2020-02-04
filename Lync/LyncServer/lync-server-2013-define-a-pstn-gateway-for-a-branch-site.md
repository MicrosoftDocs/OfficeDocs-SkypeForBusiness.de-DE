---
title: 'Lync Server 2013: Definieren eines PSTN-Gateways für eine Zweigstelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4445647e6ffcbfc2cfc137bd120d0aced6a9908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="d3633-102">Definieren eines PSTN-Gateways für eine Zweigstelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3633-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3633-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d3633-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d3633-104">Führen Sie dieses Verfahren an der zentralen Website aus, die mindestens einen Front-End-Pool oder Standard Edition-Server enthält.</span><span class="sxs-lookup"><span data-stu-id="d3633-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3633-105">Bevor Sie das Verfahren ausführen, müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="d3633-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="d3633-106">Die lync Server&nbsp;2013-Kommunikationssoftware muss am zentralen Standort eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="d3633-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="d3633-107">Der Vermittlungs Server muss am zentralen Standort bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d3633-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="d3633-108">So definieren Sie ein PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="d3633-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="d3633-109">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="d3633-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d3633-110">Erweitern Sie in der Konsolenstruktur den zentralen Standort, erweitern Sie **Zweigstellenstandorte**, erweitern Sie Name der Verzweigungs Website, für die Sie ein PSTN-Gateway (Public Switched Telephone Network) definieren möchten, und erweitern Sie dann **freigegebene Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="d3633-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="d3633-111">Klicken Sie mit der rechten Maustaste auf **PSTN-Gateways**, und klicken Sie dann auf **neues IP/PSTN-Gateway**.</span><span class="sxs-lookup"><span data-stu-id="d3633-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="d3633-112">Klicken Sie im Dialogfeld **neues IP/PSTN-Gateway definieren** auf **Gateway-FQDN oder IP-Adresse**, und geben Sie dann den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Gateways ein, das Sie auf der Zweigstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d3633-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="d3633-113">Klicken Sie auf **Überwachungs Port für IP/PSTN-Gateway**, und übernehmen Sie dann die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="d3633-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="d3633-114">Klicken Sie in der Liste **SIP-Transportprotokoll** auf das Transportprotokoll, das vom Gateway verwendet wird, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3633-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d3633-115">Aus Sicherheitsgründen empfehlen wir dringend, ein PSTN-Gateway zu verwenden, das TLS (Transport Layer Security) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d3633-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="d3633-116">Verwenden Sie das Cmdlet <STRONG>Satz-CsPstnGateway</STRONG> , um die Eigenschaften eines PSTN-Gateways zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d3633-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="d3633-117">Ausführliche Informationen finden Sie unter " <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Satz-CsPstnGateway</A>" in der Hilfe zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="d3633-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="d3633-118">**Nächster Schritt** für die Ausfallsicherheit von Zweigstellen: [Konfigurieren von Benutzern für die Stabilität des Zweigstellen Standorts in lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="d3633-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d3633-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3633-119">See Also</span></span>


[<span data-ttu-id="d3633-120">Bereitstellungsoptionen für PSTN-Gateways in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3633-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

