---
title: 'Lync Server 2013: Wiederherstellen eines Dateispeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73ba97ccadcc5cb34a5dbc3963d80620da8e516
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="a883b-102">Wiederherstellen eines Dateispeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a883b-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a883b-103">_**Letztes Änderungsstand des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="a883b-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="a883b-104">Dateispeicher für Standard Edition befinden sich normalerweise im Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="a883b-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="a883b-105">Dateispeicher für Enterprise Edition befinden sich normalerweise auf einem Dateiserver oder Cluster.</span><span class="sxs-lookup"><span data-stu-id="a883b-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="a883b-106">Im folgenden Verfahren wird beschrieben, wie Sie eine Dateispeicher wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="a883b-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="a883b-107">So stellen Sie eine Dateispeicher wieder her</span><span class="sxs-lookup"><span data-stu-id="a883b-107">To restore a File Store</span></span>

1.  <span data-ttu-id="a883b-108">Wenn ein Dateispeicher fehlschlägt, kopieren Sie den entsprechenden Dateispeicher\\ aus $Backup an den Dateispeicher Speicherort auf dem Dateiserver oder Standard Edition-Server, und geben Sie dann den Ordner frei.</span><span class="sxs-lookup"><span data-stu-id="a883b-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a883b-109">Der Pfad und der Dateiname für das wiederhergestellte Dateispeicher sollten genau mit dem gesicherten Dateispeicher identisch sein, damit Komponenten, die die Dateien verwenden, darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="a883b-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="a883b-110">Legen Sie bei Bedarf die Zugriffssteuerungslisten (Access Control Lists, ACLs) für die Dateispeicher fest.</span><span class="sxs-lookup"><span data-stu-id="a883b-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="a883b-111">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a883b-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a883b-112">Sie müssen diesen Schritt nur ausführen, wenn Sie den Topologie-Generator während des Wiederherstellungsvorgangs nicht anderweitig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="a883b-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

