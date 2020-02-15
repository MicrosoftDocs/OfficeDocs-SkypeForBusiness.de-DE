---
title: 'Lync Server 2013: hohe Verfügbarkeit von Dateifreigaben'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453b4c63f58f6153092dae0259155dbfa72b5eca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Hohe Verfügbarkeit der Dateifreigabe in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-03-30_

Um eine hohe Verfügbarkeit für lync Server Dateifreigabe in einem einzelnen Rechenzentrum sicherzustellen, können Sie das verteilte Datei System (DFS) verwenden. DFS unterstützt Failover von einem Dateiserver auf einen anderen Dateiserver innerhalb des gleichen Rechenzentrums. Bei einer umfassenden Bereitstellung empfehlen wir Ihnen die Verwendung von dedizierten Dateiservern, die mithilfe von DFS kombiniert werden.

Abhängig von der Größe Ihres Netzwerks und der gewünschten Ausfallsicherheit können Sie ein Serverpaar zum Hosten von sämtlichen Dateifreigaben eines Standorts oder ein Paar je Front-End-Pool verwenden.

DFS ist ein "Best Effort"-Mechanismus für die Dateireplikation ohne veröffentlichte Zusagen für Wiederherstellungszeit (Recovery Time Objective - RTO) oder Wiederherstellungspunkt (Recovery Point Objective - RPO). Der Failover zwischen den DFS-Servern sollte schnell abgeschlossen werden, jedoch kann eine Verzögerung bei der Datenreplikation verhindern, dass Benutzer ihre laufende Arbeit fortsetzen können, wenn der Failover auftritt.

Wenn Sie DFS verwenden und Datenspeicher bei der Dateifreigabe wichtig ist, sollten Sie die Dateifreigaben öfters speichern, zum Beispiel alle vier bis acht Stunden. Wenn eine Dateifreigabe ausfällt und die Replikation nicht auf dem neuesten Stand ist, können Sie die Sicherung verwenden, um den Inhalt auf dem ausgefallenen Server auf den anderen Server wiederherzustellen, der mit dem Server kombiniert ist, welcher jetzt nicht verfügbar ist.

</div>

<span> </span>

</div>

</div>

</div>

