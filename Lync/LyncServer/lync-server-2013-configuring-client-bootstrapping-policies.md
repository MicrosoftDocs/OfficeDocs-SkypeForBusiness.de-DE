---
title: Konfigurieren von Richtlinien für das Clientbootstrapping in Lync Server 2013
TOCTitle: Konfigurieren von Richtlinien für das Clientbootstrapping in Lync Server 2013
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425941(v=OCS.15)
ms:contentKeyID: 49293853
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Richtlinien für das Clientbootstrapping in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Die Gruppenrichtlinien-Verwaltungskonsole und der Gruppenrichtlinienobjekt-Editor sind Tools zur Verwaltung der Gruppenrichtlinie. Die administrativen Vorlagen .admx (ADMX) und .adml (ADML) für Lync 2013 sind in der administrativen Vorlage "Office-Gruppenrichtlinie" eingeschlossen und enthalten die registrierungsbasierten Richtlinieneinstellungen, die Sie für Gruppenrichtlinienobjekte in der Domäne konfigurieren. ADML-Dateien sind sprachenspezifische Komplemente für ADMX-Dateien. Jede ADMX- und ADML-Datei enthält die Richtlinieneinstellungen für eine einzelne Office-Anwendung.

Für Lync 2013 gibt es verschiedene Richtlinien für das Clientbootstrapping, die Sie vor der ersten Anmeldung von Benutzern am Server konfigurieren sollten, beispielsweise die Standardserver und der Sicherheitsmodus, die der Client verwenden sollte, bis der Anmeldevorgang abgeschlossen ist. Sie können die Gruppenrichtlinie verwenden, um diese Einstellungen in den Registrierungen der Computer von Benutzern vorzunehmen, bevor diese sich anmelden und erstmals In-Band-Bereitstellungseinstellungen vom Server empfangen. In der folgenden Tabelle sind die für Lync 2013 verfügbaren Gruppenrichtlinieneinstellungen aufgeführt.

### Gruppenrichtlinieneinstellungen für Lync 2013

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
<td><p>Gibt an, wie Lync 2013 das bei der Anmeldung zu verwendende Transportprotokoll sowie den zu verwendenden Server ermittelt. In dieser Einstellung geben Sie Folgendes an:</p>
<ul>
<li><p>ServerAddressExternal: Gibt den Servernamen oder die IP-Adresse an, der bzw. die von Clients und Verbundkontakten verwendet wird, um von außerhalb der Firewall eine Verbindung herzustellen.</p></li>
<li><p>ServerAddressInternal: Gibt den Servernamen oder die IP-Adresse an, der bzw. die verwendet wird, wenn Clients eine Verbindung von innerhalb der Unternehmensfirewall herstellen.</p></li>
<li><p>Transport: Gibt entweder TCP (Transmission Control Protocol) oder TLS (Transport Layer Security) an.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Zusätzliche unterstützte Serverversionen<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Gibt eine durch Semikolons getrennte Liste mit Namen von Serverversionen an, bei denen Lync Server 2013 sich anmeldet – zusätzlich zu den Serverversionen, die standardmäßig unterstützt werden.</p></td>
</tr>
<tr class="odd">
<td><p>Automatisches Hochladen von Anmeldefehlerprotokollen deaktivieren (DisableAutomaticSendTracing)</p></td>
<td><p>Lädt Anmeldefehlerprotokolle automatisch zur Analyse auf Lync Server hoch. Bei erfolgreicher Anmeldung werden keine Protokolle automatisch hochgeladen. Wenn diese Richtlinie nicht konfiguriert ist, tritt folgende Situation ein:</p>
<dl>
<dt><span></span></dt>
<dd><p>Für Lync Online-Benutzer: Anmeldefehlerprotokolle werden automatisch hochgeladen.</p>
</dd>
<dt><span></span></dt>
<dd><p>Für lokale Lync-Benutzer: Dem Benutzer wird vor dem Hochladen ein Bestätigungsdialogfeld angezeigt.</p>
</dd>
</dl>
<p>Wenn diese Einstellung deaktiviert ist, werden Anmeldeprotokolle sowohl für lokale Lync-Benutzer als auch für Lync Online-Benutzer automatisch auf Lync Server hochgeladen. Wenn diese Einstellung aktiviert ist, werden Anmeldeprotokolle niemals automatisch hochgeladen.</p></td>
</tr>
<tr class="even">
<td><p>HTTP-Fallback für SIP-Verbindung deaktivieren<br />
(DisableHttpConnect)</p></td>
<td><p>Verhindert, dass Lync Server versucht, sich mithilfe von HTTP mit dem Server zu verbinden, wenn TLS oder TCP nicht verfügbar ist. Standardmäßig versucht Lync zunächst, sich über TLS oder TCP mit dem Server zu verbinden. Wenn keine dieser Transportmethoden erfolgreich ist, versucht Lync, die Verbindung über HTTP herzustellen. Verwenden Sie diese Richtlinie, um die Fallbackoption für den HTTP-Verbindungsversuch zu deaktivieren.</p></td>
</tr>
<tr class="odd">
<td><p>Anmeldedaten sind erforderlich<br />
(DisableNTCredentials)</p></td>
<td><p>Bewirkt, dass der Benutzer bei der Anmeldung an einem SIP-Server (Session Initiation-Protokoll) Anmeldeinformationen für Lync angeben muss und nicht automatisch die Windows-Anmeldinformationen verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p>Server-Versionsprüfung deaktivieren<br />
(DisableServerCheck)</p></td>
<td><p>Wenn Sie diese Richtlinie auf &quot;1&quot; festlegen, wird verhindert, dass Lync vor der Anmeldung den Servernamen und die Serverversion überprüft. Standardmäßig überprüft Lync vor dem Anmelden den Servernamen und die Version.</p></td>
</tr>
<tr class="odd">
<td><p>Verwendung von BITS zum Herunterladen von Adressbuchdienst-Dateien aktivieren<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Diese Richtlinie erlaubt es Lync, die Dateien der Adressbuchdienste über den intelligenten Hintergrundübertragungsdienst (Background Intelligent Transfer Service, BITS) herunterzuladen.</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren des SIP-Sicherheitsmodus<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Aktiviert das sichere Senden und Empfangen von Sofortnachrichten über Lync. Diese Richtlinie hat keine Auswirkung auf Windows .NET- oder Microsoft Exchange Server-Dienste.</p>
<p>Wenn Sie diese Richtlinieneinstellung nicht konfigurieren, kann Lync ein beliebiges Transportprotokoll verwenden. Wenn jedoch nicht TLS verwendet wird und der Server Benutzer authentifiziert, muss Lync die NTLM- oder die Kerberos-Authentifizierung verwenden.</p></td>
</tr>
<tr class="odd">
<td><p>Globale Anfangsverzögerung bei Adressbuch-Download<br />
(GalDownloadInitialDelay)</p></td>
<td><p>Legt den Zeitraum bis zum Download der globalen Adressliste (GAL) fest. Der Standardwert beträgt 60 Minuten, d. h., der Server verzögert den Download der globalen Adressliste um einen zufälligen Zeitraum zwischen 0 und 60 Minuten.</p></td>
</tr>
<tr class="even">
<td><p>Verhindert, dass Benutzer Microsoft Lync ausführen<br />
(PreventRun)</p></td>
<td><p>Verhindert, dass die Benutzer Lync ausführen. Diese Richtlinieneinstellung kann sowohl in der Computerkonfiguration als auch in der Benutzerkonfiguration vorgenommen werden, die Einstellung in der Computerkonfiguration hat jedoch Vorrang.</p></td>
</tr>
<tr class="odd">
<td><p>Speicherung von Benutzerkennwörtern zulassen<br />
(SavePassword)</p></td>
<td><p>Ermöglicht das Speichern von Kennwörtern in Lync.</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren des SIP-Komprimierungsmodus<br />
(SipCompression)</p></td>
<td><p>Gibt an, wann die SIP-Komprimierung aktiviert wird. Die SIP-Komprimierung wird standardmäßig auf Grundlage der Adaptergeschwindigkeit aktiviert. Beachten Sie, dass die Festlegung dieser Richtlinie die Anmeldezeit verlängern kann.</p></td>
</tr>
<tr class="odd">
<td><p>Listen mit vertrauenswürdigen Domänen<br />
(TrustModelData)</p></td>
<td><p>Listet die vertrauenswürdigen Domänen auf, die nicht mit dem Präfix der SIP-Domäne des Kunden übereinstimmen.</p></td>
</tr>
</tbody>
</table>


Auf dem Server konfigurierte Richtlinien haben Vorrang vor Gruppenrichtlinieneinstellungen und Clientoptionen, die vom Benutzer konfiguriert wurden. In der folgenden Tabelle wird zusammengefasst, welche Einstellungen Vorrang haben, falls ein Konflikt auftritt.

### Rangfolge von Gruppenrichtlinien

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
<td><p>Lync Server 2013-In-Band-Bereitstellung</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Dialogfeld &quot;Lync – Optionen&quot; in Lync 2013</p></td>
</tr>
</tbody>
</table>


## So definieren Sie Gruppenrichtlinieneinstellungen mithilfe der administrativen Vorlagendateien für Lync 2013

1.  Erstellen Sie einen Ordner auf Stammebene, der alle sprachneutralen ADMX-Dateien enthalten soll. Erstellen Sie beispielsweise den Stammordner für den zentralen Speicher auf Ihrem Domänencontroller an folgendem Speicherort:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    

    > [!NOTE]
    > Bei diesem Verfahren wird angenommen, dass Sie in Ihrer Domäne mehrere Computer verwalten möchten. Speichern Sie in diesem Fall die Vorlagen in einem zentralen Speicher im Ordner "Sysvol" auf dem primären Domänencontroller. Dies schafft einen replizierten zentralen Speicherort für administrative Domänenvorlagen.



2.  Erstellen Sie einen Unterordner für jede Sprache, die Sie verwenden. Diese Unterordner enthalten die sprachenspezifischen ADML-Ressourcendateien. Erstellen Sie beispielsweise einen Unterordner für Englisch – USA (EN-US) an folgendem Speicherort:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

Ausführliche Informationen zu ADMX-Dateien finden Sie im Artikel "Managing Group Policy ADMX Files Step-by-Step Guide" (Schrittweise Anleitung zur Verwaltung von ADMX-Dateien in Gruppenrichtlinien) unter [http://go.microsoft.com/fwlink/?linkid=75124\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=75124%26clcid=0x407).

