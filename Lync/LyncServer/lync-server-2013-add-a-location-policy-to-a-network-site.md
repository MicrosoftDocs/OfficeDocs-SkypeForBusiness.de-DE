---
title: 'Lync Server 2013: Hinzufügen einer ortungsrichtlinie zu einem Netzwerkstandort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a817a1a94b6e02167d488212dd532537cec0146
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="404f0-102">Hinzufügen einer ortungsrichtlinie zu einem Netzwerkstandort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="404f0-102">Add a location policy to a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="404f0-103">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="404f0-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="404f0-104">Die folgenden Beispiele zeigen, wie Sie die in [Create Location Policies in lync Server 2013](lync-server-2013-create-location-policies.md) definierte **Redmond** -ortungsrichtlinie einem vorhandenen Netzwerkstandort hinzufügen und wie Sie einen neuen Netzwerkstandort erstellen, der die Standortrichtlinie von **Redmond** verwendet.</span><span class="sxs-lookup"><span data-stu-id="404f0-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="404f0-105">Ausführliche Informationen zum Arbeiten mit Netzwerkstandorten finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="404f0-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="404f0-106">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="404f0-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="404f0-107">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="404f0-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="404f0-108">**Gruppe-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="404f0-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="404f0-109">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="404f0-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="404f0-110">So weisen Sie eine Ortungsrichtlinie einem vorhandenen Netzwerkstandort zu</span><span class="sxs-lookup"><span data-stu-id="404f0-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="404f0-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="404f0-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="404f0-112">Führen Sie die folgenden Cmdlets aus, um einen vorhandenen Netzwerkstandort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="404f0-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="404f0-113">Weisen Sie die Standortrichtlinie " **Redmond** Tagged Location" einem vorhandenen Netzwerkstandort namens " **Redmond**" zu.</span><span class="sxs-lookup"><span data-stu-id="404f0-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="404f0-114">So weisen Sie eine Ortungsrichtlinie einem neuen Netzwerkstandort zu</span><span class="sxs-lookup"><span data-stu-id="404f0-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="404f0-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="404f0-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="404f0-116">Führen Sie das folgende Cmdlet aus, um einen neuen Netzwerkstandort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="404f0-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="404f0-117">Erstellen Sie einen neuen Netzwerkstandort in der Netzwerkregion, und weisen Sie diesem Standort die Ortungsrichtlinie mit dem Tag **Redmond** zu.</span><span class="sxs-lookup"><span data-stu-id="404f0-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

