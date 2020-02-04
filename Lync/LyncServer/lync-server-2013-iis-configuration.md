---
title: 'Lync Server 2013: IIS-Konfiguration'
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
ms.openlocfilehash: 0cb8fe023d872ff19e29beb329488304048895b2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a>IIS-Konfiguration in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-17_

Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie am Server minimal als lokaler Administrator und Domänenbenutzer angemeldet sein.

Bevor Sie den Front-End-Server für lync Server 2013, Standard Edition oder den ersten Front-End-Server in einem Pool konfigurieren und installieren, installieren und konfigurieren Sie die Server Rolle und die Webdienste für Internet Informationsdienste (IIS).

<div class=" ">


> [!IMPORTANT]  
> Wenn Ihre Organisation erfordert, dass Sie IIS und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk finden, können Sie den Pfad für den Installationspfad für die lync Server 2013-Dateien im Dialogfeld "Setup" ändern, wenn Sie den lync Server 2013 zuerst installieren. Verwaltungstools. Sie installieren die Verwaltungstools, bevor Sie IIS installieren. Wenn Sie die Setup Dateien in diesem Pfad, einschließlich OCSCore. msi, installieren, werden die restlichen lync Server 2013-Dateien ebenfalls auf diesem Laufwerk bereitgestellt. Informationen zu dtails finden Sie unter <A href="lync-server-2013-install-lync-server-administrative-tools.md">Installieren von lync Server 2013-Verwaltungstools</A>. Ausführliche Informationen dazu, wie Sie die INETPUB, die vom Windows Server-Manager bereitgestellt werden, <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>bei der Installation von IIS verschieben, finden Sie unter.



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
<th>Rollen Überschrift</th>
<th>Rollendienst</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Allgemeine HTTP-Features installiert</p></td>
<td><p>Statischer Inhalt</p></td>
</tr>
<tr class="even">
<td><p>Allgemeine HTTP-Features installiert</p></td>
<td><p>Standarddokument</p></td>
</tr>
<tr class="odd">
<td><p>Allgemeine HTTP-Features installiert</p></td>
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
<td><p>Status und Diagnose</p></td>
<td><p>HTTP-Protokollierung</p></td>
</tr>
<tr class="odd">
<td><p>Status und Diagnose</p></td>
<td><p>Protokollierungstools</p></td>
</tr>
<tr class="even">
<td><p>Status und Diagnose</p></td>
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
<td><p>Authentifizierung der Client Zertifikatzuordnung</p></td>
</tr>
<tr class="even">
<td><p>Sicherheit</p></td>
<td><p>Anforderungsfilterung</p></td>
</tr>
<tr class="odd">
<td><p>Leistung</p></td>
<td><p>Komprimierung statischer Inhalte</p>
<p>Dynamische Inhaltskomprimierung</p></td>
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


Auf dem Windows Server 2008 R2 SP1 x64-Betriebssystem können Sie Windows PowerShell 2,0 verwenden. Sie müssen zuerst das Server-Modul importieren und dann die IIS 7,5-Rollen-und-Rollendienste installieren.

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> Die anonyme Authentifizierung wird standardmäßig mit der IIS-Serverrolle installiert. Sie können die anonyme Authentifizierung nach der Installation von IIS verwalten. Ausführliche Informationen finden Sie unter "Aktivieren der <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>anonymen Authentifizierung (IIS 7.0)" unter.



</div>

In der folgenden Tabelle sind die erforderlichen IIS 8,0-und IIS 8,5-Rollendienste für Windows Server 2012 und Windows Server 2012 R2 angegeben.

<div class=" ">


> [!NOTE]  
> Für Windows Server 2012 und Windows Server 2012 R2 wurde das Cmdlet Add-Cmdlets durch das Cmdlet Install-Cmdlets ersetzt. Ausführliche Informationen finden Sie unter <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">install-Cmdlets</A>.



</div>

### <a name="iis-80-and-iis-85-role-services"></a>IIS 8,0 und IIS 8,5-Rollendienste

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rollen Überschrift</th>
<th>Rollendienst</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Webserver (IIS)</p></td>
<td><p>Web Server</p></td>
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
<td><p>Anforderungs Monitor</p></td>
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
<td><p>Server seitige includes</p></td>
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
<td><p>.NET 3,5-Framework</p></td>
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
<td><p>Freihand-und Handschriftdienste</p></td>
<td><p>Freihand-und Handschriftdienste</p></td>
</tr>
<tr class="even">
<td><p>Media Foundation</p></td>
<td><p>Media Foundation</p></td>
</tr>
<tr class="odd">
<td><p>Benutzeroberflächen und Infrastruktur</p></td>
<td><p>Grafische Verwaltungs Tools und-Infrastruktur</p></td>
</tr>
<tr class="even">
<td><p>Benutzeroberflächen und Infrastruktur</p></td>
<td><p>Desktop Experience</p></td>
</tr>
<tr class="odd">
<td><p>Benutzeroberflächen und Infrastruktur</p></td>
<td><p>Grafische Server-Shell</p></td>
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


In Windows Server 2012 und Windows Server 2012 R2 können Sie Windows PowerShell 3,0 verwenden, um die IIS-Anforderungen zu installieren. Geben Sie im Server-Modul von Windows PowerShell 3,0 Folgendes ein:

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Neu in Windows Server 2012 ist der-source-Parameter, der definiert, wo die Windows Server 2012-Quellmedien gefunden werden können. Die Medien können als DVD-Laufwerk (beispielsweise D:\Sources\Sxs) oder als Netzwerkfreigabe definiert werden, in der die Mediendateien kopiert wurden (beispielsweise \\fileserver\windows2012\sources\Sxs).



</div>

<div>

## <a name="see-also"></a>Siehe auch


[IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

