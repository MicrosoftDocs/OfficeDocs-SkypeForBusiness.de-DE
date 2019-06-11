---
title: Integrieren einer Drittanbieter-Zusammenarbeitsanwendung in lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b56fabbc1bd341e3ba2c5fe535d147c09335b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>Integrieren einer Drittanbieter-Zusammenarbeitsanwendung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Sie können lync 2013 in eine beliebige Anwendung für die Online Zusammenarbeit von Drittanbietern integrieren, indem Sie der Registrierung Informationen zur Anwendung hinzufügen. Sie können lync 2013 verwenden, um Datenkonferenz Sitzungen zu starten, die auf einem internen Server, einem Internet basierten Dienst oder in beiden gehostet werden. Die Zusammenarbeits-oder Datenkonferenz Sitzung kann über die Kontaktliste oder über eine vorhandene Chat-, sprach-oder Videositzung gestartet werden. Lync 2013 fungiert nur als Vehikel für das Starten der Anwendung. Alle vorhandenen lync 2013-Unterhaltungen bleiben nach Beginn der Online Zusammenarbeitssitzung aktiv.

In den folgenden Abschnitten wird beschrieben, wie Sie lync 2013 mit Internet basierten und Server basierten Zusammenarbeitsanwendungen integrieren.

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>Integrieren einer Internet basierten Zusammenarbeitsanwendung in lync 2013

Im Allgemeinen sind die Schritte, die für die Integration einer Drittanbieter-Zusammenarbeitsanwendung erforderlich sind, wie folgt:

1.  Der Registrierung werden Informationen zur Anwendung hinzugefügt.

2.  Der Organisator meldet sich bei lync 2013 an und wählt Kontakte für die Datenfreigabe und Zusammenarbeit aus. Oder der Organisator befindet sich möglicherweise bereits in einer Unterhaltung und entscheidet sich, Datenkonferenzen hinzuzufügen.

3.  Lync 2013 liest die Registrierung, startet die Zusammenarbeitsanwendung und sendet dann eine benutzerdefinierte SIP-Nachricht – eine appINVITE – an die ausgewählten Teilnehmer.

4.  Die Teilnehmer akzeptieren die Einladung, und die Zusammenarbeitsanwendung wird auf dem Computer jeder Person gestartet. Lync 2013 verwendet die Registrierung, um zu ermitteln, welche Zusammenarbeitsanwendung verwendet werden soll, und startet dann die Anwendung mithilfe der Parameter, die in der appINVITE-Nachricht enthalten sind.

In der folgenden Tabelle werden die Registrierungseinträge beschrieben, die für die Integration einer Internet basierten Zusammenarbeitsanwendung in lync 2013 erforderlich sind. Diese Einträge werden in der Registrierung an folgendem Speicherort gespeichert:

  - HKEY\_-\_Software\\\\für lokale\\Computer\\Microsoft\\Office\\15,0 lync\\SessionManager-apps\\-Parameter

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Registrierungseinträge für eine Internet basierte Zusammenarbeitsanwendung

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
<td><p>Der Anwendungsname für lync 2013-Menüs.</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>Pfad zu 16 Pixel x 16-Pixel-Symbol, BMP oder PNG.</p></td>
</tr>
<tr class="odd">
<td><p>Pfad</p></td>
<td><p>REG_SZ</p></td>
<td><p>Teilnehmerpfad zum Starten der Anwendung für die Online Zusammenarbeit.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Organizer-Pfad zum Starten der Anwendung für die Online Zusammenarbeit. Dieser Pfad kann einen oder mehrere benutzerdefinierte Parameter enthalten, die im Unterschlüssel Parameters definiert sind. Zum Beispiel<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</p>
<p>1 = Sitzung mit zwei Teilnehmern (Standard). Lync 2013 startet die Anwendung lokal und sendet dann eine Systembenachrichtigung an den anderen Benutzer. Der andere Benutzer klickt auf die Benachrichtigung und startet die angegebene Anwendung auf Ihrem Computer.</p>
<p>2 = mehrteilige Sitzung. Lync 2013 startet die Anwendung lokal und sendet dann System Benachrichtigungen an die anderen Benutzer und fordert Sie auf, die angegebene Anwendung auf Ihrem eigenen Computer zu starten.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Eine Liste der Menüs, in denen dieser Befehl angezeigt wird, getrennt durch Semikolons. Mögliche Werte:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Wenn ExtensibleMenu nicht definiert ist, werden die Standardwerte MainWindowRightClick und ConversationWindowActions verwendet.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Registrierungseinträge für Parameter beschrieben. Diese Einträge finden Sie unter HKEY\_aktuelle\_Benutzer\\Software\\Microsoft\\Office\\15,0\\lync\\SessionManager\\-\\apps-Parameter.

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Registrierungseinträge für eine Internet basierte Zusammenarbeitsanwendung

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
<td><p>Parameter1</p></td>
<td><p>REG_SZ</p></td>
<td><p>Wird in tokenformat (<code>%Parm1%</code>) verwendet, um dem Registrierungsschlüssel OriginatorPath benutzerspezifische Werte hinzuzufügen.</p></td>
</tr>
<tr class="even">
<td><p>Parameter2</p></td>
<td><p>REG_SZ</p></td>
<td><p>Siehe parameter1.</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>Siehe parameter1.</p></td>
</tr>
</tbody>
</table>


Die folgenden Beispiel Registrierungseinstellungen integrieren den Adatum-Zusammenarbeits Client in lync 2013:

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>Integrieren einer Server basierten Zusammenarbeitsanwendung in lync 2013

Die Einstellungen zum Hinzufügen von Befehlen zum Starten einer Server basierten Zusammenarbeitsanwendung in lync 2013 ähneln denen im vorherigen Abschnitt, in dem eine Internet basierte Zusammenarbeitsanwendung mit lync 2013 integriert wurde. Die OriginatorPath ist jedoch nicht erforderlich, und einige Werte werden geändert. Registrierungseinträge werden an folgendem Speicherort gespeichert:

  - HKEY\_-\_Software\\\\für lokale\\Computer\\Microsoft\\Office\\15,0 lync\\SessionManager-apps\\-Parameter

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>Registrierungseinträge für eine Server basierte Zusammenarbeitsanwendung

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
<td><p>Der Name der Anwendung, wie er im Menü angezeigt wird.</p></td>
</tr>
<tr class="even">
<td><p>Applicationtype</p></td>
<td><p>DWORD</p></td>
<td><p>Wert = 1. Legt den Anwendungstyp auf Protocol fest. In diesem Fall gelten die anderen möglichen Werte nicht. Wenn es nicht vorhanden ist, wird applicationtype auf 0 (ausführbare Datei) gesetzt.</p></td>
</tr>
<tr class="odd">
<td><p>Pfad</p></td>
<td><p>REG_SZ</p></td>
<td><p>Das Protokoll, das zum Starten der Zusammenarbeitsanwendung verwendet wird. Für Live Meeting 2007 ist der Wert von Path auf <code>meet:%conf-uri%</code>gesetzt.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</p>
<p>1 = Sitzung mit zwei Teilnehmern (Standard). Lync 2013 startet die Anwendung lokal und sendet dann eine Systembenachrichtigung an den anderen Benutzer. Der andere Benutzer klickt auf die Benachrichtigung und startet die angegebene Anwendung auf Ihrem Computer.</p>
<p>2 = mehrteilige Sitzung. Lync 2013 startet die Anwendung lokal und sendet dann System Benachrichtigungen an die anderen Benutzer und fordert Sie auf, die angegebene Anwendung auf Ihrem Computer zu starten.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>Data = der Servertyp.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Eine Liste der Menüs, in denen dieser Befehl angezeigt wird, getrennt durch Semikolons. Mögliche Werte:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Wenn ExtensibleMenu nicht definiert ist, werden die Standardwerte MainWindowRightClick und ConversationWindowActions verwendet.</p></td>
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

