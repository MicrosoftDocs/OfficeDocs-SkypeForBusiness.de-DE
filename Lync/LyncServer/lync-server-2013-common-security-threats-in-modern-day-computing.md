---
title: Häufig auftretende Sicherheitsbedrohungen in der modernen EDV
TOCTitle: Häufig auftretende Sicherheitsbedrohungen in der modernen EDV
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56558905
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Häufig auftretende Sicherheitsbedrohungen in der modernen EDV

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Da es sich bei Lync Server 2013 um ein Kommunikationssystem auf Unternehmensniveau handelt, sollten Sie die häufig auftretenden Sicherheitsbedrohungen kennen, die eine permanente Gefahr für die Infrastruktur und die Kommunikation darstellen.

## Angriff mit kompromittierten Schlüsseln

Ein Schlüssel ist ein geheimer Code oder eine geheime Nummer zur Verschlüsselung, Entschlüsselung oder Überprüfung geheimer Informationen. Bei der Infrastruktur öffentlicher Schlüssel (Public Key Infrastructure, PKI) werden zwei vertrauliche Schlüssel verwendet, die berücksichtigt werden müssen:

  - Der private Schlüssel, der sich im Besitz des jeweiligen Zertifikatinhabers befindet

  - Der Sitzungsschlüssel, der nach der erfolgreichen Identifikation und dem Sitzungsschlüsselaustausch durch die Kommunikationspartner verwendet wird

Ein Angriff mit kompromittierten Schlüsseln liegt vor, wenn der Angreifer den privaten Schlüssel oder den Sitzungsschlüssel ermittelt. Gelingt dem Angreifer die Ermittlung des Schlüssels, kann er den Schlüssel zum Entschlüsseln verschlüsselter Daten ohne Wissen des Absenders verwenden.

Lync Server 2013 verwendet die PKI-Funktionen des Windows Server-Betriebssystems, um die für die Verschlüsselung für TLS-Verbindungen (Transport Layer Security) verwendeten Schlüsseldaten zu schützen. Die für die Medienverschlüsselung verwendeten Schlüssel werden über TLS-Verbindungen ausgetauscht.

## Denial-of-Service-Angriff auf das Netzwerk

Ein *Denial-of-Service-Angriff* liegt vor, wenn der Angreifer die normale Netzwerknutzung durch gültige Benutzer verhindert. Hierbei überflutet der Angreifer den Dienst mit legitimen Anforderungen, sodass er für die berechtigten Benutzer nicht mehr erreichbar ist. Bei einem Denial-of-Service-Angriff eröffnen sich dem Angreifer folgende Möglichkeiten:

  - Er kann ungültige Daten an Anwendungen und Dienste senden, die in dem angegriffenen Netzwerk ausgeführt werden, um ihre Funktionsweise zu beeinträchtigen.

  - Er kann große Datenmengen senden, um das System zu überlasten, bis es nicht mehr oder nur noch verzögert auf legitime Anforderungen reagiert.

  - Er kann die Spuren seines Angriffs vertuschen.

  - Er kann Benutzer vom Zugriff auf die Netzwerkressourcen abhalten.

## Abhöraktionen ("Sniffing", "Snooping")

*Abhöraktionen* sind Aktionen, bei denen ein Angreifer Zugriff auf den Datenpfad in einem Netzwerk erlangt und anschließend den Datenverkehr überwachen und lesen kann. Dies wird auch als "Schnüffeln" (auch Lauschangriff, englisch *Sniffing* oder *Snooping*) bezeichnet. Wenn der Datenverkehr aus reinem Text besteht, kann der Angreifer ihn lesen, sobald er Zugriff auf den Pfad hat. Ein Beispiel wäre ein Angriff, bei dem ein Router auf dem Datenpfad kontrolliert wird.

Als Standardeinstellung empfiehlt sich für den Datenverkehr innerhalb von Microsoft Lync Server 2013 die Verwendung von MTLS (Mutual TLS) zwischen vertrauenswürdigen Servern und TLS vom Client zum Server. Diese Schutzmaßnahme macht einen derartigen Angriff innerhalb der Zeitspanne, in der eine Unterhaltung erfolgt, äußerst schwer oder unmöglich. Mit TLS werden alle Parteien authentifiziert und der gesamte Datenverkehr verschlüsselt. Damit können Abhöraktionen nicht verhindert werden, aber der Angreifer kann den Datenverkehr nicht lesen, es sei denn, die Verschlüsselung geht verloren.

Das TURN-Protokoll (Traversal Using Relay NAT) setzt keine Verschlüsselung des Datenverkehrs voraus. Die Daten, die darüber versendet werden, unterliegen dem Schutz durch die Nachrichtenintegrität. Es ist rein theoretisch möglich, sie abzuhören, aber die Informationen, die über das TURN-Protokoll gesendet werden (d. h. die IP-Adressen und der Port), können direkt extrahiert werden, indem die Quell- und Zieladressen der Pakete angezeigt werden. Der A/V-Edgedienst stellt sicher, dass die Daten gültig sind, indem er die Nachrichtenintegrität der Nachricht mithilfe des Schlüssels überprüft, der von bestimmten Objekten abgeleitet wird. Dazu gehört auch ein TURN-Kennwort, das nie als Klartext gesendet wird. Wenn SRTP (Secure Real Time Protocol) verwendet wird, so wird auch der Mediendatenverkehr verschlüsselt.

## Identitätsvortäuschung (Spoofing der IP-Adresse)

*Spoofing* liegt vor, wenn der Angreifer unbefugt die IP-Adresse eines Netzwerks, Computers oder einer Netzwerkkomponente ermittelt und verwendet. Nach einem erfolgreichen Angriff kann sich der Angreifer als die normalerweise durch diese IP-Adresse identifizierte Entität ausgeben. Im Rahmen von Microsoft Lync Server 2013 kommt diese Situation nur vor, wenn der Administrator die folgenden beiden Aktionen unternommen hat:

  - Er hat Verbindungen konfiguriert, die nur TCP (Transmission Control Protocol) unterstützen. (Dies ist nicht zu empfehlen, da die TCP-Kommunikation unverschlüsselt ist.)

  - Er hat die IP-Adressen dieser Verbindungen als vertrauenswürdige Hosts markiert.

Dies ist für TLS-Verbindungen (Transport Layer Security) weniger ein Problem, da TLS alle Parteien authentifiziert und den gesamten Datenverkehr verschlüsselt. Die Verwendung von TLS verhindert Spoofingangriffe auf bestimmte Verbindungen (Mutual-TLS-Verbindungen). Jedoch könnte die Adresse des von Lync Server 2013 verwendeten DNS-Servers durch Spoofing ermittelt werden. Da die Authentifizierung in Lync jedoch mittels Zertifikaten erfolgt, verfügt der Angreifer nicht über ein gültiges Zertifikat, das für das Spoofing für eine der Kommunikationsparteien notwendig ist.

## Man-in-the-Middle-Angriff

Von einem "Man-in-the-Middle-Angriff" spricht man, wenn ein Angreifer die Kommunikation zwischen zwei Benutzern ohne deren Wissen über seinen eigenen Computer leitet. Der Angreifer kann die übertragenen Daten überwachen und lesen, eher er sie an den eigentlichen Empfänger weiterleitet. Jeder der beiden Kommunikationspartner sendet unwissentlich Daten an den Angreifer und empfängt Daten von ihm und ist dabei in dem Glauben, ausschließlich mit der beabsichtigten Person zu kommunizieren. Dies kann passieren, wenn es einem Angreifer gelingt, die Active Directory-Domänendienste so zu ändern, dass sein Server als vertrauenswürdiger Server hinzugefügt wird, oder den DNS-Eintrag (Domain Name System) so zu ändern, dass Clients auf ihrem Weg zum Server über den Computer des Angreifers geleitet werden. Ein Man-in-the-Middle-Angriff kann auch bei Mediendatenverkehr zwischen zwei Clients erfolgen, wobei jedoch in Microsoft Lync Server 2013 Point-to-Point-Audio-, Video- und Anwendungsfreigabe-Datenströme mit dem Secure Real-Time Transport Protocol (SRTP) verschlüsselt werden. Dabei werden kryptografische Schlüssel verwendet, die mit SIP über TLS zwischen den Peers ausgehandelt werden. Server wie Gruppenchat nutzen HTTPS zur Erhöhung der Sicherheit des Webdatenverkehrs.

## Angriff mit Aufzeichnungswiederholung (RTP-Datenverkehr)

Bei einem *Angriff mit Aufzeichnungswiederholung* wird in böswilliger Absicht eine gültige Medienübertragung zwischen zwei Parteien abgefangen und erneut übertragen. Durch die Verwendung von SRTP in Verbindung mit einem sicheren Signalübermittlungsprotokoll werden Übertragungen vor Angriffen mit Aufzeichnungswiederholung geschützt. Mit SRTP kann der Empfänger einen Index der bereits empfangenen RTP-Pakete erstellen und jedes neue Paket mit den bereits enthaltenen vergleichen.

## SPIM (Spam over Instant Messaging)

Unter *SPIM* sind unaufgeforderte Werbe-SMS oder Anwesenheitsabonnementanforderungen zu verstehen. Zwar wird das Netzwerk nicht unmittelbar beeinträchtigt, doch ist SPIM zumindest ärgerlich, kann die Ressourcenverfügbarkeit und die Produktivität reduzieren und möglicherweise zu einer Beeinträchtigung des Netzwerks führen. Ein Beispiel für Spimming sind Benutzer, die sich gegenseitig Anfragen zusenden. Benutzer können sich gegenseitig blockieren, um dies zu verhindern. Ein koordinierter Spimangriff im Partnerverbund kann jedoch schwer abzuwehren sein, wenn Sie den Verbund für den Partner nicht deaktivieren.

## Viren und Würmer

Ein *Virus* ist eine Codeeinheit, deren Zweck darin besteht, zusätzliche, ähnliche Codeeinheiten zu reproduzieren. Für seine Arbeit benötigt der Virus einen Host, wie z. B. eine Datei, eine E-Mail oder ein Programm. Wie ein Virus ist ein *Wurm* ebenfalls eine Codeeinheit, die auf die Reproduktion zusätzlicher, ähnlicher Codeeinheiten programmiert ist. Im Gegensatz zum Virus wird jedoch kein Host benötigt. Viren und Würmer treten vornehmlich bei Dateiübertragungen zwischen Clients auf oder wenn URLs von anderen Benutzern gesendet werden. Befindet sich auf Ihrem Computer ein Virus, kann er beispielsweise Ihre Identität verwenden und Chatnachrichten in Ihrem Namen senden.

## Informationen zur Identifikation von Personen

In Microsoft Lync Server 2013 werden potenziell Informationen über ein öffentliches Netzwerk offengelegt, die u. U. direkt mit einer Person in Zusammenhang gebracht werden können. Bei diesen Informationen kann es sich um zwei Kategorien von Angaben handeln:

  - **Erweiterte Anwesenheitsdaten** Erweiterte Anwesenheitsdaten sind Informationen, die ein Benutzer über einen Link einem Verbundpartner oder Kontakten innerhalb einer Organisation übermitteln kann. Diese Daten werden nicht mit Benutzern in einem öffentlichen Instant Messaging-Netzwerk ausgetauscht. Clientrichtlinien und andere Clientkonfigurationseinstellungen können dem Systemadministrator ein gewisses Maß an Kontrolle über solche personenbezogenen Daten an die Hand geben. In Lync Server 2013 können Sie den Datenschutzmodus für erweiterte Anwesenheitsinformationen für einen einzelnen Benutzer konfigurieren. Damit verhindern Sie, dass Lync-Benutzer, die sich nicht in der Kontaktliste des Benutzers befinden, dessen Anwesenheitsinformationen sehen können. Mit dem Datenschutzmodus für erweiterte Anwesenheitsinformationen können Sie aber nicht verhindern, dass Benutzer von Microsoft Office Communicator 2007 und Microsoft Office Communicator 2007 R2 die Anwesenheitsinformationen eines Benutzers sehen. Weitere Informationen dazu finden Sie unter [Neue Funktionen für Clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) im Dokumentationsabschnitt "Erste Schritte" und unter [Konfigurieren des erweiterten Datenschutzmodus für Anwesenheitsinformationen](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in der Bereitstellungsdokumentation.

  - **Pflichtdaten** Pflichtdaten sind für den ordnungsgemäßen Betrieb des Servers oder Clients erforderlich und unterliegen NICHT der Kontrolle der Client- oder Systemverwaltung. Es handelt sich um Informationen, die auf Server- oder Netzwerkebene für das Routing, die Statuspflege und die Signalübermittlung erforderlich sind.

In den folgenden Tabellen wird angegeben, welche Daten über ein öffentliches Netzwerk offengelegt werden.

### Erweiterte Anwesenheitsdaten

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


### Pflichtdaten

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

