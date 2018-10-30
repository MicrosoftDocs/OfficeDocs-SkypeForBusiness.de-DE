---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung von E9-1-1'
TOCTitle: Prüfliste zur Bereitstellung von E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398864(v=OCS.15)
ms:contentKeyID: 49295429
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prüfliste zur Bereitstellung von E9-1-1 in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Berücksichtigen Sie bei einer effektiven Planung für erweiterte Notfalldienste (E9-1-1) die folgenden Bereitstellungsanforderungen:

  - Voraussetzungen für die Bereitstellung von E9-1-1

  - Erforderliche Schritte für die Bereitstellung von E9-1-1

## Voraussetzungen für die Bereitstellung von E9-1-1

Bevor Sie E9-1-1 bereitstellen können, müssen Sie die internen Lync Server-Server (einschließlich eines zentraler Verwaltungsspeichers, Front-End-Pools oder Standard Edition-Servers), einen oder mehrere Vermittlungsserver oder Vermittlungsserverpools und Lync Server-Clients bereitstellen. Darüber hinaus erfordert eine E9-1-1-Bereitstellung einen SIP-Trunk zu einem qualifizierten E9-1-1-Dienstanbieter oder ein ELIN-Gateway (Emergency Location Identification Number) zu Ihrem Telefonfestnetz (Public Switched Telephone Network, PSTN). Lync Server unterstützt die Verwendung von E9-1-1-Dienstanbietern nur in den USA.

## Bereitstellungsprozess

Die folgende Tabelle zeigt eine Übersicht über den E9-1-1-Bereitstellungsprozess. Ausführliche Informationen zu den Bereitstellungsschritten finden Sie unter [Konfigurieren von E9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in der Bereitstellungsdokumentation.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Rollen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Konfigurieren von VoIP-Nutzungen, -Routen und Trunkkonfigurationen</p></td>
<td><ol>
<li><p>Erstellen Sie einen neuen PSTN-Verwendungseintrag. Hierbei handelt es sich um den gleichen Namen, der in der Standortrichtlinie für die Einstellung <strong>PSTN-Verwendung</strong> verwendet wird.</p></li>
<li><p>Erstellen Sie eine VoiP-Route, oder weisen Sie dem im vorherigen Schritt erstellten PSTN-Verwendungseintrag eine solche zu, und verweisen Sie das Gatewayattribut auf den E9-1-1-SIP-Trunk oder das ELIN-Gateway.</p></li>
<li><p>Stellen Sie für SIP-Trunk-E9-1-1-Dienstanbieter den Trunk, der E9-1-1-Anrufe über das SIP verwaltet, so ein, dass PIDF-LO-Daten mithilfe des <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>-Cmdlets weitergegeben werden.</p></li>
<li><p>Optional können Sie für SIP-Trunk-E9-1-1-Dienstanbieter eine lokale PSTN-Route für Anrufe erstellen oder zuweisen, die nicht vom SIP-Trunk des E9-1-1-Dienstanbieters verwaltet werden. Diese Route wird verwendet, wenn keine Verbindung zum E9-1-1-Dienstanbieter besteht. Wenn dies von Ihrem E9-1-1-Dienstanbieter unterstützt wird, weisen Sie dem Gateway eine Trunkkonfigurationsregel zu, die die Notrufzeichenfolge in die DID (Direct Inward Dialing)-Nummer des nationalen/regionalen Telefoncenters für Notrufe (Emergency Call Response Center, ECRC) übersetzt.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Konfigurieren einer E9-1-1-VoIP-Route in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Erstellen von Standortrichtlinien und Zuweisen dieser Standortrichtlinien zu Benutzern und Subnetzen</p></td>
<td><ol>
<li><p>Überprüfen Sie die globale Standortrichtlinie.</p></li>
<li><p>Erstellen Sie eine Standortrichtlinie auf Benutzerebene, oder erstellen Sie, wenn die Organisation über mehr als einen Standort mit verschiedenen Notfallverwendungen verfügt, eine Standortrichtlinie auf Netzwerkebene.</p></li>
<li><p>Weisen Sie die Standortrichtlinie zu Netzwerkstandorten zu.</p></li>
<li><p>Fügen Sie dem Netzwerkstandort geeignete Subnetze hinzu.</p></li>
<li><p>(Optional) Weisen Sie die Standortrichtlinie zu Benutzerrichtlinien zu.</p></li>
</ol>
<p></p></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (außer bei Erstellung von Standortrichtlinien)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Erstellen von Ortungsrichtlinien in Lync Server 2013</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Hinzufügen einer Ortungsrichtlinie zu einem Netzwerkstandort in Lync Server 2013</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Zuordnen von Subnetzen zu Netzwerkstandorten für E9-1-1 in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Konfigurieren der Standortdatenbank</p></td>
<td><ol>
<li><p>Füllen Sie die Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten auf.</p></li>
<li><p>Fügen Sie für ELIN-Gateways die ELINs der Spalte &lt;CompanyName&gt; hinzu.</p></li>
<li><p>Konfigurieren Sie für die Verbindung zum E9-1-1-Dienstanbieter die Überprüfung der Adressen.</p></li>
<li><p>Gleichen Sie die Adressen mit dem E9-1-1-Dienstanbieter ab.</p></li>
<li><p>Veröffentlichen Sie die aktualisierte Datenbank.</p></li>
<li><p>Laden Sie für ELIN-Gateways die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hoch.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Konfigurieren der Standortdatenbank in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von erweiterten Funktionen (optional)</p></td>
<td><ol>
<li><p>Konfigurieren Sie die URL für die SNMP-Anwendung.</p></li>
<li><p>Konfigurieren Sie die URL für den sekundären Standortinformationsdienst.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">Konfigurieren einer SNMP-Anwendung in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Konfigurieren eines sekundären Standortinformationsdiensts in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

