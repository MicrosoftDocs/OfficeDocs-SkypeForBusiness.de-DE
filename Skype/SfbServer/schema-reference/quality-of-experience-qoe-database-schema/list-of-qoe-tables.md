---
title: Liste von QoE-Tabellen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: Das Datenbankschema besteht aus den folgenden Tabellen.
ms.openlocfilehash: ba6f439d97692a40fd485a2c550da079092d7365
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294915"
---
# <a name="list-of-qoe-tables"></a>Liste von QoE-Tabellen
 
Das Datenbankschema besteht aus den folgenden Tabellen. 
  
**Unterstützende Tabellen**

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[AppSharingMetricsThreshold-Tabelle](appsharingmetricsthreshold.md) <br/> |Speichert optimale und akzeptable Werte für die Qualität der Erfahrungs Metrik, die bei der Anwendungsfreigabe verwendet wird.  <br/> |
|[CodecDescription-Tabelle](codecdescription.md) <br/> |Ordnet eindeutige Codec-IDs dem zugehörigen Codec zu.  <br/> |
|[IPAddress-Tabelle](ipaddress.md) <br/> |Ordnet IP-Adressen den eindeutigen IP-Adress Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden.  <br/> |
|[NetworkConnectionDetail-Tabelle](networkconnectiondetail.md) <br/> |Ordnet Netzwerkverbindungstypen den Netzwerk Verbindungs Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden.  <br/> |
|[PurgeSettings-Tabelle (QoE)](purgesettings-qoe.md) <br/> |Speichert Informationen, die angeben, ob (und wann) veraltete Quality of Experience-Datensätze automatisch aus der QoE-Datenbank gelöscht werden.  <br/> |
|[TraceRoute-Tabelle](traceroute.md) <br/> |Speichert Routinginformationen für Anrufe.  <br/> |
|[UserAgentDef-Tabelle (QoE)](useragentdef-qoe.md) <br/> |Ordnet die Bezeichner des Benutzer-Agents den beschreibenden Namen des Agents zu.  <br/> |
|[VideoMetricsThreshold-Tabelle](videometricsthreshold.md) <br/> |Speichert optimale und akzeptable Werte für die Qualität der bei Videoanrufen verwendeten Metriken für die Erfahrung.  <br/> |
|[UserAgent-Tabelle](useragent.md) <br/> |Speichert SIP-Benutzer-Agent (Session Initiation Protocol)-Zeichenfolgen und UA-Typen, die in Audio-und Videositzungen verwendet werden.  <br/> |
|[User-Tabelle](user-0.md) <br/> |Speichert Benutzer-, Konferenz-und Telefon-URIs, die in Audio-und Videositzungen verwendet werden.  <br/> |
|[Endpoint-Tabelle](endpoint.md) <br/> |Speichert FQDN-Computernamen von Endpunkten, die an Audio-und Videositzungen teilnehmen.  <br/> |
|[Pool-Tabelle](pool.md) <br/> |Speichert die Namen der Pools, zu denen Metrikdaten gehören.  <br/> |
|[Device-Tabelle](device.md) <br/> |Speichert Aufnahmegeräte und rendergeräte, die in Audio-und Videogesprächen verwendet werden.  <br/> |
|[DeviceDriver-Tabelle](devicedriver.md) <br/> |Speichert den Treiber für das Aufnahmegerät und das Render-Gerät, die in Audio-und Videoanrufen verwendet werden.  <br/> |
|[Conference-Tabelle](conference.md) <br/> |Speichert Konferenz-URIs für Konferenzszenarien oder Dialogfelder für andere Szenarien.  <br/> |
|[SessionCorrelation-Tabelle](sessioncorrelation.md) <br/> |Speichert CorrelationId für PSTN-Anrufe.  <br/> |
|[PayloadDescription-Tabelle](payloaddescription.md) <br/> |Speichert den in Audio-und Videoanrufen verwendeten Codec.  <br/> |
|[AppliedBandwidthSource-Tabelle](appliedbandwidthsource.md) <br/> |Speichert die in Audio-und Videoanrufen verwendete Bandbreiten Quelle.  <br/> |
|[MacAddress-Tabelle](macaddress.md) <br/> |Speichert die Mac-Adresse der Endpunkte, die an Audio-und Videositzungen teilnehmen.  <br/> |
|[Dialog-Tabelle](dialog.md) <br/> |Speichert die Dialog-ID für Audio-und Videositzungen.  <br/> |
|[Region-Tabelle](region.md) <br/> |Speichert die in der NCS-Einstellung definierte netzwerkregion.  <br/> |
|[UserSite-Tabelle](usersite.md) <br/> |Speichert die in der NCS-Einstellung definierte Netzwerk Website.  <br/> |
|[Subnet-Tabelle](subnet.md) <br/> |Speichert das in der NCS-Einstellung definierte Subnetz.  <br/> |
|[MonitoredRegionLink-Tabelle](monitoredregionlink.md) <br/> |Speichert den in der NCS-Einstellung definierten Link "Region".  <br/> |
|[MonitoredUserSiteLink-Tabelle](monitoredusersitelink.md) <br/> |Speichert die in der NCS-Einstellung definierten Netzwerkstandort Links.  <br/> |
|[EndpointSubnet-Tabelle](endpointsubnet.md) <br/> |Speichert das Subnetz des Endpunkts, der an einer Audio-und Videositzung teilnimmt.  <br/> |
|[Servertabelle](server.md) <br/> |Speichert den FQDN oder die IP-Adresse des Servers, den das Medium durchläuft.  <br/> |
   
**Tabellen für Metrikdaten**

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[AppSharingStream-Tabelle](appsharingstream.md) <br/> |Speichert die Qualität der Erfahrungswerte für die netzwerkdatenströme, die für die Anwendungsfreigabe verwendet werden. Metrik für die Qualität der Erfahrung für die netzwerkdatenströme, die für die Anwendungsfreigabe verwendet werden.  <br/> |
|[Session-Tabelle](session.md) <br/> |Speichert allgemeine Informationen zu einer Audio-oder Audio/Video-Sitzung. Eine Sitzung ist als Audio-oder Video-SIP-Dialogfeld zwischen zwei Endpunkten definiert.  <br/> |
|[MediaLine-Tabelle](medialine-0.md) <br/> |Speichert Informationen zu jeder medienzeile in einer Sitzung. Eine medienzeile ist eine Sammlung von einem oder mehreren Audio-und Videodatenströmen. In der Regel besitzt eine einzelne medienzeile zwei Streams, entweder Audio oder Video.  <br/> |
|[AudioStream-Tabelle](audiostream.md) <br/> |Speichert Qualitäts Metriken für Audio-Medien für jeden Audiostream in der Medien Linie.  <br/> |
|[AudioSignal-Tabelle](audiosignal.md) <br/> |Speichert Qualitäts Metriken für Audiomedien in der medienzeile. Dazu gehören akustische Echo Unterdrückungs-und AGC-Metriken (Automatic Gain Control).  <br/> |
|[VideoStream-Tabelle](videostream.md) <br/> |Speichert Qualitäts Metriken für Video Medien für jeden Audiostream in der Medien Linie.  <br/> |
|[AudioClientEvent-Tabelle](audioclientevent.md) <br/> |Speichert die von der Client Veranstaltung gesammelten Qualitäts Metriken für Audio-Medien.  <br/> |
|[VideoClientEvent-Tabelle](videoclientevent.md) <br/> |Speichert Qualitäts Metriken für Video Medien, die vom Clientereignis gesammelt wurden.  <br/> |
|**DiagnosticData-Tabelle** <br/> |Speichert Diagnosedaten, die nur für die interne Verwendung vorgesehen sind.  <br/> |
   
**Tabellen für Zusammenfassungsdaten**

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|**ServerSummary-Tabelle** <br/> |Speichert Zusammenfassungsdaten für die Server, diese Daten werden nur für QoE-Berichte (Quality of Experience) verwendet.  <br/> |
|**UserSummary-Tabelle** <br/> |Speichert Zusammenfassungsdaten für Benutzer, diese Daten werden nur für QoE-Berichte verwendet.  <br/> |
|**CallTypeSummary-Tabelle** <br/> |Speichern von Zusammenfassungsdaten für Anruftypen werden diese Daten nur für QoE-Berichte verwendet.  <br/> |
   
**Tabellen für die interne Verwendung durch Monitoring Server**

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Nur für interne Verwendung.  <br/> |
|**DbConfigInt** <br/> |Nur für interne Verwendung.  <br/> |
|**Frontend-Tabelle** <br/> |Nur für interne Verwendung.  <br/> |
|**Aufgaben Tabelle** <br/> |Nur für interne Verwendung.  <br/> |
|**SummaryTableConfiguration** <br/> |Nur für interne Verwendung.  <br/> |
|**Dberrormessage** <br/> |Nur für interne Verwendung.  <br/> |
|**MetricsThreshold** <br/> |Nur für interne Verwendung.  <br/> |
|**DaylightSavingYears** <br/> |Nur für interne Verwendung.  <br/> |
|**TimeZoneConfiguration** <br/> |Nur für interne Verwendung.  <br/> |
|**Zeitzonen** <br/> |Nur für interne Verwendung.  <br/> |
|**CallSummary-Tabelle** <br/> |Nur für interne Verwendung.  <br/> |
|**DeviceCallSumary-Tabelle** <br/> |Nur für interne Verwendung.  <br/> |
|**Mandantentabelle** <br/> |Nur für interne Verwendung.  <br/> |
|**VideoCallSummaryTable** <br/> |Nur für interne Verwendung.  <br/> |
|**ASCallSummaryTable** <br/> |Nur für interne Verwendung.  <br/> |
   

