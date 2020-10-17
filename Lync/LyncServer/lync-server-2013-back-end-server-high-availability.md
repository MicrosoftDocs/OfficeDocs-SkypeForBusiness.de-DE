---
title: 'Lync Server 2013: hohe Verfügbarkeit des Back-End-Servers'
description: 'Lync Server 2013: hohe Verfügbarkeit des Back-End-Servers.'
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
ms.openlocfilehash: 805cbf96e107329aa5c374cfa1e2d01234d360a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543771"
---
# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Hohe Verfügbarkeit von Back-End-Servern in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-08-12_

Um eine hohe Verfügbarkeit für die Back-End-Server sicherzustellen, können Sie entweder synchrone SQL-Spiegelung oder SQL-Clustering verwenden. Die Verwendung einer dieser Lösungen ist optional, wird jedoch empfohlen, um die Geschäftskontinuität in Ihrer Organisation aufrechtzuerhalten. Die asynchrone SQL-Spiegelung wird für die hohe Verfügbarkeit von Back-End-Servern in lync Server 2013 nicht unterstützt. In diesem Dokument steht, sofern nicht anders angegeben, SQL-Spiegelung für die synchrone SQL-Spiegelung.

Sie können die SQL-Spiegelung ganz einfach mit dem Topologie-Generator einrichten. Für SQL-Failoverclustering müssen Sie SQL Server für das Setup verwenden.

Wenn Sie entweder SQL-Spiegelung oder SQL-Clustering in einem Pool verwenden, der mit einem anderen Front-End-Pool für die Notfallwiederherstellung gekoppelt ist, sollten Sie dieselbe Back-End-Lösung für hohe Verfügbarkeit in beiden Pools verwenden. Sie sollten keinen Pool mit SQL-Spiegelung mit einem Pool mit SQL-Clustering koppeln.

Wenn Sie die SQL-Spiegelung bereitstellen, werden alle lync Server-Datenbanken im Pool gespiegelt, einschließlich des zentralen Verwaltungsspeichers, wenn Sie sich in diesem Pool befinden, sowie der Reaktionsgruppenanwendung Datenbank und der Anwendung zum Parken von Anrufen Datenbank, wenn diese Anwendungen im Pool ausführen.

Bei der SQL-Spiegelung müssen Sie keinen gemeinsam genutzten Speicher für die Server verwenden. Jeder Server verwaltet eine Kopie der Datenbanken im lokalen Speicher.

Sie können die SQL-Spiegelung mit oder ohne einen Spiegelungszeugen bereitstellen. Wir empfehlen die Verwendung eines Spiegelungszeugen, da dadurch das automatische Failover des Back-End-Servers ermöglicht wird. Andernfalls muss ein Administrator das Failover manuell auslösen. Beachten Sie, dass selbst bei der Bereitstellung eines Spiegelungszeugen ein Administrator bei Bedarf das Failover des Back-End-Servers manuell auslösen kann.

Wenn Sie einen Spiegelungszeugen verwenden, können Sie einen einzelnen Spiegelungszeugen für mehrere Back-End-Serverpaare verwenden. Es gibt keine strikte 1:1-Entsprechung zwischen Spiegelungszeugen und Back-End-Serverpaaren. Bereitstellungen, bei denen ein einzelner Spiegelungszeuge für mehrere Back-End-Serverpaare verwendet wird, sind nicht ganz so stabil wie Topologien mit einem separaten Spiegelungszeugen für jedes Back-End-Serverpaar.

Weitere Informationen zur Unterstützung von SQL-Clusterunterstützung finden Sie unter [Datenbanksoftware-Unterstützung in lync Server 2013](lync-server-2013-database-software-support.md). Ausführliche Informationen zum Bereitstellen von SQL-Clustering finden Sie unter [configure SQL Server Clustering for lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>Wiederherstellungszeit für automatisches Back-End-Server Failover mit SQL-Spiegelung

Für das automatische Back-End-Failover mit SQL-Spiegelung beträgt das Entwicklungsziel für die Wiederherstellungszeit (RTO) 5 Minuten. Aufgrund der synchronen SQL-Spiegelung wird nicht von einem Datenverlust bei Ausfällen von Back-End-Servern ausgegangen, außen in seltenen Fällen, wenn sowohl der Front-End-Server als auch der Back-End-Server beim Verschieben von Daten zwischen diesen Servern gleichzeitig ausfällt. Für den Wiederherstellungspunkt (Recovery Point Objective, RPO) wird ein Zielwert von 5 Minuten angestrebt.

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>Benutzerfreundlichkeit während des Back-End-Server Fehlers mit SQL-Spiegelung

Die Benutzerfreundlichkeit bei einem Ausfall hängt von der Art des Ausfalls und Ihrer Topologie ab.

Wenn Sie die SQL-Spiegelung verwenden und einen Zeugen konfiguriert haben und der Prinzipal ausfällt, erfolgt das Failover des Back-End-Servers automatisch und schnell. Aktive Benutzer sollten bei ihren laufenden Sitzungen keine große Unterbrechung feststellen.

Wenn kein Zeuge konfiguriert ist, dauert es einige Zeit, bis der Administrator das Failover manuell aufruft. Während dieser Zeit sind möglicherweise aktive Benutzer betroffen. Sie werden Ihre Sitzungen wie gewohnt für etwa 30 Minuten fortsetzen. Wenn das primäre Gerät noch nicht wiederhergestellt wurde oder ein Administrator nicht auf die Sicherung gescheitert ist, werden die Benutzer in den Ausfall Sicherheitsmodus umgeschaltet, was bedeutet, dass Sie keine Aufgaben ausführen können, die eine beständige Änderung am lync Server erfordern (beispielsweise das Hinzufügen eines Kontakts).

Wenn Sowohl der Prinzipalserver als auch der Spiegel-Back-End-Server ausfallen, oder wenn einer dieser Server und der Spiegelungszeuge ausfallen, ist der Back-End-Server nicht mehr verfügbar (selbst wenn der Prinzipalserver weiterhin einsatzbereit ist). In diesem Fall werden die aktiven Benutzer nach einer Weile auf den Ausfallsicherheitsmodus umgestellt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

