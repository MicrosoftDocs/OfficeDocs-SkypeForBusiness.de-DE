---
title: 'Lync Server 2013: Datensicherheit beim Bilden von Front-End-Poolpaaren'
TOCTitle: Datensicherheit beim Bilden von Front-End-Poolpaaren
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49890999
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Datensicherheit beim Bilden von Front-End-Poolpaaren in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Der Sicherungsdienst ist ein Datenreplikationsmechanismus, der Lync Server 2013 eingeführt wurde. Er überträgt kontinuierlich Benutzerdaten und Konferenzinhalte zwischen zwei Front-End-Poolss, die als Paar konfiguriert sind, über zwei Rechenzentren für Notfallwiederherstellungszwecke. Die Benutzerdaten enthalten SIP-URIs für Benutzer sowie Kontaktlisten und Einstellungen. Konferenzinhalte umfassen Microsoft PowerPoint 2010-Uploads sowie in Konferenzen verwendete Whiteboards. Vom Quellpool werden die Benutzerdaten und Konferenzinhalte aus dem lokalen Speicher exportiert, gezippt, zum Zielpool übertragen, wo sie entzippt werden, und in den lokalen Speicher importiert. Der Sicherungsdienst geht davon aus, dass die Kommunikationsverbindung zwischen den beiden Rechenzentren innerhalb des Unternehmensnetzwerks besteht, das vor dem Internet geschützt ist. Daher werden die übertragenen Daten nicht zwischen den zwei Rechenzentren verschlüsselt und auch nicht innerhalb eines sicheren Protokolls, etwa HTTPS, nativ verschlüsselt. Infolgedessen sind Man-in-the-Middle-Angriffe von internen Mitarbeitern innerhalb des Unternehmensnetzwerks möglich.

## Bewerten von Sicherheitsrisiken

Jedes Unternehmen, das Lync Server 2013 über mehrere Rechenzentren hinweg bereitstellt und das Feature für die Notfallwiederherstellung verwendet, muss sicherstellen, dass der die Rechenzentren übergreifende Datenverkehr durch das unternehmenseigene Intranet geschützt wird. Unternehmen, die ihren Datenverkehr vor internen Angriffen schützen möchten, müssen die Kommunikationsverbindungen zwischen den Rechenzentren schützen.

Es ist eine weit verbreitete Annahme, dass Rechenzentren eines Unternehmens hinter dem firmeneigenen Intranet geschützt sind. Viele andere Arten von vertraulichen Unternehmensdaten werden ebenfalls zwischen diesen Rechenzentren übertragen. Die IT-Infrastruktur des Unternehmens ist massiv gefährdet, wenn diese rechenzentrenübergreifenden Verbindungen nicht geschützt werden.

Das Risiko von Man-in-the-Middle-Angriffen innerhalb des Unternehmensnetzwerks besteht zwar, doch ist es im Vergleich zur Gefährdung des Datenverkehrs im Internet relativ begrenzt. Insbesondere die Benutzerdaten, die vom Sicherungsdienst verfügbar gemacht werden (z. B. SIP-URIs), sind für alle Mitarbeiter im Unternehmen über andere Mittel wie etwa das globale Adressbuch von Exchange oder andere Verzeichnissoftware allgemein verfügbar. Daher sollte der Schwerpunkt auf dem Schutz des WANs zwischen den beiden Rechenzentren liegen, wenn der Sicherungsdienst zum Kopieren von Daten zwischen einem Poolpaar verwendet wird.

## Minimieren von Sicherheitsrisiken

Es gibt zahlreiche Möglichkeiten, den Schutz des Datenverkehrs vom Sicherungsdienst zu verbessern, vom Beschränken des Zugriffs auf die Rechenzentren bis hin zum Schützen des WAN-Transports zwischen den beiden Rechenzentren. In den meisten Fällen haben Unternehmen, die Lync Server 2013 bereitstellen, die erforderliche Sicherheitsinfrastruktur wahrscheinlich schon implementiert. Unternehmen, die hier ihre Maßnahmen noch verstärken müssen, bietet Microsoft eine Lösung als Beispiel für das Aufbauen einer sicheren IT-Infrastruktur an. Das soll nicht heißen, dass dies die einzig mögliche Lösung oder die bevorzugte Lösung für Lync Server ist. Wir empfehlen, dass Unternehmen die Lösung wählen, die ihrem individuellen Bedarf am meisten entspricht, je nach ihrer IT-Sicherheitsinfrastruktur und ihren Sicherheitsanforderungen. In der Microsoft-Beispiellösung werden IPsec und Gruppenrichtlinien für die Server- und Domänenisolation verwendet. Ausführliche Informationen finden Sie unter [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544). Wenn Sie Fragen oder Anregungen hierzu haben, kontaktieren Sie secwish@microsoft.com.

Eine weitere mögliche Lösung besteht in der Verwendung von IPSec ausschließlich zur Sicherung der vom Sicherungsdienst selbst gesendeten Daten. Wenn Sie sich für diese Methode entscheiden, konfigurieren Sie die IPSec-Regeln für das SMB-Protokoll auf den folgenden Servern, wenn Pool A und Pool B zwei verbundene Front-End-Pools sind.

  - Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool A an den von Pool B verwendeten Dateispeicher.

  - Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool B an den von Pool A verwendeten Dateispeicher.


> [!WARNING]
> IPsec ist nicht als Ersatz für Sicherheit auf Anwendungsebene wie etwa SSL/TLS gedacht. Ein Vorteil der Verwendung von IPsec liegt darin, dass es Sicherheit für Netzwerkdatenverkehr für vorhandene Anwendungen bereitstellen kann, ohne dass diese geändert werden müssen. Unternehmen, die einfach nur den Transport zwischen den beiden Rechenzentren schützen möchten, sollten sich bei den Herstellern der jeweiligen Netzwerkhardware erkundigen, wie sie mit den betreffenden Geräten sichere WAN-Verbindungen einrichten können.


