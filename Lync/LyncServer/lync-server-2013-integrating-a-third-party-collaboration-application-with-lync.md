---
title: Integrieren einer Drittanbieteranwendung für die Zusammenarbeit in Lync
TOCTitle: Integrieren einer Drittanbieteranwendung für die Zusammenarbeit in Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398068(v=OCS.15)
ms:contentKeyID: 52056273
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Integrieren einer Drittanbieteranwendung für die Zusammenarbeit in Lync

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In Lync 2013 lassen sich beliebige Drittanbieterprogramme für die Onlinezusammenarbeit integrieren, indem in der Registrierung Informationen zum jeweiligen Programm hinzugefügt werden. Sie können mit Lync 2013 Datenkonferenzsitzungen starten, die auf einem internen Server oder von einem internetbasierten Dienst oder beiden Diensttypen gehostet werden. Die Zusammenarbeitssitzung bzw. Datenkonferenz kann über die Kontaktliste oder von einer bestehenden Chat-, Gesprächs- oder Videositzung aus gestartet werden. Lync 2013 fungiert lediglich als Komponente zum Starten der Anwendung. Aktuelle Lync 2013-Unterhaltungen bleiben auch nach dem Start der Onlinezusammenarbeitssitzung aktiv.

In den folgenden Abschnitten wird erläutert, wie internetbasierte und serverbasierte Zusammenarbeitsprogramme in Lync 2013 integriert werden.

## Integrieren einer internetbasierten Anwendung für die Zusammenarbeit in Lync 2013

Im Allgemeinen müssen die folgenden Schritte ausgeführt werden, um eine Drittanbieteranwendung für die Zusammenarbeit zu integrieren:

1.  Der Registrierung werden Informationen zur Anwendung hinzugefügt.

2.  Der Organisator meldet sich an Lync 2013 an und wählt Kontakte für die Datenfreigabe und Zusammenarbeit aus. Oder der Organisator befindet sich bereits in einer Unterhaltung und beschließt, eine Datenkonferenz zu starten.

3.  Lync 2013 liest die Registrierung, startet die Anwendung für die Zusammenarbeit und sendet eine benutzerdefinierte SIP-Nachricht (appINVITE) an die ausgewählten Teilnehmer.

4.  Die Teilnehmer akzeptieren die Einladung, und die Anwendung für die Zusammenarbeit wird auf den Computern aller Teilnehmer gestartet. Lync 2013 verwendet die Informationen in der Registrierung, um die zu verwendende Anwendung für die Zusammenarbeit zu ermitteln. Anschließend wird diese Anwendung unter Verwendung der in der appINVITE-Nachricht enthaltenen Parameter gestartet.

Die folgende Tabelle beschreibt die Registrierungseinträge, die zur Integration einer internetbasierten Anwendung für die Zusammenarbeit in Lync 2013 erforderlich sind. Diese Einträge werden an folgendem Speicherort in der Registrierung platziert:

  - HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters

### Registrierungseinträge für eine internetbasierte Anwendung für die Zusammenarbeit

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Typ</th>
<th>Daten</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>REG_SZ</p></td>
<td><p>Der Anwendungsname für Lync 2013-Menüs.</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>Pfad zu Symbol mit 16 Pixel x 16 Pixel, BMP oder PNG.</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Teilnehmerpfad zum Starten der Anwendung für die Onlinezusammenarbeit.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Organisatorpfad zum Starten der Anwendung für die Onlinezusammenarbeit. Dieser Pfad kann einen oder mehrere benutzerdefinierte Parameter enthalten, die im Unterschlüssel &quot;Parameters&quot; definiert sind. Beispiel: <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</p>
<p>1 = Sitzung mit zwei Teilnehmern (Standardeinstellung). Lync 2013 startet die Anwendung lokal und sendet anschließend eine Systembenachrichtigung an den zweiten Benutzer. Der andere Benutzer klickt auf die Benachrichtigung und startet die angegebene Anwendung auf seinem Computer.</p>
<p>2 = Sitzung mit mehreren Teilnehmern. Lync 2013 startet die Anwendung lokal und sendet dann Systembenachrichtigungen an die weiteren Teilnehmer. Darin werden die Benutzer aufgefordert, die angegebene Anwendung auf ihrem eigenen Computer zu starten.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Eine Liste der Menüs, in denen dieser Befehl angezeigt wird, getrennt durch Semikolons. Mögliche Werte sind:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Wenn &quot;ExtensibleMenu&quot; nicht definiert ist, werden die Standardwerte von &quot;MainWindowRightClick&quot; und &quot;ConversationWindowActions&quot; verwendet.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Registrierungseinträge für Parameter beschrieben. Diese Einträge werden unter "HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters" platziert.

### Registrierungseinträge für eine internetbasierte Anwendung für die Zusammenarbeit

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Typ</th>
<th>Daten</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p>Wird im Tokenformat (<code>%Parm1%</code>) verwendet, um benutzerspezifische Werte zum Registrierungsschlüssel &quot;OriginatorPath&quot; hinzuzufügen.</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
<td><p>REG_SZ</p></td>
<td><p>Siehe Param1.</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>Siehe Param1.</p></td>
</tr>
</tbody>
</table>


Im folgenden Beispiel für Registrierungseinstellungen wird der ADatum-Client für die Zusammenarbeit in Lync 2013 integriert:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

## Integrieren einer serverbasierten Anwendung für die Zusammenarbeit in Lync 2013

Die Einstellungen für das Hinzufügen von Befehlen zum Starten einer serverbasierten Anwendung für die Zusammenarbeit von Lync 2013 aus ähneln den im Abschnitt "Integrieren einer internetbasierten Anwendung für die Zusammenarbeit in Lync 2013" beschriebenen Einstellungen. "OriginatorPath" ist jedoch nicht erforderlich, und einige Werte sind geändert. Die Registrierungseinträge werden an folgendem Speicherorten platziert:

  - HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters

### Registrierungseinträge für eine serverbasierte Anwendung für die Zusammenarbeit

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Typ</th>
<th>Daten</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>REG_SZ</p></td>
<td><p>Name der Anwendung, wie er im Menü angezeigt wird.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>Wert = 1. Legt den Anwendungstyp auf &quot;protocol&quot; fest. Die weiteren möglichen Werte gelten in diesem Fall nicht. Wenn nicht vorhanden, ist &quot;ApplicationType&quot; standardmäßig auf 0 (ausführbar) festgelegt.</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Zum Starten der Anwendung für die Zusammenarbeit verwendetes Protokoll. Für Live Meeting 2007 wird der Wert für &quot;Path&quot; auf <code>meet:%conf-uri%</code> festgelegt.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</p>
<p>1 = Sitzung mit zwei Teilnehmern (Standardeinstellung). Lync 2013 startet die Anwendung lokal und sendet anschließend eine Systembenachrichtigung an den zweiten Benutzer. Der andere Benutzer klickt auf die Benachrichtigung und startet die angegebene Anwendung auf seinem Computer.</p>
<p>2 = Sitzung mit mehreren Teilnehmern. Lync 2013 startet die Anwendung lokal und sendet dann Systembenachrichtigungen an die weiteren Teilnehmer. Darin werden die Benutzer aufgefordert, die angegebene Anwendung auf ihrem eigenen Computer zu starten.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = Typ des Servers.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Eine Liste der Menüs, in denen dieser Befehl angezeigt wird, getrennt durch Semikolons. Mögliche Werte sind:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Wenn &quot;ExtensibleMenu&quot; nicht definiert ist, werden die Standardwerte von &quot;MainWindowRightClick&quot; und &quot;ConversationWindowActions&quot; verwendet.</p></td>
</tr>
</tbody>
</table>


Im folgenden Beispiel werden Befehle zum Starten des ADatum-Clients für die Zusammenarbeit aus Lync 2013 hinzugefügt:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

