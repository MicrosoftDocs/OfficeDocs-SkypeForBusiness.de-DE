---
title: 'Lync Server 2013: Verwenden des zentralen Protokollierungsdiensts'
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
ms.openlocfilehash: 2fb3687d036f7d72160c8af0e168a40d09c84e4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Verwenden des zentralisierten Protokollierungsdiensts in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Der zentralisierte Protokollierungsdienst ist ein neues Feature in lync Server 2013. Es handelt sich um einen verbesserten Ersatz für die **OCSLogger** -und **OCSTracer** -Tools, die in früheren Versionen bereitgestellt wurden. Sie können den zentralisierten Protokollierungsdienst verwenden, um die folgenden Aufgaben auszuführen:

  - Starten Sie die Protokollierung an einem oder mehreren Computern und Pools von einem einzelnen Standort und Befehl aus.

  - Beenden Sie die Protokollierung an einem oder mehreren Computern und Pools an einem einzigen Speicherort und Befehl.

  - Durchsuchen von Protokollen auf einem oder mehreren Computern und Pools für einen einzelnen Standort und Befehl. Sie können den Suchbefehl so anpassen, dass die gesamte Aggregation von Protokollen zurückgegeben wird, die auf allen Computern erfasst und gespeichert wurden, oder Sie können ein gekürztes Ergebnis zurückgeben, in dem bestimmte Daten erfasst werden.

  - Konfigurieren Sie die Protokollierungssitzungen wie folgt:
    
      - Definieren Sie ein **Szenario** oder verwenden Sie ein Standardszenario. Ein *Szenario* im zentralisierten Protokollierungsdienst besteht aus dem Bereich (Global oder Website), einem Szenarionamen zur Identifizierung des Zwecks des Szenarios und einem oder mehreren Anbietern. Sie können zwei Szenarios zu einem beliebigen Zeitpunkt auf einem Computer ausführen.
    
      - Sie können einen vorhandenen *Anbieter* verwenden oder einen neuen Anbieter erstellen. Der *Anbieter* definiert, was bei der Protokollierungssitzung erfasst wird, welche Detailebene gilt, welche Komponenten nachverfolgt werden und welche Flags angewendet werden.
        
        <div>
        

        > [!TIP]  
        > Wenn Sie mit der Verwendung von OCSLogger vertraut sind: Der Begriff <EM>Anbieter</EM> bezieht sich auf die Sammlung der <STRONG>Komponenten</STRONG> (z. B. S4, SIPStack), einen <STRONG>Protokollierungstyp</STRONG> (z. B. WPP, EventLog oder IIS logfile), eine <STRONG>Ablaufverfolgungsstufe</STRONG> (z. B. All, verbose, debug) sowie <STRONG>Flags</STRONG> (z. B. TF_COMPONENT, TF_DIAG). Diese Elemente werden im Anbieter (eine Windows PowerShell-Variable) definiert und an den Befehl "zentralisierter Protokollierungsdienst" übergeben.

        
        </div>
    
      - Konfigurieren Sie die Computer und Pools, aus denen Sie Protokolle sammeln möchten.
    
      - Definieren Sie den Bereich für die Protokollierungssitzung auf der **Seite** "Optionen" (nur Protokollierungs Aufzeichnungen auf Computern auf dieser Website) oder **Global** (Ausführen der Protokollierungs Aufzeichnung auf allen Computern in der Bereitstellung).

Der zentralisierte Protokollierungsdienst ist äußerst leistungsstark und kann nahezu alle Anforderungen für die Problembehandlung erfüllen – groß oder klein. Von der Ursachenanalyse bis zu Leistungsproblemen kann der zentralisierte Protokollierungsdienst ein wichtiges Tool für jeden Administrator sein. Alle Beispiele werden mithilfe der lync Server-Verwaltungsshell angezeigt. Es gibt eine Befehlszeilenkomponente für den zentralisierten Protokollierungsdienst namens " **CLSController. exe**". Hilfe wird für das Befehlszeilentool über das Tool selbst bereitgestellt. Es gibt jedoch eine begrenzte Anzahl von Funktionen, die Sie über die Befehlszeile ausführen können. Mithilfe der lync Server-Verwaltungsshell haben Sie Zugriff auf eine viel größere und viel mehr konfigurierbare Gruppe von Features. Wenn Sie den zentralisierten Protokollierungsdienst verwenden, sollten Sie die lync Server-Verwaltungsshell immer als die erste und wichtigste Methode beachten.

In den Themen in diesem Abschnitt wird erläutert, wie der zentralisierte Protokollierungsdienst und Beispiele für die Verwendung der zahlreichen Features verwendet werden.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Grundlegendes zu den Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Verwenden von "Start" für den zentralisierten Protokollierungsdienst zum Aufzeichnen von Protokollen in lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Verwenden von "beenden" für den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Verwenden der Suche in Aufzeichnungs Protokollen, die vom zentralisierten Protokollierungsdienst in lync Server 2013 erstellt wurden](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lesen von Aufnahme Protokollen vom zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

