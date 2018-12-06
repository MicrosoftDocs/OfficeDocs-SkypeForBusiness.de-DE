---
title: 'Lync Server 2013: Zusätzliche Softwareanforderungen'
TOCTitle: Zusätzliche Softwareanforderungen
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398686(v=OCS.15)
ms:contentKeyID: 49294652
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zusätzliche Softwareanforderungen für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Zusätzlich zu den Anforderungen im Hinblick auf Hardware und Betriebssystem, die für Serverplattformen erfüllt werden müssen, erfordert Lync Server 2013 die Installation zusätzlicher Software auf den Servern, die Sie bereitstellen.


> [!NOTE]
> Ausführliche Informationen zu den Plattformanforderungen für Server mit Lync Server finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Serverhardwareplattformen für Lync Server&nbsp;2013</A> und <A href="lync-server-2013-server-and-tools-operating-system-support.md">Betriebssystemunterstützung für Server und Tools in Lync Server 2013</A>. Einzelheiten zu den Systemanforderungen für Clientcomputer und -geräte finden Sie unter <A href="lync-server-2013-planning-for-clients-and-devices.md">Planen von Clients und Geräten in Lync Server 2013</A> in der Planungsdokumentation. Ausführliche Informationen zu den Softwareanforderungen für Verwaltungstools finden Sie unter <A href="lync-server-2013-administrative-tools-software-requirements.md">Softwareanforderungen für Verwaltungstools in Lync Server 2013</A>.



## Zusätzliche Softwareanforderungen für alle internen Serverrollen

In diesem Abschnitt finden Sie die für alle internen Serverrollen benötigte Software. Dies sind alle Serverrollen von Lync Server mit Ausnahme von Edgeserver. Die Voraussetzungen für die Edgeserver und Edgepools werden weiter unten in diesem Thema unter **Zusätzliche Software für Edgeserver** aufgeführt.

## Windows PowerShell 3.0

Auf jedem Server, auf dem Lync Server 2013 ausgeführt wird, muss die korrekte Version von Windows PowerShell 3.0 installiert sein. Ausführliche Informationen finden Sie unter [Installieren von Windows PowerShell 3.0 für Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

## Microsoft .NET Framework 4.5

Lync Server erfordert Microsoft .NET Framework 4.5 auf allen internen Serverrollen und auf allen Computern, auf denen die administrativen Tools von Lync Server oder Microsoft Lync Server 2013, Planungstool ausgeführt werden. Für Lync Server 2013 müssen Sie die 64-Bit-Version von Microsoft .NET Framework 4.5 auf dem Server installieren, bevor Sie Lync Server 2013 installieren. Laden Sie zur manuellen Installation das Microsoft .NET 4.5 Framework aus dem Microsoft Download Center unter [http://go.microsoft.com/fwlink/p/?LinkId=268529](http://go.microsoft.com/fwlink/p/?linkid=268529) herunter.

## Installation von Microsoft .NET Framework 4.5 auf Servern mit Windows Server 2012

Wenn Sie Microsoft .NET Framework 4.5 auf Servern mit Lync Server 2013 und Windows Server 2012 installieren, müssen Sie einen zusätzlichen Schritt ausführen. Nachdem .NET Framework 4.5 installiert ist, verwenden Sie Server-Manager zum Installieren der HTTP-Aktivierung.

**So installieren Sie .NET 4.5 HTTP-Aktivierung unter Windows Server 2012**

1.  Klicken Sie im Menü **Start** auf **Programme** , dann auf **Verwaltung** und anschließend auf **Server-Manager** .

2.  Wählen Sie im Server-Manager unter **Featureübersicht** die Option **Features hinzufügen** aus.

3.  Erweitern Sie die Option **.NET Framework 4.5** .

4.  Wählen Sie **WCF Activation** aus, wenn diese Option noch nicht ausgewählt wurde. Wählen Sie dann die Option **HTTP-Aktivierung** aus.

5.  Klicken Sie auf **Weiter** und befolgen Sie die Aufforderungen, um die Installation zu beenden.

## Windows Identity Foundation

**Windows Identity Foundation** in Lync Server 2013 erfordert die Installation von Windows Identity Foundation, damit Server-zu-Server-Authentifizierungsszenarien unterstützt werden. Windows Server 2008 R2 und Windows Server 2012 erfordern unterschiedliche Verfahren für die Installation von Windows Identify Foundation. Wählen Sie in der folgende Liste das von Ihnen verwendete Betriebssystem aus:

  - Windows Server 2008 R2   Für Windows Server 2008 R2 überprüfen Sie, ob die Software bereits auf Ihrem Computer installiert wurde. Hierzu wählen Sie in der Systemsteuerung **Software** , **Installierte Updates anzeigen** und suchen unter **Windows** nach dem Eintrag **Windows Identity Foundation (KB974405)** . Ausführliche Informationen zur Installation von Windows Identity Foundation finden Sie unter <http://go.microsoft.com/fwlink/?linkid=204657>.

  - Windows Server 2012   Für Windows Server 2012 verwenden Sie den **Server-Manager** zur Installation von Windows Identity Foundation. Im Server-Manager- **Assistenten zum Hinzufügen von Rollen und Features** wählen Sie **Features** aus. Wählen Sie dann in der Liste **Windows Identity Foundation 3.5** aus. Klicken Sie auf **Weiter** und anschließend auf **Installieren** .

## Zusätzliche Software für sämtliche Front-End-Server und Standard Edition-Server

Auf sämtlichen Front-End-Servern und Standard Edition-Servern müssen auch die Internetinformationsdienste (Internet Information Services, IIS) mit bestimmten Modulen ausgeführt werden. Zusätzlich muss auf allen Front-End-Servern und Standard Edition-Servern, auf denen die Konferenzfunktion, Anwendung zum Parken von Anrufen, die Ansageanwendung oder Reaktionsgruppenanwendung bereitgestellt werden, die Windows Media Format-Laufzeitkomponente ausgeführt werden.

## Internetinformationsdienste (Internet Information Services, IIS)

Auf Front-End-Servern und Standard Edition-Servern müssen die Internetinformationsdienste (Internet Information Services, IIS) mit den folgenden Modulen ausgeführt werden:

  - Statischer Inhalt

  - Standarddokument

  - HTTP-Fehler

  - ASP.NET

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

  - Anonyme Authentifizierung (wird bei der Installation von IIS standardmäßig installiert)

  - Clientzertifikatzuordnungs-Authentifizierung

## Windows Media Format Runtime und Windows Desktop Experience

**Windows Desktop Experience**Auf allen Front-End-Servern und Standard Edition-Servern, auf denen die Konferenzfunktion bereitgestellt wird, muss die Windows Media Format-Laufzeitkomponente installiert sein. Die Windows Media Format-Laufzeitkomponente ist, mit Ausnahme von Windows Server 2012 als Teil der Windows Desktop Experience installiert. Windows Server 2012 erfordert Microsoft Media Foundation. Die Windows Media Format-Laufzeitkomponente ist für die WMA-Dateien (Windows Media Audio) erforderlich, die in der Anwendung von Parken von Anrufen, in der Ansageanwendung und in der Reaktionsgruppenanwendung für die Wiedergabe von Ansagen und Musik verwendet werden.

Es wird empfohlen, Windows Desktop Experience vor der Installation von Lync Server 2013 zu installieren. Wenn Lync Server 2013 diese Software auf dem Server nicht findet, werden Sie zur Installation aufgefordert und müssen zum Abschließen der Installation den Server neu starten.

## Zusätzliche Software für Front-End-Server und Standard Edition-Server mit Windows Server 2012

Front-End-Server erfordert .NET 3.5, da es nicht standardmäßig unter Windows Server 2012 installiert ist. Legen Sie zur Installation dieser Software die Windows Server 2012-Installationsmedien in Laufwerk D ein, und geben Sie Folgendes ein:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Genauere Informationen zur Installation von .NET 3.5 auf Servern unter Windows Server 2012 finden Sie in "Microsoft .NET Framework 3.5 Deployment Considerations" unter <http://go.microsoft.com/fwlink/p/?linkid=275032>.

## Zusätzliche Software für Director-Server

Auf Director-Servern müssen die Internetinformationsdienste (Internet Information Services, IIS) mit den folgenden Modulen ausgeführt werden:

  - Statischer Inhalt

  - Standarddokument

  - HTTP-Fehler

  - ASP.NET

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

  - Anonyme Authentifizierung (wird bei der Installation von IIS standardmäßig installiert)

  - Clientzertifikatzuordnungs-Authentifizierung

## Zusätzliche Software für Front-End-Server für beständigen Chat

Auf Front-End-Servern für beständigen Chat muss Message Queuing (auch bekannt als MSMQ) ausgeführt werden, die eine Komponente von Windows Server ist.

Informationen zur Aktivierung von MSMQ [finden Sie hier.](http://technet.microsoft.com/en-us/library/cc771474.aspx)

## Zusätzliche Software für Edgeserver

Edgeserver erfordern folgende Software:

  - Auf jedem Server, auf dem Lync Server 2013 ausgeführt wird, muss die korrekte Version von Windows PowerShell 3.0 installiert sein. Ausführliche Informationen finden Sie unter [Installieren von Windows PowerShell 3.0 für Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Lync Server erfordert Microsoft .NET Framework 4.5. Für die Installation von Lync Server 2013 unter Windows Server 2008 R2 müssen Sie die 64-Bit-Version von Microsoft .NET Framework 4.5 auf dem Server installieren, bevor Sie Lync Server 2013 installieren. Laden Sie zur manuellen Installation das Microsoft .NET 4.5 Framework aus dem Microsoft Download Center unter [http://go.microsoft.com/fwlink/p/?LinkId=268529](http://go.microsoft.com/fwlink/p/?linkid=268529) herunter.

  - **Windows Identity Foundation** in Lync Server 2013 erfordert die Installation von Windows Identity Foundation, damit Server-zu-Server-Authentifizierungsszenarien unterstützt werden. Windows Server 2008 R2 und Windows Server 2012 erfordern unterschiedliche Verfahren für die Installation von Windows Identify Foundation. Wählen Sie in der folgende Liste das von Ihnen verwendete Betriebssystem aus:
    
      - Windows Server 2008 R2   Für Windows Server 2008 R2 überprüfen Sie, ob die Software bereits auf Ihrem Computer installiert wurde. Hierzu wählen Sie in der Systemsteuerung **Software** , **Installierte Updates anzeigen** und suchen unter **Windows** nach dem Eintrag **Windows Identity Foundation (KB974405)** . Ausführliche Informationen zur Installation von Windows Identity Foundation finden Sie unter <http://go.microsoft.com/fwlink/?linkid=204657>.
    
      - Windows Server 2012   Für Windows Server 2012 verwenden Sie den **Server-Manager** zur Installation von Windows Identity Foundation. Im Server-Manager- **Assistenten zum Hinzufügen von Rollen und Features** wählen Sie **Features** aus. Wählen Sie dann in der Liste **Windows Identity Foundation 3.5** aus. Klicken Sie auf **Weiter** und anschließend auf **Installieren** .

## Installieren Sie keine Mehrschicht-Dienstanbieter (Layered Service Provider, LSP) auf Medienservern

Installieren Sie keine Microsoft Internet Security and Acceleration Server (ISA)-Clientsoftware oder andere Winsock LSP-Software (Layered Service Provider, Mehrschicht-Dienstanbieter) auf einem beliebigen Front-End-Server oder auf eigenständigen Vermittlungsservern. Die Installation dieser Software kann zu einem schlechten Mediendatenverkehr führen.

## Siehe auch

#### Konzepte

[Softwareanforderungen für Verwaltungstools in Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

