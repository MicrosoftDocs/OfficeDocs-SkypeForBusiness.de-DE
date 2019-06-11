---
title: 'Lync Server 2013: Wiederherstellen eines Dateispeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc9f1bae4e1a9a84815e576267a15155bec227da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="d80b0-102">Wiederherstellen eines Dateispeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d80b0-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d80b0-103">_**Letztes Änderungsdatum des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="d80b0-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="d80b0-104">Dateispeicher für die Standard Edition befinden sich normalerweise auf dem Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="d80b0-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="d80b0-105">Dateispeicher für Enterprise Edition befinden sich in der Regel auf einem Dateiserver oder Cluster.</span><span class="sxs-lookup"><span data-stu-id="d80b0-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="d80b0-106">Im folgenden Verfahren wird beschrieben, wie Sie einen Dateispeicher wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="d80b0-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="d80b0-107">So stellen Sie einen Dateispeicher wieder her</span><span class="sxs-lookup"><span data-stu-id="d80b0-107">To restore a File Store</span></span>

1.  <span data-ttu-id="d80b0-108">Wenn ein Dateispeicher fehlschlägt, kopieren Sie den entsprechenden Dateispeicher\\ aus $Backup in den Dateispeicher Speicherort auf dem Dateiserver oder Standard Edition-Server, und geben Sie dann den Ordner frei.</span><span class="sxs-lookup"><span data-stu-id="d80b0-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d80b0-109">Der Pfad und Dateinamen für den wiederhergestellten Dateispeicher sollten exakt mit dem gesicherten Dateispeicher identisch sein, damit die Komponenten, die die Dateien verwenden, darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="d80b0-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="d80b0-110">Legen Sie bei Bedarf die Zugriffssteuerungslisten (ACLs) für den Dateispeicher ab.</span><span class="sxs-lookup"><span data-stu-id="d80b0-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="d80b0-111">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d80b0-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d80b0-112">Sie müssen diesen Schritt nur ausführen, wenn Sie den Topology Builder während des Wiederherstellungsprozesses nicht anderweitig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="d80b0-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

