---
title: 'Lync Server 2013: Erstellen von Netzwerk-standortübergreifenden Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 655cde30a3d798d57520c57e3882b2162010888c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="b6214-102">Erstellen von Netzwerk-standortübergreifenden Richtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6214-102">Create network intersite policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6214-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b6214-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b6214-104">Eine *Netzwerk-standortübergreifende Richtlinie* definiert Bandbreiteneinschränkungen zwischen Websites, die direkte WAN-Verbindungen zwischen Ihnen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b6214-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="b6214-105">Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b6214-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="b6214-106">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b6214-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="b6214-107">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b6214-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="b6214-108">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b6214-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="b6214-109">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b6214-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b6214-110">Eine Netzwerk-standortübergreifende Richtlinie ist <EM>nur</EM> erforderlich, wenn zwischen zwei Netzwerkstandorten eine direkte Querverbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="b6214-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="b6214-111">In der Region „Nordamerika“ der Beispieltopologie besteht eine direkte Verbindung zwischen den Standorten „Reno“ und „Albuquerque“.</span><span class="sxs-lookup"><span data-stu-id="b6214-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="b6214-112">Diese beiden Websites erfordern eine standortübergreifende Richtlinie, die ein entsprechendes bandbreitenrichtlinienprofil anwendet.</span><span class="sxs-lookup"><span data-stu-id="b6214-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="b6214-113">Im folgenden Beispiel wird das 20MB\_-Link Profil angewendet.</span><span class="sxs-lookup"><span data-stu-id="b6214-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="b6214-114">So erstellen Sie eine netzwerkübergreifende Richtlinie</span><span class="sxs-lookup"><span data-stu-id="b6214-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="b6214-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b6214-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b6214-116">Führen Sie das Cmdlet New-CsNetworkInterSitePolicy aus, um netzwerkübergreifende Richtlinien zu erstellen und ein entsprechendes bandbreitenrichtlinienprofil für zwei Websites anzuwenden, die einen direkten Querverweis aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b6214-116">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="b6214-117">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b6214-117">For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="b6214-118">Wiederholen Sie Schritt 2 nach Bedarf, um netzwerkübergreifende Richtlinien für alle Netzwerk Website Paare zu erstellen, die eine direkte Kreuzverknüpfung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b6214-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

