---
title: 'Lync Server 2013: ConferenceSessionDetails-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c5aaa3ec022be18ad54cc8a24b8410c23faf799
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>ConferenceSessionDetails-Tabelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Jeder Datensatz stellt eine Konferenzsitzung dar, bei der es sich entweder um die Sitzung mit dem Fokus oder um die Sitzung mit einem bestimmten Konferenzserver handeln kann.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionID</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Uhrzeit der Sitzungsanforderung; wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenzsitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Konferenzsitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> . *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Fokus Konferenz-URI, der sich auf diese Sitzung bezieht. Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> . Dieser URI ist ein Fokus basierter Konferenz-URI.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>Bezeichner, der zwischen Instanzen von wiederkehrenden Konferenzen unterscheidet. Jede wiederkehrende Konferenz Instanz hat dieselbe ConferenceURI, aber einen anderen ConfInstance-Wert.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Konferenzserver-Konferenz-URI, der sich auf diese Sitzung bezieht. Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> . Dieser URI ist der Konferenz-serverbasierte Konferenz-URI. Für Konferenzsitzungen mit Fokus ist diese Spalte NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID eines Benutzers in der Konferenzsitzung. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>Eine GUID zum Identifizieren der Instanz des Endpunkts. Wenn sich ein Benutzer beispielsweise an verschiedenen Computern mit demselben Konto anmeldet, verfügt jeder Computer über eine andere Endpunkt-ID.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Gibt die ID des Benutzers an, der der Anrufer im Auftrag ist. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID des Benutzers, auf den der Anruf verweist. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Vom Konferenzbenutzer verwendete Client Version. Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Client Version, die vom Konferenzserver verwendet wird. Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID-Nummer, die das Dialogfeld identifiziert, das durch die aktuelle Sitzung ersetzt wurde. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung, die durch diese Sitzung ersetzt wird, eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Gibt an, ob die Sitzung vom Konferenz Server gestartet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Gibt an, ob die Sitzung vom Konferenzserver beendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Ob der Benutzer intern angemeldet ist oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Response Code</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>SIP-Antwortcode (Session Initiation Protocol) für die Sitzungseinladung Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-Nr</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Vom SIP-Header erfasste Diagnose-ID.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID des für diese Sitzung verwendeten Front-End-Servers. Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool-Nr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Vermittlungs Server, den der Anruf verwendet. Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Gatewayserver</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Das Gateway, das der Anruf verwendet. Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Edge-Server, den der Anruf verwendet. Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Inhaltstyp, der in der Sitzung verwendet wird. Weitere Informationen finden Sie in der Tabelle "ContentTypes" <a href="lync-server-2013-contenttypes-table.md">in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Einladen</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Der Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</p></td>
</tr>
<tr class="even">
<td><p><strong>Webantworten</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Zeitpunkt der ersten SIP-Antwort. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Der Zeitpunkt, zu dem die Sitzung beendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Fremd</p></td>
<td><p>Enthält den Wert des MCU-URI-Typs aus der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in lync Server 2013</a>. Dieses Feld wird verwendet, um die Abfrageleistung zu verbessern.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Ein Bit-Satz, der die Benutzerattribute angibt. Die folgenden Attributdefinitionen werden aufgelistet:</p>
<ul>
<li><p>Integriert mit dem Desktop-Telefon-1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Ein Bit-Satz, der die anrufattribute angibt. Die folgenden Attributdefinitionen werden aufgelistet:</p>
<ul>
<li><p>Wiederholte Sitzung – 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*Bei den meisten Sitzungen erhält SessionIdSeq den Wert 1. Wenn mehrere Sitzungen genau zur gleichen Zeit beginnen, ist der SessionIdSeq für einen 1, für einen anderen wird 2 usw.

</div>

<span> </span>

</div>

</div>

</div>

