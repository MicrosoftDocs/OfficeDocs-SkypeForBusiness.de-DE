---
title: Verwenden des Besprechungsmigrationsdiensts (MMS)
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) ist ein Dienst, der im Hintergrund ausgeführt wird und Skype for Business- und Microsoft Teams-Besprechungen automatisch für Benutzer aktualisiert. Mit MMS brauchen die Benutzer nicht mehr Meeting Migration Tool auszuführen, um ihre Skype for Business- und Microsoft Teams-Besprechungen zu aktualisieren.
ms.openlocfilehash: 18a36425e842e0c24c5cf6c2837535043e7967a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111951"
---
# <a name="using-the-meeting-migration-service-mms"></a>Verwenden des Besprechungsmigrationsdiensts (MMS)

Der Meeting Migration Service (MMS) ist ein Dienst, der die vorhandenen Besprechungen eines Benutzers in den folgenden Szenarien aktualisiert:

- Wenn ein Benutzer von lokal in die Cloud migriert wird (ob zu Skype for Business Online oder zu TeamsOnly).
- Wenn ein Administrator eine Änderung an den Audiokonferenzeinstellungen des Benutzers vor nimmt 
- Wenn ein Onlinebenutzer nur auf Teams aktualisiert wird oder wenn der Modus eines Benutzers in TeamsUpgradePolicy auf SfBwithTeamsCollabAndMeetings festgelegt ist
- Wenn Sie PowerShell verwenden 


Standardmäßig wird MMS in jedem dieser Fälle automatisch ausgelöst, obwohl Administratoren es auf Mandantenebene deaktivieren können. Darüber hinaus können Administratoren ein PowerShell-Cmdlet verwenden, um die Besprechungsmigration für einen bestimmten Benutzer manuell auszulösen.


**Einschränkungen:** Der Besprechungsmigrationsdienst kann nicht verwendet werden, wenn eine der folgenden Punkte zutreffen:

- Das Postfach des Benutzers wird lokal in Exchange gehostet.
- Der Benutzer wird lokal aus der Cloud zu Skype for Business Server migriert.

In diesen Situationen können Endbenutzer stattdessen das Tool für die [Besprechungsmigration](https://www.microsoft.com/download/details.aspx?id=51659) verwenden, um ihre eigenen Besprechungen zu migrieren.

## <a name="how-mms-works"></a>Funktionsweise von MMS

Wenn MMS für einen bestimmten Benutzer ausgelöst wird, wird eine Migrationsanforderung für den Benutzer in eine Warteschlange gesetzt. Um Rennbedingungen zu vermeiden, wird die Anforderung in der Warteschlange absichtlich erst verarbeitet, wenn mindestens 90 Minuten vergangen sind. Nachdem MMS die Anforderung verarbeitet hat, führt es die folgenden Aufgaben aus:

1. Es durchsucht das Postfach dieses Benutzers nach allen vorhandenen Besprechungen, die von diesem Benutzer organisiert und in zukunft geplant sind.
2. Basierend auf den Informationen, die im Postfach des Benutzers gefunden wurden, werden je nach genauem Szenario entweder neue Besprechungen in Teams oder Skype for Business Online für diesen Benutzer aktualisiert oder geplant.
3. In der E-Mail-Nachricht ersetzt sie den Online-Besprechungsblock in den Besprechungsdetails.
4. Die aktualisierte Version dieser Besprechung wird im Auftrag des Besprechungsorganisators an alle Besprechungsempfänger gesendet. Besprechungs-Eingeladene erhalten ein Besprechungsupdate mit aktualisierten Besprechungskoordinaten in ihrer E-Mail. 

    ![Der Besprechungsblock, der von MMS aktualisiert wird.](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Ab dem Zeitpunkt, zu dem MMS ausgelöst wird, dauert es in der Regel ca. 2 Stunden, bis die Besprechungen des Benutzers migriert werden. Wenn der Benutzer jedoch über eine große Anzahl von Besprechungen verfügt, kann dies länger dauern. Wenn BEI MMS ein Fehler beim Migrieren einer oder mehreren Besprechungen für den Benutzer auftritt, wird in regelmäßigen Abständen bis zu 9 Mal über den Zeitraum von 24 Stunden geversucht.

**Hinweise**:

- MMS ersetzt alles im Informationsblock für die Onlinebesprechung, wenn eine Besprechung migriert wird. Wenn daher ein Benutzer diesen Block bearbeitet hat, werden seine Änderungen überschrieben. Alle Inhalte, die sich in den Besprechungsdetails außerhalb des Informationsblocks der Onlinebesprechung befinden, sind nicht betroffen. Dies bedeutet, dass alle an die Besprechungs-Einladung angefügten Dateien weiterhin einbezogen werden. 
- Es werden nur die Skype for Business- oder Microsoft Teams-Besprechungen migriert, die durch Klicken auf die Schaltfläche **Skype-Besprechung hinzufügen** in Outlook im Web oder über das Skype-Besprechungs-Add-In für Outlook geplant wurden. Wenn ein Benutzer die Skype-Online-Besprechungsinformationen aus einer Besprechung in eine neue Besprechung kopiert und einfüge, wird diese neue Besprechung nicht aktualisiert, da es keine Besprechung im ursprünglichen Dienst gibt.
- Besprechungsinhalte, die erstellt oder an die Besprechung angefügt wurden (Whiteboards, Umfragen und so weiter), werden nach der MmS-Ausgeführten nicht beibehalten. Wenn Ihre Besprechungsorganisatoren im Voraus Inhalte an Besprechungen angehängt haben, müssen diese Inhalte nach der Ausführung von MMS erneut erstellt werden.
- Der Link zu freigegebenen Besprechungsnotizen im Kalenderelement und von innerhalb der Skype-Besprechung wird ebenfalls überschrieben. Beachten Sie, dass die tatsächlich in OneNote gespeicherten Besprechungsnotizen weiterhin dort gespeichert sind. Es ist nur der Link zu den freigegebenen Notizen, der überschrieben wird.
- Besprechungen mit mehr als 250 Teilnehmern (einschließlich des Organisators) werden nicht migriert.
- Einige UNICODE-Zeichen im Textkörper der Einladung werden möglicherweise fälschlicherweise auf eines der folgenden Sonderzeichen aktualisiert: ï, ¿, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Auslösen von MMS für einen Benutzer

In diesem Abschnitt wird beschrieben, was geschieht, wenn MMS in jedem der folgenden Fälle ausgelöst wird:

- Wenn ein Benutzer von der lokalen in die Cloud migriert wird
- Wenn ein Administrator eine Änderung an den Audiokonferenzeinstellungen des Benutzers vor nimmt 
- Wenn der Benutzermodus in TeamsUpgradePolicy auf TeamsOnly oder SfBWithTeamsCollabAndMeetings festgelegt ist (entweder mithilfe von Powershell oder dem Teams Admin Portal)
- Wenn Sie das PowerShell-Cmdlet verwenden, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Aktualisieren von Besprechungen beim Verschieben eines lokalen Benutzers in die Cloud

Dies ist das am häufigsten verwendeten Szenario, in dem MMS dazu beihilft, einen reibungslosen Übergang für Ihre Benutzer zu erstellen. Ohne Besprechungsmigration würden vorhandene Besprechungen, die von einem Benutzer in Skype for Business Server lokal organisiert werden, nicht mehr funktionieren, sobald der Benutzer online verschoben wurde. Wenn Sie daher die lokalen Administratortools (oder die Systemsteuerung der Administratoren) verwenden, um einen Benutzer in die Cloud zu verschieben, werden vorhandene Besprechungen automatisch wie folgt in die `Move-CsUser` Cloud verschoben:

- Wenn der Umstieg angegeben ist, werden Besprechungen direkt zu Teams migriert, und der Benutzer befindet sich `MoveToTeams` `Move-CsUser` im TeamsOnly-Modus. Für die Verwendung dieses Schalters ist Skype for Business Server 2015 mit CU8 oder höher erforderlich. Diese Benutzer können weiterhin an jeder Skype for Business-Besprechung teilnehmen, zu der sie möglicherweise eingeladen werden, entweder über den Skype for Business-Client oder die Skype-Besprechungs-App.
- Andernfalls werden Besprechungen zu Skype for Business Online migriert.

Wenn dem Benutzer in beiden Fällen eine Lizenz für Audiokonferenzen zugewiesen wurde, bevor er in die Cloud verschoben wurde, werden die Besprechungen mit Einwahlkoordinaten erstellt. Wenn Sie einen Benutzer aus der lokalen Cloud in die Cloud verschieben und beabsichtigen, dass dieser Benutzer Audiokonferenzen verwendet, empfehlen wir, die Audiokonferenz zuerst zuzuordnen, bevor Sie den Benutzer verschieben, sodass nur eine Besprechungsmigration ausgelöst wird.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aktualisieren von Besprechungen, wenn sich die Audiokonferenzeinstellungen eines Benutzers ändern

In den folgenden Fällen aktualisiert MMS vorhandene Skype for Business- und Microsoft Teams-Besprechungen, um Einwahlkoordinaten hinzuzufügen, zu entfernen oder zu ändern:

- Wenn Sie einem Benutzer eine Microsoft Audio Conferencing-Dienstlizenz zuweisen oder entfernen, und dieser Benutzer ist für einen Drittanbieter für Audiokonferenzen nicht aktiviert.
- Wenn Sie den Audiokonferenzanbieter eines Benutzers von einem anderen Anbieter in Microsoft ändern, vorausgesetzt, dem Benutzer wird eine Microsoft Audio Conferencing-Lizenz zugewiesen. Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Audiokonferenzanbieter.](./assign-microsoft-as-the-audio-conferencing-provider.md) Beachten Sie außerdem, dass die Unterstützung für Audiokonferenzanbieter von Drittanbietern [ACP] wie bereits angekündigt am 1. April 2019 für das Ende der Lebensdauer geplant [ist.](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)
- Wenn Sie Audiokonferenzen für einen Benutzer aktivieren oder deaktivieren.
- Wenn Sie die Konferenz-ID für einen Benutzer ändern oder zurücksetzen, der für die Verwendung öffentlicher Besprechungen konfiguriert ist.
- Wenn Sie den Benutzer zu einer neuen Audiokonferenzbrücke verschieben
- Wenn eine Telefonnummer von einer Audiokonferenzbrücke nicht zugewiesen wird. Dies ist ein komplexes Szenario, das zusätzliche Schritte erfordert. Weitere Informationen finden Sie unter [Ändern der Telefonnummern auf der Audiokonferenzbrücke.](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)

Nicht alle Änderungen an den Audiokonferenzeinstellungen eines Benutzers lösen MMS aus. Insbesondere die folgenden beiden Änderungen führen nicht dazu, dass MMS Besprechungen aktualisiert:

- Ändern der SIP-Adresse für den Besprechungsorganisator (entweder des SIP-Benutzernamens oder der SIP-Domäne)
- Wenn Sie die Besprechungs-URL Ihrer Organisation mithilfe des Befehls `Update-CsTenantMeetingUrl` ändern.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Aktualisieren von Besprechungen beim Zuweisen von TeamsUpgradePolicy

Standardmäßig wird die Besprechungsmigration automatisch ausgelöst, wenn einem Benutzer eine Instanz von `TeamsUpgradePolicy` mit oder `mode=TeamsOnly` gewährt `mode= SfBWithTeamsCollabAndMeetings` wird. Wenn Sie Besprechungen nicht migrieren möchten, wenn Sie einen dieser Modi gewähren, geben Sie `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` an (wenn Sie PowerShell verwenden), oder deaktivieren Sie das Kontrollkästchen, um Besprechungen zu migrieren, wenn Sie den Koexistenzmodus eines Benutzers festlegen (wenn Sie das Teams-Administratorportal verwenden).

Beachten Sie außerdem Folgendes:

- Die Besprechungsmigration wird nur aufgerufen, wenn Sie sie `TeamsUpgradePolicy` für einen bestimmten Benutzer gewähren. Wenn Sie die `TeamsUpgradePolicy` Besprechung mit oder `mode=TeamsOnly` mandantenweit gewähren, wird die `mode=SfBWithTeamsCollabAndMeetings` Besprechungsmigration nicht aufgerufen. 
- Einem Benutzer kann der TeamsOnly-Modus nur gewährt werden, wenn der Benutzer online zu Hause ist. Benutzer, die lokal zuhause sind, müssen wie zuvor beschrieben mit `Move-CsUser` verschoben werden.
- Durch das Gewähren eines anderen Modus als TeamsOnly oder SfBWithTeamsCollabAndMeetings werden vorhandene Teams-Besprechungen nicht in Skype for Business-Besprechungen konvertiert.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Manuelles Auslösen der Besprechungsmigration über das PowerShell-Cmdlet

Zusätzlich zu automatischen Besprechungsmigrationen können Administratoren die Besprechungsmigration für einen Benutzer manuell auslösen, indem sie das Cmdlet `Start-CsExMeetingMigration` ausführen. Mit diesem Cmdlet wird eine Migrationsanforderung für den angegebenen Benutzer in eine Warteschlange eingereiht.  Zusätzlich zum erforderlichen Parameter werden zwei optionale Parameter und verwendet, mit denen Sie angeben `Identity` können, `SourceMeetingType` wie `TargetMeetingType` Besprechungen migriert werden sollen:

**TargetMeetingType:**

- Mit `TargetMeetingType Current` gibt an, dass Skype for Business-Besprechungen Weiterhin Skype for Business-Besprechungen und Teams-Besprechungen Teams-Besprechungen bleiben. Audiokonferenzkoordinaten können jedoch geändert werden, und alle lokalen Skype for Business-Besprechungen würden zu Skype for Business Online migriert. Dies ist der Standardwert für TargetMeetingType.
- Mit gibt an, dass vorhandene Besprechungen zu Teams migriert werden müssen, unabhängig davon, ob die Besprechung online oder lokal in Skype for Business gehostet wird, und unabhängig davon, ob Audiokonferenzupdates erforderlich `TargetMeetingType Teams` sind. 

**SourceMeetingType:**
- Die `SourceMeetingType SfB` Verwendung gibt an, dass nur Skype for Business-Besprechungen (lokal oder online) aktualisiert werden sollten.
- Die `SourceMeetingType Teams` Verwendung gibt an, dass nur Teams-Besprechungen aktualisiert werden sollten.
- Die `SourceMeetingType All` Verwendung gibt an, dass sowohl Skype for Business-Besprechungen als auch Teams-Besprechungen aktualisiert werden sollten. Dies ist der Standardwert für SourceMeetingType.
    

Das folgende Beispiel zeigt, wie Sie die Besprechungsmigration für Benutzergruppen ashaw@contoso.com, sodass alle Besprechungen zu Teams migriert werden:

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Verwalten von MMS

Mithilfe Windows PowerShell können Sie den Status laufender Migrationen überprüfen, die Besprechungsmigration manuell auslösen und die Migration vollständig deaktivieren. 

### <a name="check-the-status-of-meeting-migrations"></a>Überprüfen des Status von Besprechungsmigrationen

Sie verwenden das `Get-CsMeetingMigrationStatus` Cmdlet, um den Status von Besprechungsmigrationen zu überprüfen. Unten sind einige Beispiele aufgeführt.

- Um einen Zusammenfassungsstatus aller MMS-Migrationen zu erhalten, führen Sie den folgenden Befehl aus, der eine tabellarische Ansicht aller Migrationszustände bietet:

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Verwenden Sie die Parameter und, um vollständige Details aller Migrationen innerhalb eines bestimmten Zeitraums `StartTime` `EndTime` zu erhalten. Der folgende Befehl gibt beispielsweise vollständige Details zu allen Migrationen zurück, die vom 1. Oktober 2018 bis zum 8. Oktober 2018 stattgefunden haben.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Verwenden Sie den -Parameter, um den Migrationsstatus für einen bestimmten Benutzer `Identity` zu überprüfen. Beispielsweise gibt der folgende Befehl den Status des Benutzers ashaw@contoso.com zurück:

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Wenn fehlgeschlagene Migrationen auftreten, ergreifen Sie Maßnahmen, um diese Probleme so schnell wie möglich zu beheben, da personen sich erst dann in die von diesen Benutzern organisierten Besprechungen einwählen können, wenn Sie sie behoben haben. Wenn `Get-CsMeetingMigrationStatus` Migrationen in einem fehlgeschlagenen Zustand gezeigt werden, führen Sie die folgenden Schritte aus:
 
1. Stellen Sie fest, welche Benutzer betroffen sind. Führen Sie den folgenden Befehl aus, um die Liste der betroffenen Benutzer und den spezifischen gemeldeten Fehler zu erhalten:

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. Führen Sie für jeden betroffenen Benutzer das Tool für die Besprechungsmigration aus, um die Besprechungen manuell zu migrieren.

3. Wenn die Migration auch mit dem Meeting Migration Tool nicht funktioniert, haben Sie zwei Möglichkeiten:

    - Weisen Sie die Benutzer an, neue Skype-Besprechungen zu erstellen.
    - [Wenden Sie sich an den Support](/microsoft-365/Admin/contact-support-for-business-products).


### <a name="enabling-and-disabling-mms"></a>Aktivieren und Deaktivieren von MMS

MMS ist standardmäßig für alle Organisationen aktiviert, kann aber wie folgt deaktiviert werden:

- Deaktivieren Sie vollständig für den Mandanten. 
- Deaktivieren Sie nur für Änderungen im Zusammenhang mit Audiokonferenzen. In diesem Fall wird MMS weiterhin ausgeführt, wenn ein Benutzer aus der lokalen Cloud migriert wird oder wenn Sie den TeamsOnly-Modus oder den SfBWithTeamsCollabAndMeetings-Modus in `TeamsUpgradePolicy` gewähren.

Sie können z. B. alle Besprechungen manuell migrieren oder MMS vorübergehend deaktivieren, während Sie wesentliche Änderungen an den Audiokonferenzeinstellungen für Ihre Organisation vornehmen.

Führen Sie den folgenden Befehl aus, um zu sehen, ob MMS für Ihre Organisation aktiviert ist. MMS ist aktiviert, wenn `MeetingMigrationEnabled` der Parameter `$true` ist.
```PowerShell
Get-CsTenantMigrationConfiguration
```
Verwenden Sie den Befehl, um MMS vollständig zu aktivieren oder `Set-CsTenantMigrationConfiguration` zu deaktivieren. Führen Sie zum Deaktivieren von MMS beispielsweise den folgenden Befehl aus:

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Wenn MMS in der Organisation aktiviert ist und Sie überprüfen möchten, ob es für Audiokonferenzupdates aktiviert ist, überprüfen Sie den Wert des Parameters in der `AutomaticallyMigrateUserMeetings` Ausgabe `Get-CsOnlineDialInConferencingTenantSettings` von. Verwenden Sie zum Aktivieren oder Deaktivieren von MMS für Audiokonferenzen `Set-CsOnlineDialInConferencingTenantSettings` . Führen Sie beispielsweise den folgenden Befehl aus, um MMS für Audiokonferenzen zu deaktivieren:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)