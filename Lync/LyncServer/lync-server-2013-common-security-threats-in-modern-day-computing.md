---
title: 'Lync Server 2013: häufige Sicherheitsrisiken in der modernen Computernutzung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2446ee0755f4544f17f6c04c6059d70576a466f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>Häufige Sicherheitsbedrohungen in der modernen EDV

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-09-10_

Da es sich bei lync Server 2013 um ein Kommunikationssystem auf Unternehmensniveau handelt, sollten Sie sich der allgemeinen Sicherheitsangriffe bewusst sein, die sich auf die Infrastruktur und die Kommunikation auswirken können.

<div>

## <a name="compromised-key-attack"></a>Angriff mit kompromittierten Schlüsseln

Ein Schlüssel ist ein geheimer Code oder eine geheime Nummer zur Verschlüsselung, Entschlüsselung oder Überprüfung geheimer Informationen. Bei der Infrastruktur öffentlicher Schlüssel (Public Key Infrastructure, PKI) werden zwei vertrauliche Schlüssel verwendet, die berücksichtigt werden müssen:

  - Der private Schlüssel, der sich im Besitz des jeweiligen Zertifikatinhabers befindet

  - Der Sitzungsschlüssel, der nach der erfolgreichen Identifikation und dem Sitzungsschlüsselaustausch durch die Kommunikationspartner verwendet wird

Ein Angriff mit kompromittierten Schlüsseln liegt vor, wenn der Angreifer den privaten Schlüssel oder den Sitzungsschlüssel ermittelt. Gelingt dem Angreifer die Ermittlung des Schlüssels, kann er den Schlüssel zum Entschlüsseln verschlüsselter Daten ohne Wissen des Absenders verwenden.

Lync Server 2013 verwendet die PKI-Features im Windows Server-Betriebssystem, um die für die Verschlüsselung verwendeten Schlüsseldaten für die TLS-Verbindungen (Transport Layer Security) zu schützen. Die für die Medienverschlüsselung verwendeten Schlüssel werden über TLS-Verbindungen ausgetauscht.

</div>

<div>

## <a name="network-denial-of-service-attack"></a>Denial-of-Service-Angriff auf das Netzwerk

Ein *Denial-of-Service-Angriff* liegt vor, wenn der Angreifer die normale Netzwerknutzung durch gültige Nutzer verhindert. Hierbei überfluten Angreifer den Dienst mit legitimen Anforderungen, sodass er für die berechtigten Nutzer nicht mehr erreichbar ist. Bei einem Denial-of-Service-Angriff eröffnen sich den Angreifern folgende Möglichkeiten:

  - Er kann ungültige Daten an Anwendungen und Dienste senden, die in dem angegriffenen Netzwerk ausgeführt werden, um ihre Funktionsweise zu beeinträchtigen.

  - Er kann große Datenmengen senden, um das System zu überlasten, bis es nicht mehr oder nur noch verzögert auf legitime Anforderungen reagiert.

  - Er kann die Spuren seines Angriffs vertuschen.

  - Er kann Benutzer vom Zugriff auf die Netzwerkressourcen abhalten.

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>Abhöraktionen ("Sniffing", "Snooping")

*Abhöraktionen* sind Aktionen, bei denen sich Angreifer Zugriff auf den Datenpfad in einem Netzwerk verschaffen und anschließend den Datenverkehr überwachen und lesen können. Dies wird auch als „Schnüffeln“ (auch „Lauschangriff“, englisch *Sniffing* oder *Snooping*) bezeichnet. Wenn der Datenverkehr aus reinem Text besteht, können Angreifer ihn lesen, sobald sie Zugriff auf den Pfad haben. Ein Beispiel wäre ein Angriff, bei dem ein Router auf dem Datenpfad kontrolliert wird.

Die Standardempfehlung und-Einstellung für den Datenverkehr in Microsoft lync Server 2013 besteht darin, MTLS (Mutual TLS) zwischen vertrauenswürdigen Servern und TLS vom Client zum Server zu verwenden. Diese Schutzmaßnahme macht einen derartigen Angriff innerhalb der Zeitspanne, in der eine Unterhaltung erfolgt, äußerst schwer oder unmöglich. Mit TLS werden alle Parteien authentifiziert und der gesamte Datenverkehr wird verschlüsselt. Damit können Abhöraktionen nicht verhindert werden, aber Angreifer können den Datenverkehr nicht lesen, es sei denn, die Verschlüsselung geht verloren.

Das TURN-Protokoll (Traversal Using Relay NAT) setzt keine Verschlüsselung des Datenverkehrs voraus. Die Daten, die darüber versendet werden, unterliegen dem Schutz durch die Nachrichtenintegrität. Es ist rein theoretisch möglich, sie abzuhören, aber die Informationen, die über das TURN-Protokoll gesendet werden (d. h. die IP-Adressen und der Port), können direkt extrahiert werden, indem die Quell- und Zieladressen der Pakete angezeigt werden. Der A/V-Edgedienst stellt sicher, dass die Daten gültig sind, indem er die Nachrichtenintegrität der Nachricht mithilfe des Schlüssels überprüft, der von bestimmten Objekten abgeleitet wird. Dazu gehört auch ein TURN-Kennwort, das nie als Klartext gesendet wird. Wenn SRTP (Secure Real Time Protocol) verwendet wird, so wird auch der Mediendatenverkehr verschlüsselt.

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>Identitätsvortäuschung (Spoofing der IP-Adresse)

*Spoofing* liegt vor, wenn Angreifer unbefugt die IP-Adresse eines Netzwerks, Computers oder einer Netzwerkkomponente ermitteln und verwenden. Nach einem erfolgreichen Angriff können sich Angreifer als die normalerweise durch diese IP-Adresse identifizierte Entität ausgeben. Im Kontext von Microsoft lync Server 2013 tritt diese Situation nur dann in das Spiel ein, wenn ein Administrator die folgenden Schritte ausgeführt hat:

  - Er hat Verbindungen konfiguriert, die nur TCP (Transmission Control Protocol) unterstützen. (Dies ist nicht zu empfehlen, da die TCP-Kommunikation unverschlüsselt ist.)

  - Er hat die IP-Adressen dieser Verbindungen als vertrauenswürdige Hosts markiert.

Dies ist für TLS-Verbindungen (Transport Layer Security) weniger ein Problem, da TLS alle Parteien authentifiziert und den gesamten Datenverkehr verschlüsselt. Die Verwendung von TLS verhindert Spoofingangriffe auf bestimmte Verbindungen (Mutual TLS-Verbindungen). Ein Angreifer kann aber weiterhin die Adresse des DNS-Servers spoofen, der von lync Server 2013 verwendet wird. Da die Authentifizierung in lync jedoch mit Zertifikaten durchgeführt wird, verfügt ein Angreifer nicht über ein gültiges Zertifikat, das zum Spoofing einer der Parteien in der Kommunikation erforderlich ist.

</div>

<div>

## <a name="man-in-the-middle-attack"></a>Man-in-the-Middle-Angriff

Von einem „Man-in-the-Middle-Angriff“ spricht man, wenn Angreifer die Kommunikation zwischen zwei Nutzern ohne deren Wissen über ihren eigenen Computer leiten. Die Angreifer können die übertragenen Daten überwachen und lesen, ehe sie an den eigentlichen Empfänger weitergeleitet werden. Beide Kommunikationspartner senden unwissentlich Daten an die Angreifer und empfangen von ihnen Daten, sind aber dabei in dem Glauben, ausschließlich mit der beabsichtigten Person zu kommunizieren. Dies kann passieren, wenn es Angreifern gelingt, die Active Directory-Domänendienste so zu ändern, dass ihr Server als vertrauenswürdiger Server hinzugefügt wird, oder wenn sie den DNS-Eintrag (Domain Name System) so ändern können, dass Clients auf ihrem Weg zum Server über den Computer der Angreifer geleitet werden. Ein Man-in-the-Middle-Angriff kann auch bei Mediendatenverkehr zwischen zwei Clients erfolgen, wobei jedoch in skype16_server_short Point-to-Point-Audio-, Video- und Anwendungsfreigabe-Datenströme mit dem Secure Real-Time Transport Protocol (SRTP) verschlüsselt werden. In Microsoft lync Server 2013 Punkt-zu-Punkt-Audio-, Video-und Anwendungsfreigabe werden Datenströme jedoch mit SRTP verschlüsselt, wobei kryptografische Schlüssel verwendet werden, die zwischen den Peers ausgehandelt werden, die SIP (Session Initiation Protocol) über TLS verwenden. Server wie Gruppenchat nutzen HTTPS zur Erhöhung der Sicherheit des Webdatenverkehrs.

</div>

<div>

## <a name="rtp-replay-attack"></a>Angriff mit Aufzeichnungswiederholung (RTP-Datenverkehr)

Bei einem *Angriff mit Aufzeichnungswiederholung* wird in böswilliger Absicht eine gültige Medienübertragung zwischen zwei Parteien abgefangen und erneut übertragen. Durch die Verwendung von SRTP in Verbindung mit einem sicheren Signalübermittlungsprotokoll werden Übertragungen vor Angriffen mit Aufzeichnungswiederholung geschützt. Mit SRTP können Empfänger einen Index der bereits empfangenen RTP-Pakete erstellen und jedes neue Paket mit den bereits enthaltenen vergleichen.

</div>

<div>

## <a name="spim"></a>SPIM (Spam over Instant Messaging)

Unter *SPIM* sind unaufgeforderte Werbe-SMS oder Anwesenheitsabonnementanforderungen zu verstehen. Zwar wird das Netzwerk nicht unmittelbar beeinträchtigt, doch ist SPIM zumindest ärgerlich, kann die Ressourcenverfügbarkeit und die Produktivität reduzieren und möglicherweise zu einer Beeinträchtigung des Netzwerks führen. Ein Beispiel für Spimming sind Nutzer, die sich gegenseitig Anfragen zusenden. Nutzer können sich gegenseitig blockieren, um dies zu verhindern. Ein koordinierter Spimangriff im Partnerverbund kann jedoch schwer abzuwehren sein, wenn Sie den Verbund für den Partner nicht deaktivieren.

</div>

<div>

## <a name="viruses-and-worms"></a>Viren und Würmer

Ein *Virus* ist eine Codeeinheit, deren Zweck darin besteht, zusätzliche, ähnliche Codeeinheiten zu reproduzieren. Für seine Arbeit benötigt der Virus einen Host, wie z. B. eine Datei, eine E-Mail oder ein Programm. Wie ein Virus ist ein *Wurm* ebenfalls eine Codeeinheit, die auf die Reproduktion zusätzlicher, ähnlicher Codeeinheiten programmiert ist. Im Gegensatz zum Virus wird jedoch kein Host benötigt. Viren und Würmer treten vornehmlich bei Dateiübertragungen zwischen Clients auf oder, wenn URLs von anderen Nutzern gesendet werden. Befindet sich auf Ihrem Computer ein Virus, kann er beispielsweise Ihre Identität verwenden und Chatnachrichten in Ihrem Namen senden.

</div>

<div>

## <a name="personally-identifiable-information"></a>Informationen zur Identifikation von Personen

Microsoft lync Server 2013 hat das Potenzial, Informationen über ein öffentliches Netzwerk offenzulegen, die möglicherweise mit einer Person verknüpft werden können. Bei diesen Informationen kann es sich um zwei Kategorien von Angaben handeln:

  - **Erweiterte Anwesenheitsdaten** Erweiterte Anwesenheitsdaten sind Informationen, die ein Benutzer für die Freigabe oder nicht Freigabe über einen Link zu einem Föderationspartner oder mit Kontakten in einer Organisation auswählen kann. Diese Daten werden nicht an Benutzer in einem öffentlichen IM-Netzwerk weitergegeben. Client-Richtlinien und andere Client-Konfigurationen können dem Systemadministrator eine gewisse Kontrolle verschaffen. In lync Server 2013 kann der Erweiterte Anwesenheitsdaten Schutzmodus für einen einzelnen Benutzer so konfiguriert werden, dass lync-Benutzer nicht in der Kontaktliste des Benutzers die Anwesenheitsinformationen des Benutzers sehen können. Der Datenschutzmodus für erhöhte Anwesenheit verhindert nicht, dass Benutzer von Microsoft Office Communicator 2007 und Microsoft Office Communicator 2007 R2 die Anwesenheitsinformationen eines Benutzers sehen. Ausführliche Informationen finden Sie unter [Neuerungen für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in der Dokumentation "erste Schritte" und [Konfigurieren des Datenschutzmodus für erhöhte Anwesenheit in lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in der Bereitstellungsdokumentation.

  - **Obligatorische Daten** Obligatorische Daten sind für den ordnungsgemäßen Betrieb des Servers oder des Clients erforderlich und unterliegen nicht der Kontrolle durch den Client oder die System Administration. Es handelt sich um Informationen, die auf Server- oder Netzwerkebene für das Routing, die Statuspflege und die Signalübermittlung erforderlich sind.

In den folgenden Tabellen wird angegeben, welche Daten über ein öffentliches Netzwerk offengelegt werden.

### <a name="enhanced-presence-data"></a>Erweiterte Anwesenheitsdaten

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Offengelegte Daten</th>
<th>Mögliche Einstellungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Persönliche Daten</p></td>
<td><p>Name, Titel, Unternehmen, E-Mail-Adresse, Zeitzone</p></td>
</tr>
<tr class="even">
<td><p>Telefonnummern</p></td>
<td><p>Geschäftlich, mobil, privat</p></td>
</tr>
<tr class="odd">
<td><p>Kalenderdaten</p></td>
<td><p>Frei/Gebucht, Abwesenheitsmitteilung, Besprechungsdetails (für Personen mit Zugriff auf Ihren Kalender)</p></td>
</tr>
<tr class="even">
<td><p>Anwesenheitsstatus</p></td>
<td><p>Abwesend, verfügbar, gebucht, nicht stören, offline</p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a>Pflichtdaten

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Offengelegte Daten</th>
<th>Beispieldaten</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IP-Adresse</p></td>
<td><p>Tatsächliche Computer- oder NAT-Adresse</p></td>
</tr>
<tr class="even">
<td><p>SIP-URI</p></td>
<td><p>jeremylos@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

