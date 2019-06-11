---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60aef8ea63d4feb0e874f72d37670c3b06860758
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="7aaf9-102">Konfigurieren von vertrauenswürdigen Anwendungsservern</span><span class="sxs-lookup"><span data-stu-id="7aaf9-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aaf9-103">_**Letztes Änderungsdatum des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="7aaf9-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="7aaf9-104">Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, nachdem Sie die Legacy Office Communications Server-Topologie mit lync Server 2013 zusammengeführt haben, und Sie einen neuen vertrauenswürdigen Anwendungsserver mithilfe des Topologie-Generators definieren, müssen Sie den Pool für den nächsten Hop so festlegen, dass er ein Lync Server 2013-Pool</span><span class="sxs-lookup"><span data-stu-id="7aaf9-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="7aaf9-105">In einer zusammengeführten Umgebung werden sowohl der Legacy-Office Communications Server-Pool als auch der lync Server 2013-Pool in der Dropdownliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7aaf9-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="7aaf9-106">Das Auswählen des Legacy Pools wird *nicht* unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7aaf9-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="7aaf9-107">So wählen Sie lync Server 2013 als nächster Hop aus, wenn Sie einen vertrauenswürdigen Anwendungs Server erstellen</span><span class="sxs-lookup"><span data-stu-id="7aaf9-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="7aaf9-108">Öffnen Sie im Topologie-Generator eine vorhandene Topologie.</span><span class="sxs-lookup"><span data-stu-id="7aaf9-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="7aaf9-109">Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver** , und klicken Sie auf **neuer vertrauenswürdiger Anwendungs Pool**.</span><span class="sxs-lookup"><span data-stu-id="7aaf9-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="7aaf9-110">Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, und wählen Sie aus, ob es sich um eine Bereitstellung mit einem oder mehreren Servern handelt.</span><span class="sxs-lookup"><span data-stu-id="7aaf9-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="7aaf9-111">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7aaf9-111">Click **Next**.</span></span>

5.  <span data-ttu-id="7aaf9-112">Wählen Sie auf der Seite **Nächster Hop auswählen** in der Liste den lync Server 2013-Front-End-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="7aaf9-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="7aaf9-113">![Dialogfeld "neuen vertrauenswürdigen Anwendungs Pool definieren"] (images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Dialogfeld \"neuen vertrauenswürdigen Anwendungs Pool definieren\"")</span><span class="sxs-lookup"><span data-stu-id="7aaf9-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="7aaf9-114">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="7aaf9-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="7aaf9-115">Wählen Sie den obersten Knoten **lync Server** aus, und wählen Sie im Bereich **Aktionen** die Option **veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="7aaf9-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="7aaf9-116">Überprüfen Sie, ob der **Vertrauenswürdige Anwendungspool** erfolgreich erstellt wurde und dem richtigen Front-End-Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7aaf9-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

