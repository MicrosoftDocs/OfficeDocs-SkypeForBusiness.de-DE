---
title: 'Lync Server 2013: Hinzufügen einer ortungsrichtlinie zu einem Netzwerkstandort'
description: 'Lync Server 2013: Fügen Sie eine ortungsrichtlinie zu einem Netzwerkstandort hinzu.'
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
ms.openlocfilehash: 20f71d3144e2ef730de5dae46be16138b5d36c42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567921"
---
# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="5f7bc-103">Hinzufügen einer ortungsrichtlinie zu einem Netzwerkstandort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f7bc-103">Add a location policy to a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f7bc-104">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="5f7bc-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="5f7bc-105">Die folgenden Beispiele zeigen, wie Sie die in [Create Location Policies in lync Server 2013](lync-server-2013-create-location-policies.md) definierte **Redmond** -ortungsrichtlinie einem vorhandenen Netzwerkstandort hinzufügen und wie Sie einen neuen Netzwerkstandort erstellen, der die Standortrichtlinie von **Redmond** verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f7bc-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="5f7bc-106">Ausführliche Informationen zum Arbeiten mit Netzwerkstandorten finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="5f7bc-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="5f7bc-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="5f7bc-107">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="5f7bc-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="5f7bc-108">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="5f7bc-109">**Gruppe-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="5f7bc-109">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="5f7bc-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="5f7bc-110">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="5f7bc-111">So weisen Sie eine Ortungsrichtlinie einem vorhandenen Netzwerkstandort zu</span><span class="sxs-lookup"><span data-stu-id="5f7bc-111">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="5f7bc-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="5f7bc-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5f7bc-113">Führen Sie die folgenden Cmdlets aus, um einen vorhandenen Netzwerkstandort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5f7bc-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="5f7bc-114">Weisen Sie die Standortrichtlinie " **Redmond** Tagged Location" einem vorhandenen Netzwerkstandort namens " **Redmond**" zu.</span><span class="sxs-lookup"><span data-stu-id="5f7bc-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="5f7bc-115">So weisen Sie eine Ortungsrichtlinie einem neuen Netzwerkstandort zu</span><span class="sxs-lookup"><span data-stu-id="5f7bc-115">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="5f7bc-116">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="5f7bc-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5f7bc-117">Führen Sie das folgende Cmdlet aus, um einen neuen Netzwerkstandort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5f7bc-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="5f7bc-118">Erstellen Sie einen neuen Netzwerkstandort in der Netzwerkregion, und weisen Sie diesem Standort die Ortungsrichtlinie mit dem Tag **Redmond** zu.</span><span class="sxs-lookup"><span data-stu-id="5f7bc-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

