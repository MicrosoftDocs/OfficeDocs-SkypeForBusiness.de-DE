---
title: 'Lync Server 2013: Verwenden des zentralisierten Protokollierungsdiensts'
description: 'Lync Server 2013: Verwenden des zentralisierten Protokollierungsdiensts.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f8b9edf839de889e9f0b01c10311f6b5c70ced8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548521"
---
# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Verwenden des zentralisierten Protokollierungsdiensts in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Der zentralisierte Protokollierungsdienst ist ein neues Feature in lync Server 2013. Er stellt einen verbesserten Ersatz für die beiden Tools **OCSLogger** und **OCSTracer** dar, die in den vorherigen Versionen enthalten waren. Sie können den zentralisierten Protokollierungsdienst verwenden, um die folgenden Aufgaben auszuführen:

  - Starten der Protokollierung für einen oder mehrere Computer und Pools über einen einzelnen Standort und Befehl.

  - Beenden der Protokollierung für einen oder mehrere Computer und Pools über einen einzelnen Standort und Befehl.

  - Durchsuchen von Protokollen auf einen oder mehreren Computern und in einem oder mehreren Pools nach einem einzelnen Standort und Befehl. Sie können den Suchbefehl anpassen, um die gesamten zusammengefassten Protokolle, die auf allen Computern aufgezeichnet und gespeichert wurden, zurückzugeben, oder um ein reduziertes Suchergebnis zu erhalten, in dem nur bestimmte Daten enthalten sind.

  - Konfigurieren Sie die Protokollierungssitzungen wie folgt:
    
      - Definieren Sie ein **Szenario**, oder verwenden Sie ein Standardszenario. Ein *Szenario* im zentralisierten Protokollierungsdienst besteht aus dem Bereich (Global oder Standort), einem Szenarionamen zur Identifizierung des Zwecks des Szenarios und einem oder mehreren Anbietern. Auf einem Computer können gleichzeitig jeweils zwei Szenarien ausgeführt werden.
    
      - Sie können einen vorhandenen *Anbieter* verwenden oder einen neuen Anbieter erstellen. Der *Anbieter* definiert, was bei der Protokollierungssitzung erfasst wird, welche Detailebene gilt, welche Komponenten nachverfolgt werden und welche Flags angewendet werden.
        
        <div>
        

        > [!TIP]  
        > Wenn Sie mit der Verwendung von OCSLogger vertraut sind: Der Begriff <EM>Anbieter</EM> bezieht sich auf die Sammlung der <STRONG>Komponenten</STRONG> (z. B. S4, SIPStack), einen <STRONG>Protokollierungstyp</STRONG> (z. B. WPP, EventLog oder IIS logfile), eine <STRONG>Ablaufverfolgungsstufe</STRONG> (z. B. All, verbose, debug) sowie <STRONG>Flags</STRONG> (z. B. TF_COMPONENT, TF_DIAG). Diese Elemente werden im Anbieter definiert (eine Windows PowerShell Variable) und an den Befehl für den zentralisierten Protokollierungsdienst übergeben.

        
        </div>
    
      - Konfigurieren Sie die Computer und Pools, von denen Sie Protokolle erfassen möchten.
    
      - Definieren Sie den Bereich der Protokollierungssitzung unter Verwendung der Optionen **Standort** (Ausführung der Protokollierungsaufzeichnung erfolgt nur auf Computern an diesem Standort) bzw. **Global** (Ausführung der Protokollierungsaufzeichnung erfolgt auf allen Computern in der Bereitstellung).

Der zentralisierte Protokollierungsdienst ist äußerst leistungsfähig und kann nahezu alle Anforderungen für Problem Behandlungs Probleme erfüllen – groß oder klein. Von der Ursachenanalyse bis hin zu Leistungsproblemen kann der zentralisierte Protokollierungsdienst ein wichtiges Tool für jeden Administrator sein. Alle Beispiele werden mit dem lync Server-Verwaltungsshell angezeigt. Es gibt eine Befehlszeilenkomponente für den zentralisierten Protokollierungsdienst namens **CLSController.exe**. Die Hilfe zum Befehlszeilentool wird über das Tool selbst bereitgestellt. Über die Befehlszeile kann jedoch nur eine beschränkte Anzahl an Funktionen ausgeführt werden. Durch die Verwendung von lync Server-Verwaltungsshell haben Sie Zugriff auf eine viel größere und viel mehr konfigurierbare Gruppe von Features. Wenn Sie den zentralisierten Protokollierungsdienst verwenden, sollten Sie lync Server-Verwaltungsshell immer als die erste und wichtigste Methode berücksichtigen.

In den Themen in diesem Abschnitt wird erklärt, wie der zentralisierte Protokollierungsdienst und Beispiele für die Verwendung der zahlreichen Funktionen verwendet werden.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Grundlegendes zu Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Verwenden von Start für den zentralisierten Protokollierungsdienst zum Erfassen von Protokollen in lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Verwenden von Stop für den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Verwenden der Suche in den vom zentralisierten Protokollierungsdienst in lync Server 2013 erstellten Aufzeichnungs Protokollen](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lesen von Erfassungs Protokollen aus dem zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

