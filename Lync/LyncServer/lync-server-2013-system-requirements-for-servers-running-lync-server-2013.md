---
title: 'Lync Server 2013: System Anforderungen für Server mit lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0affd2d951d437a930bc7f210e0878e2978f8731
ms.sourcegitcommit: 5fbb57c5f0692afcb8e65516c63b96814f51ca65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417580"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>System Anforderungen für Server mit lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-07-24_

<div>


> [!NOTE]
> Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for lync Server 2013</A>.



</div>

Standard Edition-und Enterprise Edition-Server verwenden dieselben Softwareanforderungen.

Server, auf denen lync Server 2013 Enterprise Edition betrieben wird, sind für große Organisationen als Haupt Organisations Bereitstellung gedacht. Enterprise Edition-Server sind auf ca. 80.000 verwaltete Benutzer pro Pool skalierbar. Server mit lync Server 2013 Standard Edition sind für kleinere Organisationen und Remotestandorte von der Haupt Organisations Bereitstellung vorgesehen. Ein paar von Standard Edition-Servern kann bis zu 5.000 Benutzer unterstützen.. Ausführliche Informationen zu den Unterschieden zwischen Standard Edition-Servern und Enterprise Edition-Servern finden Sie unter Übersicht über die [Bereitstellung für lync Server 2013](lync-server-2013-deployment-overview.md).

<div>

## <a name="operating-system-installation"></a>Betriebssysteminstallation

<div>


> [!IMPORTANT]
> Lync Server 2013 ist nur in einer 64-Bit-Version verfügbar, die 64-Bit-Hardware und eine 64-Bit-Edition des Windows Server-Betriebssystems erfordert. Eine 32-Bit-Version von lync Server 2013 steht in dieser Version nicht zur Verfügung.



</div>

Standard Edition und Enterprise Edition-Server können eine der folgenden Optionen verwenden:

  - Windows Server 2008 R2 SP1 oder neuestes Service Pack

  - Windows Server 2012

  - Windows Server 2012 R2

Installieren Sie die Betriebssystemsoftware im Standard Edition-Server-oder Enterprise Edition-Front-End-Server. Wenden Sie alle Updates in der vorgesehenen Reihenfolge an, um das Betriebssystem auf den neuesten Stand zu bringen und die Organisationsstandards in Bezug auf Updates zu erfüllen. Ausführliche Informationen zu den Betriebsanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

> [!NOTE] 
> Das in-Place-Upgrade des Betriebssystems wird mit lync Server 2013 nicht unterstützt.  Sie müssen einen separaten Pool bereitstellen und Benutzer mit einem anderen Betriebssystem in den neuen Pool migrieren.

<div>


> [!NOTE]
> Damit lync Server 2013 an Windows Server 2012 R2 arbeiten können, müssen Sie möglicherweise den Wert eines Registrierungsschlüssels in Windows Server ändern. Diese Änderung ist möglicherweise erforderlich, damit Zertifikate ordnungsgemäß funktionieren, und Clients können sich bei Survivable Branch Appliances registrieren. Weitere Informationen finden Sie unter <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Zusätzliche Software für lync Server 2013

Zusätzlich zu den für das Betriebssystem erforderlichen Updates erfordert lync Server 2013 Betriebssystem Rollen, Features und Software für den Betrieb. Ausführliche Informationen zu der zusätzlichen Software, die vor dem Veröffentlichen der Topologie installiert werden muss, und zum Installieren von lync Server 2013 finden Sie unter [Additional Software Requirements for lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>Zusätzliche Software, die für alle Server Rollen erforderlich ist

Für alle Serverrollen müssen Sie auch sicherstellen, dass Windows PowerShell Befehlszeilenschnittstelle 3,0 und Microsoft .NET Framework 4.5 installiert sind.

Darüber hinaus sind Windows PowerShell Befehlszeilenschnittstelle 3,0 und Microsoft .NET Framework 4.5 auf jedem Computer erforderlich, auf dem Sie die lync Server-Verwaltungstools ausführen werden.

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Für lync Server 2013 müssen Sie Windows PowerShell 3,0 auf jedem Computer installieren, der an der lync Server Topologie teilnehmen soll. Ausführliche Informationen zum Installieren von Windows PowerShell 3,0 finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

<div>


> [!NOTE]
> Unter Windows Server&nbsp;2008&nbsp;R2 mit SP1 kann Windows PowerShell Befehlszeilenschnittstelle 3,0 nicht vor der Installation von Microsoft .NET Framework 4.5 installiert werden.



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Wenn Sie Microsoft .NET Framework 4.5 auf Servern installieren, auf denen lync Server 2013 auf Windows Server 2012 oder Windows Server 2012 R2 ausgeführt wird, müssen Sie einen weiteren Schritt ausführen. Nachdem .NET Framework 4.5 installiert wurde, verwenden Sie Server-Manager, um die HTTP-Aktivierung zu installieren.

**So installieren Sie die .NET 4,5-HTTP-Aktivierung auf Windows Server 2012 oder Windows Server 2012 R2**

1.  Klicken Sie im **Startmenü** auf **Programme**und dann auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.

2.  Wählen Sie im Server-Manager unter **Zusammenfassung der Features**die Option **Features hinzufügen**aus.

3.  Erweitern Sie **.NET Framework 4.5**.

4.  Wählen Sie **WCF-Aktivierung** aus, wenn Sie nicht bereits ausgewählt ist. Wählen Sie dann **http-Aktivierung**aus.

5.  Klicken Sie auf **weiter** , und führen Sie die Anweisungen aus, um die Installation abzuschließen.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

