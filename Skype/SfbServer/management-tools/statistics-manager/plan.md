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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über Statistics Manager für Skype for Business Server zu erfahren.'
ms.openlocfilehash: 17b01924db7522e2fefc9fbdf399d223429b6c4a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612074"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Planen von Statistics Manager für Skype for Business Server

**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über Statistics Manager für Skype for Business Server zu erfahren.

 Statistics Manager für Skype for Business Server ist ein leistungsstarkes Tool, mit dem Sie Skype for Business Server Integritäts- und Leistungsdaten in Echtzeit anzeigen können. Sie können alle paar Sekunden Leistungsdaten über Hunderte von Servern abrufen und die Ergebnisse sofort auf der Statistics Manager-Website anzeigen.

Sie können Statistics Manager verwenden, um fortlaufende Leistungsprobleme zu identifizieren, die Ergebnisse einer geplanten Änderung Ihrer Umgebung anzuzeigen, die Behebung von Ausfällen nachzuverfolgen und vieles mehr. Standardmäßig ist Statistics Manager mit KHI-Schwellenwerten (Key Health Indicator) konfiguriert und kann an die individuellen Anforderungen Ihrer Bereitstellung angepasst werden.

Sie können Statistics Manager in einer lokalen Bereitstellung bereitstellen, in der ein einzelner Server alle serverseitigen Statistics Manager-Komponenten hostet. Weitere Informationen zum Bereitstellen von Statistics Manager finden Sie unter [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md). Wenn Sie bereits über eine vorhandene Bereitstellung von Statistics Manager verfügen, aber noch nicht auf Version 2.0 aktualisiert haben, finden Sie weitere Informationen [zu den Neuerungen in Version 2.0](plan.md#BKMK_WhatsNew) und [zum Upgrade von Statistics Manager für Skype for Business Server.](upgrade.md)

Dieses Thema enthält die folgenden Abschnitte:

- [Features und Funktionen](plan.md#BKMK_Features)

- [Neuigkeiten in Version 2.0](plan.md#BKMK_WhatsNew)

- [Komponenten](plan.md#BKMK_Components)

- [Lokale Bereitstellung](plan.md#BKMK_DeploymentOptions)

- [Anforderungen](plan.md#BKMK_Requirements)

- [Sicherheitsüberlegungen](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Features und Funktionen
<a name="BKMK_Features"> </a>

Statistics Manager ermöglicht Folgendes:

- Anzeigen von Rohdaten für alle Server in Echtzeit. (Daten werden mit einer sehr hohen Rate erfasst und in weniger als einer Sekunde an die Website gesendet.)

- Anzeigen von Daten, die für eine bestimmte Rolle aggregiert wurden; Beispielsweise Front-End-Server, Vermittlungsserver, Edgeserver usw.

- Führen Sie einen Drilldown durch, um Daten für bestimmte Standorte, bestimmte Pools innerhalb des Standorts und dann bestimmte Server innerhalb des Pools anzuzeigen.

- Erstellen Sie benutzerdefinierte Diagramme, sodass ausgewählte Indikatoren standardmäßig angezeigt werden.

- Zoomen und schwenken Sie sowohl auf der X- als auch auf der Y-Achse oder nur auf der X-Achse.

- Verwenden Sie Datumsbereiche oder Zeitpunkte zum Filtern von Daten.

- Anzeigen der Serverleistung basierend auf etablierten Schlüsselintegritätsindikatoren (KEY Health Indicators, KHIs). KHIs stellen eine Sammlung von Leistungsindikatoren mit einem definierten fehlerfreien Bereich dar.

- Detaillierte Metriken für jeden Indikator anzeigen.

- Vergleichen Sie Daten auf mehreren Populationen oder Servern.

- Anzeigen von latenten Zählerberichten, um Agents zu identifizieren, die keine aktuellen Daten an den Dashboarddienst melden.

- Speichern Sie eine bestimmte Instanz von Diagrammdaten in einer Datei.

- Anzeigen von KHIs in Echtzeit, einschließlich Updates. Wenn die Verlaufsansicht aktiviert ist, werden nur neue Fehler angezeigt.

  - Gleichzeitiges Anzeigen aller KHIs

  - Anzeigen von KHIs nach Server (Querformatansicht)

  - Anzeigen von KHI-Definitionen

## <a name="whats-new-in-release-20"></a>Neuigkeiten in Version 2.0
<a name="BKMK_WhatsNew"> </a>

Im Folgenden wird beschrieben, was in Version 2.0 neu ist. Wenn Sie über eine vorhandene Bereitstellung von Statistics Manager verfügen und noch kein Upgrade durchgeführt haben, finden Sie unter [Upgrade Statistics Manager Skype for Business Server](upgrade.md).

- Szenarioansichten wurden für Edgemedien-, Fabric Health-, Poolfailover- und Registrierungsszenarien hinzugefügt.

- Viele neue Leistungsindikatoren wurden für SQL Server, mehr Skype for Business Verwendungszähler usw. hinzugefügt.

- Watcher node integration for the Statistics Manager Agent – if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.

- Zahlreiche Zuverlässigkeits- und Leistungsverbesserungen.

So überprüfen Sie die Version der Statistics Manager-Website, die Sie ausführen:

- Öffnen Sie im Datei-Explorer (Standardverzeichnis) C:\Programme\Skype for Business Server StatsMan WebSite\bin

- Klicken Sie mit der rechten Maustaste auf StatsManHubWebSite.dll, und zeigen Sie dessen Eigenschaften an.

- Die Produktversion wird in den Beschreibungsdetails angezeigt.

## <a name="components"></a>Komponenten
<a name="BKMK_Components"> </a>

Statistics Manager besteht aus den folgenden Komponenten:

- **Agent.** Ein einfacher Agent, der auf jedem überwachten Server ausgeführt wird. Der Agent ermöglicht das konfigurierbare Abrufen von Leistungsindikatoren mit hoher Rate mit lokaler Aggregation.

- **Listener.** Die serverseitige API, die Daten von allen Agents empfängt und Daten über Grundgesamtheiten hinweg aggregiert.

- **Hub.** Dient als Client-API für das System, wird auf den Webservern ausgeführt und stellt Echtzeit-Datenupdates für Clients bereit, die über die Website verbunden sind. (Der Hub wird automatisch als Teil der Website-MSI installiert.)

- **Website.** Eine Benutzeroberfläche, die alle im System verfügbaren Features zusammenzieht.

Darüber hinaus erfordert Statistics Manager **Redis**, einen Open Source-Datenstrukturserver für die Zwischenspeicherung im Arbeitsspeicher. Weitere Informationen zum Herunterladen von Redis finden Sie unter [Bereitstellen von Statistics Manager.](deploy.md#BKMK_Deploy)

## <a name="on-premises-deployment"></a>Lokale Bereitstellung
<a name="BKMK_DeploymentOptions"> </a>

In einer lokalen Bereitstellung hostet ein einzelner Server alle serverseitigen Statistics Manager-Komponenten.

Das folgende Diagramm zeigt eine lokale Bereitstellung, in der das Statistics Manager-Website-, Hub-, Listener- und Redis-Zwischenspeicherungssystem auf einem einzelnen Computer gehostet wird. Statistics Manager überwacht drei Skype for Business Server, von denen jeder über einen einzelnen Agent verfügt, der Daten an den Listener überträgt. Benutzer stellen eine Verbindung zu einer einzelnen Website her, um alle vom Statistics Manager aggregierten Daten anzuzeigen:

![Lokale Bereitstellung von Stats Manager](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Anforderungen
<a name="BKMK_Requirements"> </a>

Sie müssen die folgenden Software-, Netzwerk- und Hardwareanforderungen berücksichtigen, bevor Sie Statistics Manager bereitstellen.

### <a name="software-requirements"></a>Softwareanforderungen

- Windows Server 2016 und 2019

- IIS (automatisch installiert)

- Redis

- Statistics Manager-Dienste (automatisch installiert)

- PSExec – Erforderlich für die Bereitstellung von Remote-Agents

- .NET 4.5 (im Lieferumfang von 2012 R2 enthalten) – Erforderlich für Agents und serverseitige Komponenten
- Herunterladen der [Skype for Business Server, Real-Time Statistics Manager (64-Bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Netzwerkanforderungen


|**Hostingserver**|**Agents**|**Listener**|
|:-----|:-----|:-----|
|Minimales Vollständigduplex-Netzwerk für das Gesamteindrucksmodul.  <br/> |Ausgehender TCP-Port 8443 (anpassbare Portnummer) für die Kommunikation mit dem Listener.  <br/> |Der Listener-Port muss auf allen Servern identisch sein.  <br/> |
|Eingehender TCP-Port 80 oder 443 zum Hosten der Website geöffnet.  <br/> |||
|Eingehender TCP-Port 8443 (anpassbare Portnummer), damit die Agents mit ihm kommunizieren können.  <br/> |||

Während der Installation werden Firewallports für listener und die Website automatisch erstellt. Für die Agents geht die Installation davon aus, dass ausgehende TCP-Verbindungen standardmäßig zulässig sind.

### <a name="hardware-requirements"></a>Hardwareanforderungen

In einer lokalen Bereitstellung, in der ein einzelner Server alle serverseitigen Statistics Manager-Komponenten hostet, sollte ein Server mit 16 GB RAM und 4 CPU durchschnittlich ca. 150 Beispiele pro Sekunde unterstützen können. Verwenden Sie die folgende Berechnung, um zu ermitteln, wie viele Indikatoren/Agents Sie unterstützen können:

100 Server \* 80 Zähler \* 1 Beispiel pro Minute von jedem Agent / 60 Sekunden = ~ 133 Beispiele pro Sekunde.

## <a name="security-considerations"></a>Überlegungen zur Sicherheit
<a name="BKMK_Security"> </a>

Der gesamte Datenverkehr zwischen Servern wird verschlüsselt.

- Verschlüsselter HTTPS-Datenverkehr wird über Port 8443 (standardmäßig) vom Agent an den Listener-Server gesendet.

- Der Agent überprüft den SSL-Fingerabdruck auf dem Server, um sicherzustellen, dass der Listener-Server der erwartete Empfänger ist. Beachten Sie, dass der Agent die Zertifikatfingerabdrucküberprüfung (anstelle der Verkettungsüberprüfung) verwendet. Die vollständige Zertifikatüberprüfung wird nicht ausgeführt, da es möglich ist, selbstsignate Zertifikate zu verwenden.

- Nachdem der Agent sich vergewissert hat, dass der Listener authentifiziert ist, wird vom Agent ein Kennwort angezeigt, das dann vom Listener überprüft wird.

- Der Agent beginnt mit der Übertragung von Leistungsdaten über die Verbindung an den Listener.

## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_Security"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:

- [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md)

- [Aktualisieren von Statistics Manager für Skype for Business Server](upgrade.md)

- [Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server](troubleshoot.md)
