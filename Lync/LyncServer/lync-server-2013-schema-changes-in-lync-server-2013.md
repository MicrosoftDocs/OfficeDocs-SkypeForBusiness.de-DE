---
title: 'Lync Server 2013: Schema Änderungen in lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d70b090f59c0a0f8510d778ef659def77cfd0747
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a>Schema Änderungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Bevor Sie lync Server 2013 bereitstellen und verwenden, müssen Sie Active Directory-Domänendienste durch Erweitern des Schemas vorbereiten. Die Schemaerweiterungen fügen die Klassen und Attribute hinzu, die für lync Server 2013 erforderlich sind.

Lync Server 2013 erfordert mehrere neue Klassen und Attribute und ändert einige vorhandene Klassen und Attribute. Darüber hinaus werden viele Konfigurationsinformationen für lync Server 2013 im zentralen Verwaltungsspeicher statt in AD DS wie in früheren Versionen gespeichert. Die folgenden Informationen werden weiterhin in AD DS in lync Server 2013 gespeichert:

  - **Schemaerweiterungen**:
    
      - Benutzerobjekterweiterungen
    
      - Erweiterungen für Office Communications Server 2007-und Office Communications Server 2007 R2-Klassen zum aufrecht erhalten der Abwärtskompatibilität mit unterstützten Vorgängerversionen

<!-- end list -->

  - **Daten** (in lync Server Extended Schema und in vorhandenen Schemaklassen gespeichert):
    
      - Benutzer-SIP-URI (Uniform Resource Identifier) und weitere Einstellungen
    
      - Kontaktobjekte für Anwendungen wie z. B. Reaktionsgruppe und Konferenzzentrale
    
      - Ein Verweis auf den zentralen Verwaltungsspeicher
    
      - Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)

In diesem Thema werden die von lync Server 2013 erforderlichen Active Directory Schemaänderungen beschrieben. Es werden keine Schemaänderungen beschrieben, die von früheren Versionen von Office Communications Server eingeführt wurden. Eine Liste der Klassen und deren Beschreibungen finden Sie unter [Schema Klassen und Beschreibungen in lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Eine Liste der Attribute und deren Beschreibungen finden Sie unter [Schema Attribute and Descriptions in lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Eine Liste der Klassen mit den Attributen, die Sie enthalten können, finden Sie unter [Schema Attribute by class in lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

Das msRTCSIP-Präfix identifiziert Klassen und Attribute, die spezifisch für lync Server sind.

<div>

## <a name="new-active-directory-attributes"></a>Neue Active Directory-Attribute

In der folgenden Tabelle werden die Active Directory Attribute beschrieben, die von lync Server 2013 hinzugefügt werden.

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
<td><p>Dieses mehrwertige Attribut enthält Bezeichner für Aufbewahrungsrichtlinien, die für den Benutzer gelten. Mit Aufbewahrungsrichtlinien werden für den Benutzer Postfachelemente für die Dauer der Aufbewahrung gespeichert. Dieses Attribut ist für Exchange 2013 freigegeben.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Dies ist die SIP-Routinggruppen-ID. Benutzer in derselben Gruppe registrieren sich beim selben Front-End-Server.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Dieses Attribut wird verwendet, um das vom Front-End-Pool verwendete gespiegelte SQL Server-Back-End zu speichern.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>Geänderte Active Directory-Klassen

In der folgenden Tabelle werden die Active Directory Klassen beschrieben, die von lync Server 2013 geändert wurden.

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
<td><p>Benutzer</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Kontakt</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>add: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Hinzugefügt: mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

