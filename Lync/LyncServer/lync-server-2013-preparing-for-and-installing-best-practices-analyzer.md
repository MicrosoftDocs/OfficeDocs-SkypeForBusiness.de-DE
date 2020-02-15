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
ms.openlocfilehash: 6c97657b42ec4ea26f5300b1d28215d0360b63cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Vorbereiten und Installieren von Best Practices Analyzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

Sie müssen als Mitglied der Administratorgruppe angemeldet sein, um die in diesem Thema beschriebenen Aufgaben auszuführen.

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>Systemanforderungen für die Installation von Best Practices Analyzer

Zum Ausführen von lync Server 2013, Best Practices Analyzer zum Überprüfen Ihrer Umgebung, muss auf dem Computer eine 64-Bit-Version eines der folgenden Betriebssysteme ausgeführt werden:

  - Windows Server 2008 R2 mit Service Pack 1 (SP1) Standard Betriebssystem

  - Windows Server 2008 R2 mit SP1 Enterprise-Betriebssystem

  - Windows Server 2008 R2 mit SP1 Datacenter-Betriebssystem

  - Windows Server 2012 Betriebssystem des Rechenzentrums

  - Windows Server 2012 Standard mäßiges Betriebssystem

  - Windows Server 2012 Betriebssystem des Unternehmens

  - Windows Server 2012 R2 Datacenter-Betriebssystem

  - Windows Server 2012 R2 Standard-Betriebssystem

  - Windows Server 2012 R2 Enterprise-Betriebssystem

  - Windows 8 Betriebssystem

  - Windows 7-Betriebssystem

Darüber hinaus muss auf dem Computer folgende Software ausgeführt werden:

  - Microsoft .NET Framework 4.5. Für lync Server 2013 müssen Sie die 64-Bit-Version von Microsoft .NET Framework 4.5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren.

  - Lync Server 2013, Kernkomponenten.

  - Paket für die WMI-Abwärtskompatibilität. Ausführliche Informationen finden Sie unter [install WMI abwärts Compatibility Package](install-wmi-backward-compatibility-package.md) in der Migrationsdokumentation.

  - Windows PowerShell 3.0. Ausführliche Informationen finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in der Bereitstellungsdokumentation.

Sie können Best Practices Analyzer auf Computern mit einem unterstützten Betriebssystem installieren, die nicht lync Server 2013, Kernkomponenten oder WMI-abwärts Kompatibilitätspaket ausführen, aber Sie können Best Practices Analyzer auf diesen Computern nur zum Anzeigen von Berichten verwenden, nicht zum Ausführen von Scans.

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>Auswählen eines Computers für die Installation

Es wird empfohlen, lync Server 2013, Best Practices Analyzer auf einem Computer zu installieren, der der lync Server 2013 Verwaltung gewidmet ist. Sie können das Tool auf einem Server mit lync Server 2013 oder einem Verwaltungscomputer installieren, auf dem lync Server 2013 Verwaltungstools betrieben wird. Wenn Sie das Tool auf einem Server installieren, auf dem lync Server läuft, wird empfohlen, dass Sie das Tool verwenden, um nur diesen Server zu überprüfen.

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>Installieren von Best Practices Analyzer

Sie können den Best Practices Analyzer für lync Server 2013 unter [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)herunterladen.

Um Best Practices Analyzer zu installieren, führen Sie die Microsoft Installer-Datei "RtcBPA.msi" auf dem Computer aus, auf dem das Tool installiert werden soll, und folgen den Anweisungen auf dem Bildschirm. Der Standardspeicherort für die Installation der Programmdateien \<lautet System\>\\Drive-\\Programm\\Dateien lync Server 2013 BPA.

</div>

</div>

<span> </span>

</div>

</div>

</div>

