---
title: 'Lync Server 2013: bewährte Methoden für Sicherung und Wiederherstellung'
description: 'Lync Server 2013: bewährte Methoden für Sicherung und Wiederherstellung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e8875f03a7b4445af8274ef059f3abad4d21ff8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552171"
---
# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Bewährte Methoden für die Sicherung und Wiederherstellung für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

In diesem Abschnitt werden bewährte Methoden für zwei wichtige Bereiche beschrieben:

  - Bewährte Methoden für Sicherung und Wiederherstellung.

  - Bewährte Methoden für die Minimierung der Auswirkungen eines Notfalls.

<div>

## <a name="best-practices-for-backup-and-restoration"></a>Bewährte Methoden für die Sicherung und Wiederherstellung

Wenden Sie beim Sichern oder Wiederherstellen Ihrer Daten die folgenden bewährten Methoden an, um den Sicherungs-und Wiederherstellungsvorgang zu vereinfachen:

  - Führen Sie regelmäßige Sicherungen in geeigneten Zeitabständen aus. Der einfachste und am häufigsten angewendete Sicherungstyp und -zeitplan ist eine vollständige nächtliche Sicherung der gesamten SQL Server-Datenbank. Wenn die Wiederherstellung erforderlich ist, erfordert der Wiederherstellungsprozess dann nur eine Sicherung, und es sollten nicht mehr als die Daten eines Tages verloren gehen.

  - Wenn Sie mithilfe von Cmdlets oder der lync Server-Systemsteuerung Konfigurationsänderungen vornehmen, verwenden Sie das Cmdlet **Export-CsConfiguration** , um eine Snapshot-Sicherung der Topologie-Konfigurationsdatei (XDS. mdf) zu erstellen, damit Sie die Änderungen nicht verlieren, wenn Sie die Datenbanken wiederherstellen müssen. Beachten Sie, dass diese Konfiguration im XML-Format gesichert und als ZIP-Datei komprimiert wird.

  - Stellen Sie sicher, dass der freigegebene Ordner, den Sie für die Sicherung lync Server verwenden möchten, über ausreichend Speicherplatz verfügt, um alle gesicherten Daten zu speichern.

  - Planen Sie Sicherungen, wenn lync Server Nutzung normalerweise niedrig ist, um die Server Leistung und Benutzerfreundlichkeit zu verbessern.

  - Stellen Sie sicher, dass der Speicherort, an dem Sie Daten sichern, gesichert ist (Wir empfehlen einen Remotestandort).

  - Bewahren Sie die Sicherungsdateien auf, in denen Sie verfügbar sein werden, falls Sie die Daten wiederherstellen müssen.

  - Planen und planen Sie regelmäßige Tests der Wiederherstellungsprozesse, die von Ihrer Organisation unterstützt werden.

  - Überprüfen Sie Ihre Sicherungs-und Wiederherstellungsprozesse im voraus, um sicherzustellen, dass Sie erwartungsgemäß funktionieren.

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>Bewährte Methoden für die Minimierung der Auswirkungen eines Notfalls

Die beste Strategie für den Umgang mit katastrophalen Dienstunterbrechungen (verursacht durch nicht verwaltbare Ereignisse wie Stromausfälle oder plötzliche Hardwarefehler) besteht darin, davon ausgehen, dass Sie geschehen werden, und entsprechend zu planen.

Wenn lync Services mit einem Minimum an unterbrechungs-und Ausfallzeiten für Ihre Organisation geschäftskritisch sind, sollten Sie die Implementierung gekoppelter Pools von Front-End-Servern in Betracht gezogen, wie in [Planen für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben. Wenn dann ein solcher Pool einen Notfall aufweist, kann ein Administrator die Benutzer dieses Pools mit einem Minimum an Ausfallzeiten umstellen, um vom anderen Pool bedient zu werden.

Die Notfall Verwaltungspläne, die Sie im Rahmen der Sicherungs-und Wiederherstellungsstrategie entwickeln, sollten Folgendes umfassen:

  - Das aufhalten ihrer Softwaremedien und ihrer Software-und Firmware-Updates ist leicht verfügbar.

  - Führen Sie Unterlagen über Ihre Hardware und Software.

  - Regelmäßiges Sichern Ihrer Daten und Überwachung der Integrität Ihrer Sicherungen

  - Schulen Sie Ihre Mitarbeiter in den Bereichen Notfallwiederherstellung und Dokumentieren von Verfahren, und führen Sie Übungen mit Simulationen der Notfallwiederherstellung durch.

  - Wenn Sie Ersatzhardware zur Verfügung stellen oder wenn Sie über eine Vereinbarung zum Service Level (SLA) verfügen, beauftragen Sie die Hardwareanbieter und Lieferanten für eine sofortige Ersetzung.

  - Speichern Sie die Transaktionsprotokolldateien (LDF-Dateien) getrennt von den Datenbankdateien (MDF-Dateien).

</div>

</div>

<span> </span>

</div>

</div>

</div>

