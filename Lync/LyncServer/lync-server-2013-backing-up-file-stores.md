---
title: 'Lync Server 2013: Sichern von Datei speichern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up file stores
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202167(v=OCS.15)
ms:contentKeyID: 51541449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4971b5df8646f20843569ba653cd7a0c274d501
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523162"
---
# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="49001-102">Sichern von Datei speichern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49001-102">Backing up file stores in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49001-103">_**Letztes Änderungsstand des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="49001-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="49001-104">Das Sichern der lync Server Dateispeicher umfasst alle Dateien und Ordner, die von lync Server Komponenten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="49001-104">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="49001-105">So sichern Sie Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="49001-105">To back up File Stores</span></span>

1.  <span data-ttu-id="49001-106">Um die spezifischen Speicherorte ihrer lync Server Dateispeicher zu finden, öffnen Sie den Topologie-Generator und schauen Sie sich den Knoten **Dateispeicher** an.</span><span class="sxs-lookup"><span data-stu-id="49001-106">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="49001-107">Verwenden Sie Robocopy oder ein anderes Dateisystem-Verwaltungstool, um jeden Dateispeicher in $Backup \\ Filestore zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="49001-107">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

