---
title: 'Lync Server 2013: Hosted Exchange um Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bace74b58c706ef58d05e54e31d2f79ab587ba64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="1c5e4-102">Gehostetes Exchange um Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c5e4-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c5e4-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1c5e4-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1c5e4-104">Die Exchange um Routing Anwendung wird im Front-End-Server für die Weiterleitung von Anrufen ausgeführt, entweder an eine lokale Exchange Server Unified Messaging (um)-Bereitstellung oder an einen gehosteten Exchange um Dienst.</span><span class="sxs-lookup"><span data-stu-id="1c5e4-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="1c5e4-105">Die ExUM-Routinganwendung</span><span class="sxs-lookup"><span data-stu-id="1c5e4-105">The ExUM Routing Application</span></span>

<span data-ttu-id="1c5e4-106">Die lync Server 2013 Exchange um Routing Anwendung verwendet Informationen aus Benutzerkontoeinstellungen und Richtlinienparametern für gehostete Voicemails, um zu bestimmen, wie Anrufe für gehostete Sprachnachrichten weitergeleitet werden, wie im folgenden Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1c5e4-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="1c5e4-107">**Beispiel für das Exchange UM-Routing in einer gemischten Bereitstellung**</span><span class="sxs-lookup"><span data-stu-id="1c5e4-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="1c5e4-108">![Lokale lync Server Exchange um-Bereitstellung](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Lokale lync Server Exchange um-Bereitstellung")</span><span class="sxs-lookup"><span data-stu-id="1c5e4-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="1c5e4-109">Exchange um Routing kann so konfiguriert werden, dass Anrufe an Benutzer weitergeleitet werden, die für lokale Exchange um aktiviert sind, für Benutzer, die für gehostete Exchange um aktiviert sind, oder für eine Kombination aus beiden.</span><span class="sxs-lookup"><span data-stu-id="1c5e4-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="1c5e4-110">Nehmen wir beispielsweise an, dass das Postfach und der Exchange um Dienst von Roy in einer lokalen Exchange-Bereitstellung verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1c5e4-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="1c5e4-111">Die Proxyadressinformationen aus dem Benutzerkonto von Roy bieten die Informationen, die die ExUM-Routing Anwendung zum Weiterleiten von Anrufen an einen lokalen Exchange um Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c5e4-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="1c5e4-112">Alices Postfach und Exchange um Dienst befinden sich im Rechenzentrum eines gehosteten Exchange-Dienstanbieters.</span><span class="sxs-lookup"><span data-stu-id="1c5e4-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="1c5e4-113">Das Routing für Ihre Exchange um Anrufe wird wie folgt konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="1c5e4-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="1c5e4-114">Die im Attribut "msExchUCVoiceMailSettings" des Benutzerkontos von Alice festgelegten Werte weisen die ExUM-Routinganwendung an, eine gehostete Voicemailrichtlinie auf Routingdetails zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1c5e4-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c5e4-115">Der Wert des "msexchucvoicemailsettings"-Attributs kann entweder vom Exchange-Dienstanbieter oder vom lync Server 2013 Administrator festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1c5e4-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="1c5e4-116">In dem im obigen Diagramm gezeigten Beispiel wurde der Wert (CsHostedVoiceMail = 1) vom lync Server 2013 Administrator festgelegt, um für Alice gehostete Voicemail zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c5e4-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="1c5e4-117">Ausführliche Informationen zu diesem Attribut finden Sie unter <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange User Management in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1c5e4-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="1c5e4-118">Die dem Benutzerkonto von Alice zugewiesene gehostete Voicemailrichtlinie umfasst Routingdetails:</span><span class="sxs-lookup"><span data-stu-id="1c5e4-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="1c5e4-119">Destination ist der gehostete Exchange um Dienstanbieter (LS). ExUm. \<hostedExchangeServer\>. com in diesem Beispiel).</span><span class="sxs-lookup"><span data-stu-id="1c5e4-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="1c5e4-120">Organisationen werden durch die Mandanten-IDs identifiziert, die die Routing-FQDNs für SIP-Nachrichten für Exchange Server Mandanten sind, die sich auf LS befinden. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com und Corp.litwareinc.com in diesem Beispiel).</span><span class="sxs-lookup"><span data-stu-id="1c5e4-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1c5e4-121">Der FQDN (Fully Qualified Domain Name, vollqualifizierter Domänenname) für Exchange Online lautet exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1c5e4-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="1c5e4-122">Ausführliche Informationen finden Sie unter [Hosted Voice Mail Policies in lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1c5e4-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c5e4-123">Wenn sowohl das Attribut "msExchUCVoiceMailSettings" als auch die UM-Proxyadresseinstellungen in einem Benutzerkonto vorhanden sind, hat das Attribut "msExchUCVoiceMailSettings" Vorrang.</span><span class="sxs-lookup"><span data-stu-id="1c5e4-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

