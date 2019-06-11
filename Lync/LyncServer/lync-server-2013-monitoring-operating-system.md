---
title: 'Lync Server 2013: Überwachen des Betriebssystems'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2f8124afcf2d1acbde3518ff625d528d6e34a3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a>Überwachen des Betriebssystems in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-01-26_

Sie müssen die Leistung aller Server und Komponenten in lync Server 2013 überwachen. Eine der wichtigsten Komponenten ist natürlich das Betriebssystem selbst. Lync Server 2013 unterstützt x64-Editionen von:

  - Windows Server 2008 R2

  - Windows Server 2012 und Windows Server 2012 R2

Die transparentere Methode zum Überwachen eines Betriebssystems ist die Verwendung des Windows Server-Betriebssystem-Management Packs. Sie stellt die grundlegenden Überwachungs Grundlagen wie Leistung, Integrität und Verfügbarkeit für Computer bereit, auf denen Windows Server 2012, Windows Server 2012 R2 und Windows Server 2008 R2 ausgeführt werden.

Durch die Erkennung, Benachrichtigung und automatische Reaktion auf wichtige Ereignisse und Leistungsindikatoren reduzieren diese Management Packs die auflösungszeiten für Probleme und verbessern die allgemeine Verfügbarkeit und Leistung von Systemen, auf denen der Windows-Server ausgeführt wird. Betriebssysteme.

Neben den relevanten Windows Server-Management Packs für System Center Operations Manager können die folgenden System Tools und-Ressourcen verwendet werden, um den Zustand des Betriebssystems zu überwachen (je nach Betriebssystemversion).

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 umfasst die folgenden zusätzlichen Features und Tools, die Administratoren bei der grundlegenden Überwachung und Verwaltung des Betriebssystems helfen:

  - Der **Windows-Ressourcenmonitor** ist ein leistungsstarkes Tool, um zu verstehen, wie Systemressourcen von Prozessen und Diensten verwendet werden. Zusätzlich zur Überwachung des Ressourceneinsatzes in Echtzeit kann ein Ressourcenmonitor dazu beitragen, nicht reagierende Prozesse zu analysieren, zu erkennen, welche Anwendungen Dateien verwenden, und Prozesse und Dienste zu steuern.

  - Die **Zuverlässigkeitsanalysekomponente** ist ein mitgelieferter Agent, der detaillierte Erfahrungsinformationen zur Systemauslastung und -zuverlässigkeit bereitstellt. Diese Informationen werden über eine WMI-Schnittstelle zur Verwendung durch tragbare Lesesysteme zur Verfügung gestellt. Entwickler können mit der über eine WMI-Schnittstelle verfügbar gemachten Zuverlässigkeitsanalysekomponente Anwendungen überwachen und analysieren und so die Zuverlässigkeit und Leistung steigern.

  - **Windows Server 2008 R2** verwendet die integrierte Komponente für die Zuverlässigkeitsanalyse, um einen Zuverlässigkeits Index zu berechnen, der Informationen zur allgemeinen Systemnutzung und zur Stabilität im Laufe der Zeit bereitstellt. The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Windows Server 2008 Windows-Zuverlässigkeits-und Leistungsüberwachung

Die Windows-Zuverlässigkeits- und Leistungsüberwachung ist ein MMC-Snap-In, das die Funktionalität früherer eigenständiger Tools kombiniert, darunter Leistungsprotokolle und -warnungen, Server Performance Advisor und Systemmonitor. Es stellt eine grafische Oberfläche für das Anpassen der Leistungsdatenerfassung und Ereignisablaufverfolgungssitzungen bereit.

Es umfasst zudem die Zuverlässigkeitsüberwachung, ein MMC Snap-In, das Änderungen am System nachverfolgt, mit Änderungen in der Systemstabilität vergleicht und eine grafische Ansicht der Beziehung bereitstellt.

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Windows-Zuverlässigkeits- und Leistungsüberwachung


Während die Windows-Zuverlässigkeits-und Leistungsüberwachung Funktionen einiger ehemaliger eigenständige Tools wie Leistungsprotokolle und Warnungen sowie System Monitor und Server Leistungs Ratgeber kombinieren, bietet Sie auch einige neue Funktionen für Windows Server 2008 und Windows Server 2008 R2, wie beispielsweise die folgenden:

  - Datensammlungssätze

  - Ressourcenansicht

  - Zuverlässigkeitsüberwachung

  - Assistenten und Vorlagen zum Erstellen von Protokollen

Der **Datensammlungssatz** gruppiert Datensammlungen in wiederverwendbare Elemente, die in verschiedenen Leistungsüberwachungsszenarien verwendet werden können. Nachdem eine Gruppe von Datensammlungen als Datensammlungssatz gespeichert wurde, können Vorgänge wie eine Zeitplanung durch das Ändern einer einzigen Eigenschaft für den gesamten Satz angewendet werden. Die Windows-Zuverlässigkeits- und Leistungsüberwachung beinhaltet Standardvorlagen für Datensammlungssätze, mit denen Systemadministratoren sofort beginnen können, Leistungsdaten zu sammeln, die für eine Serverrolle oder ein Überwachungsszenario spezifisch sind.

Die Startseite der Windows-Zuverlässigkeits- und -Leistungsüberwachung ist die neue **Ressourcenansicht**. Auf diesem Bildschirm wird eine grafische Echtzeitübersicht über die CPU-, Datenträger-, Netzwerk- und Arbeitsspeicherauslastung bereitgestellt. Durch Erweiterung dieser überwachten Elemente können Systemadministratoren erkennen, welche Prozesse welche Ressourcen verwenden. In früheren Versionen von Windows waren diese prozessspezifischen Echtzeitdaten nur in begrenzter Form über den Task-Manager verfügbar.

Die **Zuverlässigkeitsüberwachung** berechnet einen Systemstabilitätsindex, der darstellt, ob unerwartete Probleme die Zuverlässigkeit des Systems verringert haben. Ein Diagramm des Stabilitätsindex über die Zeit identifiziert schnell die Daten beim erstmaligen Auftreten der Probleme. Der begleitende Systemstabilitätsbericht stellt Details zur Verfügung, die die Problembehandlung der Ursache für die verringerte Zuverlässigkeit unterstützen. Durch Anzeigen von Änderungen am System (Installation oder Entfernen von Anwendungen, Updates am Betriebssystem oder Hinzufügen oder Ändern von Treibern) neben Fehlern (Anwendungsfehler, Betriebssystemabstürze oder Hardwareausfälle) kann schnell eine Strategie für die Lösung von Problemen entwickelt werden.

Das Hinzufügen von Leistungsindikatoren zu Protokolldateien und das Planen von Start, Beenden und Dauer dieser Leistungsindikatoren kann jetzt über eine **Assistenten-Oberfläche** durchgeführt werden. Darüber hinaus können Systemadministratoren durch das Speichern dieser Konfiguration als Vorlage dasselbe Protokoll auf anderen Computern erfassen, ohne die Prozesse für das Auswählen und Planen der Datensammlung wiederholen zu müssen. Features der Leistungsprotokolle und -warnungen wurden in die Windows-Zuverlässigkeits- und -Leistungsüberwachung integriert und können mit jeder Datensammlung verwendet werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

