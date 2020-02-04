---
title: 'Lync Server 2013: Anzeigen von Informationen zu einzelnen SIP-Stämmen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18b65d119b917d5ba48ef3e6805e4f70ea482ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="8bf64-102">Anzeigen von Informationen zu einzelnen SIP-Stämmen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bf64-102">View information about individual SIP trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bf64-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8bf64-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8bf64-104">SIP-Trunks werden verwendet, um das Voice-over-IP-Telefon Netzwerk von lync Server 2013 mit dem öffentlich geschalteten Telefon Netzwerk zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="8bf64-104">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="8bf64-105">In der vorherigen Produktversion wurden Trunks zum Weiterleiten ausgehender Anrufe von einem Vermittlungsserver an ein PSTN-Gateway verwendet und die einzelnen Gateways waren auf einen einzelnen Trunk beschränkt.</span><span class="sxs-lookup"><span data-stu-id="8bf64-105">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="8bf64-106">Demzufolge waren PSTN-Gateways und SIP-Trunks im Wesentlichen identisch.</span><span class="sxs-lookup"><span data-stu-id="8bf64-106">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="8bf64-107">Für Administratoren bedeutete dies, dass sie sich Informationen zu einem einzelnen SIP-Trunk anzeigen lassen konnten, indem sie einfach die Informationen zu dem zugeordneten PSTN-Gateway aufriefen.</span><span class="sxs-lookup"><span data-stu-id="8bf64-107">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="8bf64-108">In lync Server 2013 können nun jedoch mehrere Trunks einem einzigen PSTN-Gateway zugewiesen werden. Das bedeutet, dass Gateways und Trunks nicht mehr identisch sind.</span><span class="sxs-lookup"><span data-stu-id="8bf64-108">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="8bf64-109">Das bedeutet wiederum, dass Administratoren das neue Cmdlet " [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) " verwenden müssen, um Informationen zu einem einzelnen SIP-Trunk anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8bf64-109">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="8bf64-110">Das Cmdlet "Get-CsTrunk" kann entweder über die lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8bf64-110">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8bf64-111">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="8bf64-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="8bf64-112">Anzeigen von Informationen für alle SIP-Trunks</span><span class="sxs-lookup"><span data-stu-id="8bf64-112">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="8bf64-113">Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:</span><span class="sxs-lookup"><span data-stu-id="8bf64-113">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="8bf64-114">Anzeigen von Informationen für einen bestimmten SIP-Trunk</span><span class="sxs-lookup"><span data-stu-id="8bf64-114">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="8bf64-115">Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert „PstnGateway:192.168.0.240“ Informationen zurück:</span><span class="sxs-lookup"><span data-stu-id="8bf64-115">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="8bf64-116">Anzeigen von Informationen zu allen SIP-Stämmen, die einem Pool zugewiesen sind</span><span class="sxs-lookup"><span data-stu-id="8bf64-116">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="8bf64-117">In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool „atl-cs-001.litwareinc.com“ zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="8bf64-117">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

