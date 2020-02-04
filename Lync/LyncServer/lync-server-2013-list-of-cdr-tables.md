---
title: 'Lync Server 2013: Liste der CDR-Tabellen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0c620eaf6b54a89604071a18f445d20816178bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Liste der CDR-Tabellen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Das Datenbankschema für die Anrufdetailaufzeichnung (CDR) besteht aus den folgenden Tabellen.

<div>

## <a name="static-tables"></a>Statische Tabellen


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">CallPriorities-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Liste möglicher Anruf Prioritäten wie Notfall, dringend, normal, nicht dringend und mehr.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert die Klassifizierungs Grenzen, die vom Zusammenfassungsbericht zur Konferenzteilnahme verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">DeRegisterType-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert &quot;die Liste der möglichen Benutzer Deregistrierungs Gründe, wie Client initiiert,&quot; &quot;Registrierung abgelaufen&quot; &quot;, Client Absturz&quot; und vieles mehr.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">MediaList-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Liste der Medientypen, die Einträge in der Datenbank generieren können (beispielsweise Chat, Audio, Video und Dateiübertragung).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">PurgeSettings-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen, die angeben, ob (und wann) veraltete Anruf Detaildatensätze automatisch aus der CDR-Datenbank gelöscht werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Roles-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Liste möglicher Konferenz Rollen (beispielsweise Teilnehmer und Referenten).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der SIP-Antwortcodes sowie die Klassifizierung und Definition der einzelnen Codes.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>Unterstützende Tabellen


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">ClientVersions-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Clients (Clienttyp und Versionsnummer) jedes an einem Anruf beteiligten Clients mit Informationen, die in dieser Datenbank erfasst werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der ConferenceURIs, die in konferenzbezogenen Anrufen verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">ContentTypes-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert eine Liste von SIP-Inhaltstypen (Session Initiation Protocol), die sowohl in Peer-to-Peer-Anrufen als auch in Konferenzgesprächen verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Devices-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert eine Liste von Geräten, einschließlich deren Hersteller, Hardware Version und Mac-Adresse.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen über die Dialog Feld-ID für jede Sitzung in der Datenbank.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">EdgeServers-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der Edgeserver, die für externe Anrufe verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Gateways-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der Gateways, die für VoIP-Anrufe (Voice over Internet Protocol) verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der Hardware Versionen von Geräten (Tischtelefon).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Manufacturers-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der Hersteller von Geräten (Tischtelefon).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Mcus-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu den verschiedenen A/V-Konferenzservern und deren URIs.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">MediationServers-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der Vermittlungsserver, die für VoIP-Anrufe verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Phones-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert alle Telefonnummern, die in VoIP-Anrufen verwendet werden, die archiviert wurden oder deren Anrufdetails aufgezeichnet wurden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Pools-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Namen des Pools, in dem Chatnachrichten erfasst werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Servers-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert den Namen der an den anrufen beteiligten Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Mandanten, die von der aktuellen Bereitstellung unterstützt werden. Es gibt einige integrierte Mandanten für Enterprise-Benutzer, Federated-Benutzer, öffentliche Chat-Konnektivitäts-Benutzer und anonyme Benutzer.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle in lync Server 2013</a></p></td>
<td><p>Ordnet die Bezeichner des Benutzer-Agents den beschreibenden Namen des Agents zu.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert die Benutzer-URIs von Benutzern, die an Sitzungen teilgenommen haben, die in dieser Datenbank aufgezeichnet oder archiviert wurden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">UserStatistics-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zur Verwendung des Systems durch einen einzelnen Benutzer.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>Für Konferenz CdR-Datensätze spezifische Tabellen


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Conferences-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu allen Konferenzen, die archiviert wurden oder deren Details aufgezeichnet wurden, einschließlich ConferenceURI sowie Start-und Endzeit.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu jeder SIP-basierten Konferenzsitzung, einschließlich Start-und Endzeit, Benutzer-ID, Antwortcode und Diagnose-ID für jede Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu Konferenz Verknüpfungen und-Blättern, einschließlich der Rolle des Benutzers und der Client Version.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu den a/V-Konferenzservern, die an einer Konferenz beteiligt sind, und die Benutzer an-und Abreisezeiten.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>Tabellen für Nachrichten in Chat Konferenzen


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert für jede Chat Konferenz die Anzahl der Nachrichten, die von jedem Benutzer gesendet wurden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary-Tabelle in lync Server 2013</a></p></td>
<td><p>Bietet einen Gesamtbericht zu den Chat-Sitzungen, die in einer Organisation abgehalten werden.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>Tabellen für Peer-to-Peer-Sitzungen


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">SessionDetails-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu jeder Peer-to-Peer-Sitzung, einschließlich Start-und Endzeit, Benutzer-ID, Antwortcode und Nachrichtenanzahl für jeden Benutzer.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">FileTransfers-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu Dateiübertragungssitzungen, einschließlich Dateinamen und Ergebnis (akzeptiert, abgelehnt oder storniert).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Media-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu den verschiedenen Medientypen, die an Peer-zu-Peer-Sitzungen beteiligt sind.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>Tabelle für VoIP-Anruf Details


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">VoipDetails-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert für jeden zwei-Parteien-VoIP/PSTN-Anrufinformationen zu dem Anruf, wie etwa die Telefon-ID des VoIP-Telefons, das verwendete Gateway und welche Partei getrennt wurde. Bezieht sich auf die <a href="lync-server-2013-sessiondetails-table.md">SessionDetails-Tabelle in lync Server 2013</a> für die Start-und Endzeit des Anrufs und den Antwortcode.</p>
<div>

> [!NOTE]  
> Wenn eine Partei bei einem Anruf ein VoIP-Nutzer ist oder wenn ein Vermittlungs Server an dem Anruf beteiligt war, wird in dieser Tabelle ein Datensatz erstellt. Informationen zu VoIP-und VoIP-Anrufen, die kein PSTN-Telefon (Public Switched Telephone Network) betreffen, werden in der <A href="lync-server-2013-sessiondetails-table.md">SessionDetails-Tabelle in lync Server 2013</A>erfasst.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>Tabelle für die E9-1-1-Anrufüberwachung


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Locations-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert für jeden Notruf, beispielsweise einen erweiterten 9-1-1 (E9-1-1)-Anruf, Standortinformationen zu dem Anruf. Bezieht sich auf die <a href="lync-server-2013-sessiondetails-table.md">SessionDetails-Tabelle in lync Server 2013</a> für die Start-und Endzeit des Anrufs und den Antwortcode.</p>
<div>

> [!NOTE]  
> Diese Tabelle enthält nur den Standort-BLOB für den E9-1-1-Anruf. Bezieht sich auf die Tabelle "SessionDetails", um weitere detaillierte Informationen zu dem Anruf zu erhalten.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>Tabellen zur Problembehandlung


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Application-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu verschiedenen Prozessen in lync Server 2013, die an Routing und Verbindungen beteiligt sind.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">CallType-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu Typen des Anrufs, beispielsweise "Audio", "Sofortnachrichten", "Audio und Video" und "Anwendungsfreigabe".</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">ErrorCategory-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert den Anzeigenamen für jede Microsoft lync Server 2013-Diagnose Klassifizierung.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">ErrorDef-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu Fehlertypen und deren Definitionen.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">ErrorReport-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu Fehlern, die aufgetreten sind.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">ProgressReport-Tabelle in Lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu den Fortschrittsberichten verschiedener Schritte, die in lync Server 2013-Prozessen involviert sind.</p></td>
</tr>
</tbody>
</table>


Die Tabellen in der folgenden Liste werden intern von lync Server verwendet. Deren Details werden in diesem Dokument nicht beschrieben.

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Tabellen für die interne Verwendung durch lync Server


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Dberrormessage</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Frontend-Tabelle</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MSMQProcessing-Tabelle</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabelle "Syndikator"</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>SyndicatorsTenantMap-Tabelle</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Aufgaben Tabelle</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zeitzonen</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

