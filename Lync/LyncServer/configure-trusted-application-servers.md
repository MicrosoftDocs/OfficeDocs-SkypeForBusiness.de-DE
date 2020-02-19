---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535d5d9a34d450c964300e9caaa16c6b80734732
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="c7d4c-102">Konfigurieren von vertrauenswürdigen Anwendungsservern</span><span class="sxs-lookup"><span data-stu-id="c7d4c-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7d4c-103">_**Letztes Änderungsstand des Themas:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="c7d4c-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="c7d4c-104">Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den Pool für den nächsten Hop als lync Server 2013 Pool festlegen.</span><span class="sxs-lookup"><span data-stu-id="c7d4c-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="c7d4c-105">In einer gemischten Umgebung werden sowohl der Legacy lync Server 2010 Pool als auch der lync Server 2013-Pool in der Dropdownliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7d4c-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="c7d4c-106">Die Auswahl des Pools der Vorversion wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c7d4c-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="c7d4c-107">**Auswählen lync Server 2013 als nächster Hop beim Erstellen eines vertrauenswürdigen Anwendungsservers**</span><span class="sxs-lookup"><span data-stu-id="c7d4c-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="c7d4c-108">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="c7d4c-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="c7d4c-109">Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver**, und klicken Sie auf **Neuer Pool für vertrauenswürdige Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="c7d4c-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="c7d4c-110">Geben Sie den **Pool-FQDN** des Pools vertrauenswürdiger Anwendungen ein. Geben Sie an, ob der Pool einen einzelnen oder mehrere Server enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="c7d4c-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="c7d4c-111">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c7d4c-111">Click **Next**.</span></span>

5.  <span data-ttu-id="c7d4c-112">Wählen Sie auf der Seite **nächsten Hop auswählen** in der Liste die lync Server 2013 Front-End-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="c7d4c-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="c7d4c-113">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c7d4c-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="c7d4c-114">Wählen Sie den obersten Knoten **Lync Server** aus, und wählen Sie dann im Menü **Aktionen** die Option **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="c7d4c-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="c7d4c-115">Überprüfen Sie, dass der **vertrauenswürdige Anwendungspool** erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet worden ist.</span><span class="sxs-lookup"><span data-stu-id="c7d4c-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

