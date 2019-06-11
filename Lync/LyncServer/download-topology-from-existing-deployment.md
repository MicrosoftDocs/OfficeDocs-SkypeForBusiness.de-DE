---
title: Herunterladen der Topologie aus einer vorhandenen Bereitstellung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26c47e6d78d3bd9522b8f0369924f05f8f939037
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="d6f42-102">Herunterladen der Topologie aus einer vorhandenen Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="d6f42-102">Download topology from existing deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6f42-103">_**Letztes Änderungsdatum des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="d6f42-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="d6f42-104">Beim Erstellen eines lync Server 2013-Pools verwenden Sie den zentralen Verwaltungsspeicher, der lync Server 2010 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d6f42-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="d6f42-105">Wenn Sie den Topologie-Generator bei der ersten Verwendung und nachfolgenden Bearbeitungssitzungen starten, werden Sie aufgefordert, den Speicherort anzugeben, an dem der Topologie-Generator das aktuelle Konfigurationsdokument laden soll.</span><span class="sxs-lookup"><span data-stu-id="d6f42-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="d6f42-106">Da Sie bereits eine lync Server 2010-Topologie definiert haben und den zentralen Verwaltungsspeicher eingerichtet haben, sollten Sie eine Topologie aus einer vorhandenen Bereitstellung herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d6f42-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="d6f42-107">Der Topologie-Generator liest die Datenbank und ruft die aktuelle Definition ab.</span><span class="sxs-lookup"><span data-stu-id="d6f42-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="d6f42-108">**So laden Sie eine Topologie aus einer vorhandenen Bereitstellung herunter**</span><span class="sxs-lookup"><span data-stu-id="d6f42-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="d6f42-109">Öffnen Sie den **lync Server**-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="d6f42-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="d6f42-110">Klicken Sie auf der Seite **lync Server 2013 – Deployment-Assistent** auf **Verwaltungs Tools installieren**.</span><span class="sxs-lookup"><span data-stu-id="d6f42-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="d6f42-111">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013** , und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="d6f42-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="d6f42-112">Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**.</span><span class="sxs-lookup"><span data-stu-id="d6f42-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="d6f42-113">![Einstellungen des Bereitstellungs-Assistenten für Topologie-Generator] (images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Einstellungen des Bereitstellungs-Assistenten für Topologie-Generator")</span><span class="sxs-lookup"><span data-stu-id="d6f42-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="d6f42-114">Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie mit dem standardmäßigen tbxml-Dateityp.</span><span class="sxs-lookup"><span data-stu-id="d6f42-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="d6f42-115">Erweitern Sie den lync Server-Knoten, wie hier gezeigt, um die verschiedenen Server Rollen in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6f42-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="d6f42-116">![Allgemeine Eigenschaften des Topology Builder-Servers] (images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Allgemeine Eigenschaften des Topology Builder-Servers")</span><span class="sxs-lookup"><span data-stu-id="d6f42-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

