---
title: 'Lync Server 2013: Softwareanforderungen für Verwaltungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95dfed4d6cf69950a0e17ab6826d79ee7e7a68cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a>Softwareanforderungen für Verwaltungstools in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

In diesem Thema wird die Software beschrieben, die für die Installation und Verwendung von lync Server 2013-Verwaltungstools zusätzlich zu den Betriebssystemanforderungen erforderlich ist.

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Die 64-Bit-Version von Microsoft .NET Framework 4,5 ist für lync Server 2013 erforderlich.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Windows PowerShell 3,0 ist für die Ausführung einer beliebigen Komponente von Microsoft lync Server 2013 erforderlich. Weitere Informationen finden Sie unter [Installieren von Windows PowerShell 3,0 für lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="windows-installer-version-45"></a>Windows Installer, Version 4,5

Lync Server 2013 verwendet die Windows Installer-Technologie, um verschiedene Server Rollen zu installieren, zu deinstallieren und zu verwalten. Windows Installer, Version 4,5, steht als verteilbare Komponente für das Windows Server-Betriebssystem zur Verfügung. Windows Installer 4,5 wird mit Windows Server 2012 R2, Windows Server 2012 und Windows Server 2008 R2 ausgeliefert, was bedeutet, dass Sie das Dienstprogramm nicht für einen Computer herunterladen müssen, auf dem lync Server 2013 ausgeführt wird. (Lync Server 2013 kann nur auf Computern mit Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2 installiert werden.)

Wenn Sie jedoch die lync Server-Verwaltungsshell oder den lync Server Topology Builder auf einer Administratorarbeitsstation installieren möchten, müssen Sie möglicherweise Windows Installer 4,5 herunterladen. Dieses Dienstprogramm wird mit Windows 7 und Windows 2008 R2 ausgeliefert, jedoch nicht mit früheren Versionen des Windows-Betriebssystems. Sie können Windows Installer 4,5 aus dem Microsoft Download Center herunterladen <http://go.microsoft.com/fwlink/p/?linkid=197395>.

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a>Microsoft Silverlight 5-Browser-Plug-in

Die lync Server 2013-Systemsteuerung ist ein webbasiertes Tool und erfordert, dass Sie die neueste Version des Microsoft Silverlight 5-Browser-Plug-ins installieren. Wenn Sie die lync Server 2013-Systemsteuerung starten, wenn diese Software nicht installiert ist oder wenn eine frühere Version installiert ist, werden Sie in der Systemsteuerung von lync Server 2013 aufgefordert, die erforderliche Version zu installieren.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Infrastrukturanforderungen für Verwaltungstools in lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Erforderliche Administratorrechte und Gruppenmitgliedschaften für die Installation und Verwaltung von Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

