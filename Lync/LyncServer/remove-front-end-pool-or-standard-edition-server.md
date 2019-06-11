---
title: Entfernen eines Front-End-Pools oder Standard Edition-Servers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a3b08d6e8b4f0b792063b19a47889de11283c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a>Entfernen eines Front-End-Pools oder Standard Edition-Servers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Dieses Thema führt Sie durch den Vorgang zum Entfernen eines Front-End-Pools oder eines Front-End-Servers der Standard Edition. Wenn Sie einen Front-End-Pool entfernen, entfernen Sie jeden Front-End-Server, der zum Pool gehört, als Teil des Prozesses zum Entfernen des Pools. Wenn Sie einen Standard Edition-Front-End-Server entfernen, müssen Sie die SQL Store-Definition aus dem Topology Builder entfernen.

<div>

## <a name="to-remove-a-front-end-server-pool"></a>So entfernen Sie einen Front-End-Server Pool

1.  Öffnen Sie den Topologie-Generator.

2.  Navigieren Sie zum lync Server 2010-Knoten.

3.  Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie den Front-End-Pool, klicken Sie mit der rechten Maustaste auf den zu entfernenden Frontend-Pool, und klicken Sie dann auf **Löschen**.

4.  Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den lync Server-Bereitstellungs-Assistenten nach Bedarf aus.

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>So entfernen Sie einen Front-End-Server der Standard Edition

1.  Öffnen Sie den Topologie-Generator.

2.  Navigieren Sie zum lync Server 2010-Knoten.

3.  Erweitern Sie die **Standard Edition-Front-End-Server**, klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.

4.  Erweitern Sie **SQL Stores**, klicken Sie mit der rechten Maustaste auf die SQL Server-Datenbank, die dem Front-End-Server der Standard Edition zugeordnet ist, und klicken Sie dann auf **Löschen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen die Definition der SQL Server-Datenbanken vom Standard Edition-Front-End-Server entfernen.

    
    </div>

5.  Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den lync Server-Bereitstellungs-Assistenten nach Bedarf aus.

</div>

</div>

<span> </span>

</div>

</div>

</div>

