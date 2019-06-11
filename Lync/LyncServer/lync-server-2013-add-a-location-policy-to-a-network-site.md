---
title: 'Lync Server 2013: Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9ee6b5ba89cef592e137104df9e80d9373b5f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="b168a-102">Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b168a-102">Add a location policy to a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b168a-103">_**Letztes Änderungsdatum des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="b168a-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="b168a-104">In den folgenden Beispielen wird gezeigt, wie Sie die in Erstellen von [Standortrichtlinien in lync Server 2013](lync-server-2013-create-location-policies.md) definierte Standortrichtlinie für **Redmond** zu einer vorhandenen Netzwerk Website hinzufügen und wie Sie eine neue Netzwerk Website erstellen, die die Standortrichtlinie für **Redmond** verwendet.</span><span class="sxs-lookup"><span data-stu-id="b168a-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="b168a-105">Details zum Arbeiten mit Netzwerk Websites finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b168a-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="b168a-106">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="b168a-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="b168a-107">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="b168a-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="b168a-108">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="b168a-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="b168a-109">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="b168a-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="b168a-110">So weisen Sie eine Ortungsrichtlinie einem vorhandenen Netzwerkstandort zu</span><span class="sxs-lookup"><span data-stu-id="b168a-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="b168a-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b168a-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b168a-112">Führen Sie die folgenden Cmdlets aus, um einen vorhandenen Netzwerkstandort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b168a-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="b168a-113">Weisen Sie die Ortungsrichtlinie mit dem Tag **Redmond** einem vorhandenen Netzwerkstandort namens **Redmond** zu.</span><span class="sxs-lookup"><span data-stu-id="b168a-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="b168a-114">So weisen Sie eine Ortungsrichtlinie einem neuen Netzwerkstandort zu</span><span class="sxs-lookup"><span data-stu-id="b168a-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="b168a-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b168a-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b168a-116">Führen Sie das folgende Cmdlet aus, um einen neuen Netzwerkstandort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b168a-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="b168a-117">Erstellen Sie einen neuen Netzwerkstandort in der Netzwerkregion und weisen Sie diesem Standort die Ortungsrichtlinie mit dem Tag **Redmond** zu.</span><span class="sxs-lookup"><span data-stu-id="b168a-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

