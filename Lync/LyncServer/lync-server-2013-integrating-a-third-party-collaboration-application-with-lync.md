---
title: Integrieren einer Drittanbieter-Zusammenarbeitsanwendung in lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 075c8289a55683b18b0a006319b426c94796f9cd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>Integrieren einer Anwendung für die Zusammenarbeit eines Drittanbieters mit lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-20_

Sie können lync 2013 in eine beliebige Anwendung für die Online Zusammenarbeit von Drittanbietern integrieren, indem Sie der Registrierung Informationen zur Anwendung hinzufügen. Sie können lync 2013 verwenden, um Datenkonferenz Sitzungen zu starten, die auf einem internen Server, einem Internet basierten Dienst oder beides gehostet werden. Die Zusammenarbeits-oder Datenkonferenz Sitzung kann aus der Kontaktliste oder aus einer vorhandenen Chat-, sprach-oder Videositzung gestartet werden. Lync 2013 fungiert nur als das Vehikel für das Starten der Anwendung. Alle vorhandenen lync 2013 Unterhaltungen bleiben aktiv, nachdem die Online Zusammenarbeitssitzung begonnen hat.

In den folgenden Abschnitten wird beschrieben, wie Sie lync 2013 in Internet basierte und serverbasierte Zusammenarbeitsanwendungen integrieren.

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>Integrieren einer Anwendung für Internet basierte Zusammenarbeit mit lync 2013

Im Allgemeinen müssen die folgenden Schritte ausgeführt werden, um eine Drittanbieteranwendung für die Zusammenarbeit zu integrieren:

1.  Der Registrierung werden Informationen zur Anwendung hinzugefügt.

2.  Der Organisator meldet sich bei lync 2013 an und wählt Kontakte für die Datenfreigabe und Zusammenarbeit aus. Oder der Organisator befindet sich bereits in einer Unterhaltung und beschließt, eine Datenkonferenz zu starten.

3.  Lync 2013 die Registrierung liest, startet die Zusammenarbeitsanwendung und sendet dann eine benutzerdefinierte SIP-Nachricht – ein appINVITE – an die ausgewählten Teilnehmer.

4.  Die Teilnehmer nehmen die Einladung an, und die Zusammenarbeitsanwendung wird auf dem Computer der einzelnen Personen gestartet. Lync 2013 verwendet die Registrierung, um zu bestimmen, welche Zusammenarbeitsanwendung verwendet werden soll, und startet diese Anwendung dann mithilfe der Parameter, die in der appINVITE-Nachricht enthalten sind.

In der folgenden Tabelle werden die Registrierungseinträge beschrieben, die für die Integration einer Internet basierten Zusammenarbeitsanwendung mit lync 2013 erforderlich sind. Diese Einträge werden an folgendem Speicherort in der Registrierung gespeichert:

  - HKEY\_local\_Machine\\Software\\Microsoft\\Office\\15,0\\lync\\SessionManager\\-\\apps-Parameter

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Registrierungseinträge für eine internetbasierte Anwendung für die Zusammenarbeit

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
<td><p>Der Name der Anwendung für lync 2013 Menüs.</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>Pfad zu Symbol mit 16 Pixel x 16 Pixel, BMP oder PNG.</p></td>
</tr>
<tr class="odd">
<td><p>Pfad</p></td>
<td><p>REG_SZ</p></td>
<td><p>Teilnehmerpfad zum Starten der Anwendung für die Onlinezusammenarbeit.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Organisatorpfad zum Starten der Anwendung für die Onlinezusammenarbeit. Dieser Pfad kann einen oder mehrere benutzerdefinierte Parameter enthalten, die im Unterschlüssel "Parameters" definiert sind. Beispiel: <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</p>
<p>1 = Sitzung mit zwei Teilnehmern (Standardeinstellung). Lync 2013 startet die Anwendung lokal und sendet dann eine Systembenachrichtigung an den anderen Benutzer. Der andere Benutzer klickt auf die Benachrichtigung und startet die angegebene Anwendung auf seinem Computer.</p>
<p>2 = mehrteilige Sitzung. Lync 2013 startet die Anwendung lokal und sendet dann System Benachrichtigungen an die anderen Benutzer, woraufhin Sie aufgefordert werden, die angegebene Anwendung auf Ihrem eigenen Computer zu starten.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Eine Liste der Menüs, in denen dieser Befehl angezeigt wird, getrennt durch Semikolons. Mögliche Werte sind:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Wenn "ExtensibleMenu" nicht definiert ist, werden die Standardwerte von "MainWindowRightClick" und "ConversationWindowActions" verwendet.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Registrierungseinträge für Parameter beschrieben. Diese Einträge finden Sie unter HKEY\_aktuelle\_Benutzer\\Software\\Microsoft\\Office\\15,0\\lync\\SessionManager\\-\\apps-Parameter.

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Registrierungseinträge für eine internetbasierte Anwendung für die Zusammenarbeit

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
<td><p>Wird im Tokenformat (<code>%Parm1%</code>) verwendet, um dem Registrierungsschlüssel OriginatorPath benutzerspezifische Werte hinzuzufügen.</p></td>
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


Im folgenden Beispiel werden die Registrierungseinstellungen Adatum-Zusammenarbeits Client mit lync 2013 integriert:

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

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>Integrieren einer Server basierten Zusammenarbeitsanwendung mit lync 2013

Die Einstellungen zum Hinzufügen von Befehlen zum Starten einer Server basierten Zusammenarbeitsanwendung in lync 2013 ähneln denen im vorherigen Abschnitt und integrieren eine Internet basierte Zusammenarbeitsanwendung mit lync 2013. "OriginatorPath" ist jedoch nicht erforderlich, und einige Werte sind geändert. Registrierungseinträge werden an folgendem Speicherort eingefügt:

  - HKEY\_local\_Machine\\Software\\Microsoft\\Office\\15,0\\lync\\SessionManager\\-\\apps-Parameter

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>Registrierungseinträge für eine serverbasierte Anwendung für die Zusammenarbeit

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
<td><p>Wert = 1. Legt den Anwendungstyp auf "protocol" fest. Die weiteren möglichen Werte gelten in diesem Fall nicht. Wenn der Wert nicht vorhanden ist, wird applicationtype auf 0 (ausführbar) festgelegt.</p></td>
</tr>
<tr class="odd">
<td><p>Pfad</p></td>
<td><p>REG_SZ</p></td>
<td><p>Zum Starten der Anwendung für die Zusammenarbeit verwendetes Protokoll. Für Live Meeting 2007 ist der Wert von Path auf <code>meet:%conf-uri%</code>festgelegt.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</p>
<p>1 = Sitzung mit zwei Teilnehmern (Standardeinstellung). Lync 2013 startet die Anwendung lokal und sendet dann eine Systembenachrichtigung an den anderen Benutzer. Der andere Benutzer klickt auf die Benachrichtigung und startet die angegebene Anwendung auf seinem Computer.</p>
<p>2 = mehrteilige Sitzung. Lync 2013 startet die Anwendung lokal und sendet dann System Benachrichtigungen an die anderen Benutzer, woraufhin Sie aufgefordert werden, die angegebene Anwendung auf Ihrem Computer zu starten.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = Typ des Servers.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Eine Liste der Menüs, in denen dieser Befehl durch Semikolons getrennt angezeigt wird. Mögliche Werte sind:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Wenn "ExtensibleMenu" nicht definiert ist, werden die Standardwerte von "MainWindowRightClick" und "ConversationWindowActions" verwendet.</p></td>
</tr>
</tbody>
</table>


Im folgenden Beispiel werden Befehle zum Starten des Adatum-Zusammenarbeits Clients in lync 2013 hinzugefügt:

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

</div>

</div>

<span> </span>

</div>

</div>

</div>

