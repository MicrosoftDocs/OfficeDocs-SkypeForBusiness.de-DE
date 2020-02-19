---
title: 'Lync Server 2013: Hinzufügen von Befehlen zu lync-Menüs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8b4f44a1d28df4de8d79aa719f0eb1c350a27b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Hinzufügen von Befehlen zu lync-Menüs in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-04-11_

Sie können benutzerdefinierte Befehle zu lync 2013 Menüs hinzufügen und den SIP-URI (Uniform Resource Identifier) des aktuellen Benutzers und der ausgewählten Kontakte an die Anwendung übergeben, die mit dem benutzerdefinierten Befehl gestartet wird.

Die benutzerdefinierten Befehle, die Sie hinzufügen, können in einem oder mehreren der folgenden Menüs angezeigt werden:

  - Das Menü "Extras" auf der Menüleiste im lync-Hauptfenster

  - Das Kontextmenü für Kontakte in der Kontaktliste

  - Im Menü "Weitere Optionen" im Fenster "Unterhaltung"

  - Das Kontextmenü für Personen, die in der Teilnehmerliste des Unterhaltungsfensters aufgeführt sind

  - Das Menü "Optionen" auf einer Visitenkarte

Sie können benutzerdefinierte Befehle für zwei Anwendungstypen definieren – Anwendungen, die eine der folgenden Aktionen ausführen:

  - Gilt nur für den aktuellen Benutzer und wird auf dem lokalen Computer gestartet.

  - Beziehen Sie zusätzliche Benutzer ein, beispielsweise ein Online-Zusammenarbeitsprogramm, und müssen Sie auf den Computern der einzelnen Benutzer gestartet werden.

Der benutzerdefinierte Befehl kann auf folgende Weise aufgerufen werden:

  - Wählen Sie einen oder mehrere Benutzer aus, und wählen Sie dann den benutzerdefinierten Befehl aus.

  - Starten Sie eine Unterhaltung mit zwei oder mehr Teilnehmern, und wählen Sie dann den benutzerdefinierten Befehl aus.

<div>

## <a name="to-add-a-custom-command"></a>So fügen Sie einen benutzerdefinierten Befehl hinzu

Verwenden Sie die Registrierungseinstellungen in der folgenden Tabelle, um den Menüs einen Befehl hinzuzufügen. Diese Einträge werden an einem der folgenden Speicherorte in der Registrierung gespeichert:

  - Für 32bit OS: HKEY\_local\_Machine\\Software\\Microsoft\\Office\\15,0\\lync\\SessionManager\\apps

  - Für 64bit OS: HKEY\_local\_Machine\\Software\\Wow6432Node\\Microsoft\\Office\\15,0\\lync\\SessionManager\\apps

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
<td><p>Name der Anwendung, wie er im Menü angezeigt wird.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = ausführbar (Standard)</p>
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
> Muss angegeben werden, wenn applicationtype auf 0 (ausführbar) festgelegt ist.


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
<td><p>0 = Lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</p>
<p>1 = Sitzung mit zwei Teilnehmern (Standardeinstellung). Lync 2013 startet die Anwendung lokal und sendet dann eine Desktopbenachrichtigung an den anderen Benutzer. Der andere Benutzer klickt auf die Benachrichtigung, um die Anwendung auf Ihrem Computer zu starten.</p>
<p>2 = mehrteilige Sitzung. Lync 2013 startet die Anwendung lokal und sendet anschließend Desktopbenachrichtigungen an die anderen Benutzer. Der andere Benutzer klickt auf die Benachrichtigung, um die angegebene Anwendung auf Ihrem Computer zu starten.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Eine Liste der Menüs, in denen dieser Befehl durch Semikolons getrennt angezeigt wird. Mögliche Werte sind:</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>Wenn "ExtensibleMenu" nicht definiert ist, werden die Standardwerte von "MainWindowRightClick" und "ConversationWindowActions" verwendet.</p></td>
</tr>
</tbody>
</table>


Beispielsweise wird der folgende Registrierungs-Editor (. REG) zeigt die Ergebnisse des Hinzufügens eines Contoso-Menüelements "Sales Contact Manager" im Menü "Aktionen" im Fenster "Unterhaltung" an:

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

Wenn Sie nach dem Hinzufügen auf einen benutzerdefinierten Befehl zugreifen möchten, führen Sie je nach den von Ihnen definierten ExtensibleMenu-Werten einen der folgenden Schritte aus:

  - **MainWindowActions**   klicken Sie im lync-Hauptfenster auf **Extras**, und klicken Sie dann auf Ihren benutzerdefinierten Befehl.

  - **MainWindowRightClick**   klicken Sie im lync-Hauptfenster mit der rechten Maustaste auf einen Kontakt, und klicken Sie dann auf Ihren benutzerdefinierten Befehl.

  - **ConversationWindowActions**   klicken Sie im Fenster Unterhaltung auf das Symbol **Weitere Optionen** , und klicken Sie dann auf Ihren benutzerdefinierten Befehl.

  - **ConversationWindowRightClick**   klicken Sie im Fenster Unterhaltung mit der rechten Maustaste auf einen Kontaktnamen, und klicken Sie dann auf Ihren benutzerdefinierten Befehl.

</div>

</div>

<span> </span>

</div>

</div>

</div>

