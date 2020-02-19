---
title: 'Lync Server 2013: Überwachen des Betriebssystems'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea10d7dff41f310e41c1257fa858d0b5d9226bdc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a>Überwachen des Betriebssystems in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-01-26_

Sie müssen die Leistung aller Server und Komponenten im lync Server 2013 überwachen. Eine der wichtigsten Komponenten ist natürlich das Betriebssystem selbst. Lync Server 2013 unterstützt x64-Editionen von:

  - Windows Server 2008 R2

  - Windows Server 2012 und Windows Server 2012 R2

Die transparenteste Möglichkeit zum Überwachen eines Betriebssystems ist die Verwendung des Windows Server Operating System Management Packs. Es bietet die grundlegenden Überwachungs Grundlagen wie Leistung, Integrität und Verfügbarkeit für Computer, auf denen Windows Server 2012, Windows Server 2012 R2 und Windows Server 2008 R2 durchführen.

Durch die Erkennung, Warnung und automatische Reaktion auf wichtige Ereignisse und Leistungsindikatoren reduzieren diese Management Packs Lösungszeiten für Probleme und verbessern die allgemeine Verfügbarkeit und Leistung von Systemen mit Windows Server Betriebssysteme.

Neben den relevanten Windows Server Management Packs für System Center Operations Manager können die folgenden System Tools und Ressourcen verwendet werden, um die Integrität des Betriebssystems zu überwachen (je nach Betriebssystemversion).

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 enthält die folgenden zusätzlichen Features und Tools, die Administratoren bei der grundlegenden Betriebssystemüberwachung und-Verwaltung helfen:

  - Der **Windows-Ressourcen Monitor** ist ein leistungsfähiges Tool, um zu verstehen, wie Systemressourcen von Prozessen und Diensten verwendet werden. Zusätzlich zur Überwachung der Ressourcennutzung in Echtzeit kann ein Ressourcen Monitor dazu beitragen, nicht reagierende Prozesse zu analysieren, zu ermitteln, welche Anwendungen Dateien verwenden, und Prozesse und Dienste zu steuern.

  - Die **Komponente zur Zuverlässigkeitsanalyse** ist ein in-Box-Agent, der detaillierte Informationen zur Systemnutzung und Zuverlässigkeit bereitstellt. Diese Informationen werden über eine WMI-Schnittstelle verfügbar gemacht, um Sie für den Verbrauch von tragbaren Reader-Systemen zur Verfügung zu stellen. Durch das verfügbar machen der Komponente für die Zuverlässigkeitsanalyse über eine WMI-Schnittstelle können Entwickler Anwendungen überwachen und analysieren, wodurch Zuverlässigkeit und Leistung erhöht werden.

  - **Windows Server 2008 R2** verwendet die integrierte Komponente für die Zuverlässigkeitsanalyse, um einen Zuverlässigkeits Index zu berechnen, der Informationen über die allgemeine Systemauslastung und-Stabilität im Laufe der Zeit bereitstellt. Die Komponente Zuverlässigkeitsanalyse verfolgt außerdem wichtige Änderungen am System, die sich wahrscheinlich auf die Stabilität auswirken, beispielsweise Windows-Updates und Anwendungsinstallationen.

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Windows Server 2008 Windows-Zuverlässigkeits-und Leistungsüberwachung

Windows-Zuverlässigkeits-und Leistungsüberwachung ist ein MMC-Snap-in, das die Funktionen früherer eigenständiger Tools kombiniert, einschließlich Leistungsprotokolle und Warnungen, Server Leistungs Ratgeber und System Monitor. Es stellt eine grafische Oberfläche zum Anpassen von Leistungsdatensammlung und Ereignisablaufverfolgungssitzungen bereit.

Es umfasst auch Zuverlässigkeitsüberwachung, ein MMC-Snap-in, das Änderungen am System nachverfolgt und diese mit Änderungen in der Systemstabilität vergleicht und eine grafische Ansicht Ihrer Beziehung bereitstellt.

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Windows-Zuverlässigkeits-und Leistungsüberwachung

Während die Windows-Zuverlässigkeits-und Leistungsüberwachung Funktionen einiger ehemaliger eigenständiger Tools wie Leistungsprotokolle und Warnungen sowie System Monitor und Server Leistungs Ratgeber kombinieren, bietet Sie auch einige neue Funktionen für Windows Server 2008 und Windows Server 2008 R2 wie die folgenden:

  - Sammlungssätze

  - Ressourcenansicht

  - Zuverlässigkeitsüberwachung

  - Assistenten und Vorlagen zum Erstellen von Protokollen

Der **Daten sammlersatz** gruppiert Datensammler in wieder verwendbare Elemente für die Verwendung mit unterschiedlichen Leistungs Überwachungsszenarien. Nachdem eine Gruppe von Datensammlungen als Daten sammlersatz gespeichert wurde, können Vorgänge wie das Planen mithilfe einer einzelnen Eigenschaftenänderung auf die gesamte Gruppe angewendet werden. Windows-Zuverlässigkeits-und Leistungsüberwachung enthält Standardvorlagen für den Sammlungs, damit Systemadministratoren sofort Leistungsdaten sammeln können, die für eine Serverrolle oder ein Überwachungsszenario spezifisch sind.

Die Startseite der Windows-Zuverlässigkeits-und Leistungsüberwachung ist der neue **Ressourcen Ansichts** Bildschirm, der eine grafische Übersicht über die CPU-, Datenträger-, Netzwerk-und Speicherauslastung in Echtzeit bietet. Durch das Erweitern dieser überwachten Elemente können Systemadministratoren ermitteln, welche Prozesse welche Ressourcen verwenden. In früheren Versionen von Windows waren diese prozessspezifischen Daten in Echtzeit nur in beschränkter Form im Task-Manager verfügbar.

Die **Zuverlässigkeitsüberwachung** berechnet einen System Stabilitäts Index, der angibt, ob unerwartete Probleme die Zuverlässigkeit des Systems verringert haben. Ein Diagramm des Stabilitäts Index im Laufe der Zeit erkennt schnell Daten, wenn Probleme auftreten begannen. Der zugehörige System Stabilitätsbericht enthält Details zur Problembehandlung bei der Ursache für eine geringere Zuverlässigkeit. Durch Anzeigen von Systemänderungen (Installation oder Entfernung von Anwendungen, Updates des Betriebssystems oder hinzufügen oder Ändern von Treibern) nebeneinander mit Fehlern (Anwendungsfehler, Betriebssystemabstürze oder Hardwarefehler) wird eine Strategie für die Problembehandlung kann schnell entwickelt werden.

Das Hinzufügen von Leistungsindikatoren zu Protokolldateien und das Planen von Start, Stopp und Dauer kann nun über eine **Assistentenschnittstelle**erfolgen. Wenn Sie diese Konfiguration als Vorlage speichern, können Systemadministratoren außerdem dasselbe Protokoll auf anderen Computern erfassen, ohne die Daten Sammlungsauswahl und die Planungsprozesse zu wiederholen. Leistungsprotokolle und Warnungen wurden in die Windows-Zuverlässigkeits-und-Leistungsüberwachung zur Verwendung mit beliebigen Datensammlersätzen integriert.

</div>

</div>

<span> </span>

</div>

</div>

</div>

