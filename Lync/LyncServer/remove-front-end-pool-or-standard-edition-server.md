---
title: Entfernen von Front-End-Pool oder Standard Edition-Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92b6f0dc28c44d3a77bd5af2ff67a61e2f23973f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a>Entfernen von Front-End-Pool oder Standard Edition-Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-04_

In diesem Thema werden Sie durch den Vorgang zum Entfernen einer Front-End-Pool oder einer Standard Edition Front-End-Server geführt. Wenn Sie ein Front-End-Pool entfernen, entfernen Sie alle Front-End-Server, die zum Pool gehören, als Teil des Prozesses zur Pool Entfernung. Wenn Sie eine Standard Edition-Front-End-Server entfernen, müssen Sie die SQL-speicherdefinition aus dem Topologie-Generator entfernen.

<div>

## <a name="to-remove-a-front-end-server-pool"></a>So entfernen Sie einen Front-End-Server-Pool

1.  Öffnen Sie den Topologie-Generator.

2.  Navigieren Sie zum Knoten lync Server 2010.

3.  Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie die Front-End-Pool, klicken Sie mit der rechten Maustaste auf das Front-End-Pool, das Sie entfernen möchten, und klicken Sie dann auf **Löschen**.

4.  Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Assistenten für die lync Server-Bereitstellung bei Bedarf aus.

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>So entfernen Sie einen Standard Edition-Front-End-Server

1.  Öffnen Sie den Topologie-Generator.

2.  Navigieren Sie zum Knoten lync Server 2010.

3.  Erweitern Sie **Standard Edition-Front-End-Server**, klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.

4.  Erweitern Sie **SQL-Speicher**, klicken Sie mit der rechten Maustaste auf die SQL Server Datenbank, die der Standard Edition Front-End-Server zugeordnet ist, und klicken Sie dann auf **Löschen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen die Definition der verbundenen SQL Server Datenbanken aus der Standard Edition Front-End-Server entfernen.

    
    </div>

5.  Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Assistenten für die lync Server-Bereitstellung bei Bedarf aus.

</div>

</div>

<span> </span>

</div>

</div>

</div>

