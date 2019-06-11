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

# <a name="restoring-a-file-store-in-lync-server-2013"></a>Wiederherstellen eines Dateispeichers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-18_

Dateispeicher für die Standard Edition befinden sich normalerweise auf dem Standard Edition-Server. Dateispeicher für Enterprise Edition befinden sich in der Regel auf einem Dateiserver oder Cluster. Im folgenden Verfahren wird beschrieben, wie Sie einen Dateispeicher wiederherstellen.

<div>

## <a name="to-restore-a-file-store"></a>So stellen Sie einen Dateispeicher wieder her

1.  Wenn ein Dateispeicher fehlschlägt, kopieren Sie den entsprechenden Dateispeicher\\ aus $Backup in den Dateispeicher Speicherort auf dem Dateiserver oder Standard Edition-Server, und geben Sie dann den Ordner frei.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Pfad und Dateinamen für den wiederhergestellten Dateispeicher sollten exakt mit dem gesicherten Dateispeicher identisch sein, damit die Komponenten, die die Dateien verwenden, darauf zugreifen können.

    
    </div>

2.  Legen Sie bei Bedarf die Zugriffssteuerungslisten (ACLs) für den Dateispeicher ab. Geben Sie in der Befehlszeile Folgendes ein:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Sie müssen diesen Schritt nur ausführen, wenn Sie den Topology Builder während des Wiederherstellungsprozesses nicht anderweitig ausgeführt haben.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

