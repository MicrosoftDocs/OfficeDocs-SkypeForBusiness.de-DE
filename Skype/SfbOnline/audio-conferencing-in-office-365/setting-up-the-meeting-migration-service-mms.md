---
title: Verwenden des Meeting Migration Service (MMS)
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) ist ein Dienst, der im Hintergrund ausgeführt wird und Skype for Business und Microsoft Teams für Benutzer automatisch aktualisiert.
ms.openlocfilehash: 9bd76037c59bcccf2f7be16ae79cab968ee6303a
ms.sourcegitcommit: 7b704ba3c9d2db9740c4aad9e5a75a830bbbb63b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2021
ms.locfileid: "60148926"
---
# <a name="using-the-meeting-migration-service-mms"></a>Verwenden des Meeting Migration Service (MMS)

Meeting Migration Service (MMS) ist ein Dienst, der die vorhandenen Besprechungen eines Benutzers in den folgenden Szenarien aktualisiert:

- Wenn ein Benutzer von der lokalen Migration in die Cloud migriert wird.
- Wenn ein Administrator eine Änderung an den Audiokonferenzeinstellungen des Benutzers vor nimmt 
- Wenn ein Onlinebenutzer nur auf "Teams" aktualisiert wird oder wenn der Modus eines Benutzers in TeamsUpgradePolicy auf SfBwithTeamsCollabAndMeetings festgelegt ist
- Wenn Sie PowerShell verwenden 


MmS wird standardmäßig in jedem dieser Fälle automatisch ausgelöst. Darüber hinaus können Administratoren ein PowerShell-Cmdlet verwenden, um die Besprechungsmigration für einen bestimmten Benutzer manuell auszulösen.


**Einschränkungen:** Der Besprechungsmigrationsdienst kann nicht verwendet werden, wenn eine der folgenden Bedingungen zutreffen:

- Das Postfach des Benutzers wird lokal Exchange gehostet.
- Der Benutzer wird aus der Cloud in eine lokale Skype for Business Server migriert.


## <a name="how-mms-works"></a>Funktionsweise von MMS

Wenn MMS für einen bestimmten Benutzer ausgelöst wird, wird eine Migrationsanforderung für den Benutzer in einer Warteschlange platziert. Um Rennbedingungen zu vermeiden, wird die Anforderung in der Warteschlange absichtlich erst verarbeitet, wenn mindestens 90 Minuten vergangen sind. Nachdem MMS die Anforderung verarbeitet hat, führt es die folgenden Aufgaben aus:

1. Es durchsucht das Postfach dieses Benutzers nach allen vorhandenen, von diesem Benutzer organisierten und in der Zukunft geplanten Besprechungen.
2. Basierend auf den Informationen im Postfach des Benutzers aktualisiert oder plant es neue Besprechungen in Teams für diesen Benutzer, je nach genauem Szenario.
3. In der E-Mail-Nachricht ersetzt er den Online-Besprechungsblock in den Besprechungsdetails.
4. Die aktualisierte Version dieser Besprechung wird im Namen des Besprechungsorganisators an alle Besprechungsempfänger gesendet. Besprechungs-Eingeladene erhalten eine Besprechungsaktualisierung mit aktualisierten Besprechungskoordinaten in ihrer E-Mail. 

    ![Der Besprechungsblock, der von MMS aktualisiert wird.](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Ab dem Zeitpunkt, zu dem MMS ausgelöst wird, dauert es in der Regel ungefähr 2 Stunden, bis die Besprechungen des Benutzers migriert wurden. Wenn der Benutzer jedoch eine große Anzahl von Besprechungen hat, kann dies länger dauern. Wenn mms beim Migrieren einer oder von mehreren Besprechungen für den Benutzer auf einen Fehler stößt, wird es in regelmäßigen Abständen bis zu 9 Mal im Zeitraum von 24 Stunden wiederholen.

**Hinweise:**

- MMS ersetzt alles im Informationsblock für die Onlinebesprechung, wenn eine Besprechung migriert wird. Wenn daher ein Benutzer diesen Block bearbeitet hat, werden seine Änderungen überschrieben. Alle Inhalte, die sich in den Besprechungsdetails außerhalb des Informationsblocks der Onlinebesprechung befinden, sind nicht betroffen. Dies bedeutet, dass alle an die Besprechungs-Einladung angefügten Dateien weiterhin enthalten sind. 
- Es werden nur die Skype for Business- oder Microsoft Teams-Besprechungen migriert, die durch Klicken auf die Schaltfläche **Skype-Besprechung hinzufügen** in Outlook im Web oder über das Skype-Besprechungs-Add-In für Outlook geplant wurden. Wenn ein Benutzer die Skype-Online-Besprechungsinformationen von einer Besprechung in eine neue Besprechung kopiert und einfüge, wird diese neue Besprechung nicht aktualisiert, da es im ursprünglichen Dienst keine Besprechung gibt.
- Besprechungsinhalte, die erstellt oder an die Besprechung angehängt wurden (Whiteboards, Umfragen und so weiter), werden nach der Ausgeführten von MMS nicht beibehalten. Wenn Ihre Besprechungsorganisatoren im Voraus Inhalte an Besprechungen angehängt haben, müssen diese Inhalte nach der Ausführung von MMS erneut erstellt werden.
- Der Link zu freigegebenen Besprechungsnotizen im Kalenderelement und von innerhalb der Skype-Besprechung wird ebenfalls überschrieben. Beachten Sie, dass die in den Besprechungen OneNote gespeicherten Besprechungsnotizen weiterhin dort gespeichert sind. es ist nur der Link zu den freigegebenen Notizen, der überschrieben wird.
- Besprechungen mit mehr als 250 Teilnehmern (einschließlich des Organisators) werden nicht migriert.
- Einige UNICODE-Zeichen im Textkörper der Einladung werden möglicherweise fälschlicherweise auf eines der folgenden Sonderzeichen aktualisiert: ï, ¿, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Auslösen von MMS für einen Benutzer

In diesem Abschnitt wird beschrieben, was passiert, wenn MMS in jedem der folgenden Fälle ausgelöst wird:

- Wenn ein Benutzer aus der lokalen Migration in die Cloud migriert wird
- Wenn ein Administrator eine Änderung an den Audiokonferenzeinstellungen des Benutzers vor nimmt 
- Wenn der Modus des Benutzers in TeamsUpgradePolicy entweder auf TeamsOnly oder SfBWithTeamsCollabAndMeetings festgelegt ist (mithilfe von Powershell oder dem Teams Admin Portal)
- Wenn Sie das PowerShell-Cmdlet verwenden, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Aktualisieren von Besprechungen beim Verschieben eines lokalen Benutzers in die Cloud

Dies ist das häufigste Szenario, in dem MMS für einen reibungslosen Übergang für Ihre Benutzer sorgt. Ohne Besprechungsmigration würden von einem Benutzer in einer lokalen Skype for Business Server organisierte Besprechungen nicht mehr funktionieren, sobald der Benutzer online verschoben wurde. Wenn Sie daher die lokalen Administratortools (entweder oder die Administratorsteuerung) verwenden, um einen Benutzer in die Cloud zu verschieben, werden vorhandene Besprechungen automatisch in die Cloud verschoben und in `Move-CsUser` TeamsOnly konvertiert. 

Wenn dem Benutzer eine Lizenz für Audiokonferenzen zugewiesen wurde, bevor er in die Cloud verschoben wird, werden die Besprechungen mit Einwahlkoordinaten erstellt. Wenn Sie einen Benutzer aus der lokalen Cloud in die Cloud verschieben und beabsichtigen, audio conferencing (Audiokonferenz) zu verwenden, sollten Sie zuerst die Audiokonferenz zuweisen, bevor Sie den Benutzer verschieben, damit nur eine Besprechungsmigration ausgelöst wird.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aktualisieren von Besprechungen, wenn sich die Audiokonferenzeinstellungen eines Benutzers ändern

In den folgenden Fällen aktualisiert MMS vorhandene Skype for Business und Microsoft Teams, um Einwahlkoordinaten hinzuzufügen, zu entfernen oder zu ändern:

- Wenn Sie einem Benutzer eine Dienstlizenz für Microsoft-Audiokonferenzen zuweisen oder entfernen und dieser Benutzer nicht für einen Drittanbieter für Audiokonferenzen aktiviert ist.
- Wenn Sie den Audiokonferenzanbieter eines Benutzers von einem anderen Anbieter in Microsoft ändern, vorausgesetzt, dem Benutzer wird eine Microsoft-Lizenz für Audiokonferenzen zugewiesen. Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Audiokonferenzanbieter.](./assign-microsoft-as-the-audio-conferencing-provider.md) Beachten Sie außerdem, dass die Unterstützung für Drittanbieter für Audiokonferenzen [ACP] wie zuvor angekündigt am 1. April 2019 für das Ende des Lebenszyklus [geplant ist.](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)
- Wenn Sie Audiokonferenzen für einen Benutzer aktivieren oder deaktivieren.
- Wenn Sie die Konferenz-ID für einen Benutzer ändern oder zurücksetzen, der für die Verwendung öffentlicher Besprechungen konfiguriert ist.
- Wenn Sie den Benutzer zu einer neuen Audiokonferenzbrücke verschieben
- Wenn die Nummer einer Audiokonferenzbrücke nicht zugewiesen wird. Dies ist ein komplexes Szenario, das zusätzliche Schritte erfordert. Weitere Informationen finden Sie unter [Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke.](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)

Nicht alle Änderungen an den Audiokonferenzeinstellungen eines Benutzers lösen MMS aus. Insbesondere die folgenden beiden Änderungen führen nicht dazu, dass MMS Besprechungen aktualisiert:

- Ändern der SIP-Adresse für den Besprechungsorganisator (entweder des SIP-Benutzernamens oder der SIP-Domäne)
- Wenn Sie die Besprechungs-URL Ihrer Organisation mit dem Befehl `Update-CsTenantMeetingUrl` ändern.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Aktualisieren von Besprechungen beim Zuweisen von TeamsUpgradePolicy

Besprechungsmigration wird standardmäßig automatisch ausgelöst, wenn einem Benutzer eine Instanz von mit `TeamsUpgradePolicy` oder `mode=TeamsOnly` gewährt `mode= SfBWithTeamsCollabAndMeetings` wird. Wenn Sie Besprechungen nicht migrieren möchten, wenn Sie einen dieser Modi gewähren, geben Sie in an `MigrateMeetingsToTeams $false` (wenn Sie PowerShell verwenden), oder deaktivieren Sie das Kontrollkästchen zum Migrieren von Besprechungen beim Festlegen des Koexistenzmodus eines Benutzers (bei Verwendung des `Grant-CsTeamsUpgradePolicy` Teams-Verwaltungsportals).

Beachten Sie außerdem Folgendes:

- Die Besprechungsmigration wird nur aufgerufen, wenn sie für `TeamsUpgradePolicy` einen bestimmten Benutzer gewährt wird. Wenn Sie die `TeamsUpgradePolicy` Besprechung `mode=TeamsOnly` mit oder `mode=SfBWithTeamsCollabAndMeetings` *mandantenweit* gewähren, wird die Besprechungsmigration nicht aufgerufen.
- Einem Benutzer kann der TeamsOnly-Modus nur dann gewährt werden, wenn der Benutzer online zu Hause ist. Benutzer, die lokal behaust sind, müssen wie zuvor beschrieben `Move-CsUser` mithilfe von verschoben werden.
- Wenn ein anderer Modus als TeamsOnly oder SfBWithTeamsCollabAndMeetings verwendet wird, werden vorhandene Teams-Besprechungen nicht in Skype for Business konvertiert.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Manuelles Auslösen der Besprechungsmigration über das PowerShell-Cmdlet

Zusätzlich zu den automatischen Besprechungsmigrationen können Administratoren die Besprechungsmigration manuell für einen Benutzer auslösen, indem sie das Cmdlet `Start-CsExMeetingMigration` ausführen. Dieses Cmdlet warteschlanget eine Migrationsanforderung für den angegebenen Benutzer.  Zusätzlich zum erforderlichen Parameter übernimmt er zwei optionale Parameter, und , mit denen Sie angeben können, wie `Identity` `SourceMeetingType` `TargetMeetingType` Besprechungen migriert werden sollen:

**TargetMeetingType:**

- Mit `TargetMeetingType Current` wird angegeben, dass Skype for Business Besprechungen Skype for Business bleiben und Teams Besprechungen Teams bleiben. Die Audiokonferenzkoordinaten können jedoch geändert werden, und alle lokalen Skype for Business-Besprechungen werden nach Skype for Business Online migriert. Dies ist der Standardwert für TargetMeetingType.
- Mit wird angegeben, dass vorhandene Besprechungen nach Teams migriert werden müssen, unabhängig davon, ob die Besprechung online oder lokal in Skype for Business gehostet wird und ob Audiokonferenzaktualisierungen erforderlich `TargetMeetingType Teams` sind. 

**SourceMeetingType:**
- Die `SourceMeetingType SfB` Verwendung von gibt an, Skype for Business Besprechungen (lokal oder online) aktualisiert werden sollen.
- Die `SourceMeetingType Teams` Verwendung von gibt an, dass Teams Besprechungen aktualisiert werden sollen.
- Die `SourceMeetingType All` Verwendung von gibt an, Skype for Business Besprechungen und Teams Besprechungen aktualisiert werden sollen. Dies ist der Standardwert für SourceMeetingType.
    

Das folgende Beispiel zeigt, wie sie die Besprechungsmigration für Benutzerbesprechungen initiieren ashaw@contoso.com sodass alle Besprechungen zu einem Teams:

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Verwalten von MMS

Mithilfe Windows PowerShell können Sie den Status laufender Migrationen überprüfen, die Besprechungsmigration manuell auslösen und die Migration insgesamt deaktivieren. 

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
- Um alle Details aller Migrationen innerhalb eines bestimmten Zeitraums anzuzeigen, verwenden Sie die Parameter `StartTime` und `EndTime` . Der folgende Befehl gibt z. B. vollständige Details zu allen Migrationen zurück, die vom 1. Oktober 2018 bis zum 8. Oktober 2018 stattgefunden haben.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Verwenden Sie den -Parameter, um den Migrationsstatus für einen bestimmten Benutzer `Identity` zu überprüfen. Beispielsweise gibt der folgende Befehl den Status des Benutzers ashaw@contoso.com zurück:

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Wenn fehlgeschlagene Migrationen auftreten, ergreifen Sie eine Maßnahme, um diese Probleme so bald wie möglich zu beheben, da sich die Benutzer erst bei den von diesen Benutzern organisierten Besprechungen einwählen können, nachdem Sie die Probleme behoben haben. Wenn `Get-CsMeetingMigrationStatus` bei Migrationen ein Fehler auftritt, führen Sie die folgenden Schritte aus:
 
1. Stellen Sie fest, welche Benutzer betroffen sind. Führen Sie den folgenden Befehl aus, um die Liste der betroffenen Benutzer und den spezifischen gemeldeten Fehler zu erhalten:

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. Überprüfen Sie für jeden betroffenen Benutzer den Wert der LastMessage-Eigenschaft, um zu ermitteln, warum die Besprechungsmigration fehlgeschlagen ist und welche Behebungsmaßnahme zu ergreifen ist. Sobald eine Behebungsmaßnahme durchgeführt wurde, lösen Sie die Besprechungsmigration für die betroffenen Benutzer mithilfe der `Start-CsExMeetingMigration` PowerShell-Cmldet erneut aus, wie oben beschrieben. 

3. Wenn die Migration immer noch nicht funktioniert, haben Sie zwei Möglichkeiten:

    - Weisen Sie die Benutzer an, neue Skype-Besprechungen zu erstellen.
    - [Wenden Sie sich an den Support](/microsoft-365/Admin/contact-support-for-business-products).

Das Cmdlet kann verwendet werden, um den Status von Migrationen abzurufen, die innerhalb der letzten `Get-CsMeetingMigrationStatus` 150 Tage ausgelöst wurden. Datensätze für Migrationen, die älter als 150 Tage sind, werden aus dem System gelöscht.

### <a name="enabling-and-disabling-mms"></a>Aktivieren und Deaktivieren von MMS

MMS ist standardmäßig für alle Organisationen aktiviert, kann aber wie folgt deaktiviert werden:

- Wird vollständig für den Mandanten deaktiviert. 
- Nur für Änderungen im Zusammenhang mit Audiokonferenzen deaktivieren. In diesem Fall wird MMS weiterhin ausgeführt, wenn ein Benutzer aus der lokalen Bereitstellung in die Cloud migriert wird oder wenn Sie den TeamsOnly-Modus oder sfBWithTeamsCollabAndMeetings-Modus in `TeamsUpgradePolicy` gewähren.

Sie können z. B. alle Besprechungen manuell migrieren oder MMS vorübergehend deaktivieren, während Sie grundlegende Änderungen an den Audiokonferenzeinstellungen für Ihre Organisation vornehmen.

Um zu sehen, ob MMS für Ihre Organisation aktiviert ist, führen Sie den folgenden Befehl aus. MMS ist aktiviert, wenn der `MeetingMigrationEnabled` Parameter `$true` ist.
```PowerShell
Get-CsTenantMigrationConfiguration
```

Wenn MMS in der Organisation aktiviert ist und Sie überprüfen möchten, ob MMS für Audiokonferenzupdates aktiviert ist, überprüfen Sie den Wert des -Parameters in der `AutomaticallyMigrateUserMeetings` Ausgabe von `Get-CsOnlineDialInConferencingTenantSettings` . Verwenden Sie zum Aktivieren oder Deaktivieren von MMS für Audiokonferenzen `Set-CsOnlineDialInConferencingTenantSettings` . Führen Sie z. B. den folgenden Befehl aus, um MMS für Audiokonferenzen zu deaktivieren:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
