---
title: 'Lync Server 2013: höchst Verfügbarkeit des Back-End-Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Höhere Verfügbarkeit von Back-End-Servern in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-08-12_

Um eine optimale Verfügbarkeit für Ihre Back-End-Server zu gewährleisten, können Sie entweder synchrone SQL-Spiegelung oder SQL-Clustering verwenden. Die Verwendung einer dieser Lösungen ist optional, wird jedoch empfohlen, um die Geschäftskontinuität in Ihrer Organisation beizubehalten. Die asynchrone SQL-Spiegelung wird für den Back-End-Server mit einer höheren Verfügbarkeit in lync Server 2013 nicht unterstützt. Im restlichen Dokument bedeutet SQL-Spiegelung eine synchrone SQL-Spiegelung, sofern nichts anderes ausdrücklich angegeben ist.

Sie können die SQL-Spiegelung mit dem Topology Builder ganz einfach einrichten. Zum Einrichten von SQL-Failoverclustering müssen Sie SQL Server verwenden.

Wenn Sie entweder SQL-Spiegelung oder SQL-Clustering in einem Pool verwenden, der mit einem anderen Front-End-Pool für die Disaster Recovery gekoppelt ist, sollten Sie in beiden Pools dieselbe Lösung für das Back-End-Angebot verwenden. Mit SQL-Clustering sollten Sie keinen Pool mit SQL-Spiegelung mit einem Pool koppeln.

Wenn Sie die SQL-Spiegelung bereitstellen, werden alle lync Server-Datenbanken im Pool gespiegelt, einschließlich des zentralen Verwaltungsspeichers, wenn sich dieser in diesem Pool befindet, sowie die Anwendungsdatenbank der Reaktionsgruppe und die Anwendungsdatenbank des Anruf Parks, wenn diese Anwendungen im Pool ausgeführt werden.

Bei der SQL-Spiegelung müssen Sie keinen freigegebenen Speicher für die Server verwenden. Jeder Server verwaltet eine Kopie der Datenbanken im lokalen Speicher.

Sie können festlegen, dass die SQL-Spiegelung mit oder ohne Zeugen bereitgestellt wird. Wir empfehlen die Verwendung eines Spiegelungszeugen, da dadurch das automatische Failover des Back-End-Servers ermöglicht wird. Andernfalls muss ein Administrator das Failover manuell auslösen. Beachten Sie, dass selbst bei der Bereitstellung eines Spiegelungszeugen ein Administrator bei Bedarf das Failover des Back-End-Servers manuell auslösen kann.

Wenn Sie einen Spiegelungszeugen verwenden, können Sie einen einzelnen Spiegelungszeugen für mehrere Back-End-Serverpaare verwenden. Es gibt keine strikte 1:1-Entsprechung zwischen Spiegelungszeugen und Back-End-Serverpaaren. Bereitstellungen, bei denen ein einzelner Spiegelungszeuge für mehrere Back-End-Serverpaare verwendet wird, sind nicht ganz so stabil wie Topologien mit einem separaten Spiegelungszeugen für jedes Back-End-Serverpaar.

Weitere Informationen zur Unterstützung von SQL-Clustern finden Sie unter unter [Stützung von Datenbanksoftware in lync Server 2013](lync-server-2013-database-software-support.md). Details zum Bereitstellen von SQL-Clustering finden Sie unter [Konfigurieren des SQL Server-Clusters für lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>Wiederherstellungszeit für automatisches Failover des Back-End-Servers mit SQL-Spiegelung

Für das automatische Back-End-Failover mit SQL-Spiegelung beträgt das Entwicklungsziel für das Wiederherstellungszeitziel (RTO) 5 Minuten. Aufgrund der synchronen SQL-Spiegelung erwarten wir keine Datenverluste bei Back-End-Serverfehlern, außer in seltenen Fällen, in denen sowohl die Front-End-Server als auch der Back-End-Server gleichzeitig Herunterfahren, während Daten zwischen den Servern verschoben werden. Für den Wiederherstellungspunkt (Recovery Point Objective, RPO) wird ein Zielwert von 5 Minuten angestrebt.

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>Benutzerfreundlichkeit während des Back-End-Server Fehlers bei der SQL-Spiegelung

Die Benutzerfreundlichkeit bei einem Ausfall hängt von der Art des Ausfalls und Ihrer Topologie ab.

Wenn Sie die SQL-Spiegelung verwenden und einen Zeugen konfiguriert haben und der Prinzipal fehlschlägt, erfolgt das Failover des Back-End-Servers automatisch und schnell. Aktive Benutzer sollten bei ihren laufenden Sitzungen keine große Unterbrechung feststellen.

Wenn kein Zeuge konfiguriert ist, dauert es einige Zeit, bis der Administrator das Failover manuell aufruft. Während dieser Zeit sind möglicherweise aktive Benutzer betroffen. Sie werden Ihre Sitzungen wie gewohnt für etwa 30 Minuten fortsetzen. Wenn die primäre Person immer noch nicht wiederhergestellt wird oder ein Administrator nicht an die Sicherung gescheitert ist, werden die Benutzer in den Stabilitäts Modus versetzt, was bedeutet, dass Sie keine Aufgaben ausführen können, die eine dauerhafte Änderung auf lync Server erfordern (beispielsweise das Hinzufügen eines Kontakts).

Wenn sowohl der Prinzipalserver als auch der Spiegel-Back-End-Server ausfallen oder wenn einer dieser Server und der Spiegelungszeuge ausfallen, ist der Back-End-Server nicht mehr verfügbar (selbst wenn der Prinzipalserver weiterhin einsatzbereit ist). In diesem Fall werden die aktiven Benutzer nach einer Weile auf den Ausfallsicherheitsmodus umgestellt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

