---
title: Liste von QoE-Tabellen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: Das Datenbankschema besteht aus den folgenden Tabellen.
ms.openlocfilehash: e3e4ecb565e5a3a2f51d29ac77d4f1e87f3bf8eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920082"
---
# <a name="list-of-qoe-tables"></a>Liste von QoE-Tabellen
 
Das Datenbankschema besteht aus den folgenden Tabellen. 
  
**Hilfstabellen**

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[Tabelle "appsharingmetricsthreshold"](appsharingmetricsthreshold.md) <br/> |Speichert optimale und zulässige Werte für Quality of Experience-Metriken, die mit der Anwendungsfreigabe verwendet.  <br/> |
|[CodecDescription-Tabelle](codecdescription.md) <br/> |Ordnet eindeutige Codec-IDs dem entsprechenden Codec zu.  <br/> |
|[IPAddress-Tabelle](ipaddress.md) <br/> |Ordnet IP-Adressen den eindeutigen IP-Adress-IDs, die anderswo in der Quality of Experience-Datenbank verwendet.  <br/> |
|[NetworkConnectionDetail-Tabelle](networkconnectiondetail.md) <br/> |Ordnet Netzwerkverbindungstypen den Netzwerk Verbindung-IDs, die anderswo in der Quality of Experience-Datenbank verwendet.  <br/> |
|[PurgeSettings-Tabelle (QoE)](purgesettings-qoe.md) <br/> |Speichert Informationen, die angibt, ob (und wann) veraltete Quality of Experience Datensätze automatisch aus der QoE-Datenbank gelöscht werden.  <br/> |
|[TraceRoute-Tabelle](traceroute.md) <br/> |Speichert Routinginformationen für Anrufe.  <br/> |
|[UserAgentDef-Tabelle (QoE)](useragentdef-qoe.md) <br/> |Ordnet Benutzer-Agent-IDs den beschreibenden Namen.  <br/> |
|[VideoMetricsThreshold-Tabelle](videometricsthreshold.md) <br/> |Speichert optimale und zulässige Werte für Quality of Experience-Metriken, die bei Videoanrufen verwendet.  <br/> |
|[UserAgent-Tabelle](useragent.md) <br/> |Speichert Zeichenfolgen Session Initiation Protocol (SIP) User Agent (UA) und UA-Typen, die in Audio- und videositzungen verwendet.  <br/> |
|[User-Tabelle](user-0.md) <br/> |Speichert Benutzer, Konferenz- und Telefon-URIs, die in Audio- und videositzungen verwendet werden.  <br/> |
|[Endpoint-Tabelle](endpoint.md) <br/> |Speichert FQDN-Computernamen von Endpunkten in Audio- und videositzungen teilnehmen.  <br/> |
|[Pool-Tabelle](pool.md) <br/> |Speichert die Namen von Pools, zu denen, die metrische Daten gehören.  <br/> |
|[Device-Tabelle](device.md) <br/> |Speichert Aufnahme- und darstellungsgeräte in einer Audio-/Videoanrufen verwendet werden.  <br/> |
|[DeviceDriver-Tabelle](devicedriver.md) <br/> |Speichert den Treiber für das Aufnahmegerät und das darstellungsgerät, die bei Audio-/Videoanrufen verwendet werden.  <br/> |
|[Conference-Tabelle](conference.md) <br/> |Speichert Konferenz-URIs für konferenzszenarien oder die Dialog-ID für andere Szenarien.  <br/> |
|[SessionCorrelation-Tabelle](sessioncorrelation.md) <br/> |Speichert CorrelationID für PSTN-Anrufe.  <br/> |
|[PayloadDescription-Tabelle](payloaddescription.md) <br/> |Speichert die bei Audio-/Videoanrufen verwendeten Codecs.  <br/> |
|[AppliedBandwidthSource-Tabelle](appliedbandwidthsource.md) <br/> |Speichert die bei Audio-/Videoanrufen verwendete bandbreitenquelle.  <br/> |
|[MacAddress-Tabelle](macaddress.md) <br/> |Speichert die MAC-Adresse der Endpunkte, die Audio- und videositzungen teilnehmen.  <br/> |
|[Dialog-Tabelle](dialog.md) <br/> |Speichert die Dialog-ID von Audio- und videositzungen.  <br/> |
|[Region-Tabelle](region.md) <br/> |Speichert die netzwerkregion in der NCS-Einstellung definiert.  <br/> |
|[UserSite-Tabelle](usersite.md) <br/> |Speichert den Netzwerkstandort in der NCS-Einstellung definiert.  <br/> |
|[Subnet-Tabelle](subnet.md) <br/> |Speichert das Subnetz in der NCS-Einstellung definiert.  <br/> |
|[MonitoredRegionLink-Tabelle](monitoredregionlink.md) <br/> |Speichert die in der NCS-Einstellung festgelegten regionslink.  <br/> |
|[MonitoredUserSiteLink-Tabelle](monitoredusersitelink.md) <br/> |Speichert die netzwerkstandortverknüpfungen in der NCS-Einstellung.  <br/> |
|[EndpointSubnet-Tabelle](endpointsubnet.md) <br/> |Speichert das Subnetz des Endpunkts eine Audio- und videositzung teilnimmt.  <br/> |
|[Servertabelle](server.md) <br/> |Speichert den FQDN oder IP-Adresse des Servers, die das Medium durchläuft.  <br/> |
   
**Tabellen für metrische Daten**

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[AppSharingStream-Tabelle](appsharingstream.md) <br/> |Speichert Quality of Experience-Metriken für die Netzwerkstreams für die Anwendungsfreigabe verwendet. Die Qualität der Experience-Metriken für die Netzwerkstreams für die Anwendungsfreigabe verwendet.  <br/> |
|[Session-Tabelle](session.md) <br/> |Speichert allgemeine Informationen zu einer Audio- oder Audio-/Video-Sitzung. Eine Sitzung wird als eine Audio- oder Videodatei SIP-Dialogfeld zwischen zwei Endpunkte definiert.  <br/> |
|[MediaLine-Tabelle](medialine-0.md) <br/> |Speichert Informationen zu jeder medienzeile in einer Sitzung. Eine medienzeile ist eine Auflistung von mindestens einen Audio- und Videostreams. In der Regel wird eine einzelne medienzeile zwei Datenströme, audio oder video haben.  <br/> |
|[AudioStream-Tabelle](audiostream.md) <br/> |Speichert Audiomedien-Qualitätsmetriken für jeden Audiostream in der medienzeile.  <br/> |
|[AudioSignal-Tabelle](audiosignal.md) <br/> |Speichert Audiomedien-Qualitätsmetriken in der medienzeile. Dazu gehören echounterdrückung (AEC) und automatische Gewinn-Steuerelement (AGC) Metriken.  <br/> |
|[VideoStream-Tabelle](videostream.md) <br/> |Speichert Videomedien-Qualitätsmetriken für jeden Audiostream in der medienzeile.  <br/> |
|[AudioClientEvent-Tabelle](audioclientevent.md) <br/> |Aus dem Clientereignis empfangene speichert Audiomedien-Qualitätsmetriken.  <br/> |
|[VideoClientEvent-Tabelle](videoclientevent.md) <br/> |Aus dem Clientereignis empfangene speichert Videomedien-Qualitätsmetriken.  <br/> |
|**DiagnosticData-Tabelle** <br/> |Speichert Diagnosedaten nur zur internen Verwendung ist.  <br/> |
   
**Tabellen für Zusammenfassungsdaten**

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|**ServerSummary-Tabelle** <br/> |Zusammenfassungsdaten Speicher für die Server, diese Daten werden für Quality-of-Experience (QoE), die nur reporting verwendet.  <br/> |
|**UserSummary-Tabelle** <br/> |Speichert Zusammenfassungsdaten für Benutzer, die diese Daten werden für QoE nur reporting verwendet.  <br/> |
|**CallTypeSummary-Tabelle** <br/> |Store Zusammenfassungsdaten für Anruftypen, diese Daten werden für QoE nur reporting verwendet.  <br/> |
   
**Tabellen für die interne Verwendung durch den Monitoring Server**

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Nur zur internen Verwendung.  <br/> |
|**DbConfigInt** <br/> |Nur zur internen Verwendung.  <br/> |
|**FrontEnd-Tabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**Aufgabentabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**SummaryTableConfiguration** <br/> |Nur zur internen Verwendung.  <br/> |
|**DbErrorMessage** <br/> |Nur zur internen Verwendung.  <br/> |
|**MetricsThreshold** <br/> |Nur zur internen Verwendung.  <br/> |
|**DaylightSavingYears** <br/> |Nur zur internen Verwendung.  <br/> |
|**TimeZoneConfiguration** <br/> |Nur zur internen Verwendung.  <br/> |
|**TimeZones** <br/> |Nur zur internen Verwendung.  <br/> |
|**CallSummary-Tabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**DeviceCallSumary-Tabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**Tenant-Tabelle** <br/> |Nur zur internen Verwendung.  <br/> |
|**VideoCallSummaryTable** <br/> |Nur zur internen Verwendung.  <br/> |
|**ASCallSummaryTable** <br/> |Nur zur internen Verwendung.  <br/> |
   

