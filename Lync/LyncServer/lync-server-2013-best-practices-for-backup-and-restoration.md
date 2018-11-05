---
title: Bewährte Methoden für die Sicherung und Wiederherstellung
TOCTitle: Bewährte Methoden für die Sicherung und Wiederherstellung
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202184(v=OCS.15)
ms:contentKeyID: 52056409
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bewährte Methoden für die Sicherung und Wiederherstellung

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

In diesem Abschnitt werden bewährte Methoden für zwei wichtige Bereiche beschrieben:

  - Bewährte Methoden für die Sicherung und Wiederherstellung

  - Bewährte Methoden für die Minimierung der Auswirkungen eines Notfalls

## Bewährte Methoden für die Sicherung und Wiederherstellung

Mit den folgenden bewährten Methoden können Sie den Vorgang der Sicherung und Wiederherstellung von Daten vereinfachen:

  - Führen Sie regelmäßige Sicherungen in geeigneten Zeitabständen aus. Der einfachste und am häufigsten angewendete Sicherungstyp und -zeitplan ist eine vollständige nächtliche Sicherung der gesamten SQL Server-Datenbank. Wenn dann eine Wiederherstellung notwendig ist, wird für den Wiederherstellungsprozess nur eine Sicherung benötigt, und ein etwaiger Datenverlust umfasst nur die Daten eines Tages.

  - Wenn Sie Cmdlets oder die Lync Server-Systemsteuerung verwenden, um Konfigurationsänderungen vorzunehmen, erstellen Sie nach der Durchführung der Änderungen mithilfe des **Export-CsConfiguration**-Cmdlets eine Momentaufnahmensicherung der Konfigurationsdatei der Topologie (**Xds.mdf**), sodass diese Änderungen nicht verloren gehen, falls Sie die Datenbanken wiederherstellen müssen. Beachten Sie, dass diese Konfiguration im XML-Format gesichert und als ZIP-Datei komprimiert wird.

  - Stellen Sie sicher, dass im freigegebenen Ordner, den Sie für die Sicherung von Lync Server verwenden möchten, ausreichend Speicherplatz zur Aufnahme aller gesicherten Daten frei ist.

  - Planen Sie Sicherungen für einen Zeitpunkt, zu dem Lync Server typischerweise wenig genutzt wird, um die Serverleistung zu optimieren und die Auswirkungen auf die Benutzer möglichst gering zu halten.

  - Achten Sie darauf, dass der Speicherort, an dem Sie Daten sichern, sicher ist (empfohlen wird ein Remotestandort).

  - Bewahren Sie Sicherungsdateien für den Fall, dass Sie die Daten wiederherstellen müssen, an leicht zugänglicher Stelle auf.

  - Planen und terminieren Sie regelmäßige Tests der in Ihrer Organisation implementierten Wiederherstellungsprozesse ein.

  - Überprüfen Sie die Sicherungs- und Wiederherstellungsprozesse im Voraus, um sicherzugehen, dass sie wie erwartet funktionieren.

## Bewährte Methoden für die Minimierung der Auswirkungen eines Notfalls

Die beste Vorgehensweise für den Umgang mit Dienstunterbrechungen verheerenden Ausmaßes (verursacht etwa durch Stromausfall oder plötzliche Hardwarefehler) besteht darin: Gehen Sie davon aus, dass es passieren kann, und treffen Sie entsprechende Vorkehrungen. Die Notfallpläne, die Sie als Teil Ihrer Sicherungs- und Wiederherstellungsstrategie entwickeln, sollten Folgendes beinhalten:

Wenn Lync-Dienste, mit einem Minimum an Unterbrechungen und Ausfällen, für Ihr Unternehmen geschäftsentscheidend sind, sollten Sie überlegen, Poolpaare von Front-End-Servern zu implementieren, so wie unter [Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md) beschrieben. Wenn dann bei einem dieser Pools ein Notfall auftritt, kann ein Administrator die Benutzer dieses Pool mit einer minimalen Ausfallzeit auf den anderen Pool umstellen.

Die Notfallpläne, die Sie als Teil Ihrer Sicherungs- und Wiederherstellungsstrategie entwickeln, sollten Folgendes beinhalten:

  - Sorgen Sie dafür, dass Ihre Softwaremedien sowie Software- und Firmwareupdates immer leicht zugänglich sind.

  - Führen Sie Unterlagen über Ihre Hardware und Software.

  - Sichern Sie Ihre Daten regelmäßig, und überwachen Sie die Integrität der Sicherungen.

  - Schulen Sie Ihre Mitarbeiter in den Bereichen Notfallwiederherstellung und Dokumentieren von Verfahren, und führen Sie Übungen mit Simulationen der Notfallwiederherstellung durch.

  - Halten Sie Hardware-Austauschkomponenten bereit; wenn Sie Service Level Agreements (SLAs) mit Hardwareherstellern und -lieferanten abgeschlossen haben, sollte darin der umgehende Ersatz von Hardware geregelt sein.

  - Speichern Sie die Transaktionsprotokolldateien (LDF-Dateien) getrennt von den Datenbankdateien (MDF-Dateien).

