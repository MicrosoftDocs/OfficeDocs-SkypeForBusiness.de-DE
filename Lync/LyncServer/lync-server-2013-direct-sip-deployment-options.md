---
title: 'Lync Server 2013: Optionen für Bereitstellungen mit direkten SIP-Verbindungen'
TOCTitle: Optionen für Bereitstellungen mit direkten SIP-Verbindungen
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398672(v=OCS.15)
ms:contentKeyID: 49294618
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Optionen für Bereitstellungen mit direkten SIP-Verbindungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Dieses Thema umfasst Beispieltopologien für die Bereitstellung direkter SIP-Verbindungen.

## Eigenständiger Lync Server

Wenn in Ihrer Organisation eine der in diesem Abschnitt beschriebenen Bereitstellungen verwendet wird, können Sie die Lync Server 2013 als einzige Telefonielösung für einen Teil oder eine gesamte Organisation nutzen. In diesem Abschnitt werden die folgenden Bereitstellungen ausführlich beschrieben:

  - **Inkrementelle Bereitstellung:** bei dieser Option wird davon ausgegangen, dass Sie über eine vorhandene Infrastruktur mit Nebenstellenanlage (Private Branch Exchange, PBX) verfügen und Enterprise-VoIP schrittweise für kleinere Gruppen oder Teams innerhalb Ihrer Organisation einführen möchten.

  - **Ausschließliche Bereitstellung von Lync Server-VoIP-Funktionen:** Bei dieser Option wird davon ausgegangen, dass Sie die Bereitstellung von Enterprise-VoIP an einem Standort in Betracht ziehen, an dem keine herkömmliche Telefonieinfrastruktur vorhanden ist.

## Inkrementelle Bereitstellung

Bei der inkrementellen Bereitstellung fungiert Lync Server 2013 als alleinige Telefonielösung für einzelne Teams oder Abteilungen, während die übrigen Benutzer der Organisation weiterhin eine Nebenstellenanlage verwenden. Diese inkrementelle Bereitstellungsstrategie bietet eine Möglichkeit, die IP-Telefonie anhand kontrollierter Pilotprogramme in Ihrem Unternehmen einzuführen. Die Arbeitsgruppen, deren Kommunikationsanforderungen am besten mit Microsoft Unified Communications erfüllt werden, werden zu Enterprise-VoIP migriert, während andere Benutzer weiterhin die vorhandene Nebenstellenanlage verwenden. Im Laufe der Zeit können ggf. weitere Arbeitsgruppen zu Enterprise-VoIP migriert werden.

Die inkrementelle Bereitstellung wird empfohlen, wenn Sie über eindeutig definierte Benutzergruppen verfügen, die gemeinsame Kommunikationsanforderungen aufweisen und für eine zentrale Verwaltung geeignet sind. Außerdem ist diese Option für Teams oder Abteilungen effektiv, die geografisch weit verteilt sind, sodass deutliche Einsparungen bei den Kosten für Ferngespräche erzielt werden können. Diese Option ist hilfreich für virtuelle Teams, deren Mitglieder möglicherweise weltweit verteilt sind. Sie können solche Teams gemäß wechselnden Unternehmensanforderungen schnell zusammenstellen, ändern oder auflösen.

Die folgende Abbildung zeigt die allgemeine Topologie für die Bereitstellung von Enterprise-VoIP hinter einer Nebenstellenanlage. Diese Topologie wird für die inkrementelle Bereitstellung empfohlen.

**Inkrementelle Bereitstellung**

![Abteilungsbezogene Migrationsoption (Diagramm)](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Abteilungsbezogene Migrationsoption (Diagramm)")


> [!NOTE]
> Wenn Sie Ihre Lync Server-Bereitstellung mit einem zertifizierten Partner für direkte SIP-Verbindungen verbinden, ist kein PSTN-Gateway zwischen dem Vermittlungsserver und der Nebenstellenanlage erforderlich. Eine Liste mit zertifizierten Partnern für direkte SIP-Verbindungen finden Sie auf der Website für das Microsoft Unified Communications Open Interoperability Program unter <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.




> [!NOTE]
> Für den in dieser Abbildung gezeigten Medienpfad wurde die Medienumgehung aktiviert (empfohlene Konfiguration). Wenn Sie die Medienumgehung deaktivieren, wird der Medienpfad durch den Vermittlungsserver geleitet.



In dieser Topologie werden ausgewählte Abteilungen oder Arbeitsgruppen für Enterprise-VoIP aktiviert. Die VoIP-Arbeitsgruppe wird über ein PSTN-Gateway mit der Nebenstellenanlage verbunden. Die für Enterprise-VoIP aktivierten Benutzer - Remotemitarbeiter eingeschlossen - kommunizieren über ein IP-Netzwerk miteinander. Anrufe von Enterprise-VoIP-Benutzern bei PSTN-Telefonen oder bei Mitarbeitern, die nicht für Enterprise-VoIP aktiviert sind, werden an das entsprechende PSTN-Gateway weitergeleitet. Anrufe von Mitarbeitern, die noch die Nebenstellenanlage verwenden, oder von Anrufern im Telefonfestnetz werden an das PSTN-Gateway gesendet und von dort zum Routing an Lync Server weitergeleitet.

Für die Verbindung von Enterprise-VoIP mit einer vorhandenen Nebenstellenanlageninfrastruktur werden zwei Konfigurationen empfohlen, um Interoperabilität sicherzustellen: Enterprise-VoIP hinter der Nebenstellenanlage und Enterprise-VoIP vor der Nebenstellenanlage.

## Enterprise-VoIP hinter der Nebenstellenanlage

Wenn Enterprise-VoIP hinter der Nebenstellenanlage bereitgestellt wird, werden alle Anrufe aus dem Festnetz an der Nebenstellenanlage empfangen, die Anrufe an Enterprise-VoIP-Benutzer an ein PSTN-Gateway und Anrufe an Nebenstellenanlagenbenutzer an die Nebenstellenanlage weiterleitet.

## Enterprise-VoIP vor der Nebenstellenanlage

Wenn Enterprise-VoIP vor der Nebenstellenanlage bereitgestellt wird, werden alle Anrufe am PSTN-Gateway empfangen, das Anrufe für Enterprise-VoIP-Benutzer an Lync Server und Anrufe für Nebenstellenanlagenbenutzer an die Nebenstellenanlage weiterleitet. Anrufe an das Telefonfestnetz von Benutzern mit Enterprise-VoIP und von Benutzern der Nebenstellenanlage werden über das IP-Netzwerk an das kosteneffizienteste PSTN-Gateway weitergeleitet. In der folgenden Tabelle werden die Vor- und Nachteile dieser Konfiguration dargestellt.

### Vor- und Nachteile der Bereitstellung von Enterprise-VoIP vor einer Nebenstellenanlage

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Vorteile</th>
<th>Nachteile</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Die Nebenstellenanlage bedient weiterhin die Benutzer, die nicht für Enterprise-VoIP aktiviert sind.</p></td>
<td><p>Die vorhandenen Gateways unterstützen möglicherweise die gewünschten Funktionen oder Kapazitäten nicht.</p></td>
</tr>
<tr class="even">
<td><p>Die Nebenstellenanlage steuert alle älteren Geräte.</p></td>
<td><p>Notwendigkeit eines Trunks vom Gateway zur Nebenstellenanlage und vom Gateway zum Vermittlungsserver. Möglicherweise benötigen Sie weitere Trunks vom Dienstanbieter.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise-VoIP-Benutzer behalten ihre Rufnummern.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


## Ausschließliche Bereitstellung von Lync Server-VoIP-Funktionen

Enterprise-VoIP ermöglicht neuen Unternehmen sowie bestehenden Unternehmen mit neuen Niederlassungen die Implementierung einer VoIP-Lösung mit vollem Funktionsumfang, ohne dabei die Integration einer Nebenstellenanlage berücksichtigen oder die erheblichen Kosten für Bereitstellung und Betrieb einer Infrastruktur mit IP-Nebenstellenanlage tragen zu müssen. Diese Lösung unterstützt sowohl Mitarbeiter am Standort als auch Remotemitarbeiter.

In dieser Bereitstellung werden die Anrufe über das IP-Netzwerk weitergeleitet. Anrufe an das Festnetz werden an das entsprechende PSTN-Gateway weitergeleitet. Lync 2013 oder Lync Phone Edition werden als Softphones eingesetzt. Die Remoteanrufsteuerung ist nicht verfügbar und nicht erforderlich, da keine Nebenstellentelefone für Benutzer gesteuert werden müssen. Voicemail und eine automatische Telefonzentrale sind optional über Exchange Unified Messaging (UM) verfügbar.


> [!NOTE]
> Zusätzlich zur Netzwerkinfrastruktur, die zur Unterstützung von Lync Server 2013 erforderlich ist, kann bei ausschließlicher Bereitstellung von VoIP-Funktionen ein kleines, qualifiziertes Gateway zur Unterstützung von Fax- und analogen Geräten verwendet werden.



In der folgenden Abbildung wird eine typische Topologie für die ausschließliche Bereitstellung von VoIP-Funktionen dargestellt.

**Ausschließliche Bereitstellung von VoIP-Funktionen**

![Greenfidle-Bereitstellungsoption](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle-Bereitstellungsoption")


> [!NOTE]
> Für den in dieser Abbildung gezeigten Medienpfad wurde die Medienumgehung aktiviert (empfohlene Konfiguration). Wenn Sie die Medienumgehung deaktivieren, wird der Medienpfad durch den Vermittlungsserver geleitet.


