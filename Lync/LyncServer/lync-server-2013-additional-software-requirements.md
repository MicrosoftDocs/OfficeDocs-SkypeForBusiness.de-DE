---
title: 'Lync Server 2013: Zusätzliche Softwareanforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e21a375fecbd109e108806dc816a9fa3fce81a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Zusätzliche Softwareanforderungen für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Zusätzlich zu den Hardware-und Betriebssystemanforderungen für Serverplattformen erfordert lync Server 2013 die Installation zusätzlicher Software auf den von Ihnen bereitgestellten Servern.

<div>


> [!NOTE]  
> Details zu den Plattformanforderungen für Server mit lync Server finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server-Hardwareplattformen für lync Server 2013</A> und <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server-und Tools-Betriebssystemunterstützung in lync Server 2013</A>. Ausführliche Informationen zu den Systemanforderungen für Clientcomputer und Geräte finden Sie unter <A href="lync-server-2013-planning-for-clients-and-devices.md">Planen von Clients und Geräten in lync Server 2013</A> in der Planungsdokumentation. Details zu den Softwareanforderungen für Verwaltungstools finden Sie unter <A href="lync-server-2013-administrative-tools-software-requirements.md">Softwareanforderungen für Verwaltungstools in lync Server 2013</A>.



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>Zusätzliche Software, die für alle internen Server Rollen erforderlich ist

Dieser Abschnitt listet Software auf, die für alle internen Serverrollen erforderlich ist, bei denen es sich um alle lync Server-Serverrollen mit Ausnahme von Edgeserver handelt. Die Anforderungen für die Edgeserver und Edge-Pools sind weiter unten in diesem Thema unter **zusätzliche Software für Edgeserver**aufgeführt.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Auf jedem Server, auf dem lync Server 2013 ausgeführt wird, muss die richtige Version von Windows PowerShell 3,0 installiert sein. Ausführliche Informationen finden Sie unter [Installieren von Windows PowerShell 3,0 für lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server erfordert Microsoft .NET Framework 4,5 auf allen internen Server Rollen und auf allen Computern, auf denen Sie die lync Server-Verwaltungstools oder Microsoft lync Server 2013, Planungs Tool, ausführen werden. Bei lync Server 2013 müssen Sie die 64-Bit-Version von Microsoft .NET Framework 4,5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren. Wenn Sie die Datei manuell installieren möchten, laden Sie das Microsoft .NET 4,5-Framework aus dem Microsoft Download Center unter[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Installieren von Microsoft .NET Framework 4,5 auf Servern mit Windows Server 2012

Wenn Sie Microsoft .NET Framework 4,5 auf Servern installieren, auf denen lync Server 2013 und Windows Server 2012 ausgeführt wird, müssen Sie einen weiteren Schritt ausführen. Verwenden Sie nach der Installation von .NET Framework 4,5 den Server-Manager, um die HTTP-Aktivierung zu installieren.

**So installieren Sie die .NET 4,5-HTTP-Aktivierung unter Windows Server 2012**

1.  Klicken Sie im **Startmenü** auf **Programme**und dann auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.

2.  Wählen Sie im Server-Manager unter **Zusammenfassung der Features**die Option **Features hinzufügen**aus.

3.  Erweitern Sie **.NET Framework 4,5**.

4.  Wählen Sie **WCF-Aktivierung** aus, wenn Sie noch nicht ausgewählt ist. Wählen Sie dann **http-Aktivierung**aus.

5.  Klicken Sie auf **weiter** , und folgen Sie den Anweisungen, um die Installation abzuschließen.

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

**WindowsIdentity Foundation** in lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen. Windows Server 2008 R2 und Windows Server 2012 erfordern unterschiedliche Verfahren zum Installieren der Windows Identify Foundation. Wählen Sie das Betriebssystem Ihres Servers aus der folgenden Liste aus:

  - Windows Server 2008 R2 für Windows Server 2008 R2 überprüfen Sie, ob Sie bereits auf Ihrem Computer installiert ist. Wechseln Sie dazu zu **Programme hinzufügen/entfernen**, **installierte Updates anzeigen**, und suchen Sie unter **Windows** nach dem Eintrag **Windows Identity Foundation (KB974405)**. Informationen zum Installieren von Windows Identity Foundation finden Sie [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)unter.

  - Windows Server 2012 für Windows Server 2012 verwenden Sie den **Server-Manager** , um die Windows Identity Foundation zu installieren. Wählen Sie im **Assistenten zum Hinzufügen von Rollen und Features**des Server-Managers **Features**aus. Wählen Sie **Windows Identity Foundation 3,5** aus der Liste aus. Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>Zusätzliche Software für alle Front-End-Server und Standard Edition-Server

Alle Front-End-Server und Standard Edition-Server müssen auch Internet Informationsdienste (IIS) mit bestimmten Modulen ausführen. Darüber hinaus müssen alle Front-End-Server und Standard Edition-Server, auf denen Konferenz-, Anruf Park-, Ankündigungs-oder Antwortgruppen bereitgestellt werden, die Windows Media-Format Laufzeit ausführen.

<div>

## <a name="internet-information-services-iis"></a>Internetinformationsdienste (Internet Information Services, IIS)

Front-End-Server und Standard Edition-Server müssen Internet Informationsdienste (IIS) mit den folgenden Modulen ausführen:

  - Statischer Inhalt

  - Standarddokument

  - HTTP-Fehler

  - ASP.net

  - .NET-Erweiterbarkeit

  - ISAPI-Erweiterungen (Internet Server API)

  - ISAPI-Filter

  - HTTP-Protokollierung

  - Protokollierungstools

  - Ablaufverfolgung

  - Windows-Authentifizierung

  - Anforderungsfilterung

  - Komprimierung statischer Inhalte

  - Komprimierung dynamischer Inhalte

  - IIS-Verwaltungskonsole

  - IIS-Verwaltungsskripts und -tools

  - Anonyme Authentifizierung (standardmäßig installiert, wenn IIS installiert ist)

  - Clientzertifikatzuordnungs-Authentifizierung

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media Format-Laufzeit und Windows-Desktop Experience

**Windows-Desktop Umgebung** Auf allen Front-End-Servern und Standard Edition-Servern, auf denen Konferenzen bereitgestellt werden, muss die Windows Media-Format Laufzeit installiert sein, die, mit Ausnahme von Windows Server 2012, als Teil der Windows-Desktopumgebung installiert ist. Windows Server 2012 erfordert Microsoft Media Foundation. Die Windows Media-Format Laufzeit ist erforderlich, um die Windows Media-Audio-Dateien (WMA) auszuführen, die von den Anwendungen für die Anruf Park-, Ankündigungs-und Reaktionsgruppen für Ankündigungen und Musik abgespielt werden.

Wir empfehlen, dass Sie die Windows-Desktopumgebung installieren, bevor Sie lync Server 2013 installieren. Wenn lync Server 2013 diese Software auf dem Server nicht findet, werden Sie aufgefordert, Sie zu installieren, und dann müssen Sie den Server neu starten, um die Installation abzuschließen.

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Zusätzliche Software für Front-End-Server und Standard Edition-Server, die unter Windows Server 2012 ausgeführt werden

Für Front-End-Server ist .NET 3,5 erforderlich, das unter Windows Server 2012 nicht standardmäßig installiert ist. Installieren Sie das Windows Server 2012-Installationsmedium auf Laufwerk D, und geben Sie Folgendes ein:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Details zur Installation von .NET 3,5 auf Servern mit Windows Server 2012 finden Sie unter "Microsoft .NET Framework 3,5-Bereitstellungs <https://go.microsoft.com/fwlink/p/?linkid=275032>Überlegungen" unter.

</div>

<div>

## <a name="additional-software-for-directors"></a>Zusätzliche Software für Directors

Directors müssen Internet Informationsdienste (IIS) mit den folgenden Modulen ausführen:

  - Statischer Inhalt

  - Standarddokument

  - HTTP-Fehler

  - ASP.net

  - .NET-Erweiterbarkeit

  - ISAPI-Erweiterungen (Internet Server API)

  - ISAPI-Filter

  - HTTP-Protokollierung

  - Protokollierungstools

  - Ablaufverfolgung

  - Windows-Authentifizierung

  - Anforderungsfilterung

  - Komprimierung statischer Inhalte

  - IIS-Verwaltungskonsole

  - IIS-Verwaltungsskripts und -tools

  - Anonyme Authentifizierung (standardmäßig installiert, wenn IIS installiert ist)

  - Clientzertifikatzuordnungs-Authentifizierung

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>Zusätzliche Software für beständige Chat-Front-End-Server

Beständige Chat-Front-End-Server müssen Message Queuing (auch als MSMQ bezeichnet) ausführen, einer Komponente von Windows Server.

Informationen zum Aktivieren von MSMQ finden [Sie hier.](https://technet.microsoft.com/en-us/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>Zusätzliche Software für Edgeserver

Edgeserver erfordern die folgende Software:

  - Auf jedem Server, auf dem lync Server 2013 ausgeführt wird, muss die richtige Version von Windows PowerShell 3,0 installiert sein. Ausführliche Informationen finden Sie unter [Installieren von Windows PowerShell 3,0 für lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Für lync Server ist Microsoft .NET Framework 4,5 erforderlich. Für lync Server 2013, das unter Windows Server 2008 R2 installiert ist, müssen Sie die 64-Bit-Version von Microsoft .NET Framework 4,5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren. Wenn Sie die Datei manuell installieren möchten, laden Sie das Microsoft .NET 4,5-Framework aus dem Microsoft Download Center unter[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - **WindowsIdentity Foundation** in lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen. Windows Server 2008 R2 und Windows Server 2012 erfordern unterschiedliche Verfahren zum Installieren der Windows Identify Foundation. Wählen Sie das Betriebssystem Ihres Servers aus der folgenden Liste aus:
    
      - Windows Server 2008 R2 für Windows Server 2008 R2 überprüfen Sie, ob Sie bereits auf Ihrem Computer installiert ist. Wechseln Sie dazu zu **Programme hinzufügen/entfernen**, **installierte Updates anzeigen**, und suchen Sie unter **Windows** nach dem Eintrag **Windows Identity Foundation (KB974405)**. Informationen zum Installieren von Windows Identity Foundation finden Sie [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)unter.
    
      - Windows Server 2012 für Windows Server 2012 verwenden Sie den **Server-Manager** , um die Windows Identity Foundation zu installieren. Wählen Sie im **Assistenten zum Hinzufügen von Rollen und Features**des Server-Managers **Features**aus. Wählen Sie **Windows Identity Foundation 3,5** aus der Liste aus. Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>Installieren Sie keine Layered Socket-Anbieter auf Medienservern.

Installieren Sie keine Microsoft Internet Security and Acceleration (ISA) Server-Client Software oder eine andere Winsock-Schicht Service Anbieter-Software (LSP) auf allen Front-End-Servern oder eigenständigen Vermittlungsservern. Die Installation dieser Software kann zu schlechter Leistung des Medien Verkehrs führen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Softwareanforderungen für Verwaltungstools in Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

