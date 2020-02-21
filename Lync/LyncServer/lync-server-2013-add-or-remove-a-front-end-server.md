---
title: 'Lync Server 2013: Hinzufügen oder Entfernen eines Front-End-Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e358415b086594b67fabdc5ed74706a510e2f82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Hinzufügen oder Entfernen eines Front-End-Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-01-21_

Wenn Sie einem Pool einen Front-End-Server hinzufügen oder einen Front-End-Server aus einem Pool entfernen, müssen Sie den Pool anschließend neu starten. Wenden Sie beim Hinzufügen oder Entfernen eines Front-End-Servers das folgende Verfahren an, um Dienstunterbrechungen für die Benutzer zu verhindern.

<div>


> [!NOTE]  
> Wenn Sie dem Pool neue Server hinzufügen, aktualisieren Sie die neuen Pool Server so, dass Sie auf der gleichen kumulativen Update Ebene wie die vorhandenen Server im Pool sind.



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>So können Sie Front-End-Server hinzufügen oder entfernen

1.  Wenn Sie Front-End-Server entfernen, beenden Sie zunächst neue Verbindungen mit diesen Servern. Dazu können Sie das folgende Cmdlet verwenden:
    
        Stop-CsWindowsServices -Graceful

2.  Wenn auf den zu entfernenden Servern keine aktuellen Sitzungen vorhanden sind, halten Sie die Lync Server-Dienste auf diesen Servern an.

3.  Öffnen Sie den Topologie-Generator, und fügen Sie die benötigten Server hinzu, oder entfernen Sie sie.

4.  Veröffentlichen Sie die Topologie.

5.  Wenn der Pool von zwei Front-End-Servern auf mehr als zwei oder von mehr als zwei Servern auf genau zwei fortgegangen ist, müssen Sie das folgende Cmdlet eingeben:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Wenn der Pool drei oder mehr Server aufweist, müssen beim Eingeben dieses Cmdlets mindestens drei dieser Server ausgeführt werden.

6.  Starten Sie alle Front-End-Server im Pool nacheinander neu.

</div>

</div>

<span> </span>

</div>

</div>

</div>

