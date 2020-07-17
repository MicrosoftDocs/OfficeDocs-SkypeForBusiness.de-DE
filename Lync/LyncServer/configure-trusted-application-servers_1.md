---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cbaba4f59a22de6fcee38ee51845d551033cfea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="321a1-102">Konfigurieren von vertrauenswürdigen Anwendungsservern</span><span class="sxs-lookup"><span data-stu-id="321a1-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="321a1-103">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="321a1-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="321a1-104">Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, nachdem Sie die Legacy Office Communications Server-Topologie mit lync Server 2013 zusammengeführt haben und einen neuen vertrauenswürdigen Anwendungsserver mithilfe des Topologie-Generators definiert haben, müssen Sie den Pool für den nächsten Hop als lync Server 2013 Pool festlegen.</span><span class="sxs-lookup"><span data-stu-id="321a1-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="321a1-105">In einer zusammengeführten Umgebung werden sowohl der Legacy Office Communications Server Pool als auch der lync Server 2013-Pool in der Dropdownliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="321a1-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="321a1-106">Die Auswahl des Pools der Vorversion wird *nicht* unterstützt.</span><span class="sxs-lookup"><span data-stu-id="321a1-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="321a1-107">So wählen Sie beim Erstellen eines vertrauenswürdigen Anwendungsservers lync Server 2013 als nächsten Hop aus</span><span class="sxs-lookup"><span data-stu-id="321a1-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="321a1-108">Öffnen Sie eine bestehende Topologie im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="321a1-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="321a1-109">Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver**, und klicken Sie anschließend auf **Neuer Pool für vertrauenswürdige Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="321a1-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="321a1-110">Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, und legen Sie fest, ob es sich um eine Topologie mit einem einzelnen oder mehreren Servern handelt.</span><span class="sxs-lookup"><span data-stu-id="321a1-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="321a1-111">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="321a1-111">Click **Next**.</span></span>

5.  <span data-ttu-id="321a1-112">Wählen Sie auf der Seite **nächsten Hop auswählen** in der Liste die lync Server 2013 Front-End-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="321a1-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="321a1-113">![Dialogfeld "neuen vertrauenswürdigen Anwendungs Pool definieren"](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Dialogfeld "neuen vertrauenswürdigen Anwendungs Pool definieren"")</span><span class="sxs-lookup"><span data-stu-id="321a1-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="321a1-114">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="321a1-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="321a1-115">Wählen Sie den obersten Knoten **Lync Server** aus, und wählen Sie im Bereich **Aktionen** die Aktion **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="321a1-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="321a1-116">Vergewissern Sie sich, dass der **Pool für vertrauenswürdige Anwendungen** erfolgreich erstellt wurde und mit dem richtigen Front-End-Pool verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="321a1-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

