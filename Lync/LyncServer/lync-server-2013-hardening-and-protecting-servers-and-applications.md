---
title: 'Lync Server 2013: Sichern und Schützen von Servern und Anwendungen'
TOCTitle: Sichern und Schützen von Servern und Anwendungen für Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn518331(v=OCS.15)
ms:contentKeyID: 60476346
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sichern und Schützen von Servern und Anwendungen für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Sie sollten Ihr Betriebssystem und Ihre Anwendungen gemäß den bewährten Methoden für die jeweilige Komponente sichern und schützen. In diesem Abschnitt wird beschrieben, wie Sie Anwendungsserver sichern und schützen und mithilfe von Gruppenrichtlinien Sicherheitssperren implementieren.


> [!NOTE]
> Sie können auch die Datenbanken sichern und schützen, die für Ihre Microsoft Lync Server 2013-Bereitstellung verwendet werden. Ausführliche Informationen dazu finden Sie unter <A href="lync-server-2013-hardening-and-protecting-databases.md">Sichern und Schützen der Datenbanken von Lync Server 2013</A>.



## Sichern von Anwendungsservern

Bei Anwendungsservern sollten das Betriebssystem und die Anwendungen gesichert werden. Beispielsweise sollte ein Windows Server 2008-Computer für den Betrieb von Microsoft Internet Security and Acceleration (ISA) Server 2006 auf Betriebssystemebene und auf Anwendungsebene gesichert werden. Dabei sollte die Minimierung der Zahl der Dienste, die vom Server ausgeführt und bereitgestellt werden, ein vorrangiges Ziel sein.

## Sichern von virtuellen Servern

Momentaufnahmen von virtuellen Servern enthalten Kopien der Datenträger des Servers sowie Abbilder von In-Memory-Daten. Beide können sensible Kryptografiedaten enthalten, die eine Angriffsfläche bieten. Für Produktionsserver, die mit Virtualisierung implementiert worden sind, sollten Sie alle Servermomentaufnahmen deaktivieren oder sie auf strikt kontrollierte Weise verwalten. Ausführliche Informationen zum Sichern von virtuellen Servern mit Hyper-V finden Sie im Hyper-V-Sicherheitsleitfaden unter: [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176).

## Gruppenrichtlinien

In Windows Server 2008 und Windows Server 2008 R2 ermöglichen Gruppenrichtlinien eine verzeichnisbasierte Desktopkonfigurationsverwaltung. Mithilfe von Gruppenrichtlinien können Sie Sicherheitssperren implementieren, indem Sie Computer- und Benutzereinstellungen innerhalb eines Gruppenrichtlinienobjekts (GPO) für folgende Bereiche definieren:

  - Registrierungsbasierte Richtlinien

  - Sicherheit

  - Softwareinstallation

  - Skripts

  - Ordnerumleitung

  - Remoteinstallationsdiente

Um dem Administrator eine Benutzeroberfläche zum Konfigurieren dieser Einstellungen bereitzustellen, werden administrative Vorlagen zusammen mit Betriebssystemversionen, Service Pack-Versionen und einigen Anwendungen wie Lync Server 2013 geliefert.

Die Datei Communicator.adm ist eine administrative Vorlage, die mit Lync Server 2013 ausgeliefert wird, im Verzeichnis *%windir%*\\inf\\ installiert wird und eine Schnittstelle zu den Gruppenrichtlinieneinstellungen bietet. Jede Einstellung in der Datei Communicator.adm entspricht einer Einstellung in der Registrierung, die das Verhalten der Anwendung beeinflusst.

Sie können über die Datei GPedit.dll auf die Einstellungen zugreifen. Diese Datei können Sie über die Konsole Active Directory-Benutzer und -Computer und über die Gruppenrichtlinien-Verwaltungskonsole aufrufen.

## Sicherheitseinstellungen in Gruppenrichtlinien

Gruppenrichtlinien enthalten Sicherheitseinstellungen für ein Gruppenrichtlinienobjekt unter Computerkonfiguration/Windows-Einstellungen/Sicherheitseinstellungen, wenn über GPedit.dll darauf zugegriffen wird. Sie können Sicherheitsvorlagen importieren, um Sicherheitseinstellungen für das Gruppenrichtlinienobjekt zu konfigurieren. Der Windows Server 2008-Sicherheitsleitfaden unter [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) und das Windows Server 2008 R2 Security Compliance Management Toolkit unter [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) enthalten eine Reihe von Beispielvorlagen, die Sie auf Ihre individuellen Anforderungen zuschneiden können.

## Bewährte Methoden

  - Sichern Sie alle Serverbetriebssysteme und -anwendungen.

  - Schützen Sie Servermomentaufnahmen und erhöhen Sie die Sicherheit aller virtuellen Server.

  - Implementieren Sie Sicherheitssperren mithilfe von Gruppenrichtlinien.

