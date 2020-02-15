---
title: 'Lync Server 2013: Konfigurieren von clientbootstrapping-Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3827bf913c4108c1105376a6f178598a2fb45a06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Konfigurieren von clientbootstrapping-Richtlinien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Die Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) und der Gruppenrichtlinienobjekt-Editor sind Tools, die Sie zum Verwalten von Gruppenrichtlinien verwenden. Zur administrativen Vorlage für die Office-Gruppenrichtlinie gehören lync 2013. ADMX (ADMX) und. ADML (ADML) administrative Vorlagen, die die registrierungsbasierten Richtlinieneinstellungen enthalten, die Sie für Gruppenrichtlinienobjekte in der Domäne konfigurieren. ADML-Dateien sind sprachspezifische Ergänzungen zu ADMX-Dateien. Jede ADMX-und ADML-Datei enthält die Richtlinieneinstellungen für eine einzelne Office-Anwendung. Weitere Informationen finden Sie unter "Office 2013 administrative Template Files (ADMX, ADML)" in der Office 2013-Dokumentation <http://go.microsoft.com/fwlink/p/?linkid=267516>unter.

Für lync 2013 gibt es mehrere clientbootstrapping-Richtlinien, die Sie konfigurieren sollten, bevor sich Benutzer zum ersten Mal beim Server anmelden. Beispielsweise die Standardserver und der Sicherheitsmodus, die der Client verwenden soll, bis die Anmeldung abgeschlossen ist. Sie können Gruppenrichtlinien verwenden, um diese Einstellungen in den Computer Registrierungen der Benutzer einzurichten, bevor Sie sich anmelden und mit dem Empfang von in-Band-prokonfigurations Einstellungen vom Server beginnen. In der folgenden Tabelle sind die Gruppenrichtlinieneinstellungen aufgeführt, die für lync 2013 verfügbar sind.

### <a name="group-policy-settings-for-lync-2013"></a>Gruppenrichtlinieneinstellungen für Lync 2013

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
<td><p>Gibt an, wie lync 2013 den Transport und den Server identifiziert, der während der Anmeldung verwendet werden soll. In dieser Einstellung geben Sie Folgendes an:</p>
<ul>
<li><p>ServerAddressExternal: gibt den Servernamen oder die IP-Adresse an, die von Clients und verbundkontakten beim Herstellen einer Verbindung von außerhalb der externen Firewall verwendet wird.</p></li>
<li><p>ServerAddressInternal: gibt den Servernamen oder die IP-Adresse an, die verwendet wird, wenn Clients innerhalb der Firewall der Organisation eine Verbindung herstellen.</p></li>
<li><p>Transport: gibt entweder TCP (Transmission Control Protocol) oder TLS (Transport Layer Security) an.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Unterstützte zusätzliche Server Versionen<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Gibt eine Liste von Server Versionsnamen an, die durch Semikolons getrennt sind, an denen lync Server 2013 sich anmeldet, zusätzlich zu den standardmäßig unterstützten Server Versionen.</p></td>
</tr>
<tr class="odd">
<td><p>Deaktivieren des automatischen Uploads von Anmeldefehler Protokollen (DisableAutomaticSendTracing)</p></td>
<td><p>Lädt die Anmeldefehler Protokolle automatisch in lync Server zur Analyse hoch. Wenn die Anmeldung erfolgreich verläuft, werden keine Protokolle automatisch hochgeladen. Wenn diese Richtlinie nicht konfiguriert ist, geschieht Folgendes:</p>
<dl>
<dt><span></span></dt>
<dd><p>Für lync Online Benutzer: Anmeldefehler Protokolle werden automatisch hochgeladen.</p>
</dd>
<dt><span></span></dt>
<dd><p>Für lokale lync-Benutzer: dem Benutzer wird vor dem Hochladen ein Bestätigungsdialogfeld angezeigt.</p>
</dd>
</dl>
<p>Wenn diese Einstellung deaktiviert ist, werden Anmelde Protokolle automatisch in den lync Server für lokale und lync Online Benutzer von lync hochgeladen. Wenn diese Einstellung aktiviert ist, werden Anmelde Protokolle nie automatisch hochgeladen.</p></td>
</tr>
<tr class="even">
<td><p>HTTP-Fallback für SIP-Verbindung deaktivieren<br />
(DisableHttpConnect)</p></td>
<td><p>Verhindert, dass lync Server versucht, eine Verbindung mit dem Server über HTTP herzustellen, wenn TLS oder TCP nicht verfügbar sind. Standardmäßig versucht lync zunächst, eine Verbindung mit dem Server mithilfe von TLS oder TCP herzustellen, und wenn keine dieser Transportmethoden erfolgreich ist, versucht lync, eine Verbindung über HTTP herzustellen. Verwenden Sie diese Richtlinie, um die Fallbackoption für den HTTP-Verbindungsversuch zu deaktivieren.</p></td>
</tr>
<tr class="odd">
<td><p>Anmeldeinformationen erforderlich<br />
DisableNTCredentials</p></td>
<td><p>Erfordert, dass der Benutzeranmeldeinformationen für lync bereitstellt, anstatt die Windows-Anmeldeinformationen bei der Anmeldung bei einem SIP-Server automatisch zu verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Deaktivieren der Server Versionsüberprüfung<br />
(DisableServerCheck)</p></td>
<td><p>Wenn Sie diese Richtlinie auf 1 festlegen, wird verhindert, dass lync den Servernamen und die Version überprüft, bevor Sie sich anmelden. Standardmäßig führt lync diese Prüfungen aus, bevor er sich anmeldet.</p></td>
</tr>
<tr class="odd">
<td><p>Aktivieren der Verwendung von Bits zum Herunterladen von Adressbuchdienst Dateien<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Ermöglicht lync die Verwendung des Background Intelligent Transfer Service (Bits) zum Herunterladen der Adressbuchdienste-Dateien.</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren des SIP-Sicherheitsmodus<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Ermöglicht lync das sichere Senden und empfangen von Sofortnachrichten. Diese Richtlinie hat keine Auswirkung auf Windows .NET- oder Microsoft Exchange Server-Dienste.</p>
<p>Wenn Sie diese Richtlinieneinstellung nicht konfigurieren, kann lync einen beliebigen Transport verwenden. Wenn jedoch TLS nicht verwendet wird und der Server Benutzer authentifiziert, muss lync entweder NTLM oder Kerberos-Authentifizierung verwenden.</p></td>
</tr>
<tr class="odd">
<td><p>Anfängliche Verzögerung für das globale Adressbuch herunterladen<br />
GalDownloadInitialDelay</p></td>
<td><p>Gibt den Zeitraum an, vor dem ein Download der globalen Adressliste (GAL) erfolgt. Der Standardwert ist 60 Minuten, was bedeutet, dass der Server den Download der GAL-Datei für einen zufälligen Zeitraum zwischen 0 und 60 Minuten verzögert.</p></td>
</tr>
<tr class="even">
<td><p>Verhindern der Ausführung von Microsoft lync durch Benutzer<br />
(PreventRun)</p></td>
<td><p>Verhindert, dass Benutzer lync durchführen. Diese Richtlinieneinstellung kann sowohl in der Computerkonfiguration als auch in der Benutzerkonfiguration vorgenommen werden, die Einstellung in der Computerkonfiguration hat jedoch Vorrang.</p></td>
</tr>
<tr class="odd">
<td><p>Zulassen der Speicherung von Benutzerkennwörtern<br />
SavePassword</p></td>
<td><p>Ermöglicht lync das Speichern von Kennwörtern.</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren des SIP-Komprimierungsmodus<br />
(SipCompression)</p></td>
<td><p>Legt fest, wann die SIP-Komprimierung aktiviert wird. Die SIP-Komprimierung wird standardmäßig auf Grundlage der Adaptergeschwindigkeit aktiviert. Beachten Sie, dass die Festlegung dieser Richtlinie die Anmeldezeit verlängern kann.</p></td>
</tr>
<tr class="odd">
<td><p>Liste vertrauenswürdiger Domänen<br />
(TrustModelData)</p></td>
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
<th>Vorrang</th>
<th>Ort oder Einstellungsmethode</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 </p></td>
<td><p>Lync Server 2013-in-Band-prozielung</p></td>
</tr>
<tr class="even">
<td><p>2 </p></td>
<td><p>HKEY_LOCAL_MACHINE \software\policies\microsoft\office\15.0\lync</p></td>
</tr>
<tr class="odd">
<td><p>3 </p></td>
<td><p>HKEY_CURRENT_USER \software\policies\microsoft\office\15.0\lync</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>Das Dialogfeld lync-Optionen in lync 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>So definieren Sie Gruppenrichtlinieneinstellungen mithilfe der lync 2013 administrativen Vorlagendateien

1.  Erstellen Sie einen Ordner auf Stammebene, der alle sprachneutralen ADMX-Dateien enthält. Erstellen Sie den Stammordner für den zentralen Speicher beispielsweise auf dem Domänencontroller an folgendem Speicherort:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > Bei diesem Verfahren wird davon ausgegangen, dass Sie mehrere Computer in Ihrer Domäne verwalten möchten. In diesem Fall speichern Sie die Vorlagen in einem zentralen Speicher im Ordner "SYSVOL" auf dem primären Domänencontroller. Dadurch wird ein replizierter zentraler Speicherort für administrative Domänen Vorlagen bereitgestellt.

    
    </div>

2.  Erstellen Sie einen Unterordner für jede Sprache, die Sie verwenden möchten. Diese Unterordner enthalten die sprachspezifischen ADML-Ressourcendateien. Erstellen Sie an dieser Stelle beispielsweise einen Unterordner für Englisch (en-US) für Deutschland:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

