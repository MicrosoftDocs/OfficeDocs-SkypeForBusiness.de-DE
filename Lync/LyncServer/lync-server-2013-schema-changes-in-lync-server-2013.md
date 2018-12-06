---
title: Schemaänderungen in Lync Server 2013
TOCTitle: Schemaänderungen in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398944(v=OCS.15)
ms:contentKeyID: 49295562
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Schemaänderungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Vor der Bereitstellung und Ausführung von Lync Server 2013 müssen Sie die Vorbereitung von Active Directory-Domänendienste ausführen, indem Sie das Schema erweitern. Durch die Schemaerweiterungen werden die Klassen und Attribute hinzugefügt, die für Lync Server 2013 erforderlich sind.

In Lync Server 2013 werden verschiedene neue Klassen und Attribute benötigt und einige vorhandene Klassen und Attribute geändert. Darüber hinaus verwendet Lync Server 2013 zum Speichern eines Großteils der Konfigurationsinformationen nicht mehr wie vorherige Versionen AD DS, sondern den zentralen Verwaltungsspeicher. Folgende Informationen werden in Lync Server 2013 weiterhin in AD DS gespeichert:

  - **Schemaerweiterungen**:
    
      - Benutzerobjekterweiterungen
    
      - Erweiterungen für Office Communications Server 2007- und Office Communications Server 2007 R2-Klassen zur Abwärtskompatibilität mit unterstützten Vorgängerversionen

<!-- end list -->

  - **Daten** (werden im erweiterten Lync Server-Schema und in vorhandenen Schemaklassen gespeichert):
    
      - Benutzer-SIP-URI (Uniform Resource Identifier) und weitere Einstellungen
    
      - Kontaktobjekte für Anwendungen wie z. B. Reaktionsgruppe und Konferenzzentrale
    
      - Verweis auf zentralen Verwaltungsspeicher
    
      - Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)

In diesem Thema werden die in Lync Server 2013 erforderlichen Active Directory-Schemaänderungen beschrieben. Die Schemaänderungen in früheren Versionen von Office Communications Server werden hier nicht erläutert. Eine Liste der Klassen und die zugehörigen Beschreibungen finden Sie unter [Schemaklassen und Beschreibungen in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Eine Liste der Attribute und die zugehörigen Beschreibungen finden Sie unter [Schemaattribute und Beschreibungen in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Eine Liste der Klassen mit den Attributen, die diese enthalten können, finden Sie unter [Schemaattribute nach Klasse in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

Das Präfix "msRTCSIP" identifiziert die für Lync Server spezifischen Klassen und Attribute.

## Neue Active Directory-Attribute

In der folgenden Tabelle werden die Active Directory-Attribute beschrieben, die in Lync Server 2013 hinzugefügt wurden.

### In Lync Server 2013 hinzugefügte Attribute

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Dieses mehrwertige Attribut enthält Bezeichner für Aufbewahrungsrichtlinien, die für den Benutzer gelten. Mit Aufbewahrungsrichtlinien werden für den Benutzer Postfachelemente für die Dauer der Aufbewahrung gespeichert. Dieses Attribut wird gemeinsam mit Exchange 2013 verwendet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Dies ist die SIP-Routinggruppen-ID. Benutzer in derselben Gruppe registrieren sich beim selben Front-End-Server.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Mit diesem Attribut wird das gespiegelte SQL Server-Back-End gespeichert, das vom Front-End-Pool verwendet wird.</p></td>
</tr>
</tbody>
</table>


## Geänderte Active Directory-Klassen

In der folgenden Tabelle werden die Active Directory-Klassen beschrieben, die in Lync Server 2013 geändert wurden.

### In Lync Server 2013 geänderte Klassen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Klasse</th>
<th>Änderung</th>
<th>Klasse oder Attribut</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>User</p></td>
<td><p>Hinzugefügt: mayContain</p>
<p>Hinzugefügt: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Contact</p></td>
<td><p>Hinzugefügt: mayContain</p>
<p>Hinzugefügt: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>Hinzugefügt: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Hinzugefügt: mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>

