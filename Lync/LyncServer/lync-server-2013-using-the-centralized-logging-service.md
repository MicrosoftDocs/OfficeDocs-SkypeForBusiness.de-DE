---
title: Verwenden des zentralisierten Protokollierungsdiensts
TOCTitle: Verwenden des zentralisierten Protokollierungsdiensts
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49890804
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden des zentralisierten Protokollierungsdiensts

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Bei dem Dienst Zentraler Protokollierungsdienst handelt es sich um eine neue Funktion in Lync Server 2013. Er stellt einen verbesserten Ersatz für die beiden Tools **OCSLogger** und **OCSTracer** dar, die in den vorherigen Versionen enthalten waren. Sie können den Dienst Zentraler Protokollierungsdienst zur Ausführung der folgenden Aufgaben verwenden:

  - Starten der Protokollierung für einen oder mehrere Computer und Pools über einen einzelnen Standort und Befehl.

  - Beenden der Protokollierung für einen oder mehrere Computer und Pools über einen einzelnen Standort und Befehl.

  - Durchsuchen von Protokollen auf einen oder mehreren Computern und in einem oder mehreren Pools nach einem einzelnen Standort und Befehl. Sie können den Suchbefehl anpassen, um die gesamten zusammengefassten Protokolle, die auf allen Computern aufgezeichnet und gespeichert wurden, zurückzugeben, oder um ein reduziertes Suchergebnis zu erhalten, in dem nur bestimmte Daten enthalten sind.

  - Konfigurieren Sie die Protokollierungssitzungen wie folgt:
    
      - Definieren Sie ein **Szenario**, oder verwenden Sie ein Standardszenario. Ein *Szenario* im Zentraler Protokollierungsdienst besteht aus einem Bereich (global oder standortbasiert), einem Szenarionamen, mit dem der Zweck des Szenarios angegeben wird, und einem oder mehreren Anbietern. Auf einem Computer können gleichzeitig jeweils zwei Szenarien ausgeführt werden.
    
      - Sie können einen vorhandenen *Anbieter* verwenden oder einen neuen Anbieter erstellen. Der *Anbieter* definiert, was bei der Protokollierungssitzung erfasst wird, welche Detailebene gilt, welche Komponenten nachverfolgt werden und welche Flags angewendet werden.
        

        > [!TIP]
        > Wenn Sie mit der Verwendung von OCSLogger vertraut sind: Der Begriff <EM>Anbieter</EM> bezieht sich auf die Sammlung der <STRONG>Komponenten</STRONG> (z.&nbsp;B. S4, SIPStack), einen <STRONG>Protokollierungstyp</STRONG> (z.&nbsp;B. WPP, EventLog oder IIS logfile), eine <STRONG>Ablaufverfolgungsstufe</STRONG> (z.&nbsp;B. All, verbose, debug) sowie <STRONG>Flags</STRONG> (z.&nbsp;B. TF_COMPONENT, TF_DIAG). Diese Elemente werden im Anbieter definiert (eine Windows PowerShell-Variable) und an den Zentraler Protokollierungsdienst-Befehl weitergegeben.

    
      - Konfigurieren Sie die Computer und Pools, von denen Sie Protokolle erfassen möchten.
    
      - Definieren Sie den Bereich der Protokollierungssitzung unter Verwendung der Optionen **Standort** (Ausführung der Protokollierungsaufzeichnung erfolgt nur auf Computern an diesem Standort) bzw. **Global** (Ausführung der Protokollierungsaufzeichnung erfolgt auf allen Computern in der Bereitstellung).

Der Dienst Zentraler Protokollierungsdienst ist besonders leistungsstark und erfüllt nahezu alle Anforderungen zum Behandeln möglicher Probleme, egal ob diese klein oder groß sind. Von der Problemanalyse bis hin zu Leistungsproblemen kann der Zentraler Protokollierungsdienst als wichtiges Tool für alle Administratoren eingesetzt werden. Alle Beispiele werden unter Verwendung der Lync Server-Verwaltungsshell gezeigt. Es gibt eine Befehlszeilenkomponente für den Zentraler Protokollierungsdienst mit der Bezeichnung **CLSController.exe**. Die Hilfe zum Befehlszeilentool wird über das Tool selbst bereitgestellt. Über die Befehlszeile kann jedoch nur eine beschränkte Anzahl an Funktionen ausgeführt werden. Durch die Verwendung der Lync Server-Verwaltungsshell können Sie eine deutlich größere Anzahl an Funktionen und Konfigurationsoptionen nutzen. Es empfiehlt sich, die Lync Server-Verwaltungsshell als bevorzugte Methode zur Verwendung des Zentraler Protokollierungsdiensts einzusetzen.

In den Themen in diesem Abschnitt wird erläutert, wie Sie den Zentraler Protokollierungsdienst verwenden, und es werden Beispiele zur Verwendung der zahlreichen Dienstfunktionen dargestellt.

## In diesem Abschnitt

  - [Übersicht über den zentralisierten Protokollierungsdienst](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst mithilfe von PowerShell](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Grundlegendes zu Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Verwenden von "Start", damit der zentralisierte Protokollierungsdienst Protokolle erfasst](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Verwenden von "Stop" für den zentralisierten Protokollierungsdienst](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Verwenden der Suche in Erfassungsprotokollen, die vom zentralisierten Protokollierungsdienst erstellt wurden](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lesen von Erfassungsprotokollen aus dem zentralisierten Protokollierungsdienst](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

