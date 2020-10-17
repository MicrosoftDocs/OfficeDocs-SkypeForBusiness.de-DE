---
title: 'Lync Server 2013: Wiederherstellen eines Dateispeichers'
description: 'Lync Server 2013: Wiederherstellen eines Dateispeichers.'
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
ms.openlocfilehash: 201c4b20f224fa3a25e931689e564410c60143e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543831"
---
# <a name="restoring-a-file-store-in-lync-server-2013"></a>Wiederherstellen eines Dateispeichers in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-18_

Dateispeicher für Standard Edition befinden sich normalerweise im Standard Edition-Server. Dateispeicher für Enterprise Edition befinden sich normalerweise auf einem Dateiserver oder Cluster. Im folgenden Verfahren wird beschrieben, wie Sie eine Dateispeicher wiederherstellen.

<div>

## <a name="to-restore-a-file-store"></a>So stellen Sie eine Dateispeicher wieder her

1.  Wenn ein Dateispeicher fehlschlägt, kopieren Sie den entsprechenden Dateispeicher aus $Backup \\ an den Dateispeicher Speicherort auf dem Dateiserver oder Standard Edition-Server, und geben Sie dann den Ordner frei.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Pfad und der Dateiname für das wiederhergestellte Dateispeicher sollten genau mit dem gesicherten Dateispeicher identisch sein, damit Komponenten, die die Dateien verwenden, darauf zugreifen können.

    
    </div>

2.  Legen Sie bei Bedarf die Zugriffssteuerungslisten (Access Control Lists, ACLs) für die Dateispeicher fest. Geben Sie in die Befehlszeile Folgendes ein:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Sie müssen diesen Schritt nur ausführen, wenn Sie den Topologie-Generator während des Wiederherstellungsvorgangs nicht anderweitig ausgeführt haben.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

