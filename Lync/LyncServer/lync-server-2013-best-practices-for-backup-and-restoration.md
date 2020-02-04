---
title: 'Lync Server 2013: bewährte Methoden für Sicherung und Wiederherstellung'
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
ms.openlocfilehash: e51f846d92f5d8cfecbbface31df6543c5c9ac23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Bewährte Methoden für die Sicherung und Wiederherstellung für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Dieser Abschnitt enthält zwei Arten von bewährten Methoden:

  - Bewährte Methoden für Sicherung und Wiederherstellung

  - Bewährte Methoden zum Minimieren der Auswirkungen eines Notfalls

<div>

## <a name="best-practices-for-backup-and-restoration"></a>Bewährte Methoden für Sicherung und Wiederherstellung

Wenden Sie beim Sichern oder Wiederherstellen Ihrer Daten die folgenden bewährten Methoden an, um den Sicherungs-und Wiederherstellungsprozess zu vereinfachen:

  - Führen Sie regelmäßige Sicherungen in angemessenen Abständen aus. Der einfachste und am häufigsten verwendete Backup-Typ und-Rotations Zeitplan ist eine vollständige, nächtliche Sicherung der gesamten SQL Server-Datenbank. Wenn die Wiederherstellung erforderlich ist, erfordert der Wiederherstellungsprozess nur eine Sicherung, und es sollten nicht mehr als die Daten eines Tages verloren gehen.

  - Wenn Sie mithilfe von Cmdlets oder der lync Server-Systemsteuerung Konfigurationsänderungen vornehmen, verwenden Sie das Cmdlet **Export-CsConfiguration** , um eine Snapshot-Sicherung der Topologie-Konfigurationsdatei (XDS. mdf) zu erstellen, nachdem Sie die Änderungen vorgenommen haben, damit die Änderungen nicht verloren gehen, wenn Sie die Datenbanken wiederherstellen müssen. Beachten Sie, dass diese Konfiguration im XML-Format gesichert und als ZIP-Datei komprimiert wird.

  - Stellen Sie sicher, dass der freigegebene Ordner, den Sie zum Sichern von lync Server verwenden möchten, über genügend Speicherplatz verfügt, um alle gesicherten Daten zu speichern.

  - Planen Sie Sicherungen, wenn die lync Server-Auslastung in der Regel gering ist, um die Serverleistung und die Benutzerfreundlichkeit zu verbessern.

  - Stellen Sie sicher, dass der Speicherort, an dem Sie Daten sichern, sicher ist (Wir empfehlen einen Remotestandort).

  - Bewahren Sie die Sicherungsdateien auf, wo Sie verfügbar sein werden, falls Sie die Daten wiederherstellen müssen.

  - Planen und planen Sie regelmäßige Tests der Wiederherstellungsprozesse, die von Ihrer Organisation unterstützt werden.

  - Überprüfen Sie Ihre Sicherungs-und Wiederherstellungsprozesse im voraus, um sicherzustellen, dass Sie wie erwartet funktionieren.

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>Bewährte Methoden zum Minimieren der Auswirkungen eines Notfalls

Die beste Strategie für den Umgang mit katastrophalen Dienstunterbrechungen (verursacht durch nicht verwaltbare Ereignisse wie Stromausfälle oder plötzliche Hardwareausfälle) besteht darin, davon auszugehen, dass dies geschieht, und entsprechend zu planen.

Wenn die lync-Dienste mit einem mindestunterbrechungs-und Ausfallrisiko für Ihre Organisation unternehmenskritisch sind, sollten Sie in der Lage sein, gekoppelte Pools von Front-End-Servern zu implementieren, wie unter [Planen von hoher Verfügbarkeit und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben. Wenn eines dieser Pools einen Notfall hat, kann ein Administrator die Benutzer des Pools so umschalten, dass Sie mit einem mindestausfall von einem anderen Pool bedient werden.

Die Notfall Verwaltungspläne, die Sie im Rahmen ihrer Sicherungs-und Wiederherstellungsstrategie entwickeln, sollten Folgendes umfassen:

  - Sie können Ihr Software-Medium sowie Ihre Software-und Firmware-Updates bereitstellen.

  - Verwalten von Hardware-und Software Datensätzen

  - Regelmäßiges Sichern Ihrer Daten und Überwachen der Integrität Ihrer Sicherungen

  - Schulung Ihrer Mitarbeiter in Disaster Recovery, Dokumentation von Verfahren und Implementierung von Disaster Recovery-Simulationsübungen.

  - Wenn Sie Ersatzhardware zur Verfügung haben oder wenn Sie über einen Service Level Agreement (SLA) verfügen, können Sie sich mit Hardwareanbietern und Lieferanten für den sofortigen Austausch beauftragen.

  - Trennen des Speicherorts ihrer Transaktionsprotokolldateien (LDF-Dateien) und Datenbankdateien (MDF-Dateien)

</div>

</div>

<span> </span>

</div>

</div>

</div>

