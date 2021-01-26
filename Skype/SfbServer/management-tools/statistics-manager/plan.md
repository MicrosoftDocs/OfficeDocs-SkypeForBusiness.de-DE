---
title: Planen von Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Zusammenfassung: In diesem Thema erfahren Sie mehr über Statistics Manager für Skype for Business Server.'
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821825"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Planen von Statistics Manager für Skype for Business Server

**Zusammenfassung:** In diesem Thema erfahren Sie mehr über Statistics Manager für Skype for Business Server.

 Statistics Manager für Skype for Business Server ist ein leistungsstarkes Tool, mit dem Sie Integritäts- und Leistungsdaten von Skype for Business Server in Echtzeit anzeigen können. Sie können alle paar Sekunden Leistungsdaten auf Hunderten von Servern abfragen und die Ergebnisse sofort auf der Statistics Manager-Website anzeigen.

Sie können Statistics Manager verwenden, um laufende Leistungsprobleme zu identifizieren, die Ergebnisse einer geplanten Änderung an Ihrer Umgebung zu sehen, die Lösung von Ausfällen nachverfolgt und vieles mehr. Statistics Manager ist mit Key Health Indicator (KHI)-Schwellenwerten konfiguriert und kann an die individuellen Anforderungen Ihrer Bereitstellung angepasst werden.

Sie können Statistics Manager in einer lokalen Bereitstellung bereitstellen, in der ein einzelner Server alle serverseitigen Statistics Manager-Komponenten hostet. Weitere Informationen zum Bereitstellen von Statistics Manager finden Sie unter [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md). Wenn Sie bereits über eine Bereitstellung von Statistics Manager verfügen, aber noch nicht auf Version 2.0 aktualisiert haben, lesen Sie ["Neues" in Version 2.0](plan.md#BKMK_WhatsNew) und aktualisieren Sie [Statistics Manager für Skype for Business Server](upgrade.md).

Dieses Thema enthält die folgenden Abschnitte:

- [Features und Funktionen](plan.md#BKMK_Features)

- [Neues in Version 2.0](plan.md#BKMK_WhatsNew)

- [Komponenten](plan.md#BKMK_Components)

- [Lokale Bereitstellung](plan.md#BKMK_DeploymentOptions)

- [Anforderungen](plan.md#BKMK_Requirements)

- [Sicherheitsüberlegungen](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Features und Funktionen
<a name="BKMK_Features"> </a>

Statistics Manager ermöglicht Ihnen:

- Zeigen Sie Rohdaten für alle Server in Echtzeit an. (Daten werden mit einer sehr hohen Rate stichprobeniert und in weniger als einer Sekunde an die Website gesendet.)

- Anzeigen von Daten, die für eine bestimmte Rolle aggregiert werden; Beispielsweise Front-End-Server, Vermittlungsserver, Edgeserver und so weiter.

- Führen Sie einen Drilldown aus, um Daten für bestimmte Standorte, bestimmte Pools innerhalb des Standorts und dann bestimmte Server innerhalb des Pools anzeigen.

- Erstellen Sie benutzerdefinierte Diagramme, sodass ausgewählte Leistungsindikatoren standardmäßig angezeigt werden.

- Zoomen und Schwenken auf der X- und der Y-Achse oder nur auf der X-Achse.

- Verwenden Sie Datumsbereiche oder Zeitpunkte zum Filtern von Daten.

- Zeigen Sie die Serverleistung basierend auf etablierten Key Health Indicators (KHIs) an. KHIs stellen eine Sammlung von Leistungsindikatoren mit einem definierten fehlerfreien Bereich dar.

- Zeigen Sie detaillierte Metriken für jeden Indikator an.

- Vergleichen Sie Daten über mehrere Populationen oder Server hinweg.

- Zeigen Sie latente Leistungsindikatorenberichte an, um Agents zu identifizieren, die dem Dashboarddienst keine aktuellen Daten melden.

- Speichern Sie eine bestimmte Instanz von Diagrammdaten in einer Datei.

- Anzeigen von KHIs in Echtzeit, einschließlich Updates. Wenn die Verlaufsansicht aktiviert ist, werden nur neue Fehler angezeigt.

  - Gleichzeitiges Anzeigen aller KHIs

  - Anzeigen von KHIs nach Server (Querformatansicht)

  - Anzeigen von KHI-Definitionen

## <a name="whats-new-in-release-20"></a>Neues in Version 2.0
<a name="BKMK_WhatsNew"> </a>

Im Folgenden werden die Neuen in Version 2.0 beschrieben. Wenn Sie über eine vorhandene Bereitstellung von Statistics Manager verfügen und noch kein Upgrade durchgeführt haben, finden Sie weitere Informationen unter [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).

- Szenarioansichten wurden für Edgemedien-, Fabric-Integritäts-, Poolfailover- und Registrierungsszenarien hinzugefügt.

- Viele neue Leistungsindikatoren wurden für SQL, mehr Skype for Business-Nutzungsindikatoren und so weiter hinzugefügt.

- Integration von Watcher-Knoten für den Statistics Manager-Agent: Wenn der Agent auf einem Watcher-Knoten installiert ist, werden synthetische Transaktionsstatistiken als Leistungsindikatoren zurück an Statistics Manager berichtet.

- Zahlreiche Zuverlässigkeits- und Leistungsverbesserungen.

So überprüfen Sie die Version der Statistics Manager-Website, die Sie ausführen:

- Öffnen Sie im #A0 (Standardverzeichnis) "C:\Programme\Skype for Business Server StatsMan WebSite\bin".

- Klicken Sie mit der rechten Maustaste auf StatsManHubWebSite.dll und zeigen Sie dessen Eigenschaften an.

- Die Produktversion wird in den Beschreibungsdetails angezeigt.

## <a name="components"></a>Komponenten
<a name="BKMK_Components"> </a>

Statistics Manager besteht aus den folgenden Komponenten:

- **Agent.** Ein einfacher Agent, der auf jedem überwachten Server ausgeführt wird. Der Agent ermöglicht das konfigurierbare Abrufen von Leistungsindikatoren mit hoher Rate mit lokaler Aggregation.

- **Listener.** Die serverseitige API, die Daten von allen Agents empfängt und Daten über Populationen hinweg aggregiert.

- **Hub.** Dient als Client-API für das System, wird auf den Webservern ausgeführt und stellt Echtzeitdatenupdates für Clients bereit, die über die Website verbunden sind. (Der Hub wird automatisch als Teil der Website msi installiert.)

- **Website.** Eine Benutzeroberfläche, die alle im System verfügbaren Features zusammenführungst.

Darüber hinaus benötigt Statistics Manager **Redis**, einen Open-Source-Datenstrukturserver für die Zwischenspeicherung im Arbeitsspeicher. Weitere Informationen zum Herunterladen von Redis finden Sie unter [Bereitstellen von Statistics Manager](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Lokale Bereitstellung
<a name="BKMK_DeploymentOptions"> </a>

In einer lokalen Bereitstellung hostet ein einzelner Server alle serverseitigen Statistics Manager-Komponenten.

Das folgende Diagramm zeigt eine lokale Bereitstellung, in der das Statistics Manager-Website-, Hub-, Listener- und Redis-Cache-System auf einem einzelnen Computer gehostet werden. Statistics Manager überwacht drei Skype for Business-Server, von denen jeder einen einzelnen Agent hat, der Daten an den Listener überträgt. Benutzer stellen eine Verbindung mit einer einzelnen Website auf, um alle von Statistics Manager aggregierten Daten anzeigen zu können:

![Stats Manager Lokale Bereitstellung](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Anforderungen
<a name="BKMK_Requirements"> </a>

Sie müssen die folgenden Software-, Netzwerk- und Hardwareanforderungen berücksichtigen, bevor Sie Statistics Manager bereitstellen.

### <a name="software-requirements"></a>Softwareanforderungen

- Windows Server 2016 und 2019

- IIS (automatisch installiert)

- Redis

- Statistics Manager Services (automatisch installiert)

- PSExec – Erforderlich für Remote-Agent-Bereitstellung

- .NET 4.5 (im Lieferumfang von 2012 R2 enthalten) – Erforderlich für Agents und serverseitige Komponenten
- Herunterladen von [Skype for Business Server, Real-Time Statistics Manager (64-Bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Netzwerkanforderungen


|**Hostingserver**|**Agents**|**Listener**|
|:-----|:-----|:-----|
|Minimales Gigabit-Fullduplex-Netzwerk.  <br/> |Ausgehender TCP-Port 8443 (anpassbare Portnummer), um mit dem Listener zu kommunizieren.  <br/> |Der Listenerport muss auf allen Servern identisch sein.  <br/> |
|Eingehender TCP-Port 80 oder 443 zum Hosten der Website geöffnet.  <br/> |||
|Eingehender TCP-Port 8443 (anpassbare Portnummer), mit dem die Agents kommunizieren können.  <br/> |||

Während der Installation werden Firewallports für den Listener und die Website automatisch erstellt. Für die Agents wird bei der Installation davon ausgegangen, dass ausgehende TCP-Verbindungen standardmäßig zulässig sind.

### <a name="hardware-requirements"></a>Hardwareanforderungen

In einer lokalen Bereitstellung, in der ein einzelner Server alle serverseitigen Statistics Manager-Komponenten hostet, sollte ein Server mit 16 GB RAM und 4 CPU im Durchschnitt ca. 150 Stichproben pro Sekunde unterstützen können. Verwenden Sie die folgende Berechnung, um zu ermitteln, wie viele Leistungsindikatoren/Agents Unterstützt werden können:

100 Server 80 Leistungsindikatoren 1 Beispiel pro Minute von jedem \* Agent / 60 Sekunden = ~ \* 133 Beispiele pro Sekunde.

## <a name="security-considerations"></a>Überlegungen zur Sicherheit
<a name="BKMK_Security"> </a>

Der datenverkehr zwischen Servern wird verschlüsselt.

- Verschlüsselter HTTPS-Datenverkehr wird (standardmäßig) über Port 8443 vom Agent an den Listenerserver gesendet.

- Der Agent überprüft den SSL-Fingerabdruck auf dem Server, um sicherzustellen, dass der Listenerserver der erwartete Empfänger ist. Beachten Sie, dass der Agent die Überprüfung des Zertifikatfingerabdrucks (anstelle der Verkettungsüberprüfung) verwendet. Die vollständige Zertifikatüberprüfung wird nicht abgeschlossen, da selbst signierte Zertifikate verwendet werden können.

- Nachdem der Agent bestätigt hat, dass der Listener authentifiziert ist, wird vom Agent ein Kennwort präsentiert, das dann vom Listener überprüft wird.

- Der Agent beginnt mit der Übertragung von Leistungsdaten über die Verbindung an den Listener.

## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_Security"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:

- [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md)

- [Aktualisieren von Statistics Manager für Skype for Business Server](upgrade.md)

- [Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server](troubleshoot.md)
