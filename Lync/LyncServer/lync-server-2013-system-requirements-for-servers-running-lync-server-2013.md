---
title: 'Lync Server 2013: Systemanforderungen für Server mit Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad30b9687c9566adb7936612e71ae9f41e69095
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Systemanforderungen für Server mit Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-07-24_

<div>


> [!NOTE]  
> Details zu den Hardwareanforderungen finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server Hardwareplattformen für lync Server 2013</A>.



</div>

Standard Edition-und Enterprise Edition-Server haben die gleichen Softwareanforderungen.

Server mit lync Server 2013, Enterprise Edition, sind für große Organisationen als die wichtigste organisatorische Bereitstellung vorgesehen. Der Enterprise Edition-Server wurde für die Skalierung auf ungefähr 80.000-verwaltete Benutzer pro Pool konzipiert. Server, auf denen lync Server 2013, Standard Edition ausgeführt wird, sind für kleinere Organisationen und Remotestandorte von der Haupt Bereitstellung der Organisation vorgesehen. Ein paar von Standard Edition-Servern kann bis zu 5.000-Benutzer unterstützen. Einzelheiten zu den Unterschieden zwischen Standard Edition-Servern und Enterprise Edition-Servern finden Sie unter Übersicht über die [Bereitstellung von lync Server 2013](lync-server-2013-deployment-overview.md).

<div>

## <a name="operating-system-installation"></a>Installation des Betriebssystems

<div>


> [!IMPORTANT]  
> Lync Server 2013 ist nur in einer 64-Bit-Edition verfügbar, die eine 64-Bit-Hardware und eine 64-Bit-Version des Windows Server-Betriebssystems erfordert. Eine 32-Bit-Version von lync Server 2013 ist in dieser Version nicht verfügbar.



</div>

Standard Edition und Enterprise Edition Server können eine der folgenden Aktionen verwenden:

  - Windows Server 2008 R2 SP1 oder neuestes Service Pack

  - Windows Server 2012

  - Windows Server 2012 R2

Installieren Sie die Betriebssystemsoftware auf dem Standard Edition-Server oder Enterprise Edition-Front-End-Server. Wenden Sie alle Updates an, um das Betriebssystem auf das neueste Update und die erforderliche Aktualisierungsstufe zu bringen, die mit den Standards Ihrer Organisation in Einklang steht. Weitere Informationen zu den Betriebsanforderungen finden Sie unter unter [Stützung von Server-und Tools-Betriebssystemen in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.

<div>


> [!NOTE]  
> Damit lync Server 2013 unter Windows Server 2012 R2 funktioniert, müssen Sie möglicherweise den Wert eines Registrierungsschlüssels in Windows Server ändern. Diese Änderung ist möglicherweise erforderlich, damit Zertifikate ordnungsgemäß funktionieren, und Clients können sich bei Überlebenden Branch-Appliances registrieren. Weitere Informationen finden Sie unter <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>.



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Zusätzliche Software für lync Server 2013

Zusätzlich zu den für das Betriebssystem erforderlichen Updates erfordert lync Server 2013 die Verwendung von Betriebssystem Rollen,-Features und-Software. Details zur zusätzlichen Software, die vor der Veröffentlichung Ihrer Topologie und der Installation von lync Server 2013 installiert werden muss, finden Sie unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>Zusätzliche Software, die für alle Server Rollen erforderlich ist

Auf allen Serverrollen müssen Sie auch sicherstellen, dass die Windows PowerShell-Befehlszeilenschnittstelle 3,0 und Microsoft .NET Framework 4,5 installiert sind.

Darüber hinaus sind Windows PowerShell-Befehlszeilenschnittstellen 3,0 und Microsoft .NET Framework 4,5 auf jedem Computer erforderlich, auf dem die lync Server-Verwaltungstools ausgeführt werden.

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 erfordert, dass Sie Windows PowerShell 3,0 auf jedem Computer installieren, der an ihrer lync Server-Topologie teilnehmen wird. Details zur Installation von Windows PowerShell 3,0 finden Sie unter [Installieren von Windows PowerShell 3,0 für lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

<div>


> [!NOTE]  
> Unter Windows Server&nbsp;2008&nbsp;R2 mit SP1 kann die Windows PowerShell-Befehlszeilenschnittstelle 3,0 nicht vor der Installation von Microsoft .NET Framework 4,5 installiert werden.



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Wenn Sie Microsoft .NET Framework 4,5 auf Servern installieren, auf denen lync Server 2013 unter Windows Server 2012 oder Windows Server 2012 R2 ausgeführt wird, müssen Sie einen weiteren Schritt ausführen. Verwenden Sie nach der Installation von .NET Framework 4,5 den Server-Manager, um die HTTP-Aktivierung zu installieren.

**So installieren Sie die .NET 4,5-HTTP-Aktivierung unter Windows Server 2012 oder Windows Server 2012 R2**

1.  Klicken Sie im **Startmenü** auf **Programme**und dann auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.

2.  Wählen Sie im Server-Manager unter **Zusammenfassung der Features**die Option **Features hinzufügen**aus.

3.  Erweitern Sie **.NET Framework 4,5**.

4.  Wählen Sie **WCF-Aktivierung** aus, wenn Sie noch nicht ausgewählt ist. Wählen Sie dann **http-Aktivierung**aus.

5.  Klicken Sie auf **weiter** , und folgen Sie den Anweisungen, um die Installation abzuschließen.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

