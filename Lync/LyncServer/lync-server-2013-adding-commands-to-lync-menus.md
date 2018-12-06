---
title: Hinzufügen von Befehlen zu Lync-Menüs
TOCTitle: Hinzufügen von Befehlen zu Lync-Menüs
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412788(v=OCS.15)
ms:contentKeyID: 52056429
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hinzufügen von Befehlen zu Lync-Menüs

 

_**Letztes Änderungsdatum des Themas:** 2016-04-11_

Sie können Lync 2013-Menüs benutzerdefinierte Befehle hinzufügen und den SIP-URI (Uniform Resource Identifier) des aktuellen Benutzers und ausgewählter Kontakte an die Anwendung übergeben, die der benutzerdefinierte Befehl startet.

Die benutzerdefinierten Befehle, die Sie hinzufügen, können in einem oder mehreren der folgenden Menüs angezeigt werden:

  - Im Menü "Extras" auf der Menüleiste im Lync-Hauptfenster

  - Im Kontextmenü für Kontakte in der Liste "Kontakte"

  - Im Menü "Weitere Optionen" im Fenster "Unterhaltung"

  - Im Kontextmenü für Personen in der Teilnehmerliste im Fenster "Unterhaltung"

  - Im Menü "Optionen" auf einer Visitenkarte

Sie können benutzerdefinierte Befehle für zwei Typen von Anwendungen definieren, für die eine der folgenden Angaben gilt:

  - Die Befehle gelten nur für den aktuellen Benutzer und werden auf dem lokalen Computer gestartet.

  - Die Befehle betreffen weitere Benutzer, z. B. bei einem Programm für die Onlinezusammenarbeit, und müssen auf den Computern aller Benutzer gestartet werden.

Zum Aufrufen des benutzerdefiniertes Befehls haben Sie folgende Möglichkeiten:

  - Wählen Sie einen oder mehrere Benutzer aus, und rufen Sie anschließend den benutzerdefinierten Befehl auf.

  - Starten Sie eine Unterhaltung mit zwei oder mehreren Teilnehmern, und rufen Sie anschließend den benutzerdefinierten Befehl auf.

## So fügen Sie einen benutzerdefinierten Befehl hinzu

Über die Registrierungseinstellungen in der folgenden Tabelle können Sie den Menüs einen Befehl hinzufügen. Diese Einträge werden an den folgenden Stellen in der Registrierung platziert:

HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\CustomCommands

### Registrierungseinträge für benutzerdefinierte Befehle

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
<td><p>0 = Ausführbar (Standard)</p>
<div>

> [!NOTE]
> "ApplicationInstallPath" erforderlich.


</div>
<p>1 = Protokoll</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Vollständiger Pfad der ausführbaren Datei.</p>
<div>

> [!NOTE]
> Muss angegeben werden, falls "ApplicationType" gleich 0 (ausführbar) ist.


</div></td>
</tr>
<tr class="even">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Vollständiger Pfad zusammen mit beliebigen Parametern, einschließlich der Standardparameter <em>%Benutzer-ID%</em> und <em>%Kontakt-ID%</em>.</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Lokale Sitzung. Die Anwendung wird auf dem lokalen Computer gestartet.</p>
<p>1 = Sitzung mit zwei Teilnehmern (Standard). Lync 2013 startet die Anwendung lokal und sendet dann eine Desktopbenachrichtigung an den anderen Benutzer. Der andere Benutzer klickt auf die Benachrichtigung, um die Anwendung auf seinem Computer zu starten.</p>
<p>2 = Sitzung mit mehreren Teilnehmern. Lync 2013 startet die Anwendung lokal und sendet dann eine Desktopbenachrichtigung an die anderen Benutzer. Der andere Benutzer klickt auf die Benachrichtigung, um die angegebene Anwendung auf seinem Computer zu starten.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Eine Liste der Menüs, in denen dieser Befehl angezeigt wird, getrennt durch Semikolons. Mögliche Werte sind:</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>Wenn &quot;ExtensibleMenu&quot; nicht definiert ist, werden die Standardwerte von &quot;MainWindowRightClick&quot; und &quot;ConversationWindowActions&quot; verwendet.</p></td>
</tr>
</tbody>
</table>


Die folgende Registrierungs-Editor-Datei (.reg) enthält beispielsweise das Ergebnis des Hinzufügens des Menüpunkts "Contoso Sales Contact Manager" zum Menü "Aktionen" im Fenster "Unterhaltung":

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\CustomCommands\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

## So greifen Sie auf einen benutzerdefinierten Befehl zu

Führen Sie für den Zugriff auf einen hinzugefügten benutzerdefinierten Befehl (abhängig von den festgelegten Werten für "ExtensibleMenu") einen der folgenden Schritte aus:

  - **MainWindowActions**   Klicken Sie im Lync-Hauptfenster auf **Tools** und anschließend auf den gewünschten benutzerdefinierten Befehl.

  - MainWindowRightClick   Klicken Sie im Lync-Hauptfenster mit der rechten Maustaste auf einen Kontakt und anschließend auf den gewünschten benutzerdefinierten Befehl.

  - **ConversationWindowActions**   Klicken Sie im Fenster "Unterhaltung" auf das Symbol **Weitere Optionen** und anschließend auf den gewünschten benutzerdefinierten Befehl.

  - **ConversationWindowRightClick**   Klicken Sie im Fenster "Unterhaltung" mit der rechten Maustaste auf einen Kontakt, und klicken Sie anschließend auf den gewünschten benutzerdefinierten Befehl.

  - **ContactCardMenu**   Klicken Sie auf der Visitenkarte einer Person auf das Symbol "Optionen" und anschließend auf den gewünschten benutzerdefinierten Befehl.

