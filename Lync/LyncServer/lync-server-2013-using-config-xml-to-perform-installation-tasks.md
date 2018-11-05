---
title: Verwenden von Config.xml zum Durchführen von Installationsaufgben
TOCTitle: Verwenden von Config.xml zum Durchführen von Installationsaufgben
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204651(v=OCS.15)
ms:contentKeyID: 49293088
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden von Config.xml zum Durchführen von Installationsaufgben

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Das Office-Anpassungstool (OAT) ist zwar das primäre Tool für die angepasste Installation, Administratoren können jedoch mit der Datei "Config.xml" zusätzliche, im OAT nicht verfügbare Installationsanweisungen angeben. Die folgenden Anpassungen können nur mithilfe der Datei **Config.xml** vorgenommen werden:

  - Angeben des Netzwerkinstallationspfads

  - Auswählen der zu installierenden Produkte

  - Konfigurieren der Protokollierung und des Speicherorts der Setupanpassungsdatei und Softwareupdates

  - Angeben von Installationsoptionen, z. B. Benutzername

  - Kopieren der lokalen Installationsquelle (Local Installation Source, LIS) auf den Benutzercomputer ohne Installation von Office

  - Hinzufügen oder Entfernen von Sprachen in der Installation

Es wird empfohlen, zum Konfigurieren der automatischen Installation von Lync 2013 die Datei "Config.xml" zu verwenden.

Standardmäßig wird Setup durch die im Hauptproduktordner (z. B. \\*Produkt*.WW) gespeicherte Datei "Config.xml" angewiesen, das betreffende Produkt zu installieren. Beispielsweise wird durch die Datei "Config.xml" im folgenden Ordner Lync 2013 installiert:

  - \\\\server\\share\\Lync15\\Lync.WW \\Config.xml

Die für die Installation von Lync 2013 am häufigsten verwendeten Config.xml-Elemente sind in der folgenden Tabelle aufgeführt:

### Config.xml-Elemente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Element</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Konfiguration</p></td>
<td><p>Element der obersten Ebene (erforderlich). Enthält das Produktattribut, z. B.: Product=Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>Gibt an, wie bestimmte Produktfeatures während der Installation behandelt werden. Verhindern Sie mit den folgenden Attributen die Installation von Business Connectivity Services. Diese Dienste enthalten freigegebene Komponenten, die Konflikte mit Outlook 2010 verursachen:</p>
<ul>
<li><p>Id=&quot;LOBiMain&quot;</p></li>
<li><p>State=&quot;Absent&quot;</p></li>
<li><p>Children=&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Anzeige</p>
<p></p></td>
<td><p>Die Ebene der Benutzeroberfläche, die dem Benutzer angezeigt wird. Zu den typischen Attributen zählen Folgende:</p>
<ul>
<li><p>CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(Standard)</p></li>
<li><p>AcceptEula=&quot;Yes&quot; | &quot;No&quot;(Standard)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Protokollierung</p></td>
<td><p>Optionen für den vom Setup ausgeführten Protokollierungstyp. Zu den typischen Attributen zählen Folgende:</p>
<ul>
<li><p>Type =&quot;Off&quot; | &quot;Standard&quot;(Standard) | &quot;Verbose&quot;</p></li>
<li><p>Template=”<em>Dateiname</em>.txt” (Name der Protokolldatei)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Einstellung</p></td>
<td><p>Gibt Werte für Windows Installer-Eigenschaften an. Zu den typischen Attributen zählen Folgende:</p>
<ul>
<li><p>Setting Id=&quot;<em>Name</em>&quot; (Name der Windows Installer-Eigenschaft)</p></li>
<li><p>Value=&quot;<em>Wert</em>&quot; (der der Eigenschaft zuzuweisende Wert)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>Der vollqualifizierte Pfad des Netzwerkinstallationspfads, von dem die Installation ausgeführt werden soll. Enthält das Standortattribut:</p>
<ul>
<li><p>Location=”<em>Pfad</em>”</p></li>
</ul></td>
</tr>
</tbody>
</table>


Das folgende Beispiel zeigt eine Datei "Config.xml" für eine typische automatische Installation von Lync 2013:

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Ausführliche Informationen zur Verwendung der Datei "Config.xml" zum Ausführen der Office-Installation und von Wartungsaufgaben stehen unter [http://go.microsoft.com/fwlink/?linkid=267514\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=267514%26clcid=0x407) zur Verfügung.

## So passen Sie die Datei "Config.xml" an

1.  Öffnen Sie die Datei "Config.xml" in einem Text-Editor wie Editor.

2.  Suchen Sie die Zeilen, die die zu ändernden Elemente enthalten.

3.  Ändern Sie den Elementeintrag mit den gewünschten Optionen für eine automatische Installation. Entfernen Sie unbedingt die Kommentartrennzeichen "\<\!--" und "--\>". Verwenden Sie z. B. die folgende Syntax:
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Speichern Sie die Datei **Config.xml**.

