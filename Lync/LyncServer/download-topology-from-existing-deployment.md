---
title: Herunterladen der Topologie aus einer vorhandenen Bereitstellung
description: Laden Sie die Topologie aus einer vorhandenen Bereitstellung herunter.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22d746f8faf3fdf14a44e751eeb3c88bf3eef4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551181"
---
# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="3b674-103">Herunterladen der Topologie aus einer vorhandenen Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="3b674-103">Download topology from existing deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b674-104">_**Letztes Änderungsstand des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="3b674-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="3b674-105">Beim Erstellen eines lync Server 2013 Pools verwenden Sie die zentraler Verwaltungsspeicher, die lync Server 2010 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3b674-105">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="3b674-106">Beim erstmaligen Starten des Topologie-Generators und in nachfolgenden Bearbeitungssitzungen werden Sie zur Angabe des Speicherorts aufgefordert, an dem der Topologie-Generator das aktuelle Konfigurationsdokument laden soll.</span><span class="sxs-lookup"><span data-stu-id="3b674-106">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="3b674-107">Da Sie bereits eine lync Server 2010 Topologie definiert haben und den zentralen Verwaltungsspeicher eingerichtet haben, sollten Sie eine Topologie aus einer vorhandenen Bereitstellung herunterladen.</span><span class="sxs-lookup"><span data-stu-id="3b674-107">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="3b674-108">Der Topologie-Generator liest die Informationen aus der Datenbank und ruft die aktuelle Definition ab.</span><span class="sxs-lookup"><span data-stu-id="3b674-108">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="3b674-109">**So laden Sie eine Topologie aus einer vorhandenen Bereitstellung herunter**</span><span class="sxs-lookup"><span data-stu-id="3b674-109">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="3b674-110">Öffnen Sie den\*\*\*\* Lync Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="3b674-110">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="3b674-111">Klicken Sie auf der Seite **Lync Server 2013 – Bereitstellungs-Assistent** auf **Verwaltungstools installieren**.</span><span class="sxs-lookup"><span data-stu-id="3b674-111">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="3b674-112">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013** , und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="3b674-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="3b674-113">Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="3b674-113">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="3b674-114">![Einstellungen für den Bereitstellungs-Assistenten für Topologie-Generator](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Einstellungen für den Bereitstellungs-Assistenten für Topologie-Generator")</span><span class="sxs-lookup"><span data-stu-id="3b674-114">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="3b674-115">Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie als standardmäßigen TBXML-Dateityp.</span><span class="sxs-lookup"><span data-stu-id="3b674-115">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="3b674-116">Erweitern Sie den Lync Server-Knoten (siehe Abbildung), um die verschiedenen Serverrollen in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3b674-116">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="3b674-117">![Topologie-Generator-Serverrolle: Allgemeine Eigenschaften](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topologie-Generator-Serverrolle: Allgemeine Eigenschaften")</span><span class="sxs-lookup"><span data-stu-id="3b674-117">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

