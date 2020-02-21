---
title: 'Lync Server 2013: zusätzliche Softwareanforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4565f91afeb703de967040edb8f6d437aedac9eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Zusätzliche Softwareanforderungen für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-12-08_

Zusätzlich zu den Hardware-und Betriebssystemanforderungen für Serverplattformen erfordert lync Server 2013 die Installation zusätzlicher Software auf den Servern, die Sie bereitstellen.

<div>


> [!NOTE]  
> Ausführliche Informationen zu den Plattformanforderungen für Server, auf denen lync Server ausgeführt werden, finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools Operating System Support in lync Server 2013</A>. Ausführliche Informationen zu den Systemanforderungen für Clientcomputer und-Geräte finden Sie unter <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for Clients and Devices in lync Server 2013</A> in der Planungsdokumentation. Ausführliche Informationen zu den Softwareanforderungen für Verwaltungstools finden Sie unter <A href="lync-server-2013-administrative-tools-software-requirements.md">Software Requirements for Administration Tools in lync Server 2013</A>.



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>Zusätzliche Software, die für alle internen Server Rollen erforderlich ist

In diesem Abschnitt werden die erforderlichen Softwarekomponenten für alle internen Serverrollen aufgelistet, die alle lync Server Serverrollen außer Edgeserver sind. Die Anforderungen für die Edgeserver und Edge-Pools werden weiter unten in diesem Thema unter **zusätzliche Software für Edgeserver**aufgeführt.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Auf jedem Server mit lync Server 2013 muss die richtige Version von Windows PowerShell 3,0 installiert sein. Ausführliche Informationen finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server erfordert Microsoft .NET Framework 4.5 für alle internen Server Rollen und auf jedem Computer, auf dem Sie die lync Server Verwaltungstools oder Microsoft lync Server 2013, Planungs Tool ausführen werden. Für lync Server 2013 müssen Sie die 64-Bit-Version von Microsoft .NET Framework 4.5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren. Um es manuell zu installieren, laden Sie das Microsoft .NET 4,5 Framework aus dem Microsoft Download Center unter[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Installieren von Microsoft .NET Framework 4.5 auf Servern mit Windows Server 2012

Wenn Sie Microsoft .NET Framework 4.5 auf Servern installieren, auf denen lync Server 2013 und Windows Server 2012 ausgeführt wird, müssen Sie einen weiteren Schritt ausführen. Nachdem .NET Framework 4.5 installiert wurde, verwenden Sie Server-Manager, um die HTTP-Aktivierung zu installieren.

**So installieren Sie die .NET 4,5-HTTP-Aktivierung auf Windows Server 2012**

1.  Klicken Sie im **Startmenü** auf **Programme**und dann auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.

2.  Wählen Sie im Server-Manager unter **Zusammenfassung der Features**die Option **Features hinzufügen**aus.

3.  Erweitern Sie **.NET Framework 4.5**.

4.  Wählen Sie **WCF-Aktivierung** aus, wenn Sie nicht bereits ausgewählt ist. Wählen Sie dann **http-Aktivierung**aus.

5.  Klicken Sie auf **weiter** , und führen Sie die Anweisungen aus, um die Installation abzuschließen.

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

**WindowsIdentity Foundation** in lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen. Windows Server 2008 R2 und Windows Server 2012 erfordern unterschiedliche Verfahren zum Installieren der Windows Identify Foundation. Wählen Sie Ihr Server Betriebssystem aus der folgenden Liste aus:

  - Windows Server 2008 R2 für Windows Server 2008 R2 überprüfen Sie, ob Sie bereits auf Ihrem Computer installiert wurde. Wechseln Sie dazu zu **Software hinzufügen/entfernen**, **zeigen Sie installierte Updates**an, und schauen Sie unter **Windows** nach dem Eintrag **Windows Identity Foundation (KB974405)**. Ausführliche Informationen zum Installieren von Windows Identity Foundation finden [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Sie unter.

  - Windows Server 2012 für Windows Server 2012 verwenden Sie den **Server-Manager** , um die Windows Identity Foundation zu installieren. Wählen Sie im **Assistenten zum Hinzufügen von Rollen und Features**von Server-Manager die Option **Features**aus. Wählen Sie **Windows Identity Foundation 3,5** aus der Liste aus. Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>Zusätzliche Software für alle Front-End-Server und Standard Edition-Server

Alle Front-End-Server und Standard Edition-Server müssen auch Internet Information Services (IIS) mit bestimmten Modulen ausführen. Darüber hinaus müssen alle Front-End-Server und Standard Edition-Server, auf denen Konferenz-, Anwendung zum Parken von anrufen-, Ankündigungs-oder Reaktionsgruppen bereitgestellt werden, Windows Media Format Runtime ausführen.

<div>

## <a name="internet-information-services-iis"></a>Internetinformationsdienste (IIS)

Front-End-Server und Standard Edition-Server müssen Internet Information Services (IIS) mit den folgenden Modulen ausgeführt werden:

  - Statischer Inhalt

  - Standarddokument

  - HTTP-Fehler

  - ASP.NET

  - .NET-Erweiterbarkeit

  - ISAPI-Erweiterungen (Internet Server API)

  - ISAPI-Filter

  - HTTP-Protokollierung

  - Protokollierungstools

  - Tracing

  - Windows-Authentifizierung

  - Anforderungsfilterung

  - Komprimierung statischer Inhalte

  - Komprimierung dynamischer Inhalte

  - IIS-Verwaltungskonsole

  - IIS-Verwaltungsskripts und -tools

  - Anonyme Authentifizierung (wird bei der Installation von IIS standardmäßig installiert.)

  - Authentifizierung der Client Zertifikatzuordnung

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media Format Laufzeit und Windows-Desktop Erfahrung

**Windows-Desktop Umgebung** Auf allen Front-End-Servern und Standard Edition-Servern, auf denen Konferenzen bereitgestellt werden, muss die Windows Media Format Runtime installiert sein, die mit Ausnahme von Windows Server 2012 als Teil der Windows-Desktopumgebung installiert wird. Für Windows Server 2012 ist Microsoft Media Foundation erforderlich. Die Windows Media Format-Laufzeitkomponente ist für die WMA-Dateien (Windows Media Audio) erforderlich, die in der Anwendung zum Parken von Anrufen, in der Ansageanwendung und in der Reaktionsgruppenanwendung für die Wiedergabe von Ansagen und Musik verwendet werden.

Es wird empfohlen, dass Sie Windows Desktop Experience installieren, bevor Sie lync Server 2013 installieren. Wenn lync Server 2013 diese Software nicht auf dem Server findet, werden Sie aufgefordert, Sie zu installieren, und Sie müssen den Server neu starten, um die Installation abzuschließen.

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Zusätzliche Software für Front-End-Server und Standard Edition-Server mit Windows Server 2012

Front-End-Server benötigen .NET 3,5, das in Windows Server 2012 nicht standardmäßig installiert ist. Um Sie zu installieren, legen Sie die Windows Server 2012 Installationsmedien in Laufwerk D ab, und geben Sie Folgendes ein:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Ausführliche Informationen zur Installation von .NET 3,5 auf Servern mit Windows Server 2012 finden Sie unter "Überlegungen <https://go.microsoft.com/fwlink/p/?linkid=275032>zur Microsoft .NET Framework 3.5-Bereitstellung" unter.

</div>

<div>

## <a name="additional-software-for-directors"></a>Zusätzliche Software für Directors

Directors müssen Internet Information Services (IIS) mit den folgenden Modulen ausführen:

  - Statischer Inhalt

  - Standarddokument

  - HTTP-Fehler

  - ASP.NET

  - .NET-Erweiterbarkeit

  - ISAPI-Erweiterungen (Internet Server API)

  - ISAPI-Filter

  - HTTP-Protokollierung

  - Protokollierungstools

  - Tracing

  - Windows-Authentifizierung

  - Anforderungsfilterung

  - Komprimierung statischer Inhalte

  - IIS-Verwaltungskonsole

  - IIS-Verwaltungsskripts und -tools

  - Anonyme Authentifizierung (wird bei der Installation von IIS standardmäßig installiert.)

  - Authentifizierung der Client Zertifikatzuordnung

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>Zusätzliche Software für Front-End-Server für beständigen Chat

Front-End-Server für beständigen Chat müssen Message Queuing (auch als MSMQ bezeichnet) ausführen, bei dem es sich um eine Komponente von Windows Server handelt.

Informationen zum Aktivieren von MSMQ finden [Sie hier.](https://technet.microsoft.com/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>Zusätzliche Software für Edge-Server

Für Edgeserver ist die folgende Software erforderlich:

  - Auf jedem Server mit lync Server 2013 muss die richtige Version von Windows PowerShell 3,0 installiert sein. Ausführliche Informationen finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Lync Server erfordert Microsoft .NET Framework 4.5. Für lync Server 2013, die auf Windows Server 2008 R2 installiert sind, müssen Sie die 64-Bit-Edition von Microsoft .NET Framework 4.5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren. Um es manuell zu installieren, laden Sie das Microsoft .NET 4,5 Framework aus dem Microsoft Download Center unter[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - **WindowsIdentity Foundation** in lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen. Windows Server 2008 R2 und Windows Server 2012 erfordern unterschiedliche Verfahren zum Installieren der Windows Identify Foundation. Wählen Sie Ihr Server Betriebssystem aus der folgenden Liste aus:
    
      - Windows Server 2008 R2 für Windows Server 2008 R2 überprüfen Sie, ob Sie bereits auf Ihrem Computer installiert wurde. Wechseln Sie dazu zu **Software hinzufügen/entfernen**, **zeigen Sie installierte Updates**an, und schauen Sie unter **Windows** nach dem Eintrag **Windows Identity Foundation (KB974405)**. Ausführliche Informationen zum Installieren von Windows Identity Foundation finden [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Sie unter.
    
      - Windows Server 2012 für Windows Server 2012 verwenden Sie den **Server-Manager** , um die Windows Identity Foundation zu installieren. Wählen Sie im **Assistenten zum Hinzufügen von Rollen und Features**von Server-Manager die Option **Features**aus. Wählen Sie **Windows Identity Foundation 3,5** aus der Liste aus. Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>Installieren von mehrschichtigen Socket-Anbietern auf Medienservern

Installieren Sie keine ISA (Microsoft Internet Security and Acceleration Server)-Client Software oder andere LSP-Software (Winsock Layered Service Providers) auf allen Front-End-Servern oder eigenständigen Vermittlungsservern. Die Installation dieser Software kann zu einer schlechten Leistung des Datenverkehrs führen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Softwareanforderungen für Verwaltungstools in lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

