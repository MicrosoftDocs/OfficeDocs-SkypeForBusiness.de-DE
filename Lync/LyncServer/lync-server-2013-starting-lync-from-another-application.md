---
title: 'Lync Server 2013: Starten von lync aus einer anderen Anwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75e7a48645301b6c822eed52ea31e6d4b46019bd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>Starten von lync aus einer anderen Anwendung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-20_

Sie können Befehlszeilenparameter verwenden, um lync 2013 schnell zu starten. Wenn ein Benutzer beispielsweise auf eine Telefonnummer in einer anderen Anwendung klickt, kann die Anwendung eine Instanz von lync 2013 starten und einen Anruf an diese Nummer initiieren.

Lync 2013 können auch eine durch Semikolons getrennte Liste von Kontaktnamen für Mehrparteienkonferenzen erkennen.

Wenn lync 2013 für die automatische Anmeldung beim Start konfiguriert ist, wird beim Starten von lync 2013 mit Befehlszeilenparametern das lync-Hauptfenster geöffnet. Wenn Lync nicht für die automatische Anmeldung beim Starten konfiguriert ist, wird das Anmeldefenster geöffnet.

Die folgende Tabelle zeigt die verfügbaren Parameter.

### <a name="lync-2013-command-line-parameters"></a>Lync 2013 Befehlszeilenparameter

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Erweiterung</th>
<th>Datenformat</th>
<th>Aktion</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel</p></td>
<td><p>Tel-URI</p></td>
<td><p>Öffnet das Fenster "Unterhaltung" für einen Audioanruf, die angegebene Nummer wird jedoch nicht gewählt.</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>"tel:", "sip:" oder Telefon-URI, der eingegeben werden kann</p></td>
<td><p>Öffnet das Fenster "Unterhaltung" für einen Audioanruf, die angegebene Nummer wird jedoch nicht gewählt.</p></td>
</tr>
<tr class="odd">
<td><p>SIP</p></td>
<td><p>SIP-URI</p></td>
<td><p>Öffnet das Fenster "Unterhaltung" mit dem angegebenen SIP-URI (Uniform Resource Identifier) in der Teilnehmerliste.</p></td>
</tr>
<tr class="even">
<td><p>SIPs</p></td>
<td><p>SIP-URI</p></td>
<td><p>Wenn lync 2013 für die Verwendung des TLS-Protokolls (Transport Layer Security) konfiguriert ist, funktioniert genau wie bei SIP:. Wenn TLS nicht verwendet wird, wird der Benutzer in einem Dialogfeld informiert, dass eine höhere Sicherheitsstufe erforderlich ist.</p></td>
</tr>
<tr class="odd">
<td><p>conf</p></td>
<td><p>SIP-URI der Konferenz, an welcher der Benutzer teilnehmen möchte</p></td>
<td><p>Bei Verwendung des URI-Werts "self" wird das Konferenzzustandsobjekt instanziiert, und es wird ausschließlich die Konferenzliste angezeigt. Andernfalls wird die Listenansicht geöffnet, eine INVITE-Anforderung wird jedoch nicht gesendet.</p></td>
</tr>
<tr class="even">
<td><p>Chat</p></td>
<td><p>SIP-URI</p></td>
<td><p>Zeigt ein Fenster "Unterhaltung" mit dem SIP-URI an, in dem ausschließlich Sofortnachrichten gesendet werden können. Akzeptiert mehrere SIP-URIs, die innerhalb von&lt;&gt;spitzen Klammern () ohne Trennzeichen angegeben werden.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle sind Beispiele für diese Befehlszeilenparameter aufgeführt.

### <a name="command-line-parameter-examples"></a>Beispiele für Befehlszeilenparameter

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
<td><p>Öffnet eine Nur-Telefon-Ansicht mit +14255550101.</p></td>
</tr>
<tr class="even">
<td><p>Callto:tel:+ 14255550101</p></td>
<td><p>Öffnet eine Nur-Telefon-Ansicht mit +14255550101.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Öffnet eine Nur-Telefon-Ansicht mit kazuto@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Öffnet ein Fenster "Unterhaltung" mit kazuto@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p>conf: SIP:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Öffnet ein Unterhaltungsfenster und zeigt Besprechungs-audioverknüpfungs Optionen an.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

