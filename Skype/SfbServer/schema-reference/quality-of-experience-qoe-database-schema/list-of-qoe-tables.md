---
title: Liste von QoE-Tabellen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: Das Datenbankschema besteht aus den folgenden Tabellen.
ms.openlocfilehash: 291d2ddefefc264aa283480362a6f57cda9161cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834485"
---
# <a name="list-of-qoe-tables"></a>Liste von QoE-Tabellen
 
Das Datenbankschema besteht aus den folgenden Tabellen. 
  
**Unterstützungstabellen**

|**Table**|**Beschreibung**|
|:-----|:-----|
|[Tabelle "AppSharingMetricsThreshold"](appsharingmetricsthreshold.md) <br/> |Speichert optimale und zulässige Werte für Quality of Experience-Metriken, die bei der Anwendungsfreigabe verwendet werden.  <br/> |
|[Tabelle "CodecDescription"](codecdescription.md) <br/> |Ordnet eindeutige Codec-IDs dem entsprechenden Codec zu.  <br/> |
|[Tabelle "IPAddress"](ipaddress.md) <br/> |Ordnet IP-Adressen den eindeutigen IP-Adress-IDs zu, die anderswo in der QoE (Quality of Experience)-Datenbank verwendet werden.  <br/> |
|[Tabelle "NetworkConnectionDetail"](networkconnectiondetail.md) <br/> |Ordnet Netzwerkverbindungstypen den Netzwerkverbindungs-IDs zu, die anderswo in der QoE (Quality of Experience)-Datenbank verwendet werden.  <br/> |
|[Tabelle "PurgeSettings" (QoE)](purgesettings-qoe.md) <br/> |Speichert Informationen, mit denen angegeben wird, ob (und wann) veraltete QoE-(Quality of Experience)-Kommunikationsdatensätze automatisch aus der QoE-Datenbank gelöscht werden.  <br/> |
|[Tabelle "TraceRoute"](traceroute.md) <br/> |Speichert Routinginformationen für Anrufe.  <br/> |
|[Tabelle "UserAgentDef" (QoE)](useragentdef-qoe.md) <br/> |Ordnet die Bezeichner von Benutzer-Agent-IDs den beschreibenden Namen des Agents zu.  <br/> |
|[Tabelle "VideoMetricsThreshold"](videometricsthreshold.md) <br/> |Speichert optimale und zulässige Werte für Quality of Experience-Metriken, die bei Videoanrufen verwendet werden.  <br/> |
|[Tabelle "UserAgent"](useragent.md) <br/> |Speichert in Audio- und Videositzungen verwendete Session Initiation-Protokolle (SIP), Benutzer-Agent-Zeichenfolgen (UA) und UA-Typen.  <br/> |
|[Benutzertabelle](user-0.md) <br/> |Speichert in Audio- und Videositzungen verwendete Benutzer-, Konferenz- und Telefon-URIs.  <br/> |
|[Endpunkttabelle](endpoint.md) <br/> |Speichert FQDN-Computernamen von Endpunkten, die an Audio- und Videositzungen teilnehmen.  <br/> |
|[Pooltabelle](pool.md) <br/> |Speichert die Namen von Pools, zu denen metrische Daten gehören.  <br/> |
|[Gerätetabelle](device.md) <br/> |Speichert bei Audio-/Videoanrufen verwendete Aufnahme- und Darstellungsgeräte.  <br/> |
|[#A0](devicedriver.md) <br/> |Speichert den Treiber für das Aufnahmegerät und das Darstellungsgerät, die bei Audio-/Videoanrufen verwendet werden.  <br/> |
|[Konferenztabelle](conference.md) <br/> |Speichert Konferenz-URIs für Konferenzszenarien oder die Dialog-ID für andere Szenarien.  <br/> |
|[Tabelle "SessionCorrelation"](sessioncorrelation.md) <br/> |Speichert die Korrelations-ID für PSTN-Anrufe.  <br/> |
|[PayloadDescription (Tabelle)](payloaddescription.md) <br/> |Speichert die bei Audio-/Videoanrufen verwendeten Codecs.  <br/> |
|[Tabelle "AppliedBandwidthSource"](appliedbandwidthsource.md) <br/> |Speichert die bei Audio-/Videoanrufen verwendete Bandbreitenquelle.  <br/> |
|[Tabelle "MacAddress"](macaddress.md) <br/> |Speichert die MAC-Adresse der Endpunkte, die an Audio- und Videositzungen teilnehmen.  <br/> |
|[Dialogtabelle](dialog.md) <br/> |Speichert die Dialog-ID von Audio- und Videositzungen.  <br/> |
|[Tabelle "Region"](region.md) <br/> |Speichert die in der NCS-Einstellung festgelegte Netzwerkregion.  <br/> |
|[Tabelle "UserSite"](usersite.md) <br/> |Speichert den in der NCS-Einstellung festgelegten Netzwerkstandort.  <br/> |
|[Subnetztabelle](subnet.md) <br/> |Speichert das in der NCS-Einstellung festgelegte Subnetz.  <br/> |
|[MonitoredRegionLink (Tabelle)](monitoredregionlink.md) <br/> |Speichert den in der NCS-Einstellung festgelegten Regionslink.  <br/> |
|[Tabelle "MonitoredUserSiteLink"](monitoredusersitelink.md) <br/> |Speichert die in der NCS-Einstellung festgelegten Netzwerkstandortverknüpfungen.  <br/> |
|[Tabelle "EndpointSubnet"](endpointsubnet.md) <br/> |Speichert das Subnetz des Endpunkts, der an einer Audio- und Videositzung teilnimmt.  <br/> |
|[Servertabelle](server.md) <br/> |Speichert den FQDN oder die IP-Adresse des Servers, über den der Mediendatenverkehr erfolgt.  <br/> |
   
**Tabellen für metrische Daten**

|**Table**|**Beschreibung**|
|:-----|:-----|
|[Tabelle "AppSharingStream"](appsharingstream.md) <br/> |Speichert QoE (Quality of Experience)-Metriken für die Netzwerkdatenströme, die bei der Anwendungsfreigabe verwendet werden. QoE (Quality of Experience)-Metriken für die Netzwerkdatenströme, die bei der Anwendungsfreigabe verwendet werden.  <br/> |
|[Sitzungstabelle](session.md) <br/> |Speichert allgemeine Informationen zu einer Audio- oder Videositzung. Eine Sitzung ist ein Audio- oder Video-SIP-Dialog zwischen zwei Endpunkten.  <br/> |
|[Tabelle "MediaLine"](medialine-0.md) <br/> |Speichert Informationen zu jeder Medienzeile in einer Sitzung. Eine Medienzeile ist eine Sammlung von mindestens einem Audio- und Videostream. In der Regel enthält eine einzelne Medienzeile zwei Streams, entweder Audio oder Video.  <br/> |
|[Tabelle "AudioStream"](audiostream.md) <br/> |Speichert Audiomedien-Qualitätsmetriken für jeden Audiostream in der Medienzeile.  <br/> |
|[Tabelle "AudioSignal"](audiosignal.md) <br/> |Speichert Metriken für die Audiomedienqualität in der Medienzeile. Dazu gehören AEC (Echounterdrückung) und Metriken für die automatische Verstärkungssteuerung (Automatic Gain Control, AGC).  <br/> |
|[Tabelle "VideoStream"](videostream.md) <br/> |Speichert Videomedien-Qualitätsmetriken für jeden Audiostream in der Medienzeile.  <br/> |
|[Tabelle "AudioClientEvent"](audioclientevent.md) <br/> |Speichert aus dem Clientereignis empfangene Audiomedien-Qualitätsmetriken.  <br/> |
|[Tabelle "VideoClientEvent"](videoclientevent.md) <br/> |Speichert aus dem Clientereignis empfangene Videomedien-Qualitätsmetriken.  <br/> |
|**DiagnosticData-Tabelle** <br/> |Speichert Diagnosedaten ausschließlich für die interne Verwendung.  <br/> |
   
**Tabellen für Zusammenfassungsdaten**

|**Table**|**Beschreibung**|
|:-----|:-----|
|**ServerSummary-Tabelle** <br/> |Speichert Zusammenfassungsdaten für die Server. Diese Daten werden nur für Quality of Experience-Berichte (QoE) verwendet.  <br/> |
|**UserSummary-Tabelle** <br/> |Speichert Zusammenfassungsdaten für Benutzer. Diese Daten werden nur für Quality of Experience-Berichte (QoE) verwendet.  <br/> |
|**CallTypeSummary-Tabelle** <br/> |Speichert Zusammenfassungsdaten für Anruftypen. Diese Daten werden nur für Quality of Experience-Berichte (QoE) verwendet.  <br/> |
   
**Tabellen des Monitoring Servers für die interne Verwendung**

|**Table**|**Beschreibung**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Nur für interne Verwendung.  <br/> |
|**DbConfigInt** <br/> |Nur für interne Verwendung.  <br/> |
|**FrontEnd-Tabelle** <br/> |Nur für interne Verwendung.  <br/> |
|**Aufgabentabelle** <br/> |Nur für interne Verwendung.  <br/> |
|**SummaryTableConfiguration** <br/> |Nur für interne Verwendung.  <br/> |
|**DbErrorMessage** <br/> |Nur für interne Verwendung.  <br/> |
|**MetricsThreshold** <br/> |Nur für interne Verwendung.  <br/> |
|**DaylightSavingYears** <br/> |Nur für interne Verwendung.  <br/> |
|**TimeZoneConfiguration** <br/> |Ausschließlich für interne Zwecke.  <br/> |
|**TimeZones** <br/> |Ausschließlich für interne Zwecke.  <br/> |
|**CallSummary-Tabelle** <br/> |Ausschließlich für interne Zwecke.  <br/> |
|**DeviceCallSumary-Tabelle** <br/> |Ausschließlich für interne Zwecke.  <br/> |
|**Tenant-Tabelle** <br/> |Ausschließlich für interne Zwecke.  <br/> |
|**VideoCallSummaryTable** <br/> |Ausschließlich für interne Zwecke.  <br/> |
|**ASCallSummaryTable** <br/> |Ausschließlich für interne Zwecke.  <br/> |
   

