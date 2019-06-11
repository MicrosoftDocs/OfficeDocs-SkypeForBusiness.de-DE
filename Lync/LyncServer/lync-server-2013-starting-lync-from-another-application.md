---
title: 'Lync Server 2013: Starten von lync aus einer anderen Anwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e2d28a8083a7e7f1e693ddf55c5cfe3e758e96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>Starten von lync aus einer anderen Anwendung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Sie können Befehlszeilenparameter verwenden, um lync 2013 schnell zu starten. Wenn ein Benutzer beispielsweise in einer anderen Anwendung auf eine Telefonnummer klickt, kann die Anwendung eine Instanz von lync 2013 starten und einen Anruf an diese Nummer initiieren.

Lync 2013 kann auch eine durch Semikolons getrennte Liste der Kontaktnamen für mehrteilige Konferenzen erkennen.

Wenn lync 2013 so konfiguriert ist, dass die Anmeldung beim Start automatisch erfolgt, wird beim Starten von lync 2013 mit Befehlszeilenparametern das lync-Hauptfenster geöffnet. Wenn lync nicht so konfiguriert ist, dass sich beim Start automatisch anmelden, wird das Anmeldefenster geöffnet.

In der folgenden Tabelle sind die verfügbaren Parameter aufgeführt.

### <a name="lync-2013-command-line-parameters"></a>Lync 2013-Befehlszeilenparameter

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Erweiterung</th>
<th>Format der Daten</th>
<th>Aktion</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel</p></td>
<td><p>Tel-URI</p></td>
<td><p>Öffnet das Unterhaltungsfenster für einen Audioanruf, wählt aber nicht die angegebene Nummer.</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>Tel:, SIP: oder Typ Tel-URI</p></td>
<td><p>Öffnet das Unterhaltungsfenster für einen Audioanruf, wählt aber nicht die angegebene Nummer.</p></td>
</tr>
<tr class="odd">
<td><p>SIP</p></td>
<td><p>SIP-URI</p></td>
<td><p>Öffnet das Unterhaltungsfenster mit dem angegebenen SIP-URI (Uniform Resource Identifier) in der Teilnehmerliste.</p></td>
</tr>
<tr class="even">
<td><p>SIPs</p></td>
<td><p>SIP-URI</p></td>
<td><p>Wenn lync 2013 für die Verwendung des TLS-Protokolls (Transport Layer Security) konfiguriert ist, funktioniert genau wie SIP:. Wenn TLS nicht verwendet wird, wird ein Dialogfeld angezeigt, in dem der Benutzer informiert wird, dass eine höhere Sicherheitsstufe erforderlich ist.</p></td>
</tr>
<tr class="odd">
<td><p>conf</p></td>
<td><p>SIP-URI der Konferenz, an der Sie teilnehmen möchten</p></td>
<td><p>Wenn URI selbst ist, wird der Fokus instanziiert, und es wird eine Liste mit nur einer Rost geschützten Ansicht angezeigt. Andernfalls wird die Liste der Teilnehmer angezeigt, aber die Einladung wird nicht gesendet.</p></td>
</tr>
<tr class="even">
<td><p>Chat</p></td>
<td><p>SIP-URI</p></td>
<td><p>Zeigt ein Chat-Fenster mit dem SIP-URI an. Akzeptiert mehrere SIP-URIs, die in Spitze&lt;&gt;Klammern () ohne Trennzeichen angegeben sind.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


Die folgende Tabelle enthält Beispiele für diese Befehlszeilenparameter.

### <a name="command-line-parameter-examples"></a>Beispiele für Befehlszeilen Parameter

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Instanz</th>
<th>Ergebnisse</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel: + 14255550101</p></td>
<td><p>Öffnet eine nur-Telefon-Ansicht mit + 14255550101.</p></td>
</tr>
<tr class="even">
<td><p>Callto: Tel: + 14255550101</p></td>
<td><p>Öffnet eine nur-Telefon-Ansicht mit + 14255550101.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:SIP:Kazuto@litwareinc.com</p></td>
<td><p>Öffnet eine nur-Telefon-Ansicht mit Kazuto@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p>SIP:Kazuto@litwareinc.com</p></td>
<td><p>Öffnet ein Unterhaltungsfenster mit Kazuto@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p>conf: SIP:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Öffnet ein Unterhaltungsfenster und zeigt die Optionen für die Teilnahme an einer Besprechung an.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

