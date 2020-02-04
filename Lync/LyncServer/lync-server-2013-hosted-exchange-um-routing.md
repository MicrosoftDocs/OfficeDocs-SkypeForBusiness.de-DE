---
title: 'Lync Server 2013: Routing für gehostete Exchange UM-Dienste'
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
ms.openlocfilehash: e04198813f7bb0647671dbb23e12889b108ee846
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="e2413-102">Routing für gehostete Exchange UM-Dienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2413-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2413-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e2413-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e2413-104">Die Exchange um-Routing Anwendung wird auf dem Front-End-Server ausgeführt, um Anrufe an eine lokale Microsoft Exchange Server Unified Messaging (um)-Bereitstellung oder an einen gehosteten Exchange um-Dienst weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e2413-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="e2413-105">Die ExUM-Routing Anwendung</span><span class="sxs-lookup"><span data-stu-id="e2413-105">The ExUM Routing Application</span></span>

<span data-ttu-id="e2413-106">Die lync Server 2013 Exchange um-Routing Anwendung verwendet Informationen aus den Einstellungen des Benutzerkontos und den Richtlinienparametern für gehostete Voicemail, um zu bestimmen, wie Anrufe für gehostete Voicemail weitergeleitet werden, wie im folgenden Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e2413-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="e2413-107">**Beispiel für eine gemischte Bereitstellung Exchange um-Routing**</span><span class="sxs-lookup"><span data-stu-id="e2413-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="e2413-108">![Lokale lync Server Exchange um-Bereitstellung](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Lokale lync Server Exchange um-Bereitstellung")</span><span class="sxs-lookup"><span data-stu-id="e2413-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="e2413-109">Das Exchange um-Routing kann so konfiguriert werden, dass Anrufe an Benutzer weitergeleitet werden, die für lokalen Exchange um aktiviert sind, für Benutzer, die für gehostete Exchange um aktiviert sind, oder für eine Kombination der beiden.</span><span class="sxs-lookup"><span data-stu-id="e2413-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="e2413-110">Nehmen wir beispielsweise an, dass das Postfach und der Exchange um-Dienst von Roy in einer lokalen Exchange-Bereitstellung verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="e2413-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="e2413-111">Die Proxyadressinformationen des Benutzerkontos von Roy stellen die Informationen bereit, die von der ExUM-Routing Anwendung zum Weiterleiten von Anrufen an einen lokalen Exchange um-Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2413-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="e2413-112">Alices Postfach und Exchange um-Dienst befinden sich im Rechenzentrum eines gehosteten Exchange-Dienstanbieters.</span><span class="sxs-lookup"><span data-stu-id="e2413-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="e2413-113">Das Routing für Ihre Exchange um-Anrufe ist wie folgt konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="e2413-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="e2413-114">Die Werte, die im msExchUCVoiceMailSettings-Attribut des Benutzerkontos von Alice festgesetzt sind, weisen die ExUM-Routing Anwendung an, auf Routing Details in einer gehosteten Voicemail-Richtlinie zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e2413-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e2413-115">Der Wert des Attributs msExchUCVoiceMailSettings kann entweder vom Exchange-Dienstanbieter oder vom lync Server 2013-Administrator eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e2413-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="e2413-116">In dem im vorherigen Diagramm gezeigten Beispiel wurde der Wert (CsHostedVoiceMail = 1) vom lync Server 2013-Administrator so eingerichtet, dass die gehostete Voicemail für Alice aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="e2413-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="e2413-117">Details zu diesem Attribut finden Sie unter <A href="lync-server-2013-hosted-exchange-user-management.md">gehostete Exchange-Benutzerverwaltung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e2413-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="e2413-118">Die Hosted Voicemail-Richtlinie, die dem Benutzerkonto von Alice zugewiesen ist, bietet Routing Details:</span><span class="sxs-lookup"><span data-stu-id="e2413-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="e2413-119">Ziel ist der gehostete Exchange um-Dienstanbieter (LS). ExUm. \<hostedExchangeServer\>. com in diesem Beispiel).</span><span class="sxs-lookup"><span data-stu-id="e2413-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="e2413-120">Organisationen werden durch die Mandanten-IDs identifiziert, bei denen es sich um die Routing-FQDNs für SIP-Nachrichten für Exchange Server-Mandanten handelt, die sich auf LS befinden. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com und Corp.litwareinc.com in diesem Beispiel).</span><span class="sxs-lookup"><span data-stu-id="e2413-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e2413-121">Der FQDN für Exchange Online lautet exap.um.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e2413-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="e2413-122">Ausführliche Informationen finden Sie unter [Richtlinien für gehostete Voicemail in lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e2413-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2413-123">Wenn in einem Benutzerkonto sowohl das msExchUCVoiceMailSettings-Attribut als auch die um-Proxy Adresseinstellungen vorhanden sind, hat das msExchUCVoiceMailSettings-Attribut Vorrang.</span><span class="sxs-lookup"><span data-stu-id="e2413-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

