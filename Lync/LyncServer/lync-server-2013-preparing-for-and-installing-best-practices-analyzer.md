---
title: 'Lync Server 2013: Vorbereiten und Installieren von Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f5992b45d8930bac880f66422d10ddbd4b94f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Vorbereiten und Installieren von Best Practices Analyzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

Sie müssen als Mitglied der Gruppe Administratoren angemeldet sein, um die in diesem Thema beschriebenen Aufgaben ausführen zu können.

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>System Anforderungen für die Installation von Best Practices Analyzer

Damit Sie lync Server 2013, Best Practices Analyzer zum Durchsuchen Ihrer Umgebung ausführen können, muss auf dem Computer eine 64-Bit-Version eines der folgenden Betriebssysteme ausgeführt werden:

  - Windows Server 2008 R2 mit Service Pack 1 (SP1) Standard Betriebssystem

  - Windows Server 2008 R2 mit SP1 Enterprise-Betriebssystem

  - Windows Server 2008 R2 mit SP1 Datacenter-Betriebssystem

  - Windows Server 2012 Datacenter-Betriebssystem

  - Windows Server 2012 Standard-Betriebssystem

  - Windows Server 2012 Enterprise-Betriebssystem

  - Windows Server 2012 R2 Datacenter-Betriebssystem

  - Windows Server 2012 R2 Standard-Betriebssystem

  - Windows Server 2012 R2 Enterprise-Betriebssystem

  - Windows 8-Betriebssystem

  - Windows 7-Betriebssystem

Auf dem Computer muss außerdem Folgendes ausgeführt werden:

  - Microsoft .NET Framework 4,5. Bei lync Server 2013 müssen Sie die 64-Bit-Version von Microsoft .NET Framework 4,5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren.

  - Lync Server 2013, Core Components.

  - WMI-abwärts Kompatibilitätspaket. Ausführliche Informationen finden Sie unter [Installieren des WMI-abwärts Kompatibilitätspakets](install-wmi-backward-compatibility-package.md) in der Migrationsdokumentation.

  - Windows PowerShell 3,0. Ausführliche Informationen finden Sie unter [Installieren von Windows PowerShell 3,0 für lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in der Bereitstellungsdokumentation.

Sie können Best Practices Analyzer auf Computern mit einem unterstützten Betriebssystem installieren, das nicht lync Server 2013, Core Components oder WMI-abwärts Kompatibilitätspaket ausführt, aber Sie können Best Practices Analyzer auf diesen Computern nur zum Anzeigen von Berichten verwenden, nicht zum Ausführen von Scans.

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>Auswählen eines Computers für die Installation

Wir empfehlen, dass Sie lync Server 2013, Best Practices Analyzer auf einem Computer installieren, der für die Verwaltung von lync Server 2013 reserviert ist. Sie können das Tool auf einem Server mit lync Server 2013 oder einem Administratorcomputer installieren, auf dem lync Server 2013-Verwaltungstools ausgeführt werden. Wenn Sie das Tool auf einem Server installieren, auf dem lync Server ausgeführt wird, empfehlen wir, dass Sie das Tool verwenden, um nur diesen Server zu überprüfen.

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>Installieren von Best Practices Analyzer

Sie können das Best Practices Analyzer für lync Server 2013 unter [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)herunterladen.

Wenn Sie Best Practices Analyzer installieren möchten, starten Sie die Microsoft Installer-Datei RtcBPA. msi auf dem Computer, auf dem Sie das Tool installieren möchten, und folgen Sie dann den Anweisungen auf dem Bildschirm. Der Standardspeicherort für die Installation der Programmdateien \<ist System\>\\Drive-\\Programmdateien lync\\Server 2013 BPA.

</div>

</div>

<span> </span>

</div>

</div>

</div>

