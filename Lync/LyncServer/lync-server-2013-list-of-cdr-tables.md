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
ms.openlocfilehash: b2792988c24ad412c80c18a4c334d1af54bbcf3a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Liste der CDR-Tabellen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Das Datenbankschema für die Aufzeichnung von Kommunikationsdatensätzen (KDS) besteht aus den folgenden Tabellen.

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
<td><p><a href="lync-server-2013-callpriorities-table.md">CallPriorities-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert die Liste möglicher Kommunikationsprioritäten, wie z. B. Notfall, dringend, normal, nicht dringend usw.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert die Klassifizierungsgrenzen, die vom zusammenfassenden Bericht über den Zeitpunkt des Konferenzbeitritts verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Deregistertype-Tabelle in lync Server 2013</a></p></td>
<td><p>&quot;Speichert die Liste der möglichen Benutzer deregister Gründe, beispielsweise initiierter Client,&quot; &quot;Registrierung abgelaufen,&quot; &quot;Client Absturz&quot; und vieles mehr.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Medialist-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert die Liste der Medientypen, von denen Einträge in der Datenbank generiert werden können (z. B. Sofortnachricht, Audio, Video und Dateiübertragung).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">PurgeSettings-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen, mit denen angegeben wird, ob (und wann) verwaltete Kommunikationsdatensätze automatisch aus der CDR-Datenbank gelöscht werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Tabelle "Roles" in lync Server 2013</a></p></td>
<td><p>Speichert die Liste möglicher Konferenzrollen (z. B. Teilnehmer und Referent).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert eine Liste mit SIP-Antwortcodes und der Klassifizierung und Definition der einzelnen Codes.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>Hilfstabellen


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
<td><p><a href="lync-server-2013-clientversions-table.md">Client Versions-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert die Clients (sowohl Clienttyp als auch Versionsnummer) aller an einem Anruf beteiligten Clients, wobei die Informationen in dieser Datenbank erfasst werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der ConferenceURI-Werte, die bei Telefonkonferenzen verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">ContentTypes-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der SIP-Inhaltstypen (Session Initiation-Protokoll), die bei Peer-zu-Peer-Anrufen und Telefonkonferenzen verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Devices-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der Geräte, einschließlich Hersteller, Hardwareversion und MAC-Adresse.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Dialogfelder (Tabelle) in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zur Dialog-ID für jede Sitzung in der Datenbank.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">EdgeServers-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der für externe Anrufe verwendeten Edgeserver.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Gateways-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der für VoIP-Anrufe verwendeten Gateways.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Hardware Versions-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der Hardwareversionen von Geräten (Telefonapparat).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Herstellertabelle in lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der Hersteller von Geräten (Telefonapparat).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Tabelle "MCU" in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu den verschiedenen A/V-Konferenzservern und deren URIs.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">MediationServers-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert eine Liste der für VoIP-Anrufe verwendeten Vermittlungsserver.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Phones-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert alle Telefonnummern, die bei VoIP-Anrufen verwendet wurden und die archiviert oder deren Kommunikationsdatensätze aufgezeichnet wurden.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Tabelle "Pools" in lync Server 2013</a></p></td>
<td><p>Speichert die Namen der Pools, in denen Sofortnachrichten erfasst werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Server-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert den Namen der an Anrufen beteiligten Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Tabelle "Mandanten" in lync Server 2013</a></p></td>
<td><p>Speichert die von der aktuellen Bereitstellung unterstützten Mandanten. Es gibt einige integrierte Mandanten für Unternehmensbenutzer, Verbundbenutzer, Benutzer mit Verbindung mit öffentlichen Instant Messaging-Diensten sowie anonyme Benutzer.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle in lync Server 2013</a></p></td>
<td><p>Ordnet Benutzeragent-IDs den beschreibenden Namen von Agents zu.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Tabelle "Users" in lync Server 2013</a></p></td>
<td><p>Speichert die Benutzer-URIs von Benutzern, die an Sitzungen teilgenommen haben, die in dieser Datenbank aufgezeichnet oder archiviert wurden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">UserStatistics-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zur Systemnutzung eines einzelnen Benutzers.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>Spezifische Tabellen für Konferenzkommunikationsdatensätze


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
<td><p><a href="lync-server-2013-conferences-table.md">Konferenz Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu allen Konferenzen, die archiviert wurden oder deren Details aufgezeichnet wurden, einschließlich "ConferenceURI" sowie Start- und Endzeit.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert für jede Sitzung Informationen zu jeder SIP-basierten Konferenzsitzung, einschließlich Start- und Endzeit, Benutzer-ID, Antwortcode und Diagnose-ID.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zum Beitreten zu sowie zum Verlassen von Konferenzen, einschließlich der Rolle von Benutzern und der Clientversion.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu den an einer Konferenz beteiligten A/V-Konferenzservern sowie die Zeiten, wann Benutzer Konferenzen beitreten und sie verlassen.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>Tabellen für Nachrichten bei Sofortnachrichten-Konferenzen


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
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount-Tabelle in lync Server 2013</a></p></td>
<td><p>Für jede Sofortnachrichten-Konferenz wird die Anzahl der von jedem Benutzer gesendeten Nachrichten gespeichert.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary-Tabelle in lync Server 2013</a></p></td>
<td><p>Stellt einen Gesamtbericht zu den durchgeführten Chatsitzungen einer Organisation bereit.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>Tabellen für Peer-zu-Peer-Sitzungen


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
<td><p><a href="lync-server-2013-sessiondetails-table.md">SessionDetails-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert für jeden Benutzer Informationen zu jeder Peer-zu-Peer-Sitzung, einschließlich Start- und Endzeit, Benutzer-ID, Antwortcode und Nachrichtenanzahl.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Filetransfers-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu Dateiübertragungssitzungen, einschließlich Dateiname und Ergebnis (akzeptiert, abgelehnt oder abgebrochen).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Medientabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu den an Peer-zu-Peer-Sitzungen beteiligten Medientypen.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>Tabelle für VoIP-Kommunikationsdatensätze


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
<td><p><a href="lync-server-2013-voipdetails-table.md">VoipDetails-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert für jeden VoIP/PSTN-Anruf mit zwei Parteien Informationen zum Anruf, wie z. B. die Telefon-ID des VoIP-Telefons, das verwendete Gateway und welche Partei getrennt wurde. Bezieht sich auf die <a href="lync-server-2013-sessiondetails-table.md">SessionDetails-Tabelle in lync Server 2013</a> für die Start-und Endzeit des Anrufs und den Antwortcode.</p>
<div>

> [!NOTE]  
> Wenn eine Anrufpartei ein VoIP-Benutzer ist oder wenn ein Vermittlungsserver am Anruf beteiligt war, wird in dieser Tabelle ein Datensatz erstellt. Informationen zu VoIP/VoIP-Anrufen, die kein Telefon Festnetz (Public Switched Telephone Network, PSTN) betreffen, werden in der <A href="lync-server-2013-sessiondetails-table.md">SessionDetails-Tabelle in lync Server 2013</A>erfasst.


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
<td><p><a href="lync-server-2013-locations-table.md">Tabelle "Locations" in lync Server 2013</a></p></td>
<td><p>Für jeden Notruf, wie z. B. einen erweiterten 9-1-1-Anruf (E9-1-1) werden Standortinformationen zum Anruf gespeichert. Bezieht sich auf die <a href="lync-server-2013-sessiondetails-table.md">SessionDetails-Tabelle in lync Server 2013</a> für die Start-und Endzeit des Anrufs und den Antwortcode.</p>
<div>

> [!NOTE]  
> Diese Tabelle enthält nur den Standort-BLOB für den E9-1-1-Anruf. Weitere ausführliche Informationen zum Anruf finden Sie in der SessionDetails-Tabelle.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>Tabellen für die Problembehandlung


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
<td><p><a href="lync-server-2013-application-table.md">Anwendungstabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu verschiedenen Prozessen in lync Server 2013, die an Routing und Verbindungen beteiligt sind.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">CallType-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu Anruftypen, wie z. B. "Audio", "Sofortnachrichten", "Audio und Video" und "Anwendungsfreigabe".</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">ErrorCategory-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert den Anzeigenamen für jede Microsoft lync Server 2013 Diagnose Klassifizierung.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">ErrorDef-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu Fehlertypen und deren Definitionen.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">ErrorReport-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen zu aufgetretenen Fehlern.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">ProgressReport-Tabelle in lync Server 2013</a></p></td>
<td><p>Speichert Informationen über die Fortschrittsberichte verschiedener Schritte, die an lync Server 2013 Prozessen beteiligt sind.</p></td>
</tr>
</tbody>
</table>


Die Tabellen in der folgenden Liste werden intern von lync Server verwendet. Die zugehörigen Details werden in diesem Dokument nicht beschrieben.

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Tabellen für die interne Verwendung durch Lync Server


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
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Dberrormessage</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd-Tabelle</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MSMQProcessing-Tabelle</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Syndicators-Tabelle</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>SyndicatorsTenantMap-Tabelle</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Aufgabentabelle</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Nur für interne Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZones</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>Nur zur internen Verwendung.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

