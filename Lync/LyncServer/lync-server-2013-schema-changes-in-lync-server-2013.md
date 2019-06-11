---
title: 'Lync Server 2013: Schema Änderungen in lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bbe1c08b7d03042be2c03511103bfa4e43d39d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a>Schema Änderungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Vor der Bereitstellung und dem Betrieb von lync Server 2013 müssen Sie die Active Directory-Domänendienste vorbereiten, indem Sie das Schema erweitern. Die Schemaerweiterungen fügen die Klassen und Attribute hinzu, die für lync Server 2013 erforderlich sind.

Lync Server 2013 erfordert mehrere neue Klassen und Attribute und ändert einige vorhandene Klassen und Attribute. Darüber hinaus werden viele Konfigurationsinformationen für lync Server 2013 im zentralen Verwaltungsspeicher statt in AD DS gespeichert, wie in früheren Versionen. Die folgenden Informationen werden weiterhin in AD DS in lync Server 2013 gespeichert:

  - **Schema Erweiterungen**:
    
      - Benutzerobjekterweiterungen
    
      - Erweiterungen für Office Communications Server 2007 und Office Communications Server 2007 R2-Klassen zum aufrecht erhalten der Abwärtskompatibilität mit unterstützten vorherigen Versionen

<!-- end list -->

  - **Daten** (im erweiterten lync Server-Schema und in vorhandenen Schemaklassen gespeichert):
    
      - Benutzer SIP Uniform Resource Identifier (URI) und andere Benutzereinstellungen
    
      - Kontaktobjekte für Anwendungen wie Reaktionsgruppe und Konferenzzentrale
    
      - Ein Zeiger auf den zentralen Verwaltungsspeicher
    
      - Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt)

In diesem Thema werden die Active Directory-Schemaänderungen beschrieben, die von lync Server 2013 erforderlich sind. Es werden keine Schemaänderungen beschrieben, die in früheren Versionen von Office Communications Server eingeführt wurden. Eine Liste der Klassen und deren Beschreibungen finden Sie unter [Schema Klassen und Beschreibungen in lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Eine Liste der Attribute und deren Beschreibungen finden Sie unter [Schema Attribute und Beschreibungen in lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Eine Liste der Klassen mit den Attributen, die Sie enthalten können, finden Sie unter [Schema Attribute nach Klasse in lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

Das Attribut msRTCSIP-Präfix identifiziert Klassen und Attribute, die für lync Server spezifisch sind.

<div>

## <a name="new-active-directory-attributes"></a>Neue Active Directory-Attribute

In der folgenden Tabelle werden die Active Directory-Attribute beschrieben, die von lync Server 2013 hinzugefügt werden.

### <a name="attributes-added-by-lync-server-2013"></a>Von lync Server 2013 hinzugefügte Attribute

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
<td><p>Dieses mehrwertige Attribut enthält Bezeichner für für den Benutzer geltende Aufbewahrungsrichtlinien. Aufbewahrungsrichtlinien behalten Postfachelemente für den Benutzer für die Dauer des haltebereichs bei. Dieses Attribut wird für Exchange 2013 freigegeben.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Hierbei handelt es sich um die SIP-Routinggruppen-ID. Benutzer in der gleichen Gruppe werden für denselben Front-End-Server registriert.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Dieses Attribut wird zum Speichern des vom Front-End-Pool verwendeten gespiegelten SQL Server-Back-Ends verwendet.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>Geänderte Active Directory-Klassen

In der folgenden Tabelle werden die Active Directory-Klassen beschrieben, die von lync Server 2013 geändert werden.

### <a name="classes-modified-by-lync-server-2013"></a>Von lync Server 2013 geänderte Klassen

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
<td><p>Add: mayContain</p>
<p>Add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>Attribut msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Kontakt</p></td>
<td><p>Add: mayContain</p>
<p>Add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>Attribut msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>E-Mail-Empfänger</p></td>
<td><p>Add: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Add: mayContain</p></td>
<td><p>Attribut msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

