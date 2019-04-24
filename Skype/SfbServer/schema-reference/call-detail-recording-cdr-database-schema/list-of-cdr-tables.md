---
title: Liste der CDR-Tabellen in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: Die Aufzeichnung von kommunikationsdatensätzen (CDR)-Datenbankschema besteht aus den folgenden Tabellen.
ms.openlocfilehash: 977c48b58c5b1d1c0f21fbac07a28ec6efb0bfd6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213015"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Liste der CDR-Tabellen in Skype für Business Server 2015
 
Die Aufzeichnung von kommunikationsdatensätzen (CDR)-Datenbankschema besteht aus den folgenden Tabellen. 
  
## <a name="static-tables"></a>Statische Tabellen

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[CallPriorities-Tabelle in Skype für Business Server 2015](callpriorities.md) <br/> |Speichert die Liste der möglichen Anruf Prioritäten, wie etwa Emergency, dringende, normale, nicht dringende und vieles mehr.  <br/> |
|[ConferenceJoinTimeThresholds-Tabelle in Skype für Business Server 2015](conferencejointimethresholds.md) <br/> |Speichert die klassifizierungsgrenzen, die von der Konferenz beitreten Zeit Summary Report verwendet.  <br/> |
|[DeRegisterType-Tabelle in Skype für Business Server 2015](deregistertype.md) <br/> |Speichert die Liste der möglichen Benutzer aufheben der Gründe, z. B. "Client initiiert," registrieren "Registrierung abgelaufen," "Client Absturz" und vieles mehr.  <br/> |
|[MediaList-Tabelle](medialist.md) <br/> |Speichert die Liste der Medientypen, die Einträge in der Datenbank generieren kann (beispielsweise Sofortnachrichten, audio, Video, und File transfer).  <br/> |
|[PurgeSettings-Tabelle](purgesettings.md) <br/> |Speichert Informationen, die angibt, ob (und wann) verwaltete kommunikationsdatensätze automatisch aus der CDR-Datenbank gelöscht werden.  <br/> |
|[Roles-Tabelle](roles.md) <br/> |Speichert die Liste der möglichen Konferenzrollen (beispielsweise Teilnehmer und Referent).  <br/> |
|[SIPResponseMetaData-Tabelle](sipresponsemetadata.md) <br/> |Speichert eine Liste der SIP-Antwortcodes und der Klassifizierung und Definition der einzelnen Codes.  <br/> |
   
## <a name="supporting-tables"></a>Hilfstabellen

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[ClientVersions-Tabelle in Skype für Business Server 2015](clientversions.md) <br/> |Speichert die Clients (sowohl Typ und die Version-Clientnummer) von jedem Client einen Anruf beteiligt mit Informationen in dieser Datenbank aufgezeichnet.  <br/> |
|[ConferenceUris-Tabelle in Skype für Business Server 2015](conferenceuris.md) <br/> |Speichert eine Liste der conferenceuri-Werte, die bei Telefonkonferenzen verwendet werden verwandte Anrufe.  <br/> |
|[ContentTypes-Tabelle in Skype für Business Server 2015](contenttypes.md) <br/> |Speichert eine Liste der Inhaltstypen Session Initiation Protocol (SIP), die verwendet werden in Peer-zu-Peer-Anrufe und Konferenzanrufe.  <br/> |
|[Devices-Tabelle in Skype für Business Server 2015](devices.md) <br/> |Speichert eine Liste der Geräte, einschließlich Hersteller, Hardwareversion und MAC-Adresse.  <br/> |
|[Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) <br/> |Speichert Informationen zur Dialog-ID für jede Sitzung in der Datenbank an.  <br/> |
|[EdgeServers-Tabelle in Skype für Business Server 2015](edgeservers.md) <br/> |Speichert eine Liste der Edge-Servern, die für externe Anrufe verwendet werden.  <br/> |
|[Gateways-Tabelle in Skype für Business Server 2015](gateways.md) <br/> |Speichert eine Liste der Gateways, die für Voice over Internet Protocol (VoIP) Anrufe verwendet werden.  <br/> |
|[HardwareVersions-Tabelle in Skype für Business Server 2015](hardwareversions.md) <br/> |Speichert eine Liste der Hardwareversionen von Geräten (Telefonapparat).  <br/> |
|[Manufacturers-Tabelle in Skype für Business Server 2015](manufacturers.md) <br/> |Speichert eine Liste der Hersteller von Geräten (Telefonapparat).  <br/> |
|[MCUs-Tabelle in Skype für Business Server 2015](mcus.md) <br/> |Speichert Informationen zu den verschiedenen A / V-Konferenzserver und deren URIs.  <br/> |
|[MediationServers-Tabelle](mediationservers.md) <br/> |Speichert eine Liste von Vermittlungsservern, die für VoIP-Anrufe verwendet werden.  <br/> |
|[Phones-Tabelle](phones.md) <br/> |Speichert alle Telefonnummern, die VoIP-Anrufe, die archiviert wurden oder deren kommunikationsdatensätze aufgezeichnet wurden, verwendet.  <br/> |
|[Pools-Tabelle](pools.md) <br/> |Speichert die Namen des Pools, auf welche Sofortnachrichten Nachrichten erfasst werden.  <br/> |
|[Servers-Tabelle](servers.md) <br/> |Speichert den Namen der an anrufen beteiligten Server.  <br/> |
|[Tenants-Tabelle](tenants.md) <br/> |Speichert die Mandanten, die durch die aktuelle Bereitstellung unterstützt. Es einige integrierte Mandanten für Enterprise-Benutzer, zum Verbund gehörenden Benutzer, öffentliche Instant Messaging-Diensten Benutzer und anonyme Benutzer.  <br/> |
|[UserAgentDef-Tabelle](useragentdef.md) <br/> |Ordnet Benutzer-Agent-IDs den beschreibenden Namen.  <br/> |
|[Users-Tabelle](users.md) <br/> |Speichert den Benutzer URIs von Benutzern, die an Sitzungen teilgenommen haben aufgezeichnet oder archiviert in dieser Datenbank.  <br/> |
|[UserStatistics-Tabelle](userstatistics.md) <br/> |Speichert Informationen zur Nutzung eines einzelnen Benutzers des Systems.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Spezifische Tabellen für konferenzkommunikationsdatensätze

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[Conferences-Tabelle in Skype für Business Server 2015](conferences.md) <br/> |Speichert Informationen zu allen Konferenzen, die archiviert wurden oder deren Details aufgezeichnet wurden, einschließlich "ConferenceURI" sowie Start-und Endzeit.  <br/> |
|[ConferenceSessionDetails-Tabelle in Skype für Business Server 2015](conferencesessiondetails-0.md) <br/> |Speichert Informationen zu jeder SIP-basierten konferenzsitzung, einschließlich Start- und Endzeit, Benutzer-ID, Antwortcode und Diagnose-ID für jede Sitzung.  <br/> |
|[FocusJoinsAndLeaves-Tabelle in Skype für Business Server 2015](focusjoinsandleaves.md) <br/> |Speichert Informationen zu einer Konferenz beitritt und verlässt, einschließlich der Rolle von Benutzern und der Clientversion.  <br/> |
|[McuJoinsAndLeaves-Tabelle in Skype für Business Server 2015](mcujoinsandleaves.md) <br/> |Speichert Informationen zu den A / V-Konferenzserver, die an einer Konferenz und der Benutzer beteiligt sind beitreten und wie oft lassen.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tabellen für Nachrichten bei Sofortnachrichten-Konferenzen

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[ConferenceMessageCount-Tabelle in Skype für Business Server 2015](conferencemessagecount.md) <br/> |Für jede Sofortnachrichten-Konferenz speichert die Anzahl der Nachrichten, die von jedem Benutzer gesendet wurden.  <br/> |
|[IMReportSummary-Tabelle in Skype für Business Server 2015](imreportsummary.md) <br/> |Stellt einen Gesamtbericht auf die chatsitzungen in einer Organisation bereit.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tabellen für Peer-zu-Peer-Sitzungen

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[SessionDetails-Tabelle](sessiondetails.md) <br/> |Speichert Informationen zu jeder Peer-zu-Peer-Sitzung, einschließlich Start- und Endzeit, Benutzer-ID, Antwortcode und Anzahl der Nachrichten für jeden Benutzer.  <br/> |
|[FileTransfers-Tabelle in Skype für Business Server 2015](filetransfers-0.md) <br/> |Speichert Informationen zu dateiübertragungssitzungen, einschließlich Dateiname und Ergebnis (akzeptiert, abgelehnt oder abgebrochen).  <br/> |
|[Media-Tabelle](media.md) <br/> |Speichert Informationen zu den an Peer-zu-Peer-Sitzungen beteiligten Medientypen.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tabelle für VoIP-Kommunikationsdatensätze

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[VoipDetails-Tabelle](voipdetails-0.md) <br/> |Für jeden zwei Teilnehmern VoIP/PSTN-Anruf speichert Informationen über den Anruf, wie das Telefon-ID des VoIP-Telefon, verwendetes Gateway und welche Partei getrennt. Bezieht sich auf die [SessionDetails-Tabelle](sessiondetails.md) Anruf Start-/Endzeit und Antwortcode. <br/> |
   
> [!NOTE]
> Wenn eine Partei bei einem Aufruf ein VoIP-Benutzer ist oder wenn der Aufruf eines Vermittlungsservers beteiligt waren, wird in dieser Tabelle ein Datensatz erstellt werden. Informationen zur VoIP/VoIP-Anrufe, die nicht unter Verwendung von ein Telefon public switched Telephone Network (Telefonfestnetz PSTN) in der [SessionDetails-Tabelle](sessiondetails.md)erfasst wird. 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tabelle für E9-1-1-Anrufüberwachung

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[Locations-Tabelle in Skype für Business Server 2015](locations.md) <br/> |Für jede Notruf, wie ein Anruf erweiterten E9-1-1 (E9-1-1) speichert Standortinformationen über den Anruf. Bezieht sich auf die [SessionDetails-Tabelle](sessiondetails.md) Anruf Start-/Endzeit und Antwortcode. <br/> |
   
> [!NOTE]
> Die folgende Tabelle enthält nur den Speicherort Blob für den Anruf E9-1-1. Bezieht sich auf der SessionDetails-Tabelle für andere detaillierte Informationen über den Anruf. 
  
## <a name="tables-for-troubleshooting"></a>Tabellen für die Problembehandlung

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[Application-Tabelle in Skype für Business Server 2015](application.md) <br/> |Speichert Informationen zu verschiedenen Prozessen in Skype für Business Server 2015, die beteiligt sind routing und Verbindungen.  <br/> |
|[CallType-Tabelle in Skype für Business Server 2015](calltype.md) <br/> |Speichert Informationen zu Typen des Anrufs, wie beispielsweise "Audio", "Sofortnachrichten", "audio und video" und "Anwendungsfreigabe".  <br/> |
|[ErrorCategory-Tabelle in Skype für Business Server 2015](errorcategory.md) <br/> |Speichert den Anzeigenamen für jedes Skype für Business Server 2015-diagnoseklassifizierung.  <br/> |
|[ErrorDef-Tabelle in Skype für Business Server 2015](errordef.md) <br/> |Speichert Informationen zu Fehlertypen und deren Definitionen.  <br/> |
|[ErrorReport-Tabelle in Skype für Business Server 2015](errorreport.md) <br/> |Speichert Informationen zu aufgetretenen Fehlern.  <br/> |
|[ProgressReport-Tabelle](progressreport.md) <br/> |Speichert Informationen zum Fortschrittsbericht verschiedener Schritte Skype für Business Server 2015-Prozessen beteiligt.  <br/> |
   
Die Tabellen in der folgenden Liste werden intern von Skype für Business Server 2015 verwendet. Ihre Informationen werden nicht in diesem Dokument beschrieben.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tabellen für die interne Verwendung von Lync Server

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Nur zur internen Verwendung.  <br/> |
|**DbConfigInt** <br/> |Nur zur internen Verwendung.  <br/> |
|**DbErrorMessage** <br/> |Nur zur internen Verwendung.  <br/> |
|**FrontEnd-Tabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**MSMQProcessing-Tabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**SummaryTableConfiguration** <br/> |Nur zur internen Verwendung.  <br/> |
|**Syndicators-Tabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**SyndicatorsTenantMap-Tabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**Aufgabentabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**UserStatistics** <br/> |Nur zur internen Verwendung.  <br/> |
|**UsageSummary_UQ** <br/> |Nur zur internen Verwendung.  <br/> |
|**Nutzungszusammen Fassung** <br/> |Nur zur internen Verwendung.  <br/> |
|**DaylightSavingYears** <br/> |Nur zur internen Verwendung.  <br/> |
|**TimeZoneConfiguration** <br/> |Nur zur internen Verwendung.  <br/> |
|**TimeZones** <br/> |Nur zur internen Verwendung.  <br/> |
|**FailureSummary_UQ** <br/> |Nur zur internen Verwendung.  <br/> |
|**FailureSummary** <br/> |Nur zur internen Verwendung.  <br/> |
|**ServerSummary** <br/> |Nur zur internen Verwendung.  <br/> |
|**MsDiagMetaData** <br/> |Nur zur internen Verwendung.  <br/> |
   

