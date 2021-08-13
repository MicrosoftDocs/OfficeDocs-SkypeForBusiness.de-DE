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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) ist ein Dienst, der im Hintergrund ausgeführt wird und Skype for Business und Microsoft Teams für Benutzer automatisch aktualisiert. Mit MMS brauchen die Benutzer nicht mehr Meeting Migration Tool auszuführen, um ihre Skype for Business- und Microsoft Teams-Besprechungen zu aktualisieren.
ms.openlocfilehash: 71fefa3986d9daf3a9eb7cd1403ba9490cbbf7ff687853a7876f05cd0a75eed1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298875"
---
# <a name="using-the-meeting-migration-service-mms"></a>Verwenden des Meeting Migration Service (MMS)

Meeting Migration Service (MMS) ist ein Dienst, der die vorhandenen Besprechungen eines Benutzers in den folgenden Szenarien aktualisiert:

- Wenn ein Benutzer aus der lokalen Cloud in die Cloud migriert wird (ob online Skype for Business oder TeamsOnly).
- Wenn ein Administrator eine Änderung an den Audiokonferenzeinstellungen des Benutzers vor nimmt 
- Wenn ein Onlinebenutzer nur auf Teams aktualisiert wird oder wenn der Modus eines Benutzers in TeamsUpgradePolicy auf SfBwithTeamsCollabAndMeetings festgelegt ist
- Wenn Sie PowerShell verwenden 


STANDARDMÄßIG wird MMS in jedem dieser Fälle automatisch ausgelöst, obwohl Administratoren mms auf Mandantenebene deaktivieren können. Darüber hinaus können Administratoren ein PowerShell-Cmdlet verwenden, um die Besprechungsmigration für einen bestimmten Benutzer manuell auszulösen.


**Einschränkungen:** Der Besprechungsmigrationsdienst kann nicht verwendet werden, wenn eine der folgenden Bedingungen zutreffen:

- Das Postfach des Benutzers wird lokal Exchange gehostet.
- Der Benutzer wird aus der Cloud in eine lokale Skype for Business Server migriert.


## <a name="how-mms-works"></a>Funktionsweise von MMS

Wenn MMS für einen bestimmten Benutzer ausgelöst wird, wird eine Migrationsanforderung für den Benutzer in einer Warteschlange platziert. Um Rennbedingungen zu vermeiden, wird die Anforderung in der Warteschlange absichtlich erst verarbeitet, wenn mindestens 90 Minuten vergangen sind. Nachdem MMS die Anforderung verarbeitet hat, führt es die folgenden Aufgaben aus:

1. Es durchsucht das Postfach dieses Benutzers nach allen vorhandenen, von diesem Benutzer organisierten und in der Zukunft geplanten Besprechungen.
2. Basierend auf den Informationen im Postfach des Benutzers aktualisiert oder plant er neue Besprechungen entweder in Teams oder Skype for Business Online für diesen Benutzer, je nach genauem Szenario.
3. In der E-Mail-Nachricht ersetzt er den Online-Besprechungsblock in den Besprechungsdetails.
4. Die aktualisierte Version dieser Besprechung wird im Namen des Besprechungsorganisators an alle Besprechungsempfänger gesendet. Besprechungs-Eingeladene erhalten eine Besprechungsaktualisierung mit aktualisierten Besprechungskoordinaten in ihrer E-Mail. 

    ![Der Besprechungsblock, der von MMS aktualisiert wird.](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Ab dem Zeitpunkt, zu dem MMS ausgelöst wird, dauert es in der Regel ungefähr 2 Stunden, bis die Besprechungen des Benutzers migriert wurden. Wenn der Benutzer jedoch eine große Anzahl von Besprechungen hat, kann dies länger dauern. Wenn mms beim Migrieren einer oder von mehreren Besprechungen für den Benutzer auf einen Fehler stößt, wird es in regelmäßigen Abständen bis zu 9 Mal im Zeitraum von 24 Stunden wiederholen.

**Hinweise:**

- MMS ersetzt alles im Informationsblock für die Onlinebesprechung, wenn eine Besprechung migriert wird. Wenn daher ein Benutzer diesen Block bearbeitet hat, werden seine Änderungen überschrieben. Alle Inhalte, die sich in den Besprechungsdetails außerhalb des Informationsblocks der Onlinebesprechung befinden, sind nicht betroffen. Dies bedeutet, dass alle an die Besprechungs-Einladung angefügten Dateien weiterhin enthalten sind. 
- Es werden nur die Skype for Business- oder Microsoft Teams-Besprechungen migriert, die durch Klicken auf die Schaltfläche **Skype-Besprechung hinzufügen** in Outlook im Web oder über das Skype-Besprechungs-Add-In für Outlook geplant wurden. Wenn ein Benutzer die Skype-Online-Besprechungsinformationen von einer Besprechung in eine neue Besprechung kopiert und einfüge, wird diese neue Besprechung nicht aktualisiert, da keine Besprechung im ursprünglichen Dienst besteht.
- Besprechungsinhalte, die erstellt oder an die Besprechung angehängt wurden (Whiteboards, Umfragen und so weiter), werden nach der Ausgeführten von MMS nicht beibehalten. Wenn Ihre Besprechungsorganisatoren im Voraus Inhalte an Besprechungen angehängt haben, müssen diese Inhalte nach der Ausführung von MMS erneut erstellt werden.
- Der Link zu freigegebenen Besprechungsnotizen im Kalenderelement und von innerhalb der Skype-Besprechung wird ebenfalls überschrieben. Beachten Sie, dass die in der Besprechungs OneNote gespeicherten Besprechungsnotizen weiterhin dort gespeichert sind. es ist nur der Link zu den freigegebenen Notizen, der überschrieben wird.
- Besprechungen mit mehr als 250 Teilnehmern (einschließlich des Organisators) werden nicht migriert.
- Einige UNICODE-Zeichen im Textkörper der Einladung werden möglicherweise fälschlicherweise auf eines der folgenden Sonderzeichen aktualisiert: ï, ¿, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Auslösen von MMS für einen Benutzer

In diesem Abschnitt wird beschrieben, was passiert, wenn MMS in jedem der folgenden Fälle ausgelöst wird:

- Wenn ein Benutzer aus der lokalen Migration in die Cloud migriert wird
- Wenn ein Administrator eine Änderung an den Audiokonferenzeinstellungen des Benutzers vor nimmt 
- Wenn der Modus des Benutzers in TeamsUpgradePolicy entweder auf TeamsOnly oder SfBWithTeamsCollabAndMeetings festgelegt ist (mithilfe von Powershell oder dem Teams Admin Portal)
- Wenn Sie das PowerShell-Cmdlet verwenden, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Aktualisieren von Besprechungen beim Verschieben eines lokalen Benutzers in die Cloud

Dies ist das häufigste Szenario, in dem MMS für einen reibungslosen Übergang für Ihre Benutzer sorgt. Ohne Besprechungsmigration würden von einem Benutzer in einer lokalen Skype for Business Server organisierte Besprechungen nicht mehr funktionieren, sobald der Benutzer online verschoben wurde. Wenn Sie daher die lokalen Administratortools (entweder oder die Systemsteuerung der Administratoren) verwenden, um einen Benutzer in die Cloud zu verschieben, werden vorhandene Besprechungen automatisch wie folgt in die `Move-CsUser` Cloud verschoben:

- Wenn der Wechsel angegeben ist, werden Besprechungen direkt in den Teams und der Benutzer befindet sich `MoveToTeams` `Move-CsUser` im TeamsOnly-Modus. Die Verwendung dieses Schalters erfordert Skype for Business Server 2015 mit CU8 oder höher. Diese Benutzer können weiterhin an jeder Besprechung Skype for Business, zu der sie möglicherweise eingeladen werden, entweder über den Skype for Business-Client oder die Skype-Besprechung-App.
- Andernfalls werden Besprechungen nach Skype for Business Online migriert.

In beiden Fällen werden Besprechungen mit Einwahlkoordinaten erstellt, wenn dem Benutzer vor dem Umzug in die Cloud eine Lizenz für Audiokonferenzen zugewiesen wurde. Wenn Sie einen Benutzer aus der lokalen Cloud in die Cloud verschieben und beabsichtigen, audio conferencing (Audiokonferenz) zu verwenden, sollten Sie zuerst die Audiokonferenz zuweisen, bevor Sie den Benutzer verschieben, damit nur eine Besprechungsmigration ausgelöst wird.


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

Besprechungsmigration wird standardmäßig automatisch ausgelöst, wenn einem Benutzer eine Instanz von mit `TeamsUpgradePolicy` oder `mode=TeamsOnly` gewährt `mode= SfBWithTeamsCollabAndMeetings` wird. Wenn Sie Besprechungen nicht migrieren möchten, wenn Sie einen dieser Modi gewähren, geben Sie in an `MigrateMeetingsToTeams $false` (wenn Sie PowerShell verwenden), oder deaktivieren Sie das Kontrollkästchen, um Besprechungen zu migrieren, wenn Sie den Koexistenzmodus eines Benutzers festlegen (bei Verwendung des `Grant-CsTeamsUpgradePolicy` Teams-Verwaltungsportals).

Beachten Sie außerdem Folgendes:

- Die Besprechungsmigration wird nur aufgerufen, wenn Sie die `TeamsUpgradePolicy` Genehmigung für einen bestimmten Benutzer erteilen. Wenn Sie die `TeamsUpgradePolicy` Besprechung `mode=TeamsOnly` mit oder `mode=SfBWithTeamsCollabAndMeetings` *mandantenweit* gewähren, wird die Besprechungsmigration nicht aufgerufen.
- Einem Benutzer kann der TeamsOnly-Modus nur dann gewährt werden, wenn der Benutzer online zu Hause ist. Benutzer, die lokal behaust sind, müssen wie zuvor `Move-CsUser` beschrieben mithilfe von verschoben werden.
- Wenn ein anderer Modus als TeamsOnly oder SfBWithTeamsCollabAndMeetings verwendet wird, werden vorhandene Teams-Besprechungen nicht in Skype for Business konvertiert.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Manuelles Auslösen der Besprechungsmigration über das PowerShell-Cmdlet

Zusätzlich zu den automatischen Besprechungsmigrationen können Administratoren die Besprechungsmigration manuell für einen Benutzer auslösen, indem sie das Cmdlet `Start-CsExMeetingMigration` ausführen. Dieses Cmdlet warteschlanget eine Migrationsanforderung für den angegebenen Benutzer.  Zusätzlich zum erforderlichen Parameter übernimmt er zwei optionale Parameter, und , mit denen Sie angeben können, wie `Identity` `SourceMeetingType` `TargetMeetingType` Besprechungen migriert werden sollen:

**TargetMeetingType:**

- Mit `TargetMeetingType Current` wird angegeben, dass Skype for Business Besprechungen Skype for Business bleiben und Teams Besprechungen Teams bleiben. Möglicherweise werden jedoch die Audiokonferenzkoordinaten geändert, und alle lokalen Skype for Business-Besprechungen werden nach Skype for Business Online migriert. Dies ist der Standardwert für TargetMeetingType.
- Mit wird angegeben, dass vorhandene Besprechungen nach Teams migriert werden müssen, unabhängig davon, ob die Besprechung online oder lokal in Skype for Business gehostet wird und ob Audiokonferenzaktualisierungen erforderlich `TargetMeetingType Teams` sind. 

**SourceMeetingType:**
- Die `SourceMeetingType SfB` Verwendung von gibt an, Skype for Business Besprechungen (lokal oder online) aktualisiert werden sollen.
- Die `SourceMeetingType Teams` Verwendung von gibt an, dass Teams Besprechungen aktualisiert werden sollen.
- Die `SourceMeetingType All` Verwendung von gibt an, Skype for Business Besprechungen und Teams Besprechungen aktualisiert werden sollen. Dies ist der Standardwert für SourceMeetingType.
    

Das folgende Beispiel zeigt, wie sie die Besprechungsmigration für Benutzergruppen initiieren ashaw@contoso.com sodass alle Besprechungen nach Teams:

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
2. Führen Sie für jeden betroffenen Benutzer Meeting Migration Tool aus, um die Besprechungen manuell zu migrieren.

3. Wenn die Migration auch mit dem Meeting Migration Tool nicht funktioniert, haben Sie zwei Möglichkeiten:

    - Weisen Sie die Benutzer an, neue Skype-Besprechungen zu erstellen.
    - [Wenden Sie sich an den Support](/microsoft-365/Admin/contact-support-for-business-products).


### <a name="enabling-and-disabling-mms"></a>Aktivieren und Deaktivieren von MMS

MMS ist standardmäßig für alle Organisationen aktiviert, kann aber wie folgt deaktiviert werden:

- Wird vollständig für den Mandanten deaktiviert. 
- Nur für Änderungen im Zusammenhang mit Audiokonferenzen deaktivieren. In diesem Fall wird MMS weiterhin ausgeführt, wenn ein Benutzer aus der lokalen Bereitstellung in die Cloud migriert wird oder wenn Sie den TeamsOnly-Modus oder sfBWithTeamsCollabAndMeetings-Modus in `TeamsUpgradePolicy` gewähren.

Sie können z. B. alle Besprechungen manuell migrieren oder MMS vorübergehend deaktivieren, während Sie grundlegende Änderungen an den Audiokonferenzeinstellungen für Ihre Organisation vornehmen.

Um zu sehen, ob MMS für Ihre Organisation aktiviert ist, führen Sie den folgenden Befehl aus. MMS ist aktiviert, wenn der `MeetingMigrationEnabled` Parameter `$true` ist.
```PowerShell
Get-CsTenantMigrationConfiguration
```
Verwenden Sie den Befehl, um MMS vollständig zu aktivieren oder `Set-CsTenantMigrationConfiguration` zu deaktivieren. Führen Sie zum Deaktivieren von MMS beispielsweise den folgenden Befehl aus:

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Wenn MMS in der Organisation aktiviert ist und Sie überprüfen möchten, ob MMS für Audiokonferenzupdates aktiviert ist, überprüfen Sie den Wert des -Parameters in der `AutomaticallyMigrateUserMeetings` Ausgabe von `Get-CsOnlineDialInConferencingTenantSettings` . Verwenden Sie zum Aktivieren oder Deaktivieren von MMS für Audiokonferenzen `Set-CsOnlineDialInConferencingTenantSettings` . Führen Sie z. B. den folgenden Befehl aus, um MMS für Audiokonferenzen zu deaktivieren:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
