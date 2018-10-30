---
title: Testen der Skalierbarkeit
TOCTitle: Testen der Skalierbarkeit
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205226(v=OCS.15)
ms:contentKeyID: 49295264
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Testen der Skalierbarkeit

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Lync Server 2013 bietet die Serverinfrastruktur für die gesamte Lync Server- Echtzeitkommunikation, einschließlich Chats und Anwesenheit, Konferenzen und Enterprise-VoIP. Hierzu gehören alle Features, welche die Hardwareressourcen eines Lync Server 2013-Pools verwenden und dadurch die Leistung und Skalierung beeinträchtigen. Nicht alle Organisationen verwenden alle Features gleichermaßen.

Beispielsweise verwenden manche Organisationen Video in Konferenzen in großem Umfang, während andere Organisationen Video wenig oder überhaupt nicht verwenden. Manche Organisationen ziehen die Freigabe von PowerPoint-Folien der Anwendungsfreigabe vor, während bei anderen Organisationen das Gegenteil der Fall ist. Jene Organisationen, die Enterprise-VoIP bereitstellen, setzen die Reaktionsgruppenanwendung möglicherweise auf breiter Basis ein, oder aber auch nicht. Die meisten Organisationen stellen Monitoring-Server bereit, aber nur wenige Organisationen stellen Archivierungsserver bereit. Darüber hinaus weisen nicht alle Organisationen dieselbe Infrastruktur auf. Hierzu zählen Hardwarekapazitäten, Netzwerkkapazitäten und die Anzahl bzw. die Größe der bereitgestellten Pools. Die Vielfalt der Features und Infrastrukturen stellt eine Herausforderung für Skalierbarkeitstests dar, da es nicht möglich ist, alle möglichen Kombinationen der Features und Infrastrukturen zu simulieren.

Zur Bestimmung der Skalierbarkeitsunterstützung für Lync Server führen wir Tests durch, indem wir alle Lync Server-Features gleichzeitig verwenden, und zwar auf der Basis eines durchschnittlichen Nutzungsmodells (Benutzermodell). Um ein geeignetes Benutzermodell für Lync Server-Arbeitsauslastungen zu bestimmen, analysieren wir viele Datenpunkte, einschließlich Kundenumfragen, Feedback aus dem Microsoft-Programm zur Verbesserung der Benutzerfreundlichkeit, Lync Server-Nutzungsdaten der internen IT-Abteilung bei Microsoft sowie erfasste Daten unseres Live Meeting-Diensts. In vielen Fällen ist das Benutzermodell für umfangreichere Auslastungen ausgelegt, um eine bequeme Nutzung innerhalb einer Organisation zu ermöglichen.

Bei unseren Skalierbarkeitstests richten wir Lync Server 2013-Pools gemäß den empfohlenen Hardware- und Softwarespezifikationen ein, einschließlich Infrastrukturkomponenten, wie z. B. Active Directory-Domänendienste, Hardwaregeräte zum Lastenausgleich und Firewalls. Wir richten Lync Server-Umgebungen, soweit dies möglich ist, wie typische echte Umgebungen ein. Anschließend simulieren wir mit dem Lync Server 2013-Belastungs- und Leistungstool Lync Server 2013-Auslastungen (basierend auf unserem Benutzermodell).

Wir führen die Skalierbarkeitstests mehrmals aus (einschließlich mehrerer dreiwöchiger Testläufe). Die Ergebnisse aller Tests verwenden wir dann zur Leistungsoptimierung und zum Überprüfen der Unterstützung der Skalierbarkeitszahlen in unserem Benutzermodell.

