---
title: IIS-Anforderungen für Front-End-Pools und Standard Edition-Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc92cc4c27f7af395a8e41bec26679a27010562d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-19_

Für Standard Edition-Server und Front-End-Server und Directors erstellt das lync Server 2013-Installationsprogramm virtuelle Verzeichnisse in Internet Information Services (IIS) für die folgenden Zwecke:

  - So ermöglichen Sie Benutzern das Herunterladen von Dateien aus dem Adressbuchdienst

  - So aktivieren Sie Clients zum Abrufen von Updates

  - So aktivieren Sie Konferenzen

  - So ermöglichen Sie Benutzern das Herunterladen von Besprechungsinhalten

  - So ermöglichen Sie Benutzern das Erweitern von Verteilergruppen

  - So aktivieren Sie Telefonkonferenzen

  - So aktivieren Sie Reaktionsgruppenfeatures

Darüber hinaus erstellt das kumulative Update für lync Server 2010: November 2011-Installer virtuelle Verzeichnisse in IIS für die folgenden Zwecke:

  - Auf Front-End-Servern oder Standard Edition-Servern zur Unterstützung von Mobilitätsfunktionen wie Instant Messaging (Sofortnachrichten) und Anwesenheit auf mobilen Geräten

  - Auf Front-End-Servern oder Standard Edition-Servern und auf Directors, damit Mobile Geräte mobilitätsressourcen automatisch ermitteln können



> [!NOTE]
> Bei der Bereitstellung von Mobility wird die Verwendung von IIS 7,5 empfohlen. Das Installationsprogramm für lync Server Mobility Service legt einige ASP.net-Flags fest, um die Leistung zu verbessern. IIS 7.5 ist standardmäßig unter Windows Server 2008 R2 installiert, und der Mobilitätsdienst-Installer ändert die ASP.NET-Einstellungen automatisch. Wenn Sie IIS 7.0 unter Windows Server 2008 verwenden, müssen Sie diese Einstellungen manuell ändern.



Für lync Server müssen die folgenden IIS-Module installiert werden:


> [!IMPORTANT]
> Wenn in Ihrer Organisation IIS und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk lokalisiert werden müssen, können Sie den Installationspfad für die lync Server Dateien im Dialogfeld Setup ändern. Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore. msi, werden auch die restlichen lync Server Dateien auf diesem Laufwerk bereitgestellt. Ausführliche Informationen zum Verschieben des von Windows Server-Manager bereitgestellten Verzeichnis Inetpub bei der Installation von <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>IIS finden Sie unter.


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

  - Anonyme Authentifizierung (wird bei der Installation von IIS standardmäßig installiert)

  - Authentifizierung der Client Zertifikatzuordnung

In der folgenden Tabelle sind die URIs für die virtuellen Verzeichnisse für den internen Zugriff und die Dateisystemressourcen aufgeführt, auf die Sie sich berufen.

### <a name="virtual-directories-for-internal-access"></a>Virtuelle Verzeichnisse für internen Zugriff

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Feature</th>
<th>URI des virtuellen Verzeichnisses</th>
<th>Bezug auf</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Adressbuchserver</p></td>
<td><p>https://&lt;Interner FQDN&gt;/ABS/int/Handler</p></td>
<td><p>Speicherort der Adressbuch Server-Downloaddateien für interne Benutzer.</p></td>
</tr>
<tr class="even">
<td><p>AutoErmittlungsdienst</p></td>
<td><p>https://&lt;Interner FQDN&gt;/autodiscover</p></td>
<td><p>Speicherort des lync Server AutoErmittlungsdiensts, der mobilitätsressourcen für Benutzer interner mobiler Geräte sucht.</p></td>
</tr>
<tr class="odd">
<td><p>Clientupdates</p></td>
<td><p>http://&lt;Interner FQDN&gt;/AutoUpdate/int</p></td>
<td><p>Speicherort der Updatedateien für interne computerbasierte Clients.</p></td>
</tr>
<tr class="even">
<td><p>Conf</p></td>
<td><p>http://&lt;Interner FQDN&gt;/conf/int</p></td>
<td><p>Speicherort von Konferenzressourcen für interne Benutzer.</p></td>
</tr>
<tr class="odd">
<td><p>Geräte Updates</p></td>
<td><p>http://&lt;Interner FQDN&gt;/DeviceUpdateFiles_Int</p></td>
<td><p>Speicherort der UC-Geräteaktualisierungsdateien (Unified Communications) für interne UC-Geräte.</p></td>
</tr>
<tr class="even">
<td><p>Besprechung</p></td>
<td><p>http://&lt;Interner FQDN&gt;/etc/Place/NULL</p></td>
<td><p>Speicherort des Besprechungsinhalts für interne Benutzer.</p></td>
</tr>
<tr class="odd">
<td><p>Mobilitätsdienst</p></td>
<td><p>https://&lt;Interner FQDN&gt;/MCX</p></td>
<td><p>Speicherort der Mobilitätsdienst Ressourcen für Benutzer interner mobiler Geräte.</p></td>
</tr>
<tr class="even">
<td><p>Gruppenerweiterung und Adressbuch-Webabfragedienst</p></td>
<td><p>http://&lt;Interner FQDN&gt;/GroupExpansion/int/Service.asmx</p></td>
<td><p>Speicherort des Webdiensts, der die Gruppenerweiterung für interne Benutzer ermöglicht. Außerdem wird der Speicherort des Adressbuch-Webabfragedienst, der Informationen zur globalen Adressliste für interne lync Mobile Microsoft lync 2010 Mobile-Clients bereitstellt.</p></td>
</tr>
<tr class="odd">
<td><p>Telefonkonferenzen</p></td>
<td><p>http://&lt;Interner FQDN&gt;/PhoneConferencing/int</p></td>
<td><p>Speicherort der Telefonkonferenz Daten für interne Benutzer.</p></td>
</tr>
<tr class="even">
<td><p>Geräte Updates</p></td>
<td><p>http://&lt;Interner FQDN&gt;/RequestHandler</p></td>
<td><p>Speicherort des Anforderungshandlers für den Geräte Update-Webdienst, mit dem interne UC-Geräteprotokolle hochladen und nach Updates suchen können.</p></td>
</tr>
<tr class="odd">
<td><p>Reaktionsgruppenanwendung</p></td>
<td><p>http://&lt;Interner FQDN&gt;/RgsConfig</p>
<p>http://&lt;Interner FQDN&gt;/RgsClients</p></td>
<td><p>Speicherort des Reaktionsgruppen-Konfigurationstools.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Für Front-End-Pools in einer konsolidierten Konfiguration müssen Sie IIS bereitstellen, bevor Sie dem Pool Server hinzufügen können.


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" />Sicherheitshinweis:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Sie müssen das IIS-Verwaltungs-Snap-in verwenden, um das vom IIS-Webkomponentenserver verwendete Zertifikat zuzuweisen.</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

