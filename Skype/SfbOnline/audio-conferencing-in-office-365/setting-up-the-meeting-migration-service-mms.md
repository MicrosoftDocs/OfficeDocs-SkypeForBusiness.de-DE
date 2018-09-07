---
title: Einrichten des Meeting Migration Service (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) ist ein Skype for Business-Dienst, der im Hintergrund ausgeführt wird und Skype for Business- und Microsoft Teams-Besprechungen automatisch für die Benutzer aktualisiert. Mit MMS brauchen die Benutzer nicht mehr Meeting Migration Tool auszuführen, um ihre Skype for Business- und Microsoft Teams-Besprechungen zu aktualisieren.
ms.openlocfilehash: 562cc616af59ee2fb87b5a2a023c9efe6c3093c3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854315"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Einrichten des Meeting Migration Service (MMS)

Meeting Migration Service (MMS) ist ein Skype for Business-Dienst, der im Hintergrund ausgeführt wird und Skype for Business- und Microsoft Teams-Besprechungen automatisch für die Benutzer aktualisiert. Mit MMS brauchen die Benutzer nicht mehr Meeting Migration Tool auszuführen, um ihre Skype for Business- und Microsoft Teams-Besprechungen zu aktualisieren.  Mit diesem Tool können Skype for Business-Besprechungen nicht zu Microsoft Teams-Besprechungen migriert werden.  
  
 **Anforderungen**
  
Für MMS müssen sich die Postfächer der Besprechungsorganisatoren in Exchange Online befinden.
  
 **Primäre Szenarien**
  
MMS aktualisiert Skype-Besprechungen für einen Benutzer in den folgenden beiden primären Szenarien:
  
- Der Benutzer wird von einer lokalen Skype for Business Server-Instanz zu Skype for Business Online migriert.
    
- Ein Administrator nimmt eine Änderung an den Audiokonferenzeinstellungen des Benutzers vor, die eine Aktualisierung der Audiokonferenzinformationen dieses Benutzers erfordern würde.
    
 **Häufige Szenarien, in denen MMS nicht verwendet werden kann**
  
Im Folgenden werden einige häufige Szenarien vorgestellt, die auf Sie zutreffen könnten. Bei allen handelt es sich um unterstützte Szenarien für die Migration. MMS kann in diesen Szenarien allerdings nicht ausgeführt werden, und Sie müssen stattdessen das [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) verwenden.
  
- Die Benutzerpostfächer befinden sich auf einem lokalen Exchange Server
    
- Verwenden eines Drittanbieters für Audiokonferenzen
    
- Migrieren von Benutzern von Skype for Business Online zu einem lokalen Skype-Server
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>Aktualisieren von Besprechungen, wenn ein lokaler Benutzer zu Skype for Business Online migriert wird

Dies ist das häufigste Szenario, in dem MMS dazu beitragen kann, dass die Umstellung für Ihre Benutzer reibungslos verläuft. Wenn ein Benutzer von einer lokalen Skype for Business Server-Instanz zu Skype for Business Online migriert wird, erkennt MMS den neuen Benutzer und scannt den Kalender des Benutzers nach Skype for Business- und Microsoft Teams-Besprechungen. Alle zukünftigen Besprechungen werden mit den neuen Informationen für diesen Benutzer aktualisiert.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>Wenn Sie zurzeit Skype Server 2015 für Audiokonferenzen verwenden

Es wird empfohlen, den bewährten Methoden unten zu folgen, um in diesem Szenario größtmögliche Benutzerfreundlichkeit bei Verwendung von MMS zu erreichen:
  
- Da es für MMS erforderlich ist, dass sich das Postfach des Benutzers auf Exchange Online befindet, sollten Sie, wenn Sie auch von einem lokalen Exchange Server migrieren, das Postfach des Benutzers zuerst zu Exchange Online verschieben.
    
- Weisen Sie dem Benutzer die Lizenz für **Audiokonferenzen** zu, bevor Sie das `Move-CSUser`-Cmdlet zum Migrieren des Benutzers ausführen. Der Grund ist, dass MMS Besprechungen auch aktualisiert, wenn Audiokonferenzeinstellungen für einen Benutzer geändert werden. Wenn Sie die Lizenz nicht zuerst zuweisen, aktualisiert MMS alle Besprechungen erneut, nachdem Sie die Lizenz zugewiesen haben.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Wenn Sie derzeit einen externen Audiokonferenzanbieter (ACP) verwenden

Im Fall eines Drittanbieter-ACP hängt es von den Audiokonferenzeinstellungen Ihrer Organisation ab, ob MMS ausgeführt wird oder nicht. Sie können wählen, die Einwahlnummern von Ihrem ACP automatisch zu ersetzen, wenn Sie einem Benutzer eine Lizenz für **Audiokonferenzen** zuweisen. Andererseits müssen Sie dies möglicherweise verhindern und die Einwahlnummern Ihres ACP beibehalten. Um die Einstellung Ihrer Organisation anzuzeigen, führen Sie den folgenden Windows PowerShell-Befehl aus, und überprüfen Sie den Wert des Parameters `AutomaticallyReplaceAcpProvider`. Wenn Sie Hilfe mit PowerShell benötigen, finden Sie weitere Informationen im Abschnitt [Verwenden von PowerShell zum Verwalten der Skype for Business-Organisation](setting-up-the-meeting-migration-service-mms.md#WPSInfo) am Ende dieses Artikels.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Wenn der Wert dieses Parameters $true lautet, wird MMS ausgeführt, wenn einem Benutzer eine Lizenz für **Audiokonferenzen** zugewiesen wird, und dessen Besprechungen werden aktualisiert. Die Einwahlnummern von Ihrem ACP werden beibehalten, bis die Lizenz für **Audiokonferenzen** zugewiesen wird.
    
- Wenn der Wert dieses Parameters $false lautet, aktualisiert MMS die Besprechungen nicht, selbst wenn einem Benutzer eine Lizenz für **Audiokonferenzen** zugewiesen wird. Die Einwahlnummern von Ihrem ACP werden beibehalten, bis der Benutzer im Skype for Business Admin Center oder über Windows PowerShell manuell für Audiokonferenzen bereitgestellt wird.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aktualisieren von Besprechungen, wenn sich die Audiokonferenzeinstellungen eines Benutzers ändern

MMS aktualisiert die vorhandenen Skype for Business- und Microsoft Teams-Besprechungen in den folgenden Fällen:
  
- Wenn Sie eine Lizenz für **Audiokonferenzen** zuweisen oder entfernen
    
- Wenn Sie Audiokonferenzen aktivieren oder deaktivieren
    
- Wenn Sie die Konferenzkennung eines Benutzers, der für die Verwendung öffentlicher Besprechungen konfiguriert ist, ändern oder zurücksetzen
    
- Wenn Sie den Benutzer zu einer neuen Audiokonferenzbrücke verschieben
    
- Wenn die Zuweisung einer Telefonnummer zu einer Audiokonferenzbrücke aufgehoben wird. Dies ist ein komplexes Szenario, für das zusätzliche Schritte erforderlich sind. Weitere Informationen finden Sie unter [Ändern der gebührenpflichtigen oder gebührenfreien Telefonnummern in Ihrer Audiokonferenzbrücke](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).
    
> [!IMPORTANT]
> MMS aktualisiert Besprechungen nur, wenn Sie die Microsoft-Brücke verwenden. Wenn Sie einen Drittanbieter für Audiokonferenzen verwenden, müssen die Benutzer ihre Besprechungen manuell aktualisieren. In diesem Fall können Sie [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) verwenden. 
  
Nicht alle Änderungen an den Audiokonferenzeinstellungen eines Benutzers lösen MMS aus. Insbesondere die folgenden beiden Änderungen führen nicht dazu, dass MMS Besprechungen aktualisiert:
  
- Ändern der SIP-Adresse für den Besprechungsorganisator (entweder des SIP-Benutzernamens oder der SIP-Domäne)
    
- Ändern der Besprechungs-URL Ihrer Organisation anhand des Befehls [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## <a name="what-happens-when-mms-updates-meetings"></a>Was geschieht, wenn MMS Besprechungen aktualisiert?

Wenn MMS feststellt, dass die Besprechungen eines Benutzers aktualisiert werden müssen, werden folgende Schritte ausgeführt:
  
1. Identifizieren aller Skype for Business- und Microsoft Teams-Besprechungen, die der Benutzer in der Zukunft geplant hat
    
  - Alle Skype for Business- oder Microsoft Teams-Besprechungen, die vor der Ausführung von MMS stattfanden, werden übersprungen.
    
  - Nur die Besprechungen, deren Organisator der Benutzer ist, werden aktualisiert
    
2. Ersetzen des Informationsblocks für Onlinebesprechungen in den Besprechungsdetails
    
3. Senden von Aktualisierungen an alle Besprechungsempfänger im Namen des Besprechungsorganisators
    
 **Wie lange dauert die Ausführung von MMS?**
  
Wie lange es dauert, bis MMS die Besprechungen migriert hat, hängt davon ab, wie viele Benutzer betroffen sind und wie viele Skype for Business- oder Microsoft Teams-Besprechungen die einzelnen Benutzer insgesamt in ihren Kalendern haben. Die Ausführung dauert mindestens zehn Minuten. Große Migrationen können bis zu zwölf Stunden dauern; die meisten Migrationen sollten aber innerhalb von einer Stunde abgeschlossen sein.
  
 **Einschränkungen und mögliche Probleme**
  
- Es werden nur die Skype for Business- oder Microsoft Teams-Besprechungen migriert, die durch Klicken auf die Schaltfläche **Skype-Besprechung hinzufügen** in Outlook im Web oder über das Skype-Besprechungs-Add-In für Outlook geplant wurden. Wenn ein Benutzer also die Informationen einer Skype-Onlinebesprechung von einer Besprechung in eine neue Besprechung kopiert, wird diese neue Besprechung nicht aktualisiert.
    
- MMS ersetzt alles im Informationsblock für die Onlinebesprechung, wenn eine Besprechung migriert wird. Wenn daher ein Benutzer diesen Block bearbeitet hat, werden seine Änderungen überschrieben. Alle Inhalte, die sich in den Besprechungsdetails außerhalb des Informationsblocks der Onlinebesprechung befinden, sind nicht betroffen.
    
     ![Der Besprechungsblock, der von MMS aktualisiert wird.](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- Besprechungsinhalte, die erstellt oder an die Besprechung angehängt wurden (Whiteboards, Umfragen usw.), bleiben nach der Ausführung von MMS nicht erhalten. Wenn Ihre Besprechungsorganisatoren im Voraus Inhalte an Besprechungen angehängt haben, müssen diese Inhalte nach der Ausführung von MMS erneut erstellt werden.
    
- Der Link zu freigegebenen Besprechungsnotizen im Kalenderelement und von innerhalb der Skype-Besprechung wird ebenfalls überschrieben. Beachten Sie, dass die in OneNote gespeicherten Besprechungsnotizen selbst noch vorhanden sind; nur der Link zu den freigegebenen Notizen wird überschrieben.
    
- Besprechungen mit mehr als 250 Teilnehmern (einschließlich des Organisators) werden nicht migriert.
    
- Einige Unicode-Zeichen im Text der Einladung werden möglicherweise fälschlich in eines der folgenden Sonderzeichen aktualisiert: ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>Was sehen die Benutzer, wenn MMS ihre Besprechungen aktualisiert?

Wie Meeting Migration Tool sendet auch MMS Besprechungsaktualisierungen im Namen der Benutzer. Das Einzige, was Ihre Benutzer daher sehen, ist eine weitere Runde Besprechungszusagebenachrichtungen für ihre Besprechungen. Das kann für die Benutzer verwirrend sein. Daher empfehlen wir, Ihre Benutzer im Voraus nicht nur über den Zeitpunkt der Migration von der lokalen Version zu Skype for Business Online zu informieren, sondern auch, wenn Sie die Audiokonferenzänderungen vornehmen, die MMS auslösen.
  
## <a name="managing-mms"></a>Verwalten von MMS

Sie müssen Windows PowerShell verwenden, um MMS zu verwalten und den Status von laufenden Migrationen zu prüfen. Bei den Informationen in diesem Abschnitt wird davon ausgegangen, dass Sie mit der Nutzung von PowerShell zur Verwaltung Ihrer Skype for Business-Organisation vertraut sind. Wenn Sie neu bei PowerShell sind, finden Sie weitere Informationen im Abschnitt [Verwenden von PowerShell zum Verwalten der Skype for Business-Organisation](setting-up-the-meeting-migration-service-mms.md#WPSInfo) am Ende dieses Artikels.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>Wie prüfe ich den Status von Besprechungsmigrationen?

Sie verwenden das  `Get-CsMeetingMigrationStatus`-Cmdlet, um den Status von Besprechungsmigrationen zu prüfen. Unten sind einige Beispiele aufgeführt.
  
Um einen Übersichtsstatus aller MMS-Migrationen zu erhalten, führen Sie folgenden Befehl aus:
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Damit erhalten Sie eine Übersicht in Tabellenformat aller Migrationsstatus wie im folgenden Beispiel:
  
State UserCount---------------<br/> Ausstehend 21<br/>In Bearbeitung 6<br/> Fehlgeschlagen 2 <br/> Erfolgreich 131
> [!IMPORTANT]
> Wenn Sie fehlgeschlagene Migrationen sehen, ergreifen Sie die nötigen Schritte, um diese Probleme so bald wie möglich zu beheben. Die Teilnehmer können sich nicht bei den von diesen Benutzern organisierten Besprechungen einwählen, bis Sie die Probleme behoben haben. Weitere Informationen finden Sie im Abschnitt [Was tue ich, wenn ein Fehler auftritt?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting).
  
Um umfassende Details aller Migrationen innerhalb eines bestimmten Zeitraums anzuzeigen, können Sie die Parameter  `StartTime` und `EndTime` verwenden. Der folgende Befehl gibt zum Beispiel alle Einzelheiten aller Migrationen zurück, die vom 1. Oktober 2016 bis zum 8. Oktober 2016 stattgefunden haben.
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

Wenn Sie den Status der Migration für einen bestimmten Benutzer prüfen möchten, können Sie dafür den Parameter  `UserId` verwenden. Beispielsweise gibt der folgende Befehl den Status des Benutzers ashaw@contoso.com zurück:
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a>Was tue ich, wenn ein Fehler auftritt?
<a name="Troubleshooting"> </a>

Wenn Sie das  `Get-CsMeetingMigrationStatus`-Cmdlet ausführen, um eine Übersicht zu erhalten, und feststellen, dass Migrationen im Status Fehlervorhanden sind, müssen Sie folgendermaßen vorgehen:
  
1. Stellen Sie fest, welche Benutzer betroffen sind. Führen Sie den folgenden Befehl aus, um die Liste der betroffenen Benutzer und den spezifischen gemeldeten Fehler zu erhalten:
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. Führen Sie für jeden dieser Benutzer das [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) aus, um deren Besprechungen manuell zu migrieren.
    
3. Wenn die Migration auch mit dem Meeting Migration Tool nicht funktioniert, haben Sie zwei Möglichkeiten:
    
  - Weisen Sie die Benutzer an, neue Skype-Besprechungen zu erstellen.
    
  - [Wenden Sie sich an den Support](https://go.microsoft.com/fwlink/p/?LinkID=518322).
    
### <a name="enabling-and-disabling-mms"></a>Aktivieren und Deaktivieren von MMS
<a name="Troubleshooting"> </a>

MMS ist standardmäßig für alle Organisationen aktiviert, kann aber bei Bedarf deaktiviert werden. Wenn Sie z. B. alle Besprechungen manuell migrieren möchten oder einen Drittanbieter für Audiokonferenzen verwenden, ist die Ausführung von MMS nicht erforderlich. Sie können auch wählen, MMS vorübergehend zu deaktivieren. Beispiel: Sie nehmen größere Änderungen an den Audiokonferenzeinstellungen für Ihre Organisation vor, und MMS soll erst ausgeführt werden, wenn alle Änderungen abgeschlossen sind.
  
Um zu sehen, ob MMS für Ihre Organisation aktiviert ist, führen Sie den folgenden Befehl aus, und prüfen Sie den Wert für den Parameter  `MeetingMigrationEnabled`. Wenn dieser Parameter auf $true festgelegt ist, ist MMS aktiviert.
  
```
Get-CsTenantMigrationConfiguration
```

Führen Sie zum Deaktivieren von MMS den folgenden Befehl aus:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

Führen Sie zum Aktivieren von MMS den folgenden Befehl aus:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>Aktivieren und Deaktivieren von MMS nur für Audiokonferenzänderungen
<a name="Troubleshooting"> </a>

Sie können MMS auch nur für Audiokonferenzänderungen deaktivieren. MMS wird nach wie vor ausgeführt, wenn ein Benutzer von der lokalen Skype for Business-Version zu Skype for Business Online migriert wird. Um den aktuellen MMS-Status für Audiokonferenzaktualisierungen zu überprüfen, führen Sie den folgenden Befehl aus, und überprüfen Sie den Wert für den Parameter  `AutomaticallyMigrateUserMeetings`. Wenn dieser Parameter auf $true festgelegt ist, ist für MMS festgelegt, dass die Benutzerbesprechungen bei Änderungen an Audiokonferenzeinstellungen aktualisiert werden.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

Führen Sie zum Deaktivieren von MMS für Audiokonferenzen den folgenden Befehl aus:
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

Führen Sie zum Aktivieren von MMS für Audiokonferenzen den folgenden Befehl aus:
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>Wie führe ich die Besprechungsmigration manuell für Benutzer aus?
<a name="Troubleshooting"> </a>

Neben den automatischen Besprechungsmigrationen können Sie die Besprechungsmigration manuell für einen Benutzer ausführen, indem Sie das **Start-CsExMeetingMigration** -Cmdlet ausführen. Dieses Cmdlet fügt den Benutzer in der Besprechungsmigrations-Warteschlange hinzu. Meeting Migration Service liest die Benutzeranforderung und migriert die zugehörigen Besprechungen. Den Status der Besprechungsmigration können Sie mit dem **Get-CsMeetingMigrationStatus** -Cmdlet überprüfen.
  
Hier ist ein Beispiel, in dem die Besprechungsmigration für den Benutzer ashaw@contoso.com gestartet wird:
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a>Verwenden von PowerShell zum Verwalten der Skype for Business-Organisation
<a name="WPSInfo"> </a>

 **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
  
1. Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Start Menu** > **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
 **Starten einer Windows PowerShell-Sitzung**
  
1. Vom **Start Menu** > **Windows PowerShell**.
    
2. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:
    
    > [!NOTE]
    > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
Weitere Informationen zum Starten von Windows PowerShell finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder[Herstellen der Verbindung zu Skype for Business Online mit Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See Also

[Testen oder Erwerben von Audiokonferenzen in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
