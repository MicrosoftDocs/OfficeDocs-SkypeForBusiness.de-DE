---
title: 'Lync Server 2013: IIS-Konfiguration'
TOCTitle: IIS-Konfiguration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412871(v=OCS.15)
ms:contentKeyID: 49295149
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# IIS-Konfiguration in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie beim Computer mit den Mindestberechtigungen eines lokalen Administrators und Domänenbenutzers angemeldet sein.

Bevor Sie den Front-End-Server für Lync Server 2013Standard Edition oder den ersten Front-End-Server in einem Pool installieren und konfigurieren, müssen Sie die Serverrolle und die Webdienste für Internetinformationsdienste (Internet Information Services, IIS) installieren und konfigurieren.


> [!IMPORTANT]
> Wenn in Ihrer Organisation IIS und alle Webdienste auf einem anderen Laufwerk als auf dem Systemlaufwerk platziert werden müssen, können Sie das Installationsverzeichnis für die Lync Server 2013-Dateien im Setupdialogfeld ändern, wenn Sie zu Anfang die Verwaltungstools von Lync Server 2013 installieren. Die Verwaltungstools werden vor dem Installieren von Internetinformationsdiensten (IIS) installiert. Wenn Sie die Setupdateien, einschließlich "OCSCore.msi", in diesem Verzeichnis installieren, werden auch alle übrigen Lync Server 2013-Dateien auf diesem Laufwerk bereitgestellt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-install-lync-server-administrative-tools.md">Installieren von Lync Server 2013-Verwaltungstools</A>. Einzelheiten dazu, wie Sie das vom Windows Server Manager bereitgestellte Verzeichnis INETPUB beim Installieren von IIS an anderer Stelle platzieren können, finden Sie unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=216888">http://go.microsoft.com/fwlink/?linkid=216888</A>.



Die folgende Tabelle enthält die erforderlichen IIS-7.5-Rollendienste.

### IIS 7.5-Rollendienste

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rollenüberschrift</th>
<th>Rollendienst</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Allgemeine HTTP-Funktionen installiert</p></td>
<td><p>Statischer Inhalt</p></td>
</tr>
<tr class="even">
<td><p>Allgemeine HTTP-Funktionen installiert</p></td>
<td><p>Standarddokument</p></td>
</tr>
<tr class="odd">
<td><p>Allgemeine HTTP-Funktionen installiert</p></td>
<td><p>HTTP-Fehler</p></td>
</tr>
<tr class="even">
<td><p>Anwendungsentwicklung</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012 erfordert auch ASP.NET4.5</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsentwicklung</p></td>
<td><p>.NET-Erweiterbarkeit</p></td>
</tr>
<tr class="even">
<td><p>Anwendungsentwicklung</p></td>
<td><p>ISAPI-Erweiterungen (Internet Server API)</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsentwicklung</p></td>
<td><p>ISAPI-Filter</p></td>
</tr>
<tr class="even">
<td><p>Integrität und Diagnose</p></td>
<td><p>HTTP-Protokollierung</p></td>
</tr>
<tr class="odd">
<td><p>Integrität und Diagnose</p></td>
<td><p>Protokollierungstools</p></td>
</tr>
<tr class="even">
<td><p>Integrität und Diagnose</p></td>
<td><p>Ablaufverfolgung</p></td>
</tr>
<tr class="odd">
<td><p>Sicherheit</p></td>
<td><p>Anonyme Authentifizierung (standardmäßig installiert und aktiviert)</p></td>
</tr>
<tr class="even">
<td><p>Sicherheit</p></td>
<td><p>Windows-Authentifizierung</p></td>
</tr>
<tr class="odd">
<td><p>Sicherheit</p></td>
<td><p>Clientzertifikatzuordnungs-Authentifizierung</p></td>
</tr>
<tr class="even">
<td><p>Sicherheit</p></td>
<td><p>Anforderungsfilterung</p></td>
</tr>
<tr class="odd">
<td><p>Leistung</p></td>
<td><p>Komprimierung statischer Inhalte</p>
<p>Komprimierung dynamischer Inhalte</p></td>
</tr>
<tr class="even">
<td><p>Verwaltungstools</p></td>
<td><p>IIS-Verwaltungskonsole</p></td>
</tr>
<tr class="odd">
<td><p>Verwaltungstools</p></td>
<td><p>IIS-Verwaltungsskripts und -tools</p></td>
</tr>
</tbody>
</table>


Unter dem Betriebssystem Windows Server 2008 R2 SP1 x64 können Sie auch Windows PowerShell 2.0 verwenden. Sie müssen zunächst das Modul "ServerManager" importieren und anschließend die IIS 7.5-Rolle und -Rollendienste installieren.

    Import-Module ServerManager

   &nbsp;

    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console


> [!NOTE]
> Die anonyme Authentifizierung wird bei der Installation der IIS-Serverrolle standardmäßig installiert. Sie können die anonyme Authentifizierung nach der Installation von IIS verwalten. Ausführliche Informationen finden Sie unter "Aktivieren der anonymen Authentifizierung (IIS&nbsp;7)" unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=203935">http://go.microsoft.com/fwlink/?linkid=203935</A>.



Die folgende Tabelle enthält die erforderlichen IIS 8.0- und IIS 8.5 Rollendienste für Windows Server 2012 und Windows Server 2012 R2.


> [!NOTE]
> Für Windows Server 2012 und Windows Server 2012 R2 wurde das Cmdlet Add-WindowsFeature durch das Cmdlet Install-WindowsFeature ersetzt. Ausführliche Informationen finden Sie unter <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.



### IIS 8.0- und IIS 8.5-Rollendienste

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rollenüberschrift</th>
<th>Rollendienst</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Webserver (IIS)</p></td>
<td><p>Webserver</p></td>
</tr>
<tr class="even">
<td><p>Allgemeine HTTP-Funktionen</p></td>
<td><p>Standarddokument</p></td>
</tr>
<tr class="odd">
<td><p>Allgemeine HTTP-Funktionen</p></td>
<td><p>Verzeichnissuche</p></td>
</tr>
<tr class="even">
<td><p>Allgemeine HTTP-Funktionen</p></td>
<td><p>HTTP-Fehler</p></td>
</tr>
<tr class="odd">
<td><p>Allgemeine HTTP-Funktionen</p></td>
<td><p>Statischer Inhalt</p></td>
</tr>
<tr class="even">
<td><p>Allgemeine HTTP-Funktionen</p></td>
<td><p>HTTP-Umleitung</p></td>
</tr>
<tr class="odd">
<td><p>Integrität und Diagnose</p></td>
<td><p>HTTP-Protokollierung</p></td>
</tr>
<tr class="even">
<td><p>Integrität und Diagnose</p></td>
<td><p>Protokollierungstools</p></td>
</tr>
<tr class="odd">
<td><p>Integrität und Diagnose</p></td>
<td><p>Anforderungsmonitor</p></td>
</tr>
<tr class="even">
<td><p>Integrität und Diagnose</p></td>
<td><p>Ablaufverfolgung</p></td>
</tr>
<tr class="odd">
<td><p>Sicherheit</p></td>
<td><p>Anforderungsfilterung</p></td>
</tr>
<tr class="even">
<td><p>Sicherheit</p></td>
<td><p>Standardauthentifizierung</p></td>
</tr>
<tr class="odd">
<td><p>Sicherheit</p></td>
<td><p>Clientzertifikatzuordnungs-Authentifizierung</p></td>
</tr>
<tr class="even">
<td><p>Sicherheit</p></td>
<td><p>Windows-Authentifizierung</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsentwicklung</p></td>
<td><p>.NET-Erweiterbarkeit 3,5</p></td>
</tr>
<tr class="even">
<td><p>Anwendungsentwicklung</p></td>
<td><p>.NET-Erweiterbarkeit 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsentwicklung</p></td>
<td><p>ASP.NET 3,5</p></td>
</tr>
<tr class="even">
<td><p>Anwendungsentwicklung</p></td>
<td><p>ASP.NET 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsentwicklung</p></td>
<td><p>ISAPI-Erweiterungen</p></td>
</tr>
<tr class="even">
<td><p>Anwendungsentwicklung</p></td>
<td><p>ISAPI-Filter</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsentwicklung</p></td>
<td><p>Serverseitige Includes</p></td>
</tr>
<tr class="even">
<td><p>Verwaltungstools</p></td>
<td><p>IIS-Verwaltungskonsole</p></td>
</tr>
<tr class="odd">
<td><p>Verwaltungstools</p></td>
<td><p>IIS 6-Metabasiskompatibilität</p></td>
</tr>
<tr class="even">
<td><p>Verwaltungstools</p></td>
<td><p>IIS-Verwaltungsskripts und -tools</p></td>
</tr>
<tr class="odd">
<td><p>.NET 3,5 Framework-Features</p></td>
<td><p>.NET Framework 3.5</p></td>
</tr>
<tr class="even">
<td><p>.NET 4.5 Framework-Features</p></td>
<td><p>.NET Framework 4.5</p></td>
</tr>
<tr class="odd">
<td><p>.NET 4.5 Framework-Features</p></td>
<td><p>ASP.NET 4.5</p></td>
</tr>
<tr class="even">
<td><p>.NET 4.5 Framework-Features</p></td>
<td><p>HTTP-Aktivierung</p></td>
</tr>
<tr class="odd">
<td><p>.NET 4.5 Framework-Features</p></td>
<td><p>TCP-Portfreigabe</p></td>
</tr>
<tr class="even">
<td><p>Background Intelligent Transfer Service (BITS)</p></td>
<td><p>IIS-Servererweiterungen</p></td>
</tr>
<tr class="odd">
<td><p>Freihand- und Handschriftdienste</p></td>
<td><p>Freihand- und Handschriftdienste</p></td>
</tr>
<tr class="even">
<td><p>Media Foundation</p></td>
<td><p>Media Foundation</p></td>
</tr>
<tr class="odd">
<td><p>Benutzeroberflächen und Infrastruktur</p></td>
<td><p>Tools und Infrastruktur für die grafische Verwaltung</p></td>
</tr>
<tr class="even">
<td><p>Benutzeroberflächen und Infrastruktur</p></td>
<td><p>Desktopdarstellung</p></td>
</tr>
<tr class="odd">
<td><p>Benutzeroberflächen und Infrastruktur</p></td>
<td><p>Grafische Shell für Server</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3.5</p></td>
<td><p>Windows Identity Foundation 3.5</p></td>
</tr>
<tr class="odd">
<td><p>Windows-Prozessaktivierungsdienst</p></td>
<td><p>Prozessmodell</p></td>
</tr>
<tr class="even">
<td><p>Windows-Prozessaktivierungsdienst</p></td>
<td><p>Konfigurations-APIs</p></td>
</tr>
</tbody>
</table>


In Windows Server 2012 und Windows Server 2012 R2 können Sie Windows PowerShell 3.0 verwenden, um die erforderlichen IIS-Komponenten zu installieren. Geben Sie mit dem ServerManager-Modul in Windows PowerShell 3.0 Folgendes ein:

    Import-Module ServerManager

   &nbsp;

    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs


> [!IMPORTANT]
> Neu in Windows Server 2012 ist der Parameter "-Source". Dieser definiert, wo das Windows Server 2012-Quellenmedium gefunden werden kann. Das Medium kann als DVD-Laufwerk definiert werden (beispielsweise "D:\Sources\Sxs") oder für eine Netzwerkfreigabe, auf der die Mediendateien kopiert wurden (beispielsweise "\\fileserver\windows2012\sources\Sxs").



## Siehe auch

#### Konzepte

[IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

