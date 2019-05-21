---
title: Planen von Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über den Statistik-Manager für Skype for Business Server zu erfahren.'
ms.openlocfilehash: a58ca8ea8ed2d612e00a0705bb28e8d6fe95eb45
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299737"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Planen von Statistics Manager für Skype for Business Server

**Zusammenfassung:** In diesem Thema finden Sie Informationen zu Statistics Manager für Skype for Business Server.

 Statistics Manager für Skype for Business Server ist ein leistungsfähiges Tool, mit dem Sie Skype for Business Server-Status- und -Leistungsdaten in Echtzeit anzeigen können. Sie können Leistungsdaten von Hunderten von Servern innerhalb von Sekunden abfragen und die Ergebnisse unmittelbar auf der Statistics Manager-Website anzeigen.

Sie können den Statistik-Manager verwenden, um fortlaufende Leistungsprobleme zu erkennen, die Ergebnisse einer geplanten Änderung Ihrer Umgebung anzuzeigen, die Auflösung von Ausfällen zu überwachen und vieles mehr. Der Statistik-Manager ist mit KHI-Schwellenwerten (Key Health Indicator) konfiguriert und kann an die individuellen Anforderungen Ihrer Bereitstellung angepasst werden.

Sie können den Statistik-Manager in einer lokalen Bereitstellung bereitstellen, auf der ein einzelner Server alle serverseitigen Statistics Manager-Komponenten hostet. Weitere Informationen zum Bereitstellen des Statistik-Managers finden Sie unter [Bereitstellen des Statistik-Managers für Skype for Business Server](deploy.md). Wenn Sie bereits über eine vorhandene Bereitstellung von Statistik-Manager verfügen, aber noch nicht auf Release 2,0 aktualisiert haben, lesen Sie [Neuerungen in Release 2,0](plan.md#BKMK_WhatsNew) und [Upgrade Statistics Manager für Skype for Business Server](upgrade.md).

Dieses Thema enthält die folgenden Abschnitte:

- [Features und Funktionen](plan.md#BKMK_Features)

- [Neuerungen in Version 2,0](plan.md#BKMK_WhatsNew)

- [Komponenten](plan.md#BKMK_Components)

- [Lokale Bereitstellung](plan.md#BKMK_DeploymentOptions)

- [Anforderungen](plan.md#BKMK_Requirements)

- [Sicherheitsüberlegungen](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>Features und Funktionen
<a name="BKMK_Features"> </a>

Mit Statistik-Manager können Sie Folgendes ausführen:

- Anzeigen unformatierter Daten für alle Server in Echtzeit. (Die Daten werden zu einem sehr günstigen Preis abgetastet und in weniger als einer Sekunde an die Website gesendet.)

- Anzeigen von Daten, die für eine bestimmte Rolle aggregiert sind Beispiel: Front-End-Server, Vermittlungsserver, Edgeserver usw.

- Führen Sie einen Drilldown aus, um Daten für bestimmte Websites, bestimmte Pools innerhalb der Website und dann bestimmte Server im Pool anzuzeigen.

- Erstellen Sie benutzerdefinierte Diagramme, damit ausgewählte Leistungsindikatoren standardmäßig angezeigt werden.

- Zoomen und Schwenken Sie auf der x-und y-Achse oder nur auf der x-Achse.

- Verwenden Sie Datumsbereiche oder Zeitpunkte zum Filtern von Daten.

- Zeigen Sie die Serverleistung basierend auf den festgelegten Schlüssel Integritätsindikatoren (KHIs) an. KHIs stellen eine Sammlung von Leistungsindikatoren mit einem definierten, gesunden Bereich dar.

- Anzeigen detaillierter Metriken für jeden Leistungsindikator

- Vergleichen Sie Daten auf mehreren Populationen oder Servern.

- Zeigen Sie latente Indikator Berichte an, um Agents zu identifizieren, die keine aktuellen Daten an den dashboarddienst melden.

- Speichern Sie eine bestimmte Instanz von Diagrammdaten in einer Datei.

- Anzeigen von KHIs in Echtzeit, einschließlich Updates. Wenn die Verlaufsansicht aktiviert ist, werden nur neue Fehler angezeigt.

  - Alle KHIs gleichzeitig anzeigen

  - Anzeigen von KHIs nach Server (Landschaftsansicht)

  - Anzeigen von KHI-Definitionen

## <a name="whats-new-in-release-20"></a>Neuerungen in Version 2,0
<a name="BKMK_WhatsNew"> </a>

Im folgenden wird beschrieben, welche Neuerungen es in Version 2,0 gibt. Wenn Sie über eine vorhandene Bereitstellung von Statistics Manager verfügen und noch kein Upgrade durchgeführt haben, lesen Sie [Upgrade Statistics Manager für Skype for Business Server](upgrade.md).

- Szenario-Ansichten wurden für Edge-Medien, Fabric-Integrität, Pool-Failover und Registrierungs Szenarien hinzugefügt.

- Viele neue Zähler wurden für SQL-Server, weitere Skype for Business-Nutzungszähler usw. hinzugefügt.

- Watcher-Knoten Integration für den Statistik-Manager-Agent – Wenn der Agent auf einem Watcher-Knoten installiert ist, werden synthetische Transaktionsstatistiken als Leistungsindikatoren zurück zum Statistik-Manager gemeldet.

- Zahlreiche Verbesserungen bei Zuverlässigkeit und Leistung.

So überprüfen Sie die Version der von Ihnen ausgeführten Statistics Manager-Website:

- Öffnen Sie im Datei-Explorer (Standardverzeichnis) C:\Program Files\Skype for Business Server-Statistiker WebSite\bin

- Klicken Sie mit der rechten Maustaste auf StatsManHubWebSite. dll, und zeigen Sie deren Eigenschaften an.

- Die Produktversion wird unter den Beschreibungsangaben angezeigt.

## <a name="components"></a>Komponenten
<a name="BKMK_Components"> </a>

Der Statistik-Manager besteht aus den folgenden Komponenten:

- **Agent.** Ein Lightweight-Agent, der auf jedem überwachten Server ausgeführt wird. Der Agent ermöglicht die konfigurierbare hochfrequente Abfrage von Leistungsindikatoren mit lokaler Aggregation.

- **Listener.** Die serverseitige API, die Daten von allen Agents empfängt und Daten über Populationen aggregiert.

- **Hub.** Fungiert als Client-API für das System, läuft auf dem/den Web-Server (en) und stellt Echtzeit-Datenaktualisierungen für Kunden bereit, die über die Website verbunden sind. (Der Hub wird automatisch als Teil der Website MSI installiert.)

- **Website.** Eine Benutzeroberfläche, die alle im System verfügbaren Features zusammenzieht.

Darüber hinaus benötigt der Statistik- **** Manager einen Open-Source-Datenstruktur Server mit einem Open-Source-Server für die speicherinterne Zwischenspeicherung. Weitere Informationen zum Herunterladen von a/a finden Sie unter [Bereitstellen des Statistik-Managers](deploy.md#BKMK_Deploy) .

## <a name="on-premises-deployment"></a>Lokale Bereitstellung
<a name="BKMK_DeploymentOptions"> </a>

In einer lokalen Bereitstellung hostet ein einzelner Server alle serverseitigen Statistics Manager-Komponenten.

Das folgende Diagramm zeigt eine lokale Bereitstellung, in der die Statistik-Manager-Website, der Hub-, Listener-und das zwischen Speicherungssystem für das System System auf einem einzelnen Computer gehostet werden. Der Statistik-Manager überwacht drei Skype for Business-Server, die jeweils über einen einzigen Agentendaten an den Listener übertragen. Benutzer stellen eine Verbindung mit einer einzelnen Website her, um alle Daten anzuzeigen, die vom Statistik-Manager aggregiert wurden:

![Stats Manager – lokale Bereitstellung](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>Voraussetzungen
<a name="BKMK_Requirements"> </a>

Sie müssen die folgenden Software-, Netzwerk-und Hardwareanforderungen Bedenken, bevor Sie den Statistik-Manager bereitstellen.

### <a name="software-requirements"></a>Softwareanforderungen

- Windows Server 2016 und 2019

- IIS (automatisch installiert)

- Redis

- Statistik-Manager-Dienste (automatisch installiert)

- PSExec – erforderlich für die Remote-Agent-Bereitstellung

- .NET 4,5 (im Lieferumfang von 2012 R2) – erforderlich für Agents und serverseitige Komponenten
- Herunterladen des [Skype for Business-Servers, Echtzeitstatistik-Manager (64-Bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>Netzwerkanforderungen


|**Hostserver**|**Agents**|**Listener**|
|:-----|:-----|:-----|
|Minimales Gigabit-Vollduplex-Netzwerk.  <br/> |Ausgehende TCP-Port 8443 (anpassbare Portnummer) für die Kommunikation mit dem Listener.  <br/> |Der Listener-Port muss auf allen Servern identisch sein.  <br/> |
|Der eingehende TCP-Port 80 oder 443 wird geöffnet, um die Website zu hosten.  <br/> |||
|Eingehenden TCP-Port 8443 (anpassbare Portnummer), damit die Agents damit kommunizieren können.  <br/> |||

Während der Installation werden Firewall-Ports für den Listener und die Website automatisch erstellt. Bei den Agents geht die Installation davon aus, dass ausgehende TCP-Verbindungen standardmäßig zulässig sind.

### <a name="hardware-requirements"></a>Hardwareanforderungen

In einer lokalen Bereitstellung, in der ein einzelner Server alle serverseitigen Statistiken-Manager-Komponenten hostet, sollte ein Server mit 16 GB Arbeitsspeicher und 4 CPUs in der Lage sein, durchschnittlich etwa 150-Beispiele pro Sekunde zu unterstützen. Verwenden Sie die folgende Berechnung, um zu ermitteln, wie viele Leistungsindikatoren/Agents Sie unterstützen können:

100 Server \*80 Counter \* 1 Sample pro Minute von jedem Agenten/60 Sekunden = ~ 133 Samples pro Sekunde.

## <a name="security-considerations"></a>Sicherheitsüberlegungen
<a name="BKMK_Security"> </a>

Der gesamte Datenverkehr zwischen Servern ist verschlüsselt.

- Verschlüsselter HTTPS-Datenverkehr wird über Port 8443 (standardmäßig) vom Agent an den Listener-Server gesendet.

- Der Agent überprüft den SSL-Fingerabdruck auf dem Server, um sicherzustellen, dass der Listener-Server der erwartete Empfänger ist. Beachten Sie, dass der Agent bei Zertifikaten die Fingerabdruck-Verifizierung verwendet (anstatt der Kettenverifizierung). Er führt keine vollständige Verifizierung von Zertifikaten durch, weil es möglich ist, selbstsignierte Zertifikate zu verwenden.

- Nachdem der Agent erfüllt ist, ist der Listener echt, ein Kennwort wird vom Agenten angezeigt, der dann vom Listener überprüft wird.

- Der Agent beginnt mit der Übertragung von Leistungsdaten über die Verbindung mit dem Listener.

## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_Security"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:

- [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md)

- [Aktualisieren von Statistics Manager für Skype for Business Server](upgrade.md)

- [Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server](troubleshoot.md)
