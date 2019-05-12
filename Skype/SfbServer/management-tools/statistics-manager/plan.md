---
title: Planen von Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Zusammenfassung: Lesen Sie in diesem Thema, um Informationen zu Statistiken Manager für Skype für Business Server zu erfahren.'
ms.openlocfilehash: 97c169b9350801f805672549d8cc68bfa37ce14d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906613"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Planen von Statistics Manager für Skype for Business Server

**Zusammenfassung:** Lesen Sie in diesem Thema, um Informationen zu Statistiken Manager für Skype für Business Server zu erfahren.

 Statistics Manager für Skype for Business Server ist ein leistungsfähiges Tool, mit dem Sie Skype for Business Server-Status- und -Leistungsdaten in Echtzeit anzeigen können. Sie können Leistungsdaten von Hunderten von Servern innerhalb von Sekunden abfragen und die Ergebnisse unmittelbar auf der Statistics Manager-Website anzeigen.

Statistiken-Manager können Sie laufende Leistungsprobleme identifizieren, zeigen Sie die Ergebnisse einer geplanten Änderung für Ihre Umgebung, Nachverfolgen von Ausfällen Auflösung und vieles mehr. Sofort einsetzbar Statistiken Manager wird mit der Key Health Indicator (KHI) Schwellenwerte konfiguriert und eindeutige Bedürfnisse Ihrer Bereitstellung angepasst werden können.

Sie können Statistiken Manager in einer lokalen Bereitstellung bereitstellen, in denen ein einzelner Server alle serverseitigen Statistiken Manager Komponenten hostet. Weitere Informationen zum Bereitstellen von Statistiken-Manager finden Sie unter [Bereitstellen von Statistiken Manager für Skype für Business Server](deploy.md). Wenn Sie bereits über eine vorhandene Bereitstellung von Statistiken Manager verfügen, aber Sie noch nicht, Version 2.0 aktualisiert haben, finden Sie unter [Was ist neu in der Version 2.0](plan.md#BKMK_WhatsNew) und [Statistiken-Manager für Skype für Business Server aktualisieren](upgrade.md).

Dieses Thema enthält die folgenden Abschnitte:

- [Features und Funktionen](plan.md#BKMK_Features)

- [Was ist neu in der Version 2.0](plan.md#BKMK_WhatsNew)

- [Komponenten](plan.md#BKMK_Components)

- [Lokale Bereitstellung](plan.md#BKMK_DeploymentOptions)

- [Anforderungen](plan.md#BKMK_Requirements)

- [Hinweise zur Sicherheit](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Features und Funktionen
<a name="BKMK_Features"> </a>

Statistiken-Manager können Sie:

- Unformatierte Daten für alle Server in Echtzeit anzeigen. (Daten ist eine sehr hohe Fehlerrate bei ermittelt und in weniger als einer Sekunde an die Website gesendet).

- Von Anzeigedaten, die für eine bestimmte Rolle zusammengesetzt wird; beispielsweise Front-End-Server, Vermittlungsserver, Edge-Server und So weiter.

- Nach unten zum Anzeigen von Daten für bestimmte Standorte, bestimmte Pools innerhalb der Website, und klicken Sie dann auf bestimmten Servern innerhalb des Pools der Drilldown erfolgen soll.

- Erstellen Sie benutzerdefinierte Diagramme, sodass sich entschieden, dass die Leistungsindikatoren standardmäßig angezeigt werden.

- Zoomen und Schwenken auf sowohl die X - und y-Achse oder auf der x-Achse nur.

- Verwenden Sie Datumsbereiche oder Punkt in der Zeit zum Filtern von Daten an.

- Ansicht basierend auf Leistung hergestellt Key Health Indikatoren (KHIs). KHIs stellt eine Auflistung von Leistungsindikatoren mit einem fehlerfreien definierten Bereich.

- Zeigen Sie detaillierte Metriken für die einzelnen Indikatoren.

- Vergleichen der Daten in mehrere Auffüllungen oder Server.

- Anzeigen von Berichten latente Leistungsindikator Agents zu identifizieren, die nicht die aktuelle Daten mit dem Dashboard-Dienst reporting sind.

- Speichern Sie eine bestimmte Instanz von Diagrammdaten in einer Datei.

- Ansicht KHIs in Echtzeit, einschließlich Updates. Wenn die Ansicht Historie aktiviert ist, werden nur neue Fehler angezeigt.

  - Alle KHIs gleichzeitig anzeigen

  - Zeigen Sie KHIs an, indem Sie Server (Querformat anzeigen)

  - KHI Ansichtsdefinitionen

## <a name="whats-new-in-release-20"></a>Was ist neu in der Version 2.0
<a name="BKMK_WhatsNew"> </a>

Im folgenden wird beschrieben, was ist neu in der Version 2.0. Wenn Sie eine vorhandene Bereitstellung von Statistiken Manager und Sie noch nicht aktualisiert haben, finden Sie unter [Statistics-Manager für Skype für Business Server aktualisieren](upgrade.md).

- Szenario Ansichten wurden für Edgemedien, Fabric-Zustand, Failover und Registrierung Szenarien hinzugefügt.

- Viele neue Leistungsindikatoren für SQL Server, weitere Skype für Leistungsindikatoren für die Business hinzugefügt wurden und so weiter.

- Watcher-Knoten-Integration für den Statistiken Manager-Agent - Wenn der Agent, auf einem Watcher-Knoten installiert ist wird synthetische Transaktion Statistiken als Leistungsindikatoren zu Statistiken Manager gemeldet werden.

- Zahlreiche Verbesserung der Zuverlässigkeit und Leistung.

So überprüfen Sie die Version der Website für die Statistiken Manager ausgeführte:

- Öffnen Sie im Datei-Explorer (Standardverzeichnis) C:\Program Files\Skype für Business Server StatsMan WebSite\bin

- Klicken Sie mit der rechten Maustaste auf StatsManHubWebSite.dll und zeigen deren Eigenschaften an

- Die Produktversion wird unter den Beschreibungsangaben angezeigt.

## <a name="components"></a>Komponenten
<a name="BKMK_Components"> </a>

Statistiken Manager besteht aus den folgenden Komponenten:

- **Agent.** Ein lightweight-Agent, der auf jedem überwachten Server ausgeführt wird. Der Agent ermöglicht Abruf von Leistungsindikatoren mit lokalen Aggregation konfigurierbar hohes Maß an.

- **Listener.** API des Servers, der Daten von allen Agents empfängt und aggregiert Daten über Auffüllungen.

- **Hub.** Bildet die Client-API für das System, auf den Web-Servern ausgeführt wird, und bietet Echtzeitdaten-Updates für Clients, die über die Website verbunden. (Der Hub wird automatisch als Teil der Website MSI-Datei installiert).

- **Website.** Eine Benutzeroberfläche, die allen im System verfügbaren Features zusammen abruft.

Darüber hinaus erfordert Statistiken Manager **Redis**, einem Öffnen einer Führungslinie basieren Daten Struktur Server für das Zwischenspeichern im Arbeitsspeicher. Weitere Informationen zum Herunterladen von Redis finden Sie unter [Bereitstellen von Statistiken Manager](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Lokale Bereitstellung
<a name="BKMK_DeploymentOptions"> </a>

In einer lokalen Bereitstellung hostet ein einzelnes Servers alle Statistiken Manager serverseitige Komponenten.

Das folgende Diagramm zeigt eine lokale Bereitstellung, in der die Statistiken-Manager-Website, Hub, Listener und Redis Zwischenspeichern System auf einem einzigen Computer gehostet werden. Statistiken Manager überwacht drei Skype für Unternehmensserver, von denen jedes einen einzelnen Agent übertragen von Daten an den Listener haben. Benutzer Verbinden mit einer einzelnen Website alle vom Statistiken Manager aggregierte Daten anzeigen:

![Stats Manager – lokale Bereitstellung](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Voraussetzungen
<a name="BKMK_Requirements"> </a>

Sie müssen die folgenden Anforderungen Software, Netzwerk und Hardware berücksichtigen Sie vor der Bereitstellung von Statistiken-Manager.

### <a name="software-requirements"></a>Softwareanforderungen

- WindowsServer 2016 und 2019

- IIS (automatisch installiert)

- Redis

- Statistiken-Manager-Dienste (automatisch installiert)

- PSExec - remote-Agent-Bereitstellung Aktionen erforderlich

- .NET 4.5 (mit 2012 R2 enthalten) - Agents und serverseitige Komponenten erforderlich
- Laden Sie die [Skype für Business Server, in Echtzeit Statistiken Manager (64-Bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Netzwerkanforderungen


|**Hosting-server**|**Agents**|**Listener**|
|:-----|:-----|:-----|
|Minimale Gigabit Vollduplex Netzwerk.  <br/> |Ausgehende TCP-Port 8443 (anpassbar Portnummer) mit dem Listener kommunizieren.  <br/> |Der Überwachungsport muss auf allen Servern identisch sein.  <br/> |
|Eingehende TCP-Port 80 oder 443 geöffnet, auf die Website zu hosten.  <br/> |||
|Eingehende TCP-Port 8443 (anpassbar Portnummer) für die Agents Daten mit ihm austauschen.  <br/> |||

Während der Installation werden Firewallports für den Listener und die Website automatisch erstellt. Für die Agents wird die Installation davon ausgegangen, dass ausgehende TCP-Verbindungen standardmäßig zugelassen werden.

### <a name="hardware-requirements"></a>Hardwareanforderungen

In einer lokalen Bereitstellung, in dem ein einzelner Server gehostet alle Statistiken Manager serverseitige Komponenten eines Servers mit 16 GB RAM und 4 wird CPU sollte in der Lage, durchschnittlich etwa 150 Samples pro Sekunde unterstützen. Um festzustellen, wie viele Leistungsindikatoren-Agents unterstützt werden können, verwenden Sie die folgende Berechnung aus:

100 Server \*80 Leistungsindikatoren \* 1 Beispiel pro Minute pro Agent / 60 Sekunden = ~ 133 Samples pro Sekunde.

## <a name="security-considerations"></a>Hinweise zur Sicherheit
<a name="BKMK_Security"> </a>

Der gesamte Datenverkehr zwischen Servern wird verschlüsselt.

- Verschlüsselten HTTPS-Datenverkehr wird über Port 8443 (standardmäßig) vom Agent an den Listener Server gesendet werden.

- Der Agent prüft den Fingerabdruck des SSL auf dem Server, um sicherzustellen, dass der Server Listener der erwarteten Empfänger ist. Beachten Sie, dass der Agent bei Zertifikaten die Fingerabdruck-Verifizierung verwendet (anstatt der Kettenverifizierung). Er führt keine vollständige Verifizierung von Zertifikaten durch, weil es möglich ist, selbstsignierte Zertifikate zu verwenden.

- Nachdem der Agent einverstanden ist der Listener authentisch ist, ein Kennwort wird vom Agent, die dann vom Listener überprüft wird angezeigt.

- Der Agent beginnt Leistungsdaten über die Verbindung an den Listener übertragen.

## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_Security"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:

- [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md)

- [Aktualisieren von Statistics Manager für Skype for Business Server](upgrade.md)

- [Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server](troubleshoot.md)
