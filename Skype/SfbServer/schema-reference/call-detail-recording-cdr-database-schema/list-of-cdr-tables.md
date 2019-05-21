---
title: Liste der CDR-Tabellen in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: Das Datenbankschema für die Anrufdetailaufzeichnung (CDR) besteht aus den folgenden Tabellen.
ms.openlocfilehash: a8d36d75f629b41c535de99c0b9aef42770ba573
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296154"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Liste der CDR-Tabellen in Skype for Business Server 2015
 
Das Datenbankschema für die Anrufdetailaufzeichnung (CDR) besteht aus den folgenden Tabellen. 
  
## <a name="static-tables"></a>Statische Tabellen

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[CallPriorities-Tabelle in Skype for Business Server 2015](callpriorities.md) <br/> |Speichert die Liste möglicher Anruf Prioritäten wie Notfall, dringend, normal, nicht dringend und mehr.  <br/> |
|[ConferenceJoinTimeThresholds-Tabelle in Skype for Business Server 2015](conferencejointimethresholds.md) <br/> |Speichert die Klassifizierungs Grenzen, die vom Zusammenfassungsbericht zur Konferenzteilnahme verwendet werden.  <br/> |
|[Tabelle "deregistertype" in Skype for Business Server 2015](deregistertype.md) <br/> |Speichert die Liste der möglichen Benutzer Deregistrierungs Gründe, wie "Client initiiert", "Registrierung abgelaufen", "" Client Absturz "und vieles mehr.  <br/> |
|[MediaList-Tabelle](medialist.md) <br/> |Speichert die Liste der Medientypen, die Einträge in der Datenbank generieren können (beispielsweise Chat, Audio, Video und Dateiübertragung).  <br/> |
|[PurgeSettings-Tabelle](purgesettings.md) <br/> |Speichert Informationen, die angeben, ob (und wann) veraltete Anruf Detaildatensätze automatisch aus der CDR-Datenbank gelöscht werden.  <br/> |
|[Roles-Tabelle](roles.md) <br/> |Speichert die Liste möglicher Konferenz Rollen (beispielsweise Teilnehmer und Referenten).  <br/> |
|[SIPResponseMetaData-Tabelle](sipresponsemetadata.md) <br/> |Speichert eine Liste der SIP-Antwortcodes sowie die Klassifizierung und Definition der einzelnen Codes.  <br/> |
   
## <a name="supporting-tables"></a>Unterstützende Tabellen

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[ClientVersions-Tabelle in Skype for Business Server 2015](clientversions.md) <br/> |Speichert die Clients (Clienttyp und Versionsnummer) jedes an einem Anruf beteiligten Clients mit Informationen, die in dieser Datenbank erfasst werden.  <br/> |
|[ConferenceUris-Tabelle in Skype for Business Server 2015](conferenceuris.md) <br/> |Speichert eine Liste der ConferenceURIs, die in konferenzbezogenen Anrufen verwendet werden.  <br/> |
|[Tabelle "ContentTypes" in Skype for Business Server 2015](contenttypes.md) <br/> |Speichert eine Liste von SIP-Inhaltstypen (Session Initiation Protocol), die sowohl in Peer-to-Peer-Anrufen als auch in Konferenzgesprächen verwendet werden.  <br/> |
|[Tabelle "Geräte" in Skype for Business Server 2015](devices.md) <br/> |Speichert eine Liste von Geräten, einschließlich deren Hersteller, Hardware Version und Mac-Adresse.  <br/> |
|[Tabelle "Dialogfelder" in Skype for Business Server 2015](dialogs.md) <br/> |Speichert Informationen über die Dialog Feld-ID für jede Sitzung in der Datenbank.  <br/> |
|[EdgeServers-Tabelle in Skype for Business Server 2015](edgeservers.md) <br/> |Speichert eine Liste der Edgeserver, die für externe Anrufe verwendet werden.  <br/> |
|[Tabelle "Gateways" in Skype for Business Server 2015](gateways.md) <br/> |Speichert eine Liste der Gateways, die für VoIP-Anrufe (Voice over Internet Protocol) verwendet werden.  <br/> |
|[HardwareVersions-Tabelle in Skype for Business Server 2015](hardwareversions.md) <br/> |Speichert eine Liste der Hardware Versionen von Geräten (Tischtelefon).  <br/> |
|[Tabelle "Hersteller" in Skype for Business Server 2015](manufacturers.md) <br/> |Speichert eine Liste der Hersteller von Geräten (Tischtelefon).  <br/> |
|[Tabelle "Tabelle" in Skype for Business Server 2015](mcus.md) <br/> |Speichert Informationen zu den verschiedenen A/V-Konferenzservern und deren URIs.  <br/> |
|[MediationServers-Tabelle](mediationservers.md) <br/> |Speichert eine Liste der Vermittlungsserver, die für VoIP-Anrufe verwendet werden.  <br/> |
|[Phones-Tabelle](phones.md) <br/> |Speichert alle Telefonnummern, die in VoIP-Anrufen verwendet werden, die archiviert wurden oder deren Anrufdetails aufgezeichnet wurden.  <br/> |
|[Pools-Tabelle](pools.md) <br/> |Speichert die Namen des Pools, in dem Chatnachrichten erfasst werden.  <br/> |
|[Servers-Tabelle](servers.md) <br/> |Speichert den Namen der an den anrufen beteiligten Server.  <br/> |
|[Tenants-Tabelle](tenants.md) <br/> |Speichert die Mandanten, die von der aktuellen Bereitstellung unterstützt werden. Es gibt einige integrierte Mandanten für Enterprise-Benutzer, Federated-Benutzer, öffentliche Chat-Konnektivitäts-Benutzer und anonyme Benutzer.  <br/> |
|[UserAgentDef-Tabelle](useragentdef.md) <br/> |Ordnet die Bezeichner des Benutzer-Agents den beschreibenden Namen des Agents zu.  <br/> |
|[Users-Tabelle](users.md) <br/> |Speichert die Benutzer-URIs von Benutzern, die an Sitzungen teilgenommen haben, die in dieser Datenbank aufgezeichnet oder archiviert wurden.  <br/> |
|[UserStatistics-Tabelle](userstatistics.md) <br/> |Speichert Informationen zur Verwendung des Systems durch einen einzelnen Benutzer.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Für Konferenz CdR-Datensätze spezifische Tabellen

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[Konferenz Tabelle in Skype for Business Server 2015](conferences.md) <br/> |Speichert Informationen zu allen Konferenzen, die archiviert wurden oder deren Details aufgezeichnet wurden, einschließlich ConferenceURI sowie Start-und Endzeit.  <br/> |
|[ConferenceSessionDetails-Tabelle in Skype for Business Server 2015](conferencesessiondetails-0.md) <br/> |Speichert Informationen zu jeder SIP-basierten Konferenzsitzung, einschließlich Start-und Endzeit, Benutzer-ID, Antwortcode und Diagnose-ID für jede Sitzung.  <br/> |
|[FocusJoinsAndLeaves-Tabelle in Skype for Business Server 2015](focusjoinsandleaves.md) <br/> |Speichert Informationen zu Konferenz Verknüpfungen und-Blättern, einschließlich der Rolle des Benutzers und der Client Version.  <br/> |
|[McuJoinsAndLeaves-Tabelle in Skype for Business Server 2015](mcujoinsandleaves.md) <br/> |Speichert Informationen zu den a/V-Konferenzservern, die an einer Konferenz beteiligt sind, und die Benutzer an-und Abreisezeiten.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tabellen für Nachrichten in Chat Konferenzen

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[ConferenceMessageCount-Tabelle in Skype for Business Server 2015](conferencemessagecount.md) <br/> |Speichert für jede Chat Konferenz die Anzahl der Nachrichten, die von jedem Benutzer gesendet wurden.  <br/> |
|[IMReportSummary-Tabelle in Skype for Business Server 2015](imreportsummary.md) <br/> |Bietet einen Gesamtbericht zu den Chat-Sitzungen, die in einer Organisation abgehalten werden.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tabellen für Peer-to-Peer-Sitzungen

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[SessionDetails-Tabelle](sessiondetails.md) <br/> |Speichert Informationen zu jeder Peer-to-Peer-Sitzung, einschließlich Start-und Endzeit, Benutzer-ID, Antwortcode und Nachrichtenanzahl für jeden Benutzer.  <br/> |
|[Filetransfers-Tabelle in Skype for Business Server 2015](filetransfers-0.md) <br/> |Speichert Informationen zu Dateiübertragungssitzungen, einschließlich Dateinamen und Ergebnis (akzeptiert, abgelehnt oder storniert).  <br/> |
|[Media-Tabelle](media.md) <br/> |Speichert Informationen zu den verschiedenen Medientypen, die an Peer-zu-Peer-Sitzungen beteiligt sind.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tabelle für VoIP-Anruf Details

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[VoipDetails-Tabelle](voipdetails-0.md) <br/> |Speichert für jeden zwei-Parteien-VoIP/PSTN-Anrufinformationen zu dem Anruf, wie etwa die Telefon-ID des VoIP-Telefons, das verwendete Gateway und welche Partei getrennt wurde. Bezieht sich auf die [SessionDetails-Tabelle](sessiondetails.md) für die Start-und Endzeit des Anrufs und den Antwortcode. <br/> |
   
> [!NOTE]
> Wenn eine Partei bei einem Anruf ein VoIP-Nutzer ist oder wenn ein Vermittlungs Server an dem Anruf beteiligt war, wird in dieser Tabelle ein Datensatz erstellt. Informationen zu VoIP/VoIP-Anrufen, die kein öffentliches Telefonnetz (PSTN)-Telefon betreffen, werden in der [SessionDetails-Tabelle](sessiondetails.md)erfasst. 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tabelle für die E9-1-1-Anrufüberwachung

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[Tabelle "Speicherorte" in Skype for Business Server 2015](locations.md) <br/> |Speichert für jeden Notruf, beispielsweise einen erweiterten 9-1-1 (E9-1-1)-Anruf, Standortinformationen zu dem Anruf. Bezieht sich auf die [SessionDetails-Tabelle](sessiondetails.md) für die Start-und Endzeit des Anrufs und den Antwortcode. <br/> |
   
> [!NOTE]
> Diese Tabelle enthält nur den Standort-BLOB für den E9-1-1-Anruf. Bezieht sich auf die Tabelle "SessionDetails", um weitere detaillierte Informationen zu dem Anruf zu erhalten. 
  
## <a name="tables-for-troubleshooting"></a>Tabellen zur Problembehandlung

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[Anwendungstabelle in Skype for Business Server 2015](application.md) <br/> |Speichert Informationen zu verschiedenen Prozessen in Skype for Business Server 2015, die an Routing und Verbindungen beteiligt sind.  <br/> |
|[Tabelle "CallType" in Skype for Business Server 2015](calltype.md) <br/> |Speichert Informationen zu Typen des Anrufs, beispielsweise "Audio", "Sofortnachrichten", "Audio und Video" und "Anwendungsfreigabe".  <br/> |
|[ErrorCategory-Tabelle in Skype for Business Server 2015](errorcategory.md) <br/> |Speichert den Anzeigenamen für jede Skype for Business Server 2015-Diagnose Klassifizierung.  <br/> |
|[ErrorDef-Tabelle in Skype for Business Server 2015](errordef.md) <br/> |Speichert Informationen zu Fehlertypen und deren Definitionen.  <br/> |
|[ErrorReport-Tabelle in Skype for Business Server 2015](errorreport.md) <br/> |Speichert Informationen zu Fehlern, die aufgetreten sind.  <br/> |
|[ProgressReport-Tabelle](progressreport.md) <br/> |Speichert Informationen über die Fortschrittsberichte der verschiedenen Schritte, die in den Skype for Business Server 2015-Prozessen involviert sind.  <br/> |
   
Die Tabellen in der folgenden Liste werden intern von Skype for Business Server 2015 verwendet. Deren Details werden in diesem Dokument nicht beschrieben.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tabellen für die interne Verwendung durch lync Server

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Nur für interne Verwendung.  <br/> |
|**DbConfigInt** <br/> |Nur für interne Verwendung.  <br/> |
|**Dberrormessage** <br/> |Nur für interne Verwendung.  <br/> |
|**Frontend-Tabelle** <br/> |Nur für interne Verwendung.  <br/> |
|**MSMQProcessing-Tabelle** <br/> |Nur für interne Verwendung.  <br/> |
|**SummaryTableConfiguration** <br/> |Nur für interne Verwendung.  <br/> |
|**Tabelle "Syndikator"** <br/> |Nur für interne Verwendung.  <br/> |
|**SyndicatorsTenantMap-Tabelle** <br/> |Nur für interne Verwendung.  <br/> |
|**Aufgaben Tabelle** <br/> |Nur für interne Verwendung.  <br/> |
|**UserStatistics** <br/> |Nur für interne Verwendung.  <br/> |
|**UsageSummary_UQ** <br/> |Nur für interne Verwendung.  <br/> |
|**UsageSummary** <br/> |Nur für interne Verwendung.  <br/> |
|**DaylightSavingYears** <br/> |Nur für interne Verwendung.  <br/> |
|**TimeZoneConfiguration** <br/> |Nur für interne Verwendung.  <br/> |
|**Zeitzonen** <br/> |Nur für interne Verwendung.  <br/> |
|**FailureSummary_UQ** <br/> |Nur für interne Verwendung.  <br/> |
|**FailureSummary** <br/> |Nur für interne Verwendung.  <br/> |
|**ServerSummary** <br/> |Nur für interne Verwendung.  <br/> |
|**MsDiagMetaData** <br/> |Nur für interne Verwendung.  <br/> |
   

