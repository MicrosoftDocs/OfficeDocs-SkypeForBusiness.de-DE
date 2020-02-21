---
title: Herunterladen der Topologie aus einer vorhandenen Bereitstellung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a8742cf3b9eee5ab8badb18e1f6a6ae80418141
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="0aee7-102">Herunterladen der Topologie aus einer vorhandenen Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="0aee7-102">Download topology from existing deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0aee7-103">_**Letztes Änderungsstand des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="0aee7-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="0aee7-104">Beim Erstellen eines lync Server 2013 Pools verwenden Sie die zentraler Verwaltungsspeicher, die lync Server 2010 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0aee7-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="0aee7-105">Beim erstmaligen Starten des Topologie-Generators und in nachfolgenden Bearbeitungssitzungen werden Sie zur Angabe des Speicherorts aufgefordert, an dem der Topologie-Generator das aktuelle Konfigurationsdokument laden soll.</span><span class="sxs-lookup"><span data-stu-id="0aee7-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="0aee7-106">Da Sie bereits eine lync Server 2010 Topologie definiert haben und den zentralen Verwaltungsspeicher eingerichtet haben, sollten Sie eine Topologie aus einer vorhandenen Bereitstellung herunterladen.</span><span class="sxs-lookup"><span data-stu-id="0aee7-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="0aee7-107">Der Topologie-Generator liest die Informationen aus der Datenbank und ruft die aktuelle Definition ab.</span><span class="sxs-lookup"><span data-stu-id="0aee7-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="0aee7-108">**So laden Sie eine Topologie aus einer vorhandenen Bereitstellung herunter**</span><span class="sxs-lookup"><span data-stu-id="0aee7-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="0aee7-109">Öffnen Sie den\*\*\*\* Lync Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="0aee7-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="0aee7-110">Klicken Sie auf der Seite **Lync Server 2013 – Bereitstellungs-Assistent** auf **Verwaltungstools installieren**.</span><span class="sxs-lookup"><span data-stu-id="0aee7-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="0aee7-111">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013** , und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="0aee7-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="0aee7-112">Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="0aee7-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="0aee7-113">![Einstellungen für den Bereitstellungs-Assistenten für Topologie-Generator](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Einstellungen für den Bereitstellungs-Assistenten für Topologie-Generator")</span><span class="sxs-lookup"><span data-stu-id="0aee7-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="0aee7-114">Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie als standardmäßigen TBXML-Dateityp.</span><span class="sxs-lookup"><span data-stu-id="0aee7-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="0aee7-115">Erweitern Sie den Lync Server-Knoten (siehe Abbildung), um die verschiedenen Serverrollen in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0aee7-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="0aee7-116">![Topologie-Generator-Serverrolle: Allgemeine Eigenschaften](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topologie-Generator-Serverrolle: Allgemeine Eigenschaften")</span><span class="sxs-lookup"><span data-stu-id="0aee7-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

