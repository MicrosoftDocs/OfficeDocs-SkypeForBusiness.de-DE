---
title: 'Lync Server 2013: Beziehungen von Sicherungsregistrierungsstellen'
TOCTitle: Beziehungen von Sicherungsregistrierungsstellen
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205033(v=OCS.15)
ms:contentKeyID: 49294534
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Beziehungen von Sicherungsregistrierungsstellen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-06-28_

Zwei gepaarte Pools bieten nicht nur die Möglichkeit der Notfallwiederherstellung, sondern dienen auch als gegenseitige Sicherungsregistrierung. In Lync Server 2013 ist das Verhältnis von Sicherungsregistrierungen zwischen Front-End-Pools stets 1:1 und wechselseitig. Wenn P1 als Sicherung für P2 dient, muss demzufolge P2 als Sicherung für P1 dienen, und keiner von beiden kann als Sicherung für irgendeinen anderen Front-End-Pool verwendet werden. Dies unterscheidet sich von Lync Server 2010. Hier konnten die Sicherungsverhältnisse zwischen Front-End-Pools vielschichtiger sein.

Obwohl die Sicherungsverhältnisse zwischen zwei Front-End-Pools 1:1 und symmetrisch sein müssen, kann trotzdem jeder Front-End-Pool als Sicherungsregistrierung für eine beliebige Anzahl an Survivable Branch-Anwendungen dienen, wie in Lync Server 2010.

Beachten Sie, dass Lync Server 2013 die Notfallwiederherstellung für Benutzer auf einer Survivable Branch-Anwendung unterstützt. Wenn ein Front-End-Pool ausfällt, der als Sicherung für eine Survivable Branch-Anwendung dient, werden die bei der Survivable Branch-Anwendung angemeldeten Benutzer in den Ausfallsicherheitsmodus versetzt, selbst nachdem die Benutzer auf dem Front-End-Pool auf den Sicherungs- Front-End-Pool verschoben wurden.

