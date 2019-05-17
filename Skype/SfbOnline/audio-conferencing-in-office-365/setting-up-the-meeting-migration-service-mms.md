---
title: Verwenden die Migration Besprechungsdienst (MMS)
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Meeting-Migration Service (MMS) ist ein Dienst, der im Hintergrund ausgeführt, und Skype für Geschäfts- und Microsoft-Teams, Besprechungen für Benutzer automatisch aktualisiert. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: da1b21b65794354a023632e785c463b494cc38f5
ms.sourcegitcommit: ee05fe02fe68b5bd6ee38dd4a3ad69da3d37c492
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "34106174"
---
# <a name="using-the-meeting-migration-service-mms"></a>Verwenden die Migration Besprechungsdienst (MMS)

Die Besprechung Migration Service (MMS) handelt es sich um Dienst, mit dem ein Benutzer vorhandener Besprechungen in den folgenden Szenarien aktualisiert:

- Bei der Migration eines Benutzers aus lokalen in die Cloud (an, ob Skype für Business Online oder TeamsOnly).
- Wenn ein Administrator eine Änderung an den Einstellungen des Benutzers Audiokonferenzen vornimmt 
- Wenn ein Benutzer online aktualisiert wird, nur Teams, oder wenn ein Benutzermodus in TeamsUpgradePolicy auf SfBwithTeamsCollabAndMeetings festgelegt ist
- Bei der Verwendung von PowerShell 


Standardmäßig wird MMS automatisch in beiden Fällen ausgelöst, obwohl Administratoren auf der Ebene der Mandanten deaktiviert werden können. Darüber hinaus können Admins ein PowerShell-Cmdlets Sie Besprechung Migration für einen bestimmten Benutzer manuell auslösen.


**Nachteile**: die Besprechung migrationsdienst kann nicht verwendet werden, wenn Folgendes zutrifft:

- Das Postfach des Benutzers wird in Exchange lokal gehostet.
- Der Benutzer wird aus der Cloud zu Skype für Business Server lokal migriert.

In diesen Fällen können Endbenutzer das [Migrationstool der Besprechung](https://www.microsoft.com/en-us/download/details.aspx?id=51659) zum Migrieren ihrer eigenen Besprechungen verwenden stattdessen.

## <a name="how-mms-works"></a>Funktionsweise von MMS

Wenn für einen bestimmten Benutzer MMS ausgelöst wird, wird eine migrationsanforderung für diesen Benutzer in einer Warteschlange platziert. Um eine beliebige Racebedingung zu verhindern, wird die Anforderung in der Warteschlange absichtlich nicht erst mindestens 90 Minuten, durch überschritten haben verarbeitet. Nachdem MMS die Anforderung verarbeitet wird, werden die folgenden Aufgaben ausgeführt:

1. Durchsucht das Postfach für alle vorhandenen Besprechungen, die von diesem Benutzer organisiert und in der Zukunft geplant.
2. Anhand der Informationen in das Postfach des Benutzers, entweder aktualisiert oder neue Besprechungen in Teams oder Skype für Business Online für diesen Benutzer, je nach Szenario plant.
3. In der e-Mail-Nachricht ersetzt sie den online-Besprechung Block in die Details der Besprechung.
4. Sendet die aktualisierte Version von diese Besprechung an alle Empfänger der Besprechung im Auftrag der Organisator der Besprechung. Meeting eingeladene Teilnehmer erhält eine besprechungsaktualisierung mit aktualisierten Live Meeting Koordinaten in ihren e-Mail. 

    ![Der Besprechungsblock, der von MMS aktualisiert wird.](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Ab dem Zeitpunkt MMS ausgelöst wird, dauert es in der Regel ungefähr 2 Stunden, bis der Benutzer Besprechungen migriert werden. Jedoch, wenn der Benutzer eine große Anzahl von Besprechungen verfügt, kann es länger dauern. Findet MMS einen Fehler, die einen oder mehrere Besprechungen für den Benutzer migrieren, wird es in regelmäßigen Abständen bis zu 9 über den Zeitraum der 24 Stunden wiederholt.

**Notes**:

- MMS ersetzt alles im Informationsblock für die Onlinebesprechung, wenn eine Besprechung migriert wird. Wenn daher ein Benutzer diesen Block bearbeitet hat, werden seine Änderungen überschrieben. Alle Inhalte, die sich in den Besprechungsdetails außerhalb des Informationsblocks der Onlinebesprechung befinden, sind nicht betroffen.
- Es werden nur die Skype for Business- oder Microsoft Teams-Besprechungen migriert, die durch Klicken auf die Schaltfläche **Skype-Besprechung hinzufügen** in Outlook im Web oder über das Skype-Besprechungs-Add-In für Outlook geplant wurden. Wenn ein Benutzer kopiert und die Skype onlinebesprechung Informationen aus einer Besprechung zu einer neuen Besprechung fügt, werden diese neue Besprechung nicht aktualisiert, da es keine Besprechung in den ursprünglichen Dienst ist.
- Besprechungsinhalte, die erstellt wurde, oder der Besprechung (Whiteboards, abstimmungen usw.) zugeordnet werden nicht beibehalten wird, nachdem MMS ausgeführt wird. Wenn Ihre Besprechungsorganisatoren im Voraus Inhalte an Besprechungen angehängt haben, müssen diese Inhalte nach der Ausführung von MMS erneut erstellt werden.
- Der Link zu freigegebenen Besprechungsnotizen im Kalenderelement und von innerhalb der Skype-Besprechung wird ebenfalls überschrieben. Notiz, die jedoch die eigentlichen Besprechungsnotizen im OneNote weiterhin sein vorhanden. Es ist nur für den Link zur freigegebenen Notizen, der überschrieben wird.
- Besprechungen mit mehr als 250 Teilnehmern (einschließlich des Organisators) werden nicht migriert.
- Einige Unicode-Zeichen im Text der Einladung möglicherweise nicht ordnungsgemäß aktualisiert werden, auf eine der folgenden Sonderzeichen: Hiermit ¿½,.

## <a name="triggering-mms-for-a-user"></a>Auslösen der MMS für einen Benutzer

In diesem Abschnitt wird beschrieben, was geschieht, wenn MMS in jeder der folgenden Fällen ausgelöst wird:

- Wenn ein Benutzer von lokalen in die Cloud migriert
- Wenn ein Administrator eine Änderung an den Einstellungen des Benutzers Audiokonferenzen vornimmt 
- Wenn die Benutzermodus in TeamsUpgradePolicy auf TeamsOnly oder SfBWithTeamsCollabAndMeetings (mit Powershell oder der Teams Verwaltungsportals) festgelegt ist
- Wenn Sie das PowerShell-Cmdlet Start-CsExMeetingMigration verwenden

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Aktualisieren von Besprechungen, wenn Sie einen lokalen Benutzer in der Cloud verschieben

Dies ist die am häufigsten verwendeten Szenario, in dem MMS hilft einen fließender Übergang für Ihre Benutzer zu erstellen. Ohne Besprechung Migration funktioniert vorhandene Besprechungen, die von einem Benutzer in Skype für Business Server lokal organisiert nicht mehr, nachdem der Benutzer online verschoben wird. Wenn Sie daher die lokalen-Verwaltungstools verwenden (entweder `Move-CsUser` oder der Admin-Systemsteuerung) zum Verschieben eines Benutzers in die Cloud vorhandene Besprechungen werden automatisch verschoben in die Cloud wie folgt:

- Wenn die `MoveToTeams` wechseln `Move-CsUser` angegeben ist, Besprechungen direkt zu Teams migriert werden, und des Benutzers im TeamsOnly Modus. Diese Option erfordert Skype für Business Server 2015 mit CU8 oder höher. Diese Benutzer können weiterhin alle Skype für Business Besprechung teilnehmen, den, die Sie zu, eingeladen werden möglicherweise über die Skype für Business-Client oder die Skype-Meeting-App.
- Andernfalls werden Besprechungen zu Skype für Business Online migriert.

In beiden Fällen Wenn der Benutzer eine Audiokonferenz-Lizenz zugewiesen wurde, bevor Sie in der Cloud verschoben werden Besprechungen mit Zugriffsnummer für Einwahl Koordinaten erstellt werden. Wenn eines Benutzers lokal in der Cloud verschieben und Sie für diesen Benutzer an der Audiokonferenz verwenden möchten, wird empfohlen, dass Sie zuerst die Audiokonferenz zuweisen, bevor der Benutzer verschieben, sodass nur 1 Besprechung Migration ausgelöst wird.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aktualisieren von Besprechungen, wenn sich die Audiokonferenzeinstellungen eines Benutzers ändern

In den folgenden Fällen aktualisieren MMS vorhandenen Skype für Geschäfts- und Microsoft-Teams, Besprechungen zum Hinzufügen, entfernen oder Ändern von Zugriffsnummer für Einwahl Koordinaten:

- Wenn Sie zuweisen oder entfernen Sie eine Audiokonferenz Microsoft-Dienst-Lizenz eines Benutzers und der Benutzer ist nicht für einen Drittanbieter-Audiokonferenzen aktiviert.
- Wenn Sie den Anbieter von Audiokonferenzen eines Benutzers von einem anderen Anbieter an Microsoft, die vom Benutzer bereitgestellte ändern, werden eine Microsoft Audiokonferenzen Lizenz zugewiesen. Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider). Beachten Sie außerdem, dass Unterstützung für Drittanbieter-Audiokonferenzen [ACP] Ende der Lebensdauer auf 1 April 2019 als [zuvor](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)geplant ist.
- Wenn Sie aktivieren oder Deaktivieren von Audiokonferenzen für einen Benutzer.
- Beim Ändern oder Zurücksetzen die Konferenz-ID für einen Benutzer für die Verwendung von öffentlicher Besprechungen konfiguriert.
- Wenn Sie den Benutzer zu einer neuen Audiokonferenzbrücke verschieben
- Wenn eine Rufnummer aus einem audiokonferenzbrücke nicht zugewiesen ist. Hierbei handelt es sich um ein komplexes Szenario, das zusätzliche Schritte erforderlich sind. Weitere Informationen finden Sie unter [Ändern der Rufnummern Ihrer audiokonferenzbrücke](https://docs.microsoft.com/en-us/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

Nicht alle Änderungen an den Audiokonferenzeinstellungen eines Benutzers lösen MMS aus. Insbesondere die folgenden beiden Änderungen führen nicht dazu, dass MMS Besprechungen aktualisiert:

- Ändern der SIP-Adresse für den Besprechungsorganisator (entweder des SIP-Benutzernamens oder der SIP-Domäne)
- Beim Ändern Ihrer Organisation des meeting-URL mithilfe der `Update-CsTenantMeetingUrl` Befehl.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Aktualisieren von Besprechungen beim Zuweisen der TeamsUpgradePolicy

In der Standardeinstellung Migration meeting wird automatisch ausgelöst, wenn ein Benutzer eine Instanz des erteilt wird `TeamsUpgradePolicy` mit `mode=TeamsOnly` oder `mode= SfBWithTeamsCollabAndMeetings`. Wenn Sie nicht möchten, um Besprechungen zu migrieren, wenn Sie eine der folgenden Modi erteilen, und geben Sie dann `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` (bei Verwendung von PowerShell) oder deaktivieren Sie das Kontrollkästchen, um Besprechungen migrieren, wenn ein Benutzer Koexistenzmodus festlegen (bei dem Verwaltungsportal von Teams).

Beachten Sie auch Folgendes:

- Meeting-Migration wird nur aufgerufen, wenn Sie gewähren `TeamsUpgradePolicy` für einen bestimmten Benutzer. Wenn Sie gewähren `TeamsUpgradePolicy` mit `mode=TeamsOnly` oder `mode=SfBWithTeamsCollabAndMeetings` pro *Mandant geltende* meeting Migration nicht aufgerufen.
- Ein Benutzer kann nur TeamsOnly erteilt werden Modus, wenn der Benutzer online verwaltet wird. Benutzer, die lokal sind müssen verschoben werden, mithilfe von `Move-CsUser` wie weiter oben beschrieben.
- Erteilen von ein anderer Druckmodus als TeamsOnly oder SfBWithTeamsCollabAndMeetings konvertiert nicht vorhandene Teams Besprechungen zu Skype für Business Besprechungen.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Trigger Besprechung Migration manuell über den PowerShell-Cmdlets

Zusätzlich zur automatischen Besprechung Migrationen Admins können manuell auslösen Besprechung Migration für einen Benutzer durch Ausführen des Cmdlets `Start-CsExMeetingMigration`. Dieses Cmdlet nimmt eine migrationsanforderung für den angegebenen Benutzer.  Zusätzlich zu den erforderlichen `Identity` Parameter, es werden zwei optionale Parameter, `SourceMeetingType` und `TargetMeetingType`, dem können Sie angeben, wie Besprechungen zu migrieren:

**TargetMeetingType:**

- Mit `TargetMeetingType Current` gibt an, dass Skype für Business Besprechungen Skype für Business Besprechungen und Teams Besprechungen Teams Besprechungen bleiben. Jedoch Audiokonferenzen Koordinaten möglicherweise geändert werden, und alle lokalen Skype für Business Besprechungen würde zu Skype für Business Online migriert werden. Dies ist der Standardwert für TargetMeetingType.
- Mit `TargetMeetingType Teams` gibt an, dass alle vorhandenen Besprechung zu Teams migriert werden muss, unabhängig davon, ob die Besprechung in Skype für Geschäftskunden online und lokalen gehostet wird und unabhängig davon, ob von Audiokonferenzen Updates erforderlich sind. 

**SourceMeetingType:**
- Mit `SourceMeetingType SfB` gibt an, nur Skype für Business Besprechungen (, ob der lokale oder online) aktualisiert werden sollen.
- Mit `SourceMeetingType Teams` gibt an, dass nur Teams Besprechungen aktualisiert werden soll.
- Mit `SourceMeetingType All` gibt an, dass beide Skyep für Business Besprechungen und Teams Besprechungen aktualisiert werden soll. Dies ist der Standardwert für SourceMeetingType.
    

Das folgende Beispiel zeigt, wie Besprechung Migration für Benutzer ashaw@contoso.com initiieren, damit alle Besprechungen zu Teams migriert werden:

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Verwalten von MMS

Mithilfe von Windows PowerShell, überprüfen Sie den Status der laufenden Migrationen, manuell auslösen Besprechung Migration, und Migration vollständig deaktivieren. 

### <a name="check-the-status-of-meeting-migrations"></a>Überprüfen des Status des meeting-Migrationen

Verwenden Sie die `Get-CsMeetingMigrationStatus` -Cmdlet zum Überprüfen des Status der Besprechung Migrationen. Unten sind einige Beispiele aufgeführt.

- Wenn alle MMS-Migrationen Zusammenfassung Status erhalten möchten, führen Sie den folgenden Befehl eine tabellarische Ansicht aller Migration Staaten bereit:

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Wenn Sie alle Details zu allen Migrationen innerhalb eines bestimmten Zeitraums erhalten möchten, verwenden Sie die `StartTime` und `EndTime` Parameter. Beispielsweise zurückgegebenen der folgende Befehl alle Details für alle Migrationen an, die aufgetreten ist aus 1 Oktober 2018 auf 8 Oktober 2018.

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Um den Status der Migration für einen bestimmten Benutzer zu überprüfen, verwenden Sie die `Identity` Parameter. Beispielsweise gibt der folgende Befehl den Status des Benutzers ashaw@contoso.com zurück:

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Wenn Sie alle Migrationen angezeigt wird, die fehlgeschlagen sind, Ausführen einer Aktion zum Beheben dieser Probleme so bald wie möglich, da Personen nicht können Dial werden-in, das die Besprechungen, die diese Benutzer organisiert, bis Sie deren Lösung beschrieben. Wenn `Get-CsMeetingMigrationStatus` zeigt alle Migrationen im ausgefallenen Zustand, gehen Sie wie folgt vor:
 
1. Stellen Sie fest, welche Benutzer betroffen sind. Führen Sie den folgenden Befehl aus, um die Liste der betroffenen Benutzer und den spezifischen gemeldeten Fehler zu erhalten:

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table Identity, LastMessage
    ```
2. Führen Sie für jeden betroffenen Benutzer die Besprechung Migrationstools für ihre Besprechungen manuell zu migrieren.

3. Wenn die Migration auch mit dem Meeting Migration Tool nicht funktioniert, haben Sie zwei Möglichkeiten:

    - Weisen Sie die Benutzer an, neue Skype-Besprechungen zu erstellen.
    - [Wenden Sie sich an den Support](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Aktivieren und Deaktivieren von MMS

MMS ist standardmäßig für alle Organisationen aktiviert, jedoch kann folgendermaßen deaktiviert werden:

- Für den Mandanten vollständig deaktivieren. 
- Nur für Änderungen im Zusammenhang mit der Audiokonferenz deaktivieren. In diesem Fall MMS wird weiterhin ausgeführt, wenn ein Benutzer in die Cloud oder wenn Sie TeamsOnly oder SfBWithTeamsCollabAndMeetings-Modus in gewähren aus lokalen migriert `TeamsUpgradePolicy`.

Beispielsweise können Sie manuell migrieren aller Besprechungen oder vorübergehend deaktivieren möchten MMS beim Durchführen erhebliche Änderungen an der Audiokonferenz Einstellungen für die Organisation

Um herauszufinden, ob MMS für Ihre Organisation aktiviert ist, führen Sie den folgenden Befehl aus. MMS ist aktiviert, wenn die `MeetingMigrationEnabled` Parameter ist `$true`.
```
Get-CsTenantMigrationConfiguration
```
Verwenden Sie zum Aktivieren oder Deaktivieren von MMS vollständig, die `Set-CsTenantMigrationConfiguration` Befehl. Führen Sie beispielsweise den folgenden Befehl zum Deaktivieren von MMS aus:

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Wenn MMS in der Organisation aktiviert ist und Sie möchten überprüfen Sie, ob sie für Audiokonferenzen Updates aktiviert ist, überprüfen Sie den Wert der `AutomaticallyMigrateUserMeetings` Parameter in der Ausgabe von `Get-CsOnlineDialInConferencingTenantSettings`. Verwenden Sie zum Aktivieren oder Deaktivieren von MMS für Audiokonferenzen, `Set-CsOnlineDialInConferencingTenantSettings`. Führen Sie beispielsweise den folgenden Befehl zum Deaktivieren von MMS für Audiokonferenzen aus:

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Verschieben von Benutzern zwischen lokalen und cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
