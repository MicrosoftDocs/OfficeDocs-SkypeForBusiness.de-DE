---
title: Systemsteuerung – Übersicht
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/13/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: Dieser Artikel bietet eine Übersicht über die neue Systemsteuerung.
ms.openlocfilehash: 7def5267b88260b66b6aa345c9585b83659f6ea3
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2021
ms.locfileid: "61625936"
---
# <a name="control-panel"></a>Systemsteuerung

Die aktuelle Systemsteuerung ist eine neue Version der älteren Systemsteuerung, mit der sie zusammen vorhanden ist. Die neue Systemsteuerung ist aus dem kumulativen Update vom Juli 2019 entstanden. Es hilft bei der Verwaltung der Konfiguration von Servern, Benutzern, Clients und Geräten in der Umgebung einer Organisation.

Die alte Systemsteuerung funktioniert möglicherweise nicht, da die Silverlight-Technologie am 12. Oktober 2021 die Phase "Ende des Supports" erreicht hat. Weitere Informationen finden Sie unter [Silverlight-Supportende.](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788)

> [!NOTE]
> Informationen zur älteren Systemsteuerung finden Sie in der [Systemsteuerung,](../SfbServer/management-tools/install-and-open-administrative-tools.md)und navigieren Sie zum Abschnitt **Skype for Business Server Systemsteuerung.**

## <a name="access-control-panel"></a>Zugriffssteuerung

Um die neue Systemsteuerung im Browser zu starten, geben Sie https:// &lt; Pool-FQDN &gt; /macp oder eine konfigurierte einfache URL ein.

Die neue Systemsteuerung enthält häufig verwendete Menüelemente, die die meisten Anforderungen der Organisation erfüllen. Es gibt einige Menüelemente aus der älteren Systemsteuerung, die in der neuen Systemsteuerung nicht verfügbar sind. Es gibt jedoch eine Option für den Benutzer, die Funktionen in diesen Menüelementen über PowerShell-Cmdlets zu nutzen. Weitere Informationen finden Sie in der tabelle unten.

> [!NOTE]
> Die Dokumentation für andere Menüelemente wird anschließend phasenweise zur Verfügung gestellt.

## <a name="client"></a>Client

|Untermenü  |Informationsquelle für Cmdlet  |
|---------|---------|
|Clientversionsrichtlinie         |    [Clientversionsrichtlinie](use-powershell-client-menu.md#client-version-policy)     |
|Clientversionskonfiguration      |  [Clientversionskonfiguration](use-powershell-client-menu.md#client-version-configuration)       |
|Geräteaktualisierung    | [Geräteaktualisierung](use-powershell-client-menu.md#device-update)        |
|Testgerät     | [Testgerät](use-powershell-client-menu.md#test-device)        |
|Geräteprotokollkonfiguration         |    [Geräteprotokollkonfiguration](use-powershell-client-menu.md#device-log-configuration)     |
|Gerätekonfiguration         |    [Gerätekonfiguration](use-powershell-client-menu.md#device-configuration)     |
|Mobilitätsrichtlinie         |    [Mobilitätsrichtlinie](use-powershell-client-menu.md#mobility-policy)     |
|Konfiguration von Pushbenachrichtigungen         |    [Konfiguration von Pushbenachrichtigungen](use-powershell-client-menu.md#push-notification-configuration)     |

## <a name="security"></a>Sicherheit

|Untermenü  |Informationsquelle für Cmdlet  |
|---------|---------|
|Registrar         |    [Registrar](use-powershell-security-menu.md#registrar)     |
|Webdienst      |  [Webdienst](use-powershell-security-menu.md#web-service)       |
|PIN-Richtlinie    | [PIN-Richtlinie](use-powershell-security-menu.md#pin-policy)        |

## <a name="im-and-presence"></a>Sofortnachrichten und Anwesenheit

|Untermenü  |Informationsquelle für Cmdlet  |
|---------|---------|
|Dateifilter         |    [Dateifilter](use-powershell-im-and-presence-menu.md#file-filter)     |
|URL-Filter      |  [URL-Filter](use-powershell-im-and-presence-menu.md#url-filter)       |

## <a name="monitoring-and-archiving"></a>Überwachen und Archivieren

|Untermenü  |Informationsquelle für Cmdlet  |
|---------|---------|
|Aufzeichnung von Kommunikationsdatensätzen       |    [Aufzeichnung von Kommunikationsdatensätzen](use-powershell-monitoring-and-archiving-menu.md#call-detail-recording)     |
|Quality of Experience-Daten      |  [Quality of Experience-Daten](use-powershell-monitoring-and-archiving-menu.md#quality-of-experience-data)       |
|Archivierungsrichtlinie       |    [Archivierungsrichtlinie](use-powershell-monitoring-and-archiving-menu.md#archiving-policy)     |
|Archivierungskonfiguration      |  [Archivierungskonfiguration](use-powershell-monitoring-and-archiving-menu.md#archiving-configuration)       |

## <a name="network-configuration"></a>Netzwerkkonfiguration

|Untermenü  |Informationsquelle für Cmdlet  |
|---------|---------|
|Ortungsrichtlinie       |    [Standortrichtlinie](use-powershell-network-configuration-menu.md#location-policy)     |
|Bandbreitenrichtlinie      |  [Bandbreitenrichtlinie](use-powershell-network-configuration-menu.md#bandwidth-policy)       |
|Region       |    [Region](use-powershell-network-configuration-menu.md#region)     |
|Website      |  [Site](use-powershell-network-configuration-menu.md#site)       |
|Subnetz      |  [Subnetz](use-powershell-network-configuration-menu.md#subnet)       |
|Regionslink       |    [Regionslink](use-powershell-network-configuration-menu.md#region-link)     |
|Regionsroute      |  [Regionsroute](use-powershell-network-configuration-menu.md#region-route)       |

## <a name="topology"></a>Topologie

|Untermenü  |Informationsquelle für Cmdlet  |
|---------|---------|
|Status       |    [Status](use-powershell-topology-menu.md#status)     |
|Serveranwendung      |  [Serveranwendung](use-powershell-topology-menu.md#server-application)       |
|Einfache URL       |    [Einfache URL](use-powershell-topology-menu.md#simple-url)     |
|Vertrauenswürdige Anwendung       |    [Vertrauenswürdige Anwendung](use-powershell-topology-menu.md#trusted-application)     |
