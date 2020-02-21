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
ms.openlocfilehash: cceaffb2ecf0ac1b133e01bd04f50f9950cc0dec
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="d12d1-102">Sichern von Datei speichern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d12d1-102">Backing up file stores in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d12d1-103">_**Letztes Änderungsstand des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="d12d1-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="d12d1-104">Das Sichern der lync Server Dateispeicher umfasst alle Dateien und Ordner, die von lync Server Komponenten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d12d1-104">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="d12d1-105">So sichern Sie Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="d12d1-105">To back up File Stores</span></span>

1.  <span data-ttu-id="d12d1-106">Um die spezifischen Speicherorte ihrer lync Server Dateispeicher zu finden, öffnen Sie den Topologie-Generator und schauen Sie sich den Knoten **Dateispeicher** an.</span><span class="sxs-lookup"><span data-stu-id="d12d1-106">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="d12d1-107">Verwenden Sie Robocopy oder ein anderes Dateisystem-Verwaltungstool, um jeden\\Dateispeicher in $Backup Filestore zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="d12d1-107">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

