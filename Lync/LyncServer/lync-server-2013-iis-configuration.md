---
title: 'Lync Server 2013: IIS-Konfiguration'
description: 'Lync Server 2013: IIS-Konfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901aca7bf5ff8824b54e93754569a6ef5defc10e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554871"
---
# <a name="iis-configuration-in-lync-server-2013"></a>IIS-Konfiguration in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-17_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie beim Computer mit den Mindestberechtigungen eines lokalen Administrators und Domänenbenutzers angemeldet sein.

Bevor Sie die Front-End-Server für lync Server 2013, Standard Edition oder den ersten Front-End-Server in einem Pool konfigurieren und installieren, installieren und konfigurieren Sie die Server Rolle und Webdienste für Internet Information Services (IIS).

<div class=" ">


> [!IMPORTANT]  
> Wenn in Ihrer Organisation IIS und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk lokalisiert werden müssen, können Sie den Installationspfad für die lync Server 2013 Dateien im Dialogfeld Setup ändern, wenn Sie die lync Server 2013-Verwaltungstools zunächst installieren. Sie installieren die Verwaltungstools vor der Installation von IIS. Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen lync Server 2013 Dateien auf diesem Laufwerk bereitgestellt. Informationen zu dtails finden Sie unter <A href="lync-server-2013-install-lync-server-administrative-tools.md">install lync Server 2013 Administration Tools</A>. Ausführliche Informationen zum Verschieben des von Windows Server-Manager bereitgestellten Verzeichnis Inetpub bei der Installation von IIS finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .



</div>

In der folgenden Tabelle sind die erforderlichen IIS 7,5-Rollendienste angegeben.

### <a name="iis-75-role-services"></a>IIS 7,5-Rollendienste

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
<p>Windows Server 2012 erfordert auch ASP. NET 4.5</p></td>
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
<td><p>Tracing</p></td>
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


Auf dem Betriebssystem Windows Server 2008 R2 SP1 x64 können Sie Windows PowerShell 2,0 verwenden. Sie müssen zunächst das Modul "ServerManager" importieren und anschließend die IIS 7.5-Rolle und -Rollendienste installieren.

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> Die anonyme Authentifizierung wird bei der Installation der IIS-Serverrolle standardmäßig installiert. Sie können die anonyme Authentifizierung nach der Installation von IIS verwalten. Ausführliche Informationen finden Sie unter "Aktivieren der anonymen Authentifizierung (IIS 7.0)" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> .



</div>

In der folgenden Tabelle werden die erforderlichen IIS 8,0-und IIS 8,5-Rollendienste für Windows Server 2012 und Windows Server 2012 R2 angegeben.

<div class=" ">


> [!NOTE]  
> Für Windows Server 2012 und Windows Server 2012 R2 wurde das Cmdlet Add-WindowsFeature durch das Install-WindowsFeature-Cmdlet ersetzt. Ausführliche Informationen finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">install-Cmdlets</A>.



</div>

### <a name="iis-80-and-iis-85-role-services"></a>IIS 8,0 und IIS 8,5-Rollendienste

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
<td><p>Allgemeine HTTP-Features</p></td>
<td><p>Standarddokument</p></td>
</tr>
<tr class="odd">
<td><p>Allgemeine HTTP-Features</p></td>
<td><p>Verzeichnissuche</p></td>
</tr>
<tr class="even">
<td><p>Allgemeine HTTP-Features</p></td>
<td><p>HTTP-Fehler</p></td>
</tr>
<tr class="odd">
<td><p>Allgemeine HTTP-Features</p></td>
<td><p>Statischer Inhalt</p></td>
</tr>
<tr class="even">
<td><p>Allgemeine HTTP-Funktionen</p></td>
<td><p>HTTP-Umleitung</p></td>
</tr>
<tr class="odd">
<td><p>Systemzustand und Diagnose</p></td>
<td><p>HTTP-Protokollierung</p></td>
</tr>
<tr class="even">
<td><p>Integrität und Diagnose</p></td>
<td><p>Protokollierungstools</p></td>
</tr>
<tr class="odd">
<td><p>Integrität und Diagnose</p></td>
<td><p>Anforderungsüberwachung</p></td>
</tr>
<tr class="even">
<td><p>Integrität und Diagnose</p></td>
<td><p>Tracing</p></td>
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
<td><p>Authentifizierung der Client Zertifikatzuordnung</p></td>
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
<td><p>.NET-Erweiterbarkeit 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsentwicklung</p></td>
<td><p>ASP.NET 3,5</p></td>
</tr>
<tr class="even">
<td><p>Anwendungsentwicklung</p></td>
<td><p>ASP.NET 4,5</p></td>
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
<td><p>IIS 6-Metabase-Kompatibilität</p></td>
</tr>
<tr class="even">
<td><p>Verwaltungstools</p></td>
<td><p>IIS-Verwaltungsskripts und -tools</p></td>
</tr>
<tr class="odd">
<td><p>.NET 3,5 Framework-Features</p></td>
<td><p>.NET 3,5 Framework</p></td>
</tr>
<tr class="even">
<td><p>.NET 4,5 Framework-Features</p></td>
<td><p>.NET Framework 4,5</p></td>
</tr>
<tr class="odd">
<td><p>.NET 4,5 Framework-Features</p></td>
<td><p>ASP.NET 4,5</p></td>
</tr>
<tr class="even">
<td><p>.NET 4,5 Framework-Features</p></td>
<td><p>HTTP-Aktivierung</p></td>
</tr>
<tr class="odd">
<td><p>.NET 4,5 Framework-Features</p></td>
<td><p>TCP-Port Freigabe</p></td>
</tr>
<tr class="even">
<td><p>Intelligenter Hintergrundübertragungsdienst</p></td>
<td><p>IIS-Server Erweiterungen</p></td>
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
<td><p>Grafische Verwaltungs Tools und Infrastruktur</p></td>
</tr>
<tr class="even">
<td><p>Benutzeroberflächen und Infrastruktur</p></td>
<td><p>Desktop Umgebung</p></td>
</tr>
<tr class="odd">
<td><p>Benutzeroberflächen und Infrastruktur</p></td>
<td><p>Server-grafische Shell</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3,5</p></td>
<td><p>Windows Identity Foundation 3,5</p></td>
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


In Windows Server 2012 und Windows Server 2012 R2 können Sie Windows PowerShell 3,0 zum Installieren der IIS-Anforderungen verwenden. Geben Sie unter Verwendung des Server-Moduls in Windows PowerShell 3,0 Folgendes ein:

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Neu mit Windows Server 2012 ist der-source-Parameter, der definiert, wo die Windows Server 2012 Quellmedien gefunden werden können. Die Medien können als DVD-Laufwerk (beispielsweise D:\Sources\Sxs) oder für eine Netzwerkfreigabe definiert werden, in der die Mediendateien kopiert wurden (beispielsweise \\ fileserver\windows2012\sources\Sxs).



</div>

<div>

## <a name="see-also"></a>Siehe auch


[IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

