---
title: Vorbereiten und Installieren von Best Practices Analyzer
TOCTitle: Vorbereiten und Installieren von Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg591347(v=OCS.15)
ms:contentKeyID: 49294035
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vorbereiten und Installieren von Best Practices Analyzer

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Sie müssen als Mitglied der Administratorgruppe angemeldet sein, um die in diesem Thema beschriebenen Aufgaben auszuführen.

## Systemanforderungen für die Installation von Best Practices Analyzer

Um Lync Server 2013 Best Practices Analyzer ausführen und Ihre Umgebung überprüfen zu können, müssen Sie die 64-Bit-Version eines der folgenden Betriebssysteme ausführen:

  - Windows Server 2008 R2 Standard mit Service Pack 1 (SP1)

  - Windows Server 2008 R2 Enterprise SP1

  - Windows Server 2008 R2 Datacenter mit SP1

  - Windows Server 2012 Datacenter

  - Windows Server 2012 Standard

  - Windows Server 2012 Enterprise

  - Windows Server 2012 R2 Datacenter

  - Windows Server 2012 R2 Standard

  - Windows Server 2012 R2 Enterprise

  - Windows 8 

  - Windows 7 

Darüber hinaus muss auf dem Computer folgende Software ausgeführt werden:

  - Microsoft .NET Framework 4.5. Für Lync Server 2013 muss die 64-Bit-Version von Microsoft .NET Framework 4.5 manuell auf dem Server installiert werden, bevor Lync Server 2013 installiert werden kann.

  - Hauptkomponenten von Lync Server 2013

  - Paket für die WMI-Abwärtskompatibilität. Nähere Informationen finden Sie in der Migrationsdokumentation unter [Installieren des Pakets für die Abwärtskompatibilität mit WMI](install-wmi-backward-compatibility-package.md).

  - Windows PowerShell 3.0. Nähere Informationen finden Sie in der Bereitstellungsdokumentation unter [Installieren von Windows PowerShell 3.0 für Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

Sie können Best Practices Analyzer auf Computern mit einem unterstützten Betriebssystem ausführen, auf denen die Hauptkomponenten von Lync Server 2013 oder das Paket für die WMI-Abwärtskompatibilität nicht ausgeführt werden. Best Practices Analyzer kann auf diesen Computern jedoch nur zum Anzeigen von Berichten verwendet werden. Eine Überprüfung der Umgebung ist nicht möglich.

## Auswählen eines Computers für die Installation

Es wird empfohlen, Lync Server 2013 Best Practices Analyzer auf einem dedizierten Computer für die Verwaltung von Lync Server 2013 auszuführen. Sie können das Tool auf einem Server mit Lync Server 2013 oder einem Verwaltungscomputer mit Lync Server 2013-Verwaltungstools ausführen. Wenn Sie das Tool auf einem Server mit Lync Server ausführen, wird empfohlen, das Tool nur zum Überprüfen dieses Servers zu verwenden.

## Installieren von Best Practices Analyzer

Sie können Best Practices Analyzer für Lync Server 2013 unter [http://go.microsoft.com/fwlink/?linkid=266539\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=266539%26clcid=0x407).

Um Best Practices Analyzer zu installieren, führen Sie die Microsoft Installer-Datei "RtcBPA.msi" auf dem Computer aus, auf dem das Tool installiert werden soll, und folgen den Anweisungen auf dem Bildschirm. Der Standardspeicherort für das Installieren der Programmdateien lautet: *\<Systemlaufwerk\>*\\Programme\\Lync Server 2013\\BPA.

