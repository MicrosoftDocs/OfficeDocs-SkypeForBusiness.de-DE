---
title: IIS-Anforderungen für Front-End-Pools und Standard Edition-Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d804df614eab49eeabe82cca9d304e082d9ced3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-19_

Bei Standard Edition-Servern und-Front-End-Servern sowie Directors erstellt das lync Server 2013-Installationsprogramm virtuelle Verzeichnisse in Internet Informationsdienste (IIS) für die folgenden Zwecke:

  - So aktivieren Sie Benutzer zum Herunterladen von Dateien aus dem Adressbuchdienst

  - So aktivieren Sie Clients zum Abrufen von Updates

  - So aktivieren Sie Konferenzen

  - So aktivieren Sie Benutzer zum Herunterladen von Besprechungsinhalten

  - So aktivieren Sie Benutzer zum Erweitern von Verteilergruppen

  - So aktivieren Sie Telefonkonferenzen

  - So aktivieren Sie die Features der Reaktionsgruppe

Darüber hinaus erstellt das kumulative Update für lync Server 2010: November 2011-Installationsprogramm virtuelle Verzeichnisse in IIS für die folgenden Zwecke:

  - Auf Front-End-Servern oder Standard Edition-Servern zur Unterstützung von Mobilitätsfunktionen wie Instant Messaging (im) und Anwesenheit auf mobilen Geräten

  - Auf Front-End-Servern oder Standard Edition-Servern und auf Directors, damit Mobile Geräte mobilitätsressourcen automatisch entdecken können



> [!NOTE]
> Wenn Sie Mobilität bereitstellen, empfehlen wir, IIS 7,5 zu verwenden. Das lync Server Mobility Service-Installationsprogramm legt einige ASP.net-Flags fest, um die Leistung zu verbessern. IIS 7,5 wird standardmäßig unter Windows Server 2008 R2 installiert, und das Mobilitätsdienst-Installationsprogramm ändert automatisch die ASP.NET-Einstellungen. Wenn Sie IIS 7,0 unter Windows Server 2008 verwenden, müssen Sie diese Einstellungen manuell ändern.



Für lync Server müssen die folgenden IIS-Module installiert werden:


> [!IMPORTANT]
> Wenn Ihre Organisation erfordert, dass Sie IIS und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk finden, können Sie den Pfad für den Installationspfad für die lync Server-Dateien im Dialogfeld einrichten ändern. Wenn Sie die Setup Dateien in diesem Pfad, einschließlich OCSCore. msi, installieren, werden die restlichen lync Server-Dateien ebenfalls auf diesem Laufwerk bereitgestellt. Ausführliche Informationen dazu, wie Sie die INETPUB, die vom Windows Server-Manager bereitgestellt werden, <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>bei der Installation von IIS verschieben, finden Sie unter.


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

In der folgenden Tabelle sind die URIs für die virtuellen Verzeichnisse für den internen Zugriff und die Dateisystemressourcen aufgelistet, auf die Sie verweisen.

### <a name="virtual-directories-for-internal-access"></a>Virtuelle Verzeichnisse für den internen Zugriff

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Feature</th>
<th>URI für virtuelles Verzeichnis</th>
<th>Bezieht sich auf</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Adressbuchserver</p></td>
<td><p>https://&lt;Interner FQDN&gt;-/ABS/int/Handler</p></td>
<td><p>Speicherort der Adressbuch Server-Downloaddateien für interne Benutzer.</p></td>
</tr>
<tr class="even">
<td><p>AutoErmittlungsdienst</p></td>
<td><p>https://&lt;Interner FQDN&gt;-/autodiscover</p></td>
<td><p>Der Speicherort des lync Server-AutoErmittlungsdiensts, der mobilitätsressourcen für interne Benutzer von mobilen Geräten findet.</p></td>
</tr>
<tr class="odd">
<td><p>Clientupdates</p></td>
<td><p>http://&lt;Interner FQDN&gt;-/AutoUpdate/int</p></td>
<td><p>Speicherort der Updatedateien für interne computerbasierte Clients.</p></td>
</tr>
<tr class="even">
<td><p>Conf</p></td>
<td><p>http://&lt;Interner FQDN&gt;-/conf/int</p></td>
<td><p>Der Speicherort der Konferenzressourcen für interne Benutzer.</p></td>
</tr>
<tr class="odd">
<td><p>Geräte Updates</p></td>
<td><p>http://&lt;Interner FQDN&gt;-/DeviceUpdateFiles_Int</p></td>
<td><p>Speicherort der Unified Communications (UC)-Geräteaktualisierungsdateien für interne UC-Geräte.</p></td>
</tr>
<tr class="even">
<td><p>Besprechung</p></td>
<td><p>http://&lt;Interner FQDN&gt;-/etc/Place/NULL</p></td>
<td><p>Ort des Besprechungsinhalts für interne Benutzer.</p></td>
</tr>
<tr class="odd">
<td><p>Mobilitätsdienst</p></td>
<td><p>https://&lt;Interner FQDN&gt;-/MCX</p></td>
<td><p>Speicherort der Mobilitätsdienst Ressourcen für Benutzer interner mobiler Geräte.</p></td>
</tr>
<tr class="even">
<td><p>Gruppenerweiterung und Adressbuch-Webabfrage Dienst</p></td>
<td><p>http://&lt;Interner FQDN&gt;-/GroupExpansion/int/Service.asmx</p></td>
<td><p>Der Speicherort des Webdiensts, der die Gruppenerweiterung für interne Benutzer ermöglicht. Außerdem wird der Speicherort des Adressbuch-Webabfrage Diensts bereitgestellt, der den internen lync Mobile Microsoft lync 2010 Mobile-Clients globale Adresslisteninformationen bereitstellt.</p></td>
</tr>
<tr class="odd">
<td><p>Telefonkonferenzen</p></td>
<td><p>http://&lt;Interner FQDN&gt;-/PhoneConferencing/int</p></td>
<td><p>Standort von Telefonkonferenz Daten für interne Benutzer.</p></td>
</tr>
<tr class="even">
<td><p>Geräte Updates</p></td>
<td><p>http://&lt;Interner FQDN&gt;-/RequestHandler</p></td>
<td><p>Der Speicherort des Webdienst Anforderungshandlers für den Geräteaktualisierungsdienst, der es internen UC-Geräten ermöglicht, Protokolle hochzuladen und auf Updates zu überprüfen.</p></td>
</tr>
<tr class="odd">
<td><p>Reaktionsgruppenanwendung</p></td>
<td><p>http://&lt;Interner FQDN&gt;-/RgsConfig</p>
<p>http://&lt;Interner FQDN&gt;-/RgsClients</p></td>
<td><p>Speicherort des Reaktionsgruppen-Konfigurationstools</p></td>
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

