---
title: 'Lync Server 2013: Softwareanforderungen für Verwaltungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8756545969f90cbece7bbac628577a51015e371
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a>Softwareanforderungen für Verwaltungstools in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

In diesem Thema wird die Software beschrieben, die zum Installieren und Verwenden von lync Server 2013 Verwaltungstools zusätzlich zu den Betriebssystemanforderungen erforderlich ist.

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Die 64-Bit-Edition von Microsoft .NET Framework 4.5 ist für lync Server 2013 erforderlich.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Windows PowerShell 3,0 ist für die Ausführung einer beliebigen Komponente von Microsoft lync Server 2013 erforderlich. Weitere Informationen finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="windows-installer-version-45"></a>Windows Installer, Version 4.5

Lync Server 2013 verwendet Windows Installer-Technologie, um verschiedene Server Rollen zu installieren, zu deinstallieren und zu verwalten. Windows Installer, Version 4.5, ist als weitervertreibbare Komponente für das Windows Server-Betriebssystem verfügbar. Windows Installer 4,5 ist mit Windows Server 2012 R2, Windows Server 2012 und Windows Server 2008 R2en ausgeliefert, was bedeutet, dass Sie das Dienstprogramm nicht für einen Computer herunterladen müssen, auf dem lync Server 2013 läuft. (Lync Server 2013 kann nur auf Computern mit Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2 installiert werden.)

Wenn Sie jedoch lync Server-Verwaltungsshell oder lync Server Topologie-Generator auf einer Administratorarbeitsstation installieren möchten, müssen Sie möglicherweise Windows Installer 4,5 herunterladen. Dieses Dienstprogramm wird mit Windows 7 und Windows 2008 R2 ausgeliefert, jedoch nicht mit früheren Versionen des Windows-Betriebssystems. Sie können Windows Installer 4,5 aus dem Microsoft Download Center herunterladen <https://go.microsoft.com/fwlink/p/?linkid=197395>.

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a>Microsoft Silverlight 5 Browser-Plug-in

Lync Server 2013-Systemsteuerung ist ein webbasiertes Tool und erfordert, dass Sie die neueste Version von Microsoft Silverlight 5 Browser-Plug-in installieren. Wenn Sie lync Server 2013 Systemsteuerung starten, wenn diese Software nicht installiert ist oder wenn eine frühere Version installiert ist, werden Sie von lync Server 2013 Systemsteuerung aufgefordert, die erforderliche Version zu installieren.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Infrastrukturanforderungen für Verwaltungstools in lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Für die Einrichtung und Verwaltung von lync Server 2013 erforderliche Administrator Rechte und-Berechtigungen](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

