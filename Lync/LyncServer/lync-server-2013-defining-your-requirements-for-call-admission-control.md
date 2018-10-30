---
title: 'Lync Server 2013: Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung'
TOCTitle: Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398334(v=OCS.15)
ms:contentKeyID: 49293993
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Zur Planung der Anrufsteuerung (Call Admission Control, CAC) sind detaillierte Informationen zur Netzwerktopologie Ihres Unternehmens erforderlich. Führen Sie die folgenden Schritte aus, um Richtlinien für die Anrufsteuerung zu planen.

1.  Identifizieren Sie die Hubs/Backbones (als *Netzwerkregionen* bezeichnet) in Ihrem Unternehmensnetzwerk.

2.  Identifizieren Sie die Niederlassungen oder Standorte (als *Netzwerkstandorte* bezeichnet) innerhalb jeder Netzwerkregion.

3.  Definieren Sie eine Netzwerkroute zwischen jedem Netzwerkregionenpaar.

4.  Ermitteln Sie die Bandbreiteneinschränkungen für jede WAN-Verbindung.
    

    > [!NOTE]
    > Die Bandbreiteneinschränkungen beziehen sich darauf, wie viel Bandbreite einer WAN-Verbindung für Enterprise-VoIP und Audio/Video-Datenverkehr reserviert wird. Wenn eine WAN-Verbindung als eine Verbindung mit "Bandbreiteneinschränkungen" beschrieben wird, liegt die Bandbreitengrenze der WAN-Verbindung unter dem erwarteten Spitzendatenverkehr über diese Verbindung.



5.  Identifizieren Sie die IP-Subnetze, die jedem Netzwerkstandort zugewiesen sind.

Zur Erläuterung dieser Konzepte wird die in der folgenden Abbildung dargestellte Beispielnetzwerktopologie herangezogen.

**Beispieltopologie für die Anrufsteuerung**

![Litware Inc.: Netzwerktopologiebeispiel](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc.: Netzwerktopologiebeispiel")


> [!NOTE]
> Alle Netzwerkstandorte sind einer Netzwerkregion zugeordnet. Beispielsweise sind die Standorte "Portland", "Reno" und "Albuquerque" in der Region "Nordamerika" enthalten. In dieser Abbildung werden nur WAN-Verbindungen mit Bandbreiteneinschränkungen gezeigt, auf die Anrufsteuerungsrichtlinien angewendet werden. Die Netzwerkstandorte&nbsp;"Chicago", "New York" und "Detroit" werden innerhalb des Regionenovals "Nordamerika" angezeigt, da sie keine Bandbreiteneinschränkungen aufweisen und für diese Standorte daher keine Richtlinien für die Anrufsteuerung erforderlich sind.



Die Komponenten in dieser Beispieltopologie werden in den folgenden Abschnitten erläutert. Ausführliche Informationen zur Planung dieser Topologie, einschließlich der Bandbreiteneinschränkungen, finden Sie unter [Beispiel: Zusammenstellen der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).

## Identifizieren der Netzwerkregionen

Eine Netzwerkregion repräsentiert einen Netzwerkbackbone oder einen Netzwerkhub.

Ein Netzwerkbackbone oder Hub ist Bestandteil der Computernetzwerkinfrastruktur, die verschiedene Komponenten im Netzwerk verbindet und einen Pfad für den Austausch von Informationen zwischen unterschiedlichen LANs oder Subnetzen bereitstellt. Ein Backbone kann unterschiedliche Netzwerke miteinander verknüpfen, von kleinen Standorten bis hin zu einem geografisch weit verteilten Bereich. Die Kapazität des Backbones ist in der Regel höher als die der Netzwerke, die mit ihm verbunden sind.

Die hier vorgestellte Beispieltopologie umfasst drei Netzwerkregionen: Nordamerika, EMEA und APAC. Eine Netzwerkregion enthält eine Reihe von Netzwerkstandorten (siehe Definition in diesem Thema). Arbeiten Sie mit dem Team für den Netzwerkbetrieb zusammen, um die verwendeten Netzwerkregionen zu identifizieren.

## Zuordnen eines zentralen Standorts zu jeder Netzwerkregion

Die Anrufsteuerung erfordert, dass jeder Netzwerkregion ein zentraler Lync Server-Standort zugeordnet ist. Ausgewählt wird der zentrale Standort, der die beste Netzwerkverbindung und die höchste Bandbreite aller Standorte in dieser Netzwerkregion bietet. In der oben gezeigten beispielhaften Netzwerktopologie sind drei Netzwerkregionen aufgeführt, jede mit einem zentralen Standort zur Verwaltung der Entscheidungen im Rahmen der Anrufsteuerung. Die geeignete Zuordnung für das vorangehende Beispiel wird in der folgenden Tabelle gezeigt.


> [!NOTE]
> Die zentralen Standorte müssen nicht den Netzwerkstandorten entsprechen. In den Beispielen in dieser Dokumentation stimmen die Namen einiger zentraler Standorte – Chicago, London und Peking – mit den Namen von Netzwerkstandorten überein. Doch selbst wenn ein zentraler Standort und ein Netzwerkstandort denselben Namen aufweisen, ist der zentrale Standort ein Element der Lync Server-Topologie. Der Netzwerkstandort hingegen ist Teil des Gesamtnetzwerks, in dem die Lync Server-Topologie definiert wurde.



### Netzwerkregionen, zentrale Standorte und Netzwerkstandorte

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Netzwerkregion</th>
<th>Zentraler Standort</th>
<th>Netzwerkstandorte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nordamerika</p></td>
<td><p>Chicago</p></td>
<td><p>Chicago</p>
<p>New York</p>
<p>Detroit</p>
<p>Portland</p>
<p>Reno</p>
<p>Albuquerque</p></td>
</tr>
<tr class="even">
<td><p>EMEA</p></td>
<td><p>London</p></td>
<td><p>London</p>
<p>Köln</p></td>
</tr>
<tr class="odd">
<td><p>APAC</p></td>
<td><p>Peking</p></td>
<td><p>Peking</p>
<p>Manila</p></td>
</tr>
</tbody>
</table>


## Identifizieren von Netzwerkstandorten

Ein Netzwerkstandort repräsentiert einen Ort, an dem Ihre Organisation über Büros, einen Gebäudekomplex oder ein Gelände verfügt. Ein physischer Standort mit einem LAN und einer WAN-Verbindung zu anderen Standorten wird als Netzwerkstandort klassifiziert. Beginnen Sie damit, alle Büros Ihrer Organisation zu erfassen. In der verwendeten Beispieltopologie umfasst die Netzwerkregion "Nordamerika" die folgenden Netzwerkstandorte: New York, Chicago, Detroit, Portland, Reno und Albuquerque.

Sie müssen jeden Netzwerkstandort einer Netzwerkregion zuordnen. Abhängig davon, ob der Netzwerkstandort über eine eingeschränkte WAN-Verbindung verfügt oder nicht, wird dem Netzwerkstandort eine Bandbreitenrichtlinie zugeordnet. Ausführliche Informationen zu Anrufsteuerungsrichtlinien und der Bandbreite, die Sie über die Richtlinienverwendung zuweisen, finden Sie im Abschnitt "Definieren von Bandbreitenrichtlinien" weiter unten in diesem Thema. Zum Konfigurieren der Anrufsteuerung ordnen Sie Netzwerkstandorte Netzwerkregionen zu. Anschließend erstellen Sie Richtlinien zur Bandbreitenzuweisung, die auf Verbindungen mit Bandbreiteneinschränkungen zwischen einem Standort oder einer Region und die WAN-Verbindungen zwischen den Standorten und Regionen angewendet werden.

## Identifizieren von Netzwerkverbindungen

Netzwerkverbindungen repräsentieren Verbindungen zum physischen WAN, das unterschiedliche Regionen und Standorte verknüpft. In der Beispieltopologie sind zwei regionale Netzwerkverbindungen enthalten, fünf Netzwerkverbindungen zwischen Regionen und Standorten und eine Netzwerkverbindung zwischen zwei Standorten.

Die zwei regionalen Verbindungen befinden sich zwischen "Nordamerika" und "EMEA", dargestellt als "NA-EMEA-LINK", und zwischen "APAC" und "EMEA", dargestellt als "EMEA-APAC-LINK".

Die Standortverbindungen kennzeichnen die Leitungen zur Verbindung von "Portland", "Reno" und "Albuquerque" mit der Region "Nordamerika", zur Verbindung von "Manila" mit der Region "APAC" und zur Verbindung von "Köln" mit der Region "EMEA". Die Verbindung zwischen "Reno" und "Albuquerque" kennzeichnet eine direkte Netzwerkverbindung zwischen diesen zwei Standorten.

## Definieren von Bandbreitenrichtlinien

Arbeiten Sie mit dem Team für den Netzwerkbetrieb zusammen, um die verfügbare WAN-Bandbreite für in Echtzeit übertragenen Audio- und Videodatenverkehr über die WAN-Verbindungen in Ihrer Organisation zu ermitteln. Bandbreitenrichtlinien werden üblicherweise auf WAN-Verbindungen angewendet, wenn die Bandbreite eingeschränkt ist, wenn also der erwartete Datenverkehr die Bandbreite übersteigt, die für Audio- und Videodaten zugewiesen werden kann.

*Bandbreitenrichtlinien* für die Anrufsteuerung definieren, wie viel Bandbreite für in Echtzeit übertragene Audio- und Videodaten reserviert ist. Da die Bandbreite für anderen Datenverkehr bei der Anrufsteuerung nicht begrenzt wird, kann nicht verhindert werden, dass dieser die gesamte Netzwerkbandbreite durch Aktionen wie das Übertragen großer Dateien oder das Streamen von Musik beansprucht.

Bandbreitenrichtlinien für die Anrufsteuerung können einige oder alle der folgenden Werte definieren:

  - Maximal reservierte Gesamtbandbreite für Audiodaten

  - Maximal reservierte Gesamtbandbreite für Videodaten

  - Maximal reservierte Bandbreite für einen einzelnen Audioanruf (Sitzung)

  - Maximal reservierte Bandbreite für einen einzelnen Videoanruf (Sitzung)


> [!NOTE]
> Alle Bandbreitenwerte für die Anrufsteuerung stellen Maximalwerte für die <EM>unidirektionale</EM> Bandbreitenbeschränkung dar.




> [!NOTE]
> Die Lync Server 2013-Features für VoIP-Richtlinien bieten die Möglichkeit, Bandbreitenrichtlinienüberprüfungen für eingehende Anrufe beim Benutzer außer Kraft zu setzen (dies ist für vom Benutzer getätigte ausgehende Anrufe nicht möglich). Nachdem die Sitzung eingerichtet wurde, wird die Bandbreitenauslastung genau berechnet. Diese Einstellung sollte mit Bedacht verwendet werden. Ausführliche Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013</A> oder <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013</A>.



Zur Optimierung der Bandbreitenauslastung auf Sitzungsebene sollten Sie sich Gedanken über die verwendeten Audio- und Videocodecs machen. Vermeiden Sie insbesondere eine zu geringe Bandbreitenzuweisung für einen Codec, der erwartungsgemäß häufig verwendet wird. Umgekehrt sollten Sie die maximale Bandbreite pro Sitzung sehr niedrig ansetzen, wenn Sie verhindern möchten, dass für Mediendaten ein Codec mit hohen Bandbreitenanforderungen verwendet wird. Für Audiodaten ist nicht jeder Codec für jedes Szenario verfügbar. Beispiel:

  - Peer-zu-Peer-Audioanrufe zwischen Lync-Endpunkten verwenden entweder RTAudio (8 KHz) oder RTAudio (16 KHz), wenn Sie die Bandbreite und Priorisierung von Codecs berücksichtigen.

  - Konferenzanrufe zwischen Lync-Endpunkten und dem A/V-Konferenzdienst verwenden entweder G.722 oder Siren.

  - PSTN-Anrufe zu oder von Lync-Endpunkten verwenden entweder G.711 oder RTAudio (8 KHz).

Verwenden Sie die folgende Tabelle, um die maximalen Bandbreiteneinstellungen pro Sitzung zu optimieren.

### Bandbreitenauslastung nach Codec

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Codec</th>
<th>Bandbreitenanforderung ohne Vorwärtsfehlerkorrektur (Forward Error Correction, FEC)</th>
<th>Bandbreitenanforderung mit Vorwärtsfehlerkorrektur (Forward Error Correction, FEC)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio (8 KHz)</p></td>
<td><p>49,8 KBit/s</p></td>
<td><p>61,6 KBit/s</p></td>
</tr>
<tr class="even">
<td><p>RTAudio (16 KHz)</p></td>
<td><p>67 KBit/s</p></td>
<td><p>96 KBit/s</p></td>
</tr>
<tr class="odd">
<td><p>Siren</p></td>
<td><p>57,6 KBit/s</p></td>
<td><p>73,6 KBit/s</p></td>
</tr>
<tr class="even">
<td><p>G0,711</p></td>
<td><p>102 KBit/s</p></td>
<td><p>166 KBit/s</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>105,6 KBit/s</p></td>
<td><p>169,6 KBit/s</p></td>
</tr>
<tr class="even">
<td><p>RTVideo (CIF mit 15 F/s)</p></td>
<td><p>260 KBit/s</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo (VGA mit 30 F/s)</p></td>
<td><p>610 KBit/s</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Bandbreitenanforderungen berücksichtigen einen Overhead für: Ethernet II, IP, User Datagram Protocol (UDP), RTP (Real-Time Transport Protocol) und SRTP (Secure Real-Time Transport Protocol). Ebenfalls enthalten ist ein Overhead von 10&nbsp;KBit/s für RTCP.



Die Codecs G.722.1 und Siren sind ähnlich, unterscheiden sich jedoch in den Bitraten.

G.722, der Standardcodec für Lync Server-Konferenzen, unterscheidet sich grundlegend von den Codecs G.722.1 und Siren.

Der Siren-Codec wird in Lync Server in den folgenden Situationen verwendet:

  - Wenn die Bandbreitenrichtlinie zu niedrig festgelegt ist, um eine Verwendung von G.722 zuzulassen

  - Wenn ein Communications Server 2007- oder Communications Server 2007 R2-Client eine Verbindung mit einem Lync Server-Konferenzdienst herstellt (diese Clients bieten keine Unterstützung für den G.722-Codec)

### Bandbreitenauslastung nach Szenario

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Szenario</th>
<th>Bandbreitenanforderung für Menge optimiert (KBit/s)</th>
<th>Bandbreitenanforderung für Ausgleichsmodus optimiert (KBit/s)</th>
<th>Bandbreitenanforderung für Qualität optimiert (KBit/s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Peer-zu-Peer-Audioanrufe</p></td>
<td><p>45 KBit/s</p></td>
<td><p>62 KBit/s</p></td>
<td><p>91 KBit/s</p></td>
</tr>
<tr class="even">
<td><p>Telefonkonferenz</p></td>
<td><p>53 KBit/s</p></td>
<td><p>101 KBit/s</p></td>
<td><p>165 KBit/s</p></td>
</tr>
<tr class="odd">
<td><p>PSTN-Anrufe (zwischen Lync 2013 und PSTN-Gateway, mit Medienumgehung)</p></td>
<td><p>97 KBit/s</p></td>
<td><p>97 KBit/s</p></td>
<td><p>161 KBit/s</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Anrufe (zwischen Lync 2013 und Vermittlungsserver, ohne Medienumgehung)</p></td>
<td><p>45 KBit/s</p></td>
<td><p>97 KBit/s</p></td>
<td><p>161 KBit/s</p></td>
</tr>
<tr class="odd">
<td><p>PSTN-Anrufe (zwischen Vermittlungsserver und PSTN-Gateway, ohne Medienumgehung)</p></td>
<td><p>97 KBit/s</p></td>
<td><p>97 KBit/s</p></td>
<td><p>161 KBit/s</p></td>
</tr>
<tr class="even">
<td><p>Lync - Polycom-Anrufe</p></td>
<td><p>101 KBit/s</p></td>
<td><p>101 KBit/s</p></td>
<td><p>101 KBit/s</p></td>
</tr>
</tbody>
</table>


## Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Im hier verwendeten Beispiel sind dem Standort "New York" in der Region "Nordamerika" die folgenden IP-Subnetze zugewiesen: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Angenommen, der Benutzer Bob, der üblicherweise in Detroit arbeitet, reist für eine Schulung in das New Yorker Büro. Wenn er seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für "New York" reserviert sind, beispielsweise die Adresse 172.29.80.103.


> [!WARNING]
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Ein Lync-Client maskiert die lokale IP-Adresse mit der zugeordneten Subnetzmaske. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die Anrufsteuerung bereitstellen, jedoch keine Medienumgehung verwenden, funktioniert die Anrufsteuerung selbst dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.)<BR>Wenn sich ein Benutzer beispielsweise an einem Computer mit der IP-Adresse 172.29.81.57 und der IP-Subnetzmaske 255.255.255.0 anmeldet, fordert Lync 2013 die Umgehungs-ID an, die dem Subnetz 172.29.81.0 zugeordnet ist. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies \endash wenngleich der Client dem virtuellen Subnetz angehört \endash nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Daher ist es wichtig, dass der Administrator Subnetze genau wie von Lync-Clients (bereitgestellt mit den Subnetzen während der Netzwerkkonfiguration, entweder als statische Konfiguration oder über DHCP) angegeben eingibt.


