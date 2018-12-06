---
title: 'Lync Server 2013: IIS-Anforderungen für Front-End-Pools und Standard Edition-Server'
TOCTitle: IIS-Anforderungen für Front-End-Pools und Standard Edition-Server
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399038(v=OCS.15)
ms:contentKeyID: 49295761
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Für Standard Edition-Server, Front End-Server und Director-Server erstellt das Lync Server 2013-Installationsprogramm virtuelle Verzeichnisse in Internetinformationsdienste (Internet Information Services, IIS), um Folgendes zu ermöglichen:

  - Herunterladen von Dateien aus dem Adressbuchdienst durch Remotebenutzer

  - Abrufen von Updates durch Clients

  - Ermöglichen von Konferenzen

  - Herunterladen von Besprechungsinhalten durch Benutzer

  - Erweiterung von Verteilergruppen durch externe Benutzer

  - Ermöglichen von Telefonkonferenzen

  - Ermöglichen von Reaktionsgruppenfunktionen

Darüber hinaus erstellt der Installer für das kumulative Update für Lync Server 2010: November 2011 in IIS virtuelle Verzeichnisse für die folgenden Zwecke:

  - Auf Front-End-Servern oder Standard Edition-Servern zur Unterstützung der Mobilitätsfunktionen wie Sofortnachrichten und Anwesenheit auf mobilen Geräten

  - Auf Front-End-Servern oder Standard Edition-Servern und auf Directors, damit mobile Geräte automatisch Mobilitätsressourcen ermitteln können


> [!NOTE]
> Wenn Sie Mobilität bereitstellen, wird empfohlen, IIS 7.5 zu verwenden. Der Lync Server-Mobilitätsdienst-Installer legt zur Leistungsverbesserung einige der ASP.NET-Kennzeichen fest. IIS 7.5 ist standardmäßig unter Windows Server 2008 R2 installiert, und der Mobilitätsdienst-Installer ändert die ASP.NET-Einstellungen automatisch. Wenn Sie IIS 7.0 unter Windows Server 2008 verwenden, müssen Sie diese Einstellungen manuell ändern.



Für Lync Server müssen folgende IIS-Module installiert sein:


> [!IMPORTANT]
> Sollte es erforderlich sein, dass Sie IIS und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk installieren, können Sie den Installationspfad für die Lync Server-Dateien im Setup-Dialogfeld ändern. Wenn Sie die Setupdateien, einschließlich OCSCore.msi, unter diesem Installationspfad installieren, werden auch die übrigen Lync Server-Dateien auf diesem Laufwerk bereitestellt. Einzelheiten dazu, wie Sie das vom Windows Server Manager bereitgestellte Verzeichnis INETPUB beim Installieren von IIS an anderer Stelle platzieren können, finden Sie unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=216888">http://go.microsoft.com/fwlink/?linkid=216888</A>.



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

In der folgenden Tabelle werden die URIs für die virtuellen Verzeichnisse zum internen Zugriff und die Dateisystemressourcen aufgeführt, auf die diese verweisen.

### Virtuelle Verzeichnisse für den internen Zugriff

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktion</th>
<th>URI des virtuellen Verzeichnisses</th>
<th>Verweis auf</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Adressbuchserver</p></td>
<td><p>https:// <em>&lt;Interner FQDN&gt;</em> /ABS/int/Handler</p></td>
<td><p>Speicherort der Adressbuchserver-Downloaddateien für interne Benutzer</p></td>
</tr>
<tr class="even">
<td><p>AutoErmittlungsdienst</p></td>
<td><p>https:// <em>&lt;Interner FQDN&gt;</em> /Autodiscover</p></td>
<td><p>Ort des Lync Server-AutoErmittlungsdiensts, der Mobilitätsressourcen für interne mobile Gerätebenutzer ermittelt.</p></td>
</tr>
<tr class="odd">
<td><p>Clientupdates</p></td>
<td><p>http:// <em>&lt;Interner FQDN&gt;</em> /AutoUpdate/Int</p></td>
<td><p>Speicherort der Updatedateien für interne computerbasierte Clients</p></td>
</tr>
<tr class="even">
<td><p>Konferenz</p></td>
<td><p>http:// <em>&lt;Interner FQDN&gt;</em> /Conf/Int</p></td>
<td><p>Speicherort der Konferenzressourcen für interne Benutzer</p></td>
</tr>
<tr class="odd">
<td><p>Geräteaktualisierungen</p></td>
<td><p>http:// <em>&lt;Interner FQDN&gt;</em> /DeviceUpdateFiles_Int</p></td>
<td><p>Speicherort der UC-Geräteaktualisierungsdateien (Unified Communications) für interne UC-Geräte</p></td>
</tr>
<tr class="even">
<td><p>Besprechung</p></td>
<td><p>http:// <em>&lt;Interner FQDN&gt;</em> /etc/place/null</p></td>
<td><p>Speicherort der Besprechungsinhalte für interne Benutzer</p></td>
</tr>
<tr class="odd">
<td><p>Mobilitätsdienst</p></td>
<td><p>https:// <em>&lt;Interner FQDN&gt;</em> /Mcx</p></td>
<td><p>Ort der der Mobilitätsressourcen für interne mobile Gerätebenutzer.</p></td>
</tr>
<tr class="even">
<td><p>Gruppenerweiterung und Adressbuch-Webabfragedienst</p></td>
<td><p>http:// <em>&lt;Interner FQDN&gt;</em> /GroupExpansion/int/service.asmx</p></td>
<td><p>Speicherort des Webdiensts, der die Gruppenerweiterung für interne Besucher ermöglicht, zudem der Speicherort des Adressbuch-Webabfragediensts, der für die internen Lync Mobile- Microsoft Lync 2010 Mobile-Clients Informationen aus der globalen Adressliste bereitstellt.</p></td>
</tr>
<tr class="odd">
<td><p>Telefonkonferenz</p></td>
<td><p>http:// <em>&lt;Interner FQDN&gt;</em> /PhoneConferencing/Int</p></td>
<td><p>Speicherort der Telefonkonferenzdaten für interne Benutzer</p></td>
</tr>
<tr class="even">
<td><p>Geräteaktualisierungen</p></td>
<td><p>http:// <em>&lt;Interner FQDN&gt;</em> /RequestHandler</p></td>
<td><p>Speicherort des Anforderungshandlers für den Geräteaktualisierungswebdienst, über den interne UC-Geräte Protokolle hochladen und nach Updates suchen können</p></td>
</tr>
<tr class="odd">
<td><p>Reaktionsgruppenanwendung</p></td>
<td><p>http:// <em>&lt;Interner FQDN&gt;</em> /RgsConfig</p>
<p>http:// <em>&lt;Interner FQDN&gt;</em> /RgsClients</p></td>
<td><p>Speicherort des Konfigurationstools für Reaktionsgruppen</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Bei Front-End-Pools in einer konsolidierten Konfiguration müssen Sie IIS bereitstellen, bevor Sie dem Pool Server hinzufügen können.



<table>
<thead>
<tr class="header">
<th><img src="images/Gg399038.security(OCS.15).gif" title="security" alt="security" />Sicherheit Hinweis:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Sie müssen das vom IIS-Webkomponentenserver verwendete Zertifikat über das IIS-Verwaltungs-Snap-In zuweisen.</td>
</tr>
</tbody>
</table>

