---
title: 'Lync Server 2013: Softwareanforderungen für Verwaltungstools'
TOCTitle: Softwareanforderungen für Verwaltungstools
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg195653(v=OCS.15)
ms:contentKeyID: 49293564
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Softwareanforderungen für Verwaltungstools in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Thema wird die Software beschrieben, die neben den Betriebssystemanforderungen erforderlich ist, um die Lync Server 2013-Verwaltungstools zu installieren und zu verwenden.

## Microsoft .NET Framework 4.5

Die 64-Bit-Edition von Microsoft .NET Framework 4.5 ist für Lync Server 2013 erforderlich.

## Windows PowerShell 3.0

Windows PowerShell 3.0 ist zum Ausführen einer beliebigen Komponente von Microsoft Lync Server 2013 erforderlich. Weitere Informationen finden Sie unter [Installieren von Windows PowerShell 3.0 für Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

## Windows Installer, Version 4.5

Lync Server 2013 verwendet Windows Installer-Technologie für die Installation, Deinstallation und Verwaltung verschiedener Serverrollen. Windows Installer, Version 4.5, ist als weitervertreibbare Komponente für das Windows Server-Betriebssystem verfügbar. Windows Installer 4.5 ist im Lieferumfang von Windows Server 2012 R2, Windows Server 2012 und Windows Server 2008 R2 enthalten, was bedeutet, dass Sie das Dienstprogramm für keinen Computer herunterladen müssen, auf dem Lync Server 2013 ausgeführt wird. ( Lync Server 2013 kann nur auf Computern installiert werden, auf denen Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2 ausgeführt wird.)

Wenn Sie allerdings Lync Server-Verwaltungsshell oder Lync Server Topology Builder auf einer Administrator-Workstation installieren möchten, müssen Sie möglicherweise Windows Installer 4.5 herunterladen. Dieses Dienstprogramm ist im Lieferumfang von Windows 7 und Windows 2008 R2, aber nicht von früheren Versionen des Windows-Betriebssystems enthalten. Sie können Windows Installer 4.5 auf dem Microsoft Download Center unter <http://go.microsoft.com/fwlink/p/?linkid=197395> herunterladen.

## Microsoft Silverlight 5-Browser-Plug-In

Die Systemsteuerung für Lync Server 2013 ist ein webbasiertes Tool und erfordert die Installation der neuesten Version des Microsoft Silverlight 5-Browser-Plug-Ins. Wenn beim Start der Systemsteuerung für Lync Server 2013 diese Software nicht oder in einer früheren Version installiert ist, werden Sie von der Systemsteuerung für Lync Server 2013 zur Installation der erforderlichen Version aufgefordert.

## Siehe auch

#### Konzepte

[Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  

#### Weitere Ressourcen

[Infrastrukturanforderungen für Verwaltungstools in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Erforderliche Administratorrechte und Gruppenmitgliedschaften für die Installation und Verwaltung von Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

