---
title: 'Lync Server 2013: Hinzufügen von Befehlen zu lync-Menüs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dfb79a985791e6994d8409339d12b12e1146ec5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Hinzufügen von Befehlen zu lync-Menüs in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-04-11_

Sie können den lync 2013-Menüs benutzerdefinierte Befehle hinzufügen und den SIP-URI (Uniform Resource Identifier) des aktuellen Benutzers und ausgewählte Kontakte an die Anwendung übergeben, die der benutzerdefinierte Befehl startet.

Die benutzerdefinierten Befehle, die Sie hinzufügen, können in einem oder mehreren der folgenden Menüs angezeigt werden:

  - Menü "Extras" auf der Menüleiste im Hauptfenster von lync

  - Das Kontextmenü für Kontakte in der Kontaktliste

  - Das Menü "Weitere Optionen" im Unterhaltungsfenster

  - Das Kontextmenü für Personen, die in der Teilnehmerliste des Unterhaltungsfensters aufgeführt sind

  - Menü ' Optionen ' auf einer Visitenkarte

Sie können benutzerdefinierte Befehle für zwei Arten von Anwendungen definieren – Anwendungen, die eine der folgenden Aktionen ausführen:

  - Gelten nur für den aktuellen Benutzer und werden auf dem lokalen Computer gestartet.

  - Beziehen Sie zusätzliche Benutzer ein, beispielsweise ein Online Zusammenarbeitsprogramm, und müssen Sie auf dem Computer jedes Benutzers gestartet werden.

Der benutzerdefinierte Befehl kann wie folgt aufgerufen werden:

  - Wählen Sie einen oder mehrere Benutzer aus, und wählen Sie dann den benutzerdefinierten Befehl aus.

  - Starten Sie eine Unterhaltung mit zwei oder mehr Teilnehmern, und wählen Sie dann den benutzerdefinierten Befehl aus.

<div>

## <a name="to-add-a-custom-command"></a>So fügen Sie einen benutzerdefinierten Befehl hinzu

Verwenden Sie die Registrierungseinstellungen in der folgenden Tabelle, um den Menüs einen Befehl hinzuzufügen. Diese Einträge werden in der Registrierung an einem der folgenden Speicherorte gespeichert:

  - Für 32-Bit-\_Betriebs\_System\\:\\HKEY\\-\\Software\\für\\lokale Computer\\Microsoft Office 15,0 lync SessionManager-apps

  - Für 64-Bit-\_Betriebs\_System\\:\\HKEY\\local\\Machine\\Software\\Wow6432Node\\Microsoft Office\\15,0 lync SessionManager-apps

### <a name="custom-command-registry-entries"></a>Registrierungseinträge für benutzerdefinierte Befehle

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
<td><p>0 = ausführbare Datei (Standard)</p>
<div>

> [!NOTE]  
> Erfordert ApplicationInstallPath.


</div>
<p>1 = Protokoll</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Vollständiger Pfad der ausführbaren Datei.</p>
<div>

> [!NOTE]  
> Muss angegeben werden, wenn applicationtype 0 (ausführbare Datei) ist.


</div></td>
</tr>
<tr class="even">
<td><p>Pfad</p></td>
<td><p>REG_SZ</p></td>
<td><p>Vollständiger Pfad, der zusammen mit allen Parametern gestartet werden soll, einschließlich der Standardparameter <em>% User-ID%</em> und <em>% Contact-ID%</em>.</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</p>
<p>1 = Sitzung mit zwei Teilnehmern (Standard). Lync 2013 startet die Anwendung lokal und sendet dann eine Desktopbenachrichtigung an den anderen Benutzer. Der andere Benutzer klickt auf die Benachrichtigung, um die Anwendung auf Ihrem Computer zu starten.</p>
<p>2 = mehrteilige Sitzung. Lync 2013 startet die Anwendung lokal und sendet dann Desktopbenachrichtigungen an die anderen Benutzer. Der andere Benutzer klickt auf die Benachrichtigung, um die angegebene Anwendung auf dem Computer zu starten.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Eine Liste der Menüs, in denen dieser Befehl angezeigt wird, getrennt durch Semikolons. Mögliche Werte:</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>Wenn ExtensibleMenu nicht definiert ist, werden die Standardwerte MainWindowRightClick und ConversationWindowActions verwendet.</p></td>
</tr>
</tbody>
</table>


Der folgende Registrierungs-Editor (. REG) zeigt die Ergebnisse des Hinzufügens eines Contoso Sales Contact Manager-Menüelements zum Menü "Aktionen" im Unterhaltungsfenster an:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a>So greifen Sie auf einen benutzerdefinierten Befehl zu

Wenn Sie nach dem Hinzufügen auf einen benutzerdefinierten Befehl zugreifen möchten, führen Sie je nach den von Ihnen definierten ExtensibleMenu-Werten eine der folgenden Aktionen aus:

  - **MainWindowActions**   klicken Sie im Hauptfenster von lync auf **Extras**, und klicken Sie dann auf Ihren benutzerdefinierten Befehl.

  - **MainWindowRightClick**   klicken Sie im Hauptfenster von lync mit der rechten Maustaste auf einen Kontakt, und klicken Sie dann auf Ihren benutzerdefinierten Befehl.

  - **ConversationWindowActions**   klicken Sie im Unterhaltungsfenster auf das Symbol **Weitere Optionen** , und klicken Sie dann auf Ihren benutzerdefinierten Befehl.

  - **ConversationWindowRightClick**   klicken Sie im Unterhaltungsfenster mit der rechten Maustaste auf einen Kontaktnamen, und klicken Sie dann auf Ihren benutzerdefinierten Befehl.

</div>

</div>

<span> </span>

</div>

</div>

</div>

