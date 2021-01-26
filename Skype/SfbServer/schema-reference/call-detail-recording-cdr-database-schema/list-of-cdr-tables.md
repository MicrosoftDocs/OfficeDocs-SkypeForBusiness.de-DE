---
title: Liste der Tabellen für die 1.000-16-16-16-16-16-16-16-15-Server in
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: Das Datenbankschema für die Aufzeichnung von Kommunikationsdatensätzen (KDS) besteht aus den folgenden Tabellen.
ms.openlocfilehash: 7bd76a4cf374e72582c585908309605c4845454e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827595"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Liste der Tabellen für die 1.000-16-16-16-16-16-16-16-15-Server in
 
Das Datenbankschema für die Aufzeichnung von Kommunikationsdatensätzen (KDS) besteht aus den folgenden Tabellen. 
  
## <a name="static-tables"></a>Statische Tabellen

|**Table**|**Beschreibung**|
|:-----|:-----|
|[Tabelle "CallPriorities" in Skype for Business Server 2015](callpriorities.md) <br/> |Speichert die Liste möglicher Kommunikationsprioritäten, wie z. B. Notfall, dringend, normal, nicht dringend usw.  <br/> |
|[Tabelle "ConferenceJoinTimeThresholds" in Skype for Business Server 2015](conferencejointimethresholds.md) <br/> |Speichert die Klassifizierungsgrenzen, die vom zusammenfassenden Bericht über den Zeitpunkt des Konferenzbeitritts verwendet werden.  <br/> |
|[Tabelle "DeRegisterType" in Skype for Business Server 2015](deregistertype.md) <br/> |Speichert die Liste möglicher Gründe für die Aufhebung der Registrierung von Benutzern, wie z. B. "vom Client initiiert", "Registrierung abgelaufen", "Clientabsturz" usw.  <br/> |
|[Tabelle "MediaList"](medialist.md) <br/> |Speichert die Liste der Medientypen, von denen Einträge in der Datenbank generiert werden können (z. B. Sofortnachricht, Audio, Video und Dateiübertragung).  <br/> |
|[Tabelle "PurgeSettings"](purgesettings.md) <br/> |Speichert Informationen, mit denen angegeben wird, ob (und wann) verwaltete Kommunikationsdatensätze automatisch aus der CDR-Datenbank gelöscht werden.  <br/> |
|[Rollentabelle](roles.md) <br/> |Speichert die Liste möglicher Konferenzrollen (z. B. Teilnehmer und Referent).  <br/> |
|[Tabelle "SIPResponseMetaData"](sipresponsemetadata.md) <br/> |Speichert eine Liste mit SIP-Antwortcodes und der Klassifizierung und Definition der einzelnen Codes.  <br/> |
   
## <a name="supporting-tables"></a>Unterstützungstabellen

|**Table**|**Beschreibung**|
|:-----|:-----|
|[Tabelle "ClientVersions" in Skype for Business Server 2015](clientversions.md) <br/> |Speichert die Clients (sowohl Clienttyp als auch Versionsnummer) aller an einem Anruf beteiligten Clients, wobei die Informationen in dieser Datenbank erfasst werden.  <br/> |
|[Tabelle "ConferenceUris" in Skype for Business Server 2015](conferenceuris.md) <br/> |Speichert eine Liste der ConferenceURI-Werte, die bei Telefonkonferenzen verwendet werden.  <br/> |
|[Tabelle "ContentTypes" in Skype for Business Server 2015](contenttypes.md) <br/> |Speichert eine Liste der SIP-Inhaltstypen (Session Initiation-Protokoll), die bei Peer-zu-Peer-Anrufen und Telefonkonferenzen verwendet werden.  <br/> |
|[Gerätetabelle in Skype for Business Server 2015](devices.md) <br/> |Speichert eine Liste der Geräte, einschließlich Hersteller, Hardwareversion und MAC-Adresse.  <br/> |
|[Dialogfeldertabelle in Skype for Business Server 2015](dialogs.md) <br/> |Speichert Informationen zur Dialog-ID für jede Sitzung in der Datenbank.  <br/> |
|[Tabelle "EdgeServers" in Skype for Business Server 2015](edgeservers.md) <br/> |Speichert eine Liste der für externe Anrufe verwendeten Edgeserver.  <br/> |
|[Gateways table in Skype for Business Server 2015](gateways.md) <br/> |Speichert eine Liste der für VoIP-Anrufe verwendeten Gateways.  <br/> |
|[Tabelle "HardwareVersions" in Skype for Business Server 2015](hardwareversions.md) <br/> |Speichert eine Liste der Hardwareversionen von Geräten (Telefonapparat).  <br/> |
|[Herstellertabelle in Skype for Business Server 2015](manufacturers.md) <br/> |Speichert eine Liste der Hersteller von Geräten (Telefonapparat).  <br/> |
|[Tabelle "Mcus" in Skype for Business Server 2015](mcus.md) <br/> |Speichert Informationen zu den verschiedenen A/V-Konferenzservern und deren URIs.  <br/> |
|[Tabelle "MediationServers"](mediationservers.md) <br/> |Speichert eine Liste der für VoIP-Anrufe verwendeten Vermittlungsserver.  <br/> |
|[Tabelle "Telefone"](phones.md) <br/> |Speichert alle Telefonnummern, die bei VoIP-Anrufen verwendet wurden und die archiviert oder deren Kommunikationsdatensätze aufgezeichnet wurden.  <br/> |
|[Tabelle "Pools"](pools.md) <br/> |Speichert die Namen der Pools, in denen Sofortnachrichten erfasst werden.  <br/> |
|[Servertabelle](servers.md) <br/> |Speichert den Namen der an Anrufen beteiligten Server.  <br/> |
|[Tabelle "Tenants"](tenants.md) <br/> |Speichert die von der aktuellen Bereitstellung unterstützten Mandanten. Es gibt einige integrierte Mandanten für Unternehmensbenutzer, Verbundbenutzer, Benutzer mit Verbindung mit öffentlichen Instant Messaging-Diensten sowie anonyme Benutzer.  <br/> |
|[Tabelle "UserAgentDef"](useragentdef.md) <br/> |Ordnet die Bezeichner von Benutzer-Agent-IDs den beschreibenden Namen des Agents zu.  <br/> |
|[Tabelle "Users"](users.md) <br/> |Speichert die Benutzer-URIs von Benutzern, die an Sitzungen teilgenommen haben, die in dieser Datenbank aufgezeichnet oder archiviert wurden.  <br/> |
|[Tabelle "UserStatistics"](userstatistics.md) <br/> |Speichert Informationen zur Nutzung des Systems durch einen einzelnen Benutzer.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Spezifische Tabellen für Konferenzkommunikationsdatensätze

|**Table**|**Beschreibung**|
|:-----|:-----|
|[Tabelle "Konferenzen" in Skype for Business Server 2015](conferences.md) <br/> |Speichert Informationen zu allen Konferenzen, die archiviert wurden oder deren Details aufgezeichnet wurden, einschließlich "ConferenceURI" sowie Start- und Endzeit.  <br/> |
|[#A0 in Skype for Business Server 2015](conferencesessiondetails-0.md) <br/> |Speichert für jede Sitzung Informationen zu jeder SIP-basierten Konferenzsitzung, einschließlich Start- und Endzeit, Benutzer-ID, Antwortcode und Diagnose-ID.  <br/> |
|[Tabelle "FocusJoinsAndLeaves" in Skype for Business Server 2015](focusjoinsandleaves.md) <br/> |Speichert Informationen zu Konferenzan- und -ab beitreten, einschließlich Benutzerrolle und Clientversion.  <br/> |
|[Tabelle "McuJoinsAndLeaves" in Skype for Business Server 2015](mcujoinsandleaves.md) <br/> |Speichert Informationen zu den an einer Konferenz beteiligten A/V-Konferenzservern sowie die Zeiten, wann Benutzer Konferenzen beitreten und sie verlassen.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tabellen für Nachrichten bei Sofortnachrichten-Konferenzen

|**Table**|**Beschreibung**|
|:-----|:-----|
|[Tabelle "ConferenceMessageCount" in Skype for Business Server 2015](conferencemessagecount.md) <br/> |Für jede Sofortnachrichten-Konferenz wird die Anzahl der von jedem Benutzer gesendeten Nachrichten gespeichert.  <br/> |
|[Tabelle "IMReportSummary" in Skype for Business Server 2015](imreportsummary.md) <br/> |Stellt einen Gesamtbericht zu den durchgeführten Chatsitzungen einer Organisation bereit.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tabellen für Peer-zu-Peer-Sitzungen

|**Table**|**Beschreibung**|
|:-----|:-----|
|[#A0](sessiondetails.md) <br/> |Speichert für jeden Benutzer Informationen zu jeder Peer-zu-Peer-Sitzung, einschließlich Start- und Endzeit, Benutzer-ID, Antwortcode und Nachrichtenanzahl.  <br/> |
|[Tabelle "FileTransfers" in Skype for Business Server 2015](filetransfers-0.md) <br/> |Speichert Informationen zu Dateiübertragungssitzungen, einschließlich Dateiname und Ergebnis (akzeptiert, abgelehnt oder abgebrochen).  <br/> |
|[Medientabelle](media.md) <br/> |Speichert Informationen zu den an Peer-zu-Peer-Sitzungen beteiligten Medientypen.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tabelle für VoIP-Kommunikationsdatensätze

|**Table**|**Beschreibung**|
|:-----|:-----|
|[#A0](voipdetails-0.md) <br/> |Speichert für jeden VoIP/PSTN-Anruf mit zwei Parteien Informationen zum Anruf, wie z. B. die Telefon-ID des VoIP-Telefons, das verwendete Gateway und welche Partei getrennt wurde. Bezieht sich auf die [Tabelle "SessionDetails"](sessiondetails.md) für Start-/Endzeiten von Anrufen und Antwortcode. <br/> |
   
> [!NOTE]
> Wenn eine Anrufpartei ein VoIP-Benutzer ist oder wenn ein Vermittlungsserver am Anruf beteiligt war, wird in dieser Tabelle ein Datensatz erstellt. Informationen zu VoIP/VoIP-Anrufen, an denen kein Festnetztelefon (Public Switched Telephone Network, PSTN) beteiligt ist, werden in der Tabelle ["SessionDetails" erfasst.](sessiondetails.md) 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tabelle für die E9-1-1-Anrufüberwachung

|**Table**|**Beschreibung**|
|:-----|:-----|
|[Tabelle "Standorte" in Skype for Business Server 2015](locations.md) <br/> |Für jeden Notruf, wie z. B. einen erweiterten 9-1-1-Anruf (E9-1-1) werden Standortinformationen zum Anruf gespeichert. Bezieht sich auf die [Tabelle "SessionDetails"](sessiondetails.md) für Start-/Endzeiten von Anrufen und Antwortcode. <br/> |
   
> [!NOTE]
> Diese Tabelle enthält nur den Standort-BLOB für den E9-1-1-Anruf. Weitere ausführliche Informationen zum Anruf finden Sie in der SessionDetails-Tabelle. 
  
## <a name="tables-for-troubleshooting"></a>Tabellen für die Problembehandlung

|**Table**|**Beschreibung**|
|:-----|:-----|
|[Anwendungstabelle in Skype for Business Server 2015](application.md) <br/> |Speichert Informationen zu verschiedenen Prozessen in Skype for Business Server 2015, die an Routing und Verbindungen beteiligt sind.  <br/> |
|[Tabelle "CallType" in Skype for Business Server 2015](calltype.md) <br/> |Speichert Informationen zu Anruftypen, z. B. "Audio", "Instant Messaging", "Audio und Video" und "Anwendungsfreigabe".  <br/> |
|[Tabelle "ErrorCategory" in Skype for Business Server 2015](errorcategory.md) <br/> |Speichert den Anzeigenamen für jede Skype for Business Server 2015-Diagnoseklassifikation.  <br/> |
|[Tabelle "ErrorDef" in Skype for Business Server 2015](errordef.md) <br/> |Speichert Informationen zu Fehlertypen und deren Definitionen.  <br/> |
|[Tabelle "ErrorReport" in Skype for Business Server 2015](errorreport.md) <br/> |Speichert Informationen zu aufgetretenen Fehlern.  <br/> |
|[Tabelle "ProgressReport"](progressreport.md) <br/> |Speichert Informationen zu den Fortschrittsberichten verschiedener Schritte im Skype for Business Server 2015-Prozess.  <br/> |
   
Die Tabellen in der folgenden Liste werden intern von Skype for Business Server 2015 verwendet. Die zugehörigen Details werden in diesem Dokument nicht beschrieben.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tabellen für die interne Verwendung durch Lync Server

|**Table**|**Beschreibung**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Nur für interne Verwendung.  <br/> |
|**DbConfigInt** <br/> |Nur für interne Verwendung.  <br/> |
|**DbErrorMessage** <br/> |Nur für interne Verwendung.  <br/> |
|**FrontEnd-Tabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**MSMQProcessing-Tabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**SummaryTableConfiguration** <br/> |Nur zur internen Verwendung.  <br/> |
|**Syndicators-Tabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**SyndicatorsTenantMap-Tabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**Aufgabentabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**UserStatistics** <br/> |Nur zur internen Verwendung.  <br/> |
|**UsageSummary_UQ** <br/> |Nur zur internen Verwendung.  <br/> |
|**UsageSummary** <br/> |Nur zur internen Verwendung.  <br/> |
|**DaylightSavingYears** <br/> |Nur für interne Verwendung.  <br/> |
|**TimeZoneConfiguration** <br/> |Ausschließlich für interne Zwecke.  <br/> |
|**TimeZones** <br/> |Nur zur internen Verwendung.  <br/> |
|**FailureSummary_UQ** <br/> |Nur zur internen Verwendung.  <br/> |
|**FailureSummary** <br/> |Nur zur internen Verwendung.  <br/> |
|**ServerSummary** <br/> |Nur zur internen Verwendung.  <br/> |
|**MsDiagMetaData** <br/> |Nur zur internen Verwendung.  <br/> |
   

