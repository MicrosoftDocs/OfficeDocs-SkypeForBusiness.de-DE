---
title: 'Lync Server 2013: Konfigurieren von Client-Trap Ping-Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06119d5488b47adfe01a934aca9a55581feaf33e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Konfigurieren von Client-Trap Ping-Richtlinien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Die Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) und der Gruppenrichtlinienobjekt-Editor sind Tools zur Verwaltung von Gruppenrichtlinien. In der administrativen Vorlage für Office-Gruppenrichtlinien sind lync 2013. ADMX (ADMX)-und ADML (ADML)-administrative Vorlagen enthalten, die die registrierungsbasierten Richtlinieneinstellungen enthalten, die Sie für Gruppenrichtlinienobjekte in der Domäne konfigurieren. ADML-Dateien sind sprachspezifische Komplemente für ADMX-Dateien. Jede ADMX- und ADML-Datei enthält die Richtlinieneinstellungen für eine einzelne Office-Anwendung. Weitere Informationen finden Sie unter "Office 2013 administrative Template Files (ADMX, ADML)" in der Office 2013-Dokumentation <http://go.microsoft.com/fwlink/p/?linkid=267516>unter.

Für lync 2013 gibt es mehrere Richtlinien für Client-Bootstrapping, die Sie konfigurieren sollten, bevor sich Benutzer zum ersten Mal beim Server anmelden. Dazu gehören die Standardserver und der Sicherheitsmodus, die der Client bis zum Abschluss der Anmeldung verwenden soll. Sie können die Gruppenrichtlinie verwenden, um diese Einstellungen in den Registrierungen der Computer von Benutzern vorzunehmen, bevor diese sich anmelden und erstmals In-Band-Bereitstellungseinstellungen vom Server empfangen. In der folgenden Tabelle sind die Gruppenrichtlinieneinstellungen aufgeführt, die für lync 2013 verfügbar sind.

### <a name="group-policy-settings-for-lync-2013"></a>Gruppenrichtlinieneinstellungen für lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppenrichtlinieneinstellung</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server angeben<br />
(ConfigurationMode)</p></td>
<td><p>Gibt an, wie lync 2013 den Transport und den Server identifiziert, die bei der Anmeldung zu verwenden sind. In dieser Einstellung geben Sie Folgendes an:</p>
<ul>
<li><p>ServerAddressExternal: Gibt den Servernamen oder die IP-Adresse an, der bzw. die von Clients und Verbundkontakten verwendet wird, um von außerhalb der Firewall eine Verbindung herzustellen.</p></li>
<li><p>ServerAddressInternal: Gibt den Servernamen oder die IP-Adresse an, der bzw. die verwendet wird, wenn Clients eine Verbindung von innerhalb der Unternehmensfirewall herstellen.</p></li>
<li><p>Transport: Gibt entweder TCP (Transmission Control Protocol) oder TLS (Transport Layer Security) an.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Zusätzliche Server Versionen unterstützt<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Gibt eine Liste der Server Versionsnamen an, die durch Semikolons getrennt sind, bei denen sich lync Server 2013 zusätzlich zu den standardmäßig unterstützten Server Versionen anmeldet.</p></td>
</tr>
<tr class="odd">
<td><p>Automatisches Hochladen von Anmeldefehlerprotokollen deaktivieren (DisableAutomaticSendTracing)</p></td>
<td><p>Automatisches Hochladen von Anmeldefehler Protokollen zur Analyse in lync Server. Bei erfolgreichen Anmeldungen werden keine Protokolle automatisch hochgeladen. Wenn diese Richtlinie nicht konfiguriert ist, geschieht Folgendes:</p>
<dl>
<dt><span></span></dt>
<dd><p>Für lync Online-Benutzer: Anmeldefehler Protokolle werden automatisch hochgeladen.</p>
</dd>
<dt><span></span></dt>
<dd><p>Für lokale lync-Benutzer: dem Benutzer wird vor dem Hochladen ein Bestätigungsdialogfeld angezeigt.</p>
</dd>
</dl>
<p>Wenn diese Einstellung deaktiviert ist, werden Anmelde Protokolle automatisch für lync-lokale und lync Online-Benutzer auf den lync-Server hochgeladen. Wenn diese Einstellung aktiviert ist, werden Anmeldeprotokolle niemals automatisch hochgeladen.</p></td>
</tr>
<tr class="even">
<td><p>Deaktivieren des http-Fallbacks für die SIP-Verbindung<br />
(DisableHttpConnect)</p></td>
<td><p>Verhindert, dass lync Server versucht, eine Verbindung mit dem Server über HTTP herzustellen, wenn TLS oder TCP nicht verfügbar sind. Standardmäßig versucht lync zunächst, mithilfe von TLS oder TCP eine Verbindung mit dem Server herzustellen, und wenn keine dieser Transportmethoden erfolgreich ist, versucht lync, eine Verbindung über HTTP herzustellen. Verwenden Sie diese Richtlinie, um den Fall Back http-Verbindungsversuch zu deaktivieren.</p></td>
</tr>
<tr class="odd">
<td><p>Anmeldeinformationen erforderlich<br />
(DisableNTCredentials)</p></td>
<td><p>Erfordert, dass der Benutzeranmeldeinformationen für lync bereitstellt, anstatt die Windows-Anmeldeinformationen bei der Anmeldung bei einem SIP-Server automatisch zu verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Deaktivieren der Server Versionsüberprüfung<br />
(DisableServerCheck)</p></td>
<td><p>Wenn Sie diese Richtlinie auf 1 festlegen, wird verhindert, dass lync den Servernamen und die Version überprüft, bevor Sie sich anmelden. Standardmäßig führt lync diese Prüfungen aus, bevor Sie sich anmelden.</p></td>
</tr>
<tr class="odd">
<td><p>Aktivieren der Verwendung von Bits zum Herunterladen von Adressbuchdienst Dateien<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Ermöglicht lync die Verwendung von Bits (Background Intelligent Transfer Service) zum Herunterladen der Adressbuchdienste-Dateien.</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren des SIP-Sicherheitsmodus<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Ermöglicht lync das sichere Senden und empfangen von Sofortnachrichten. Diese Richtlinie hat keine Auswirkung auf Windows .NET- oder Microsoft Exchange Server-Dienste.</p>
<p>Wenn Sie diese Richtlinieneinstellung nicht konfigurieren, kann lync einen beliebigen Transport verwenden. Wenn Sie aber nicht TLS verwenden und der Server Benutzer authentifiziert, muss lync entweder NTLM-oder Kerberos-Authentifizierung verwenden.</p></td>
</tr>
<tr class="odd">
<td><p>Download des globalen Adressbuchs Anfangsverzögerung<br />
GalDownloadInitialDelay</p></td>
<td><p>Legt den Zeitraum bis zum Download der globalen Adressliste (GAL) fest. Der Standardwert beträgt 60 Minuten, d. h., der Server verzögert den Download der globalen Adressliste um einen zufälligen Zeitraum zwischen 0 und 60 Minuten.</p></td>
</tr>
<tr class="even">
<td><p>Verhindern, dass Benutzer Microsoft lync ausführen<br />
(PreventRun)</p></td>
<td><p>Verhindert, dass Benutzer lync ausführen. Sie können diese Richtlinieneinstellung unter Computerkonfiguration und Benutzerkonfiguration konfigurieren, aber die Richtlinieneinstellung unter Computerkonfiguration hat Vorrang.</p></td>
</tr>
<tr class="odd">
<td><p>Speichern von Benutzerkennwörtern zulassen<br />
(SavePassword)</p></td>
<td><p>Ermöglicht lync das Speichern von Kennwörtern.</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren des SIP-Komprimierungsmodus<br />
(SipCompression)</p></td>
<td><p>Gibt an, wann die SIP-Komprimierung aktiviert wird. Die SIP-Komprimierung wird standardmäßig auf Grundlage der Adaptergeschwindigkeit aktiviert. Beachten Sie, dass die Festlegung dieser Richtlinie die Anmeldezeit verlängern kann.</p></td>
</tr>
<tr class="odd">
<td><p>Liste der vertrauenswürdigen Domänen<br />
TrustModelData</p></td>
<td><p>Listet die vertrauenswürdigen Domänen auf, die nicht mit dem Präfix der SIP-Domäne des Kunden übereinstimmen.</p></td>
</tr>
</tbody>
</table>


Auf dem Server konfigurierte Richtlinien haben Vorrang vor Gruppenrichtlinieneinstellungen und Clientoptionen, die vom Benutzer konfiguriert wurden. In der folgenden Tabelle wird zusammengefasst, welche Einstellungen Vorrang haben, falls ein Konflikt auftritt.

### <a name="group-policy-precedence"></a>Rangfolge von Gruppenrichtlinien

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rangfolge</th>
<th>Ort oder Einstellungsmethode</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Lync Server 2013-in-Band-Bereitstellung</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Das Dialogfeld "lync-Optionen" in lync 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>So definieren Sie Gruppenrichtlinieneinstellungen mithilfe der administrativen Vorlagendateien von lync 2013

1.  Erstellen Sie einen Ordner auf Stammebene, der alle sprachneutralen ADMX-Dateien enthalten soll. Erstellen Sie beispielsweise den Stammordner für den zentralen Speicher auf Ihrem Domänencontroller an folgendem Speicherort:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > Bei diesem Verfahren wird angenommen, dass Sie in Ihrer Domäne mehrere Computer verwalten möchten. Speichern Sie in diesem Fall die Vorlagen in einem zentralen Speicher im Ordner "Sysvol" auf dem primären Domänencontroller. Dies schafft einen replizierten zentralen Speicherort für administrative Domänenvorlagen.

    
    </div>

2.  Erstellen Sie einen Unterordner für jede Sprache, die Sie verwenden. Diese Unterordner enthalten die sprachenspezifischen ADML-Ressourcendateien. Erstellen Sie beispielsweise einen Unterordner für Englisch – USA (EN-US) an folgendem Speicherort:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

