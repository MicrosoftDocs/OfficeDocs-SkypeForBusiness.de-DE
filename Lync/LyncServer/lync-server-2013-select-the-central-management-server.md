---
title: 'Lync Server 2013: Auswählen des zentralen Verwaltungsservers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Select the Central Management Server
ms:assetid: 1ca6b7d0-125c-4727-aac4-2d683d23394d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204726(v=OCS.15)
ms:contentKeyID: 48183561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef3cff58600697f64b64860f37a7daab8ebfc8f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510422"
---
# <a name="select-the-central-management-server-in-lync-server-2013"></a><span data-ttu-id="3e2fd-102">Wählen Sie den zentralen Verwaltungs Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e2fd-102">Select the Central Management Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e2fd-103">_**Letztes Änderungsstand des Themas:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="3e2fd-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="3e2fd-104">Bevor Sie die Topologie definieren und konfigurieren können, müssen Sie zunächst den Speicherort für die Installation des zentralen Verwaltungsservers definieren.</span><span class="sxs-lookup"><span data-stu-id="3e2fd-104">Before you can define and configure your topology, you must first define the location to install the Central Management Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e2fd-105">Dies wird erst wirksam, wenn Sie eine Topologie im Topologie-Generator veröffentlicht haben.</span><span class="sxs-lookup"><span data-stu-id="3e2fd-105">This will not take effect until you have published a topology in Topology Builder.</span></span> <span data-ttu-id="3e2fd-106">Um den zentralen Verwaltungs Server vor dem Erstellen und Veröffentlichen der Topologie festzulegen, führen Sie " <STRONG>CSConfigurationStoreLocation</STRONG>" aus.</span><span class="sxs-lookup"><span data-stu-id="3e2fd-106">To set the Central Management Server before the topology is created and published, run <STRONG>Set-CSConfigurationStoreLocation</STRONG>.</span></span>



</div>

<div>

## <a name="to-select-the-central-management-server"></a><span data-ttu-id="3e2fd-107">So wählen Sie den zentralen Verwaltungsserver aus</span><span class="sxs-lookup"><span data-stu-id="3e2fd-107">To select the Central Management Server</span></span>

1.  <span data-ttu-id="3e2fd-108">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="3e2fd-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="3e2fd-109">Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3e2fd-109">Right-click the Lync Server 2013 node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="3e2fd-110">Wählen Sie im Bereich zentraler Verwaltungsserver den Front-End-Server aus, auf dem der zentrale Verwaltungsserver installiert werden soll, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e2fd-110">In the Central Management Server pane, select the Front End Server to install the Central Management Server on and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

