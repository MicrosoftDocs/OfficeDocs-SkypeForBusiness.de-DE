---
title: 'Lync Server 2013: Überwachen des Betriebssystems'
TOCTitle: Überwachen des Betriebssystems
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn720918(v=OCS.15)
ms:contentKeyID: 62240044
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überwachen des Betriebssystems in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-01-26_

Sie müssen die Leistung aller Server und Komponenten in Lync Server 2013 überwachen. Eine der wichtigsten Komponenten ist natürlich das Betriebssystem selbst. Lync Server 2013 unterstützt x64-Editionen der folgenden Betriebssysteme:

  - Windows Server 2008 R2

  - Windows Server 2012 und Windows Server 2012 R2

Die transparenteste Methode zum Überwachen eines Betriebssystems ist die Verwendung des Windows Server Operating System Management Packs. Es umfasst die wesentlichen Überwachungsgrundlagen wie Leistung, Integrität und Verfügbarkeit für Computer, auf denen Windows Server 2012, Windows Server 2012 R2 und Windows Server 2008 R2 ausgeführt werden.

Durch das Erkennen, Erstellen von Warnungen und automatische Reagieren auf wichtige Ereignisse und Leistungsindikatoren verringern diese Management Packs die Zeit zum Beheben von Problemen und steigern die allgemeine Verfügbarkeit und Leistung von Systemen, auf denen die Windows Server-Betriebssysteme ausgeführt werden.

Abgesehen von entsprechenden Windows Server Management Packs für System Center Operations Manager können die folgenden Systemtools und Ressourcen verwendet werden, um die Integrität des Betriebssystems zu überwachen (abhängig von der Betriebssystemversion).

## Windows Server 2008 R2

Windows Server 2008 R2 enthält die folgenden zusätzlichen Features und Tools, die Administratoren bei einer grundlegenden Betriebssystemüberwachung und -verwaltung unterstützen:

  - Der **Windows-Ressourcenmonitor** ist ein leistungsstarkes Tool, um zu verstehen, wie Systemressourcen von Prozessen und Diensten verwendet werden. Zusätzlich zur Überwachung des Ressourceneinsatzes in Echtzeit kann ein Ressourcenmonitor dazu beitragen, nicht reagierende Prozesse zu analysieren, zu erkennen, welche Anwendungen Dateien verwenden, und Prozesse und Dienste zu steuern.

  - Die **Zuverlässigkeitsanalysekomponente** ist ein mitgelieferter Agent, der detaillierte Erfahrungsinformationen zur Systemauslastung und -zuverlässigkeit bereitstellt. Diese Informationen werden über eine WMI-Schnittstelle zur Verwendung durch tragbare Lesesysteme zur Verfügung gestellt. Entwickler können mit der über eine WMI-Schnittstelle verfügbar gemachten Zuverlässigkeitsanalysekomponente Anwendungen überwachen und analysieren und so die Zuverlässigkeit und Leistung steigern.

  - **Windows Server 2008 R2** verwendet die integrierte Zuverlässigkeitsanalysekomponente, um einen Zuverlässigkeitsindex zu berechnen, der Informationen über die allgemeine Systemauslastung und -stabilität über die Zeit bereitstellt. Die Zuverlässigkeitsanalysekomponente verfolgt außerdem alle wichtigen Änderungen am System, die sich auf die Stabilität auswirken können, zum Beispiel Windows-Updates und Anwendungsinstallationen.

## Windows Server 2008Windows-Zuverlässigkeits- und Leistungsüberwachung

Die Windows-Zuverlässigkeits- und Leistungsüberwachung ist ein MMC-Snap-In, das die Funktionalität früherer eigenständiger Tools kombiniert, darunter Leistungsprotokolle und -warnungen, Server Performance Advisor und Systemmonitor. Es stellt eine grafische Oberfläche für das Anpassen der Leistungsdatenerfassung und Ereignisablaufverfolgungssitzungen bereit.

Es umfasst zudem die Zuverlässigkeitsüberwachung, ein MMC Snap-In, das Änderungen am System nachverfolgt, mit Änderungen in der Systemstabilität vergleicht und eine grafische Ansicht der Beziehung bereitstellt.

## Windows-Zuverlässigkeits- und Leistungsüberwachung

Die Windows-Zuverlässigkeits- und Leistungsüberwachung vereint nicht nur die Funktionen einiger zuvor eigenständiger Tools wie Leistungsprotokolle und -warnungen, Systemmonitor und Server Performance Advisor, sondern bietet auch die folgende neue Funktionalität für Windows Server 2008 und Windows Server 2008 R2:

  - Datensammlungssätze

  - Ressourcenansicht

  - Zuverlässigkeitsüberwachung

  - Assistenten und Vorlagen zum Erstellen von Protokollen

Der **Datensammlungssatz** gruppiert Datensammlungen in wiederverwendbare Elemente, die in verschiedenen Leistungsüberwachungsszenarien verwendet werden können. Nachdem eine Gruppe von Datensammlungen als Datensammlungssatz gespeichert wurde, können Vorgänge wie eine Zeitplanung durch das Ändern einer einzigen Eigenschaft für den gesamten Satz angewendet werden. Die Windows-Zuverlässigkeits- und Leistungsüberwachung beinhaltet Standardvorlagen für Datensammlungssätze, mit denen Systemadministratoren sofort beginnen können, Leistungsdaten zu sammeln, die für eine Serverrolle oder ein Überwachungsszenario spezifisch sind.

Die Startseite der Windows-Zuverlässigkeits- und -Leistungsüberwachung ist die neue **Ressourcenansicht**. Auf diesem Bildschirm wird eine grafische Echtzeitübersicht über die CPU-, Datenträger-, Netzwerk- und Arbeitsspeicherauslastung bereitgestellt. Durch Erweiterung dieser überwachten Elemente können Systemadministratoren erkennen, welche Prozesse welche Ressourcen verwenden. In früheren Versionen von Windows waren diese prozessspezifischen Echtzeitdaten nur in begrenzter Form über den Task-Manager verfügbar.

Die **Zuverlässigkeitsüberwachung** berechnet einen Systemstabilitätsindex, der darstellt, ob unerwartete Probleme die Zuverlässigkeit des Systems verringert haben. Ein Diagramm des Stabilitätsindex über die Zeit identifiziert schnell die Daten beim erstmaligen Auftreten der Probleme. Der begleitende Systemstabilitätsbericht stellt Details zur Verfügung, die die Problembehandlung der Ursache für die verringerte Zuverlässigkeit unterstützen. Durch Anzeigen von Änderungen am System (Installation oder Entfernen von Anwendungen, Updates am Betriebssystem oder Hinzufügen oder Ändern von Treibern) neben Fehlern (Anwendungsfehler, Betriebssystemabstürze oder Hardwareausfälle) kann schnell eine Strategie für die Lösung von Problemen entwickelt werden.

Das Hinzufügen von Leistungsindikatoren zu Protokolldateien und das Planen von Start, Beenden und Dauer dieser Leistungsindikatoren kann jetzt über eine **Assistenten-Oberfläche** durchgeführt werden. Darüber hinaus können Systemadministratoren durch das Speichern dieser Konfiguration als Vorlage dasselbe Protokoll auf anderen Computern erfassen, ohne die Prozesse für das Auswählen und Planen der Datensammlung wiederholen zu müssen. Features der Leistungsprotokolle und -warnungen wurden in die Windows-Zuverlässigkeits- und -Leistungsüberwachung integriert und können mit jeder Datensammlung verwendet werden.

