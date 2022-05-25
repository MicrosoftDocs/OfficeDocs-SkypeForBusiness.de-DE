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
description: Meeting Migration Service (MMS) ist ein Dienst, der im Hintergrund ausgeführt wird und automatisch Skype for Business und Microsoft Teams Besprechungen für Benutzer aktualisiert.
ms.openlocfilehash: a7e917a5b579c60ff84c3e1a5e6468a28f75faff
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671641"
---
# <a name="using-the-meeting-migration-service-mms"></a>Verwenden des Meeting Migration Service (MMS)

Der Meeting Migration Service (MMS) ist ein Dienst, der die vorhandenen Besprechungen eines Benutzers in den folgenden Szenarien aktualisiert:

- Wenn ein Benutzer von der lokalen Bereitstellung in die Cloud migriert wird.
- Wenn ein Administrator eine Änderung an den Audiokonferenzeinstellungen des Benutzers vornimmt
- Wenn ein Onlinebenutzer nur auf Teams aktualisiert wird oder wenn der Modus eines Benutzers in "TeamsUpgradePolicy" auf "SfBwithTeamsCollabAndMeetings" festgelegt ist
- Wenn Sie PowerShell verwenden

Standardmäßig wird MMS in jedem dieser Fälle automatisch ausgelöst. Darüber hinaus können Administratoren ein PowerShell-Cmdlet verwenden, um die Besprechungsmigration für einen bestimmten Benutzer manuell auszulösen.

**Einschränkungen**: Der Besprechungsmigrationsdienst kann nicht verwendet werden, wenn eine der folgenden Bedingungen zutrifft:

- Das Postfach des Benutzers wird in Exchange lokal gehostet.
- Der Benutzer wird aus der Cloud zu Skype for Business Server lokal migriert.

## <a name="how-mms-works"></a>Funktionsweise von MMS

Wenn MMS für einen bestimmten Benutzer ausgelöst wird, wird eine Migrationsanforderung für diesen Benutzer in einer Warteschlange platziert. Um rennbedingte Bedingungen zu vermeiden, wird die Anfrage in der Warteschlange absichtlich erst bearbeitet, wenn mindestens 90 Minuten vergangen sind. Nachdem MMS die Anforderung verarbeitet hat, führt es die folgenden Aufgaben aus:

1. Es durchsucht das Postfach dieses Benutzers nach allen vorhandenen Besprechungen, die von diesem Benutzer organisiert und in Der Zukunft geplant sind.
2. Basierend auf den Informationen, die im Postfach des Benutzers gefunden wurden, aktualisiert oder plant es neue Besprechungen in Teams für diesen Benutzer, je nach dem genauen Szenario.
3. In der E-Mail-Nachricht ersetzt sie den Onlinebesprechungsblock in den Besprechungsdetails.
4. Sie sendet die aktualisierte Version dieser Besprechung an alle Besprechungsempfänger im Namen des Besprechungsorganisators. Besprechungseinladungen erhalten ein Besprechungsupdate mit aktualisierten Besprechungskoordinaten in ihrer E-Mail.

    ![Der Besprechungsblock, der von MMS aktualisiert wird.](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Ab dem Zeitpunkt, zu dem MMS ausgelöst wird, dauert es in der Regel etwa 2 Stunden, bis die Besprechungen des Benutzers migriert werden. Wenn der Benutzer jedoch über eine große Anzahl von Besprechungen verfügt, kann dies länger dauern. Wenn MMS beim Migrieren einer oder mehrerer Besprechungen für den Benutzer auf einen Fehler stößt, wird er in regelmäßigen Abständen bis zu 9 Mal innerhalb von 24 Stunden wiederholt.

**Hinweise**:

- MMS ersetzt alles im Informationsblock für die Onlinebesprechung, wenn eine Besprechung migriert wird. Wenn daher ein Benutzer diesen Block bearbeitet hat, werden seine Änderungen überschrieben. Alle Inhalte, die sich in den Besprechungsdetails außerhalb des Informationsblocks der Onlinebesprechung befinden, sind nicht betroffen. Dies bedeutet, dass alle an die Besprechungseinladung angefügten Dateien weiterhin einbezogen werden.
- Es werden nur die Skype for Business- oder Microsoft Teams-Besprechungen migriert, die durch Klicken auf die Schaltfläche **Skype-Besprechung hinzufügen** in Outlook im Web oder über das Skype-Besprechungs-Add-In für Outlook geplant wurden. Wenn ein Benutzer die Skype Onlinebesprechungsinformationen aus einer Besprechung kopiert und in eine neue Besprechung einfüge, wird diese neue Besprechung nicht aktualisiert, da im ursprünglichen Dienst keine Besprechung vorhanden ist.
- Besprechungsinhalte, die erstellt oder an die Besprechung angefügt wurden (Whiteboards, Umfragen usw.), werden nach der Ausführung von MMS nicht beibehalten. Wenn Ihre Besprechungsorganisatoren im Voraus Inhalte an Besprechungen angehängt haben, müssen diese Inhalte nach der Ausführung von MMS erneut erstellt werden.
- Der Link zu freigegebenen Besprechungsnotizen im Kalenderelement und von innerhalb der Skype-Besprechung wird ebenfalls überschrieben. Beachten Sie, dass die tatsächlich in OneNote gespeicherten Besprechungsnotizen weiterhin vorhanden sind. Nur der Link zu den freigegebenen Notizen wird überschrieben.
- Besprechungen mit mehr als 250 Teilnehmern (einschließlich des Organisators) werden nicht migriert.
- Einige UNICODE-Zeichen im Textkörper der Einladung werden möglicherweise fälschlicherweise auf eines der folgenden Sonderzeichen aktualisiert: ï, ¡, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Auslösen von MMS für einen Benutzer

In diesem Abschnitt wird beschrieben, was geschieht, wenn MMS in den folgenden Fällen ausgelöst wird:

- Wenn ein Benutzer von der lokalen Bereitstellung in die Cloud migriert wird
- Wenn ein Administrator eine Änderung an den Audiokonferenzeinstellungen des Benutzers vornimmt
- Wenn der Modus des Benutzers in "TeamsUpgradePolicy" auf "TeamsOnly" oder "SfBWithTeamsCollabAndMeetings" festgelegt ist (entweder mit PowerShell oder dem Teams Admin Portal)
- Wenn Sie das PowerShell-Cmdlet verwenden, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Aktualisieren von Besprechungen beim Verschieben eines lokalen Benutzers in die Cloud

Dies ist das häufigste Szenario, in dem MMS zu einem reibungsloseren Übergang für Ihre Benutzer beiträgt. Ohne Besprechungsmigration würden vorhandene Besprechungen, die von einem Benutzer in Skype for Business Server lokal organisiert wurden, nicht mehr funktionieren, sobald der Benutzer online verschoben wurde. Wenn Sie daher die lokalen Administratortools (entweder `Move-CsUser` oder die Admin Systemsteuerung) verwenden, um einen Benutzer in die Cloud zu verschieben, werden vorhandene Besprechungen automatisch in die Cloud verschoben und in TeamsOnly konvertiert.

Wenn dem Benutzer eine Audiokonferenz Lizenz zugewiesen wurde, bevor er in die Cloud verschoben wird, werden die Besprechungen mit Einwahlkoordinaten erstellt. Wenn Sie einen Benutzer aus der lokalen Umgebung in die Cloud verschieben und beabsichtigen, dass dieser Benutzer Audiokonferenz verwendet, sollten Sie die Audiokonferenz zuerst zuweisen, bevor Sie den Benutzer verschieben, sodass nur eine Besprechungsmigration ausgelöst wird.

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aktualisieren von Besprechungen, wenn sich die Audiokonferenzeinstellungen eines Benutzers ändern

In den folgenden Fällen aktualisiert MMS vorhandene Skype for Business und Microsoft Teams Besprechungen, um Einwahlkoordinaten hinzuzufügen, zu entfernen oder zu ändern:

- Wenn Sie einem Benutzer eine Microsoft Audiokonferenz-Dienstlizenz zuweisen oder entfernen, und dieser Benutzer nicht für einen Drittanbieter für Audiokonferenzen aktiviert ist.
- Wenn Sie den Audiokonferenzanbieter eines Benutzers von einem anderen Anbieter in Microsoft ändern, vorausgesetzt, dem Benutzer wird eine Microsoft Audiokonferenz-Lizenz zugewiesen. Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Audiokonferenzanbieter](./assign-microsoft-as-the-audio-conferencing-provider.md). Beachten Sie außerdem, dass die Unterstützung für Audiokonferenzanbieter von Drittanbietern (ACP) wie [bereits angekündigt](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md) am 1. April 2019 für das Ende des Lebenszyklus geplant ist.
- Wenn Sie Audiokonferenzen für einen Benutzer aktivieren oder deaktivieren.
- Wenn Sie die Konferenz-ID für einen Benutzer ändern oder zurücksetzen, der für die Verwendung öffentlicher Besprechungen konfiguriert ist.
- Wenn Sie den Benutzer zu einer neuen Audiokonferenzbrücke verschieben
- Wenn eine Telefonnummer von einer Audiokonferenzbrücke nicht zugewiesen ist. Dies ist ein komplexes Szenario, das zusätzliche Schritte erfordert. Weitere Informationen finden Sie unter [Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

Nicht alle Änderungen an den Audiokonferenzeinstellungen eines Benutzers lösen MMS aus. Insbesondere die folgenden beiden Änderungen führen nicht dazu, dass MMS Besprechungen aktualisiert:

- Ändern der SIP-Adresse für den Besprechungsorganisator (entweder des SIP-Benutzernamens oder der SIP-Domäne)
- Wenn Sie die Besprechungs-URL Ihrer Organisation mithilfe des `Update-CsTenantMeetingUrl` Befehls ändern.

### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Aktualisieren von Besprechungen beim Zuweisen von TeamsUpgradePolicy

Standardmäßig wird die Besprechungsmigration automatisch ausgelöst, wenn einem Benutzer eine Instanz von `TeamsUpgradePolicy` mit `mode=TeamsOnly` oder `mode= SfBWithTeamsCollabAndMeetings`gewährt wird. Wenn Sie Besprechungen nicht migrieren möchten, wenn Sie einen dieser Modi gewähren, geben Sie `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` (bei Verwendung von PowerShell) das Kontrollkästchen zum Migrieren von Besprechungen an, wenn Sie den Koexistenzmodus eines Benutzers festlegen (wenn Sie das Teams Admin-Portal verwenden).

Beachten Sie außerdem Folgendes:

- Die Besprechungsmigration wird nur aufgerufen, wenn Sie eine Genehmigung `TeamsUpgradePolicy` für einen bestimmten Benutzer erteilen. Wenn Sie die Besprechung mit `mode=TeamsOnly` oder `mode=SfBWithTeamsCollabAndMeetings` auf *mandantenweiter* Basis gewähren`TeamsUpgradePolicy`, wird die Besprechungsmigration nicht aufgerufen.
- Einem Benutzer kann der TeamsOnly-Modus nur gewährt werden, wenn der Benutzer online verwaltet wird. Benutzer, die lokal verwaltet werden, müssen wie zuvor beschrieben verschoben `Move-CsUser` werden.
- Durch das Gewähren eines anderen Modus als TeamsOnly oder SfBWithTeamsCollabAndMeetings werden vorhandene Teams Besprechungen nicht in Skype for Business Besprechungen konvertiert.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Manuelles Auslösen der Besprechungsmigration über das PowerShell-Cmdlet

Zusätzlich zu automatischen Besprechungsmigrationen können Administratoren die Besprechungsmigration für einen Benutzer manuell auslösen, indem sie das Cmdlet `Start-CsExMeetingMigration`ausführen. Mit diesem Cmdlet wird eine Migrationsanforderung für den angegebenen Benutzer in die Warteschlange gestellt.  Zusätzlich zum erforderlichen `Identity` Parameter werden zwei optionale Parameter verwendet, mit `TargetMeetingType`denen Sie angeben können, `SourceMeetingType` wie Besprechungen migriert werden:

**TargetMeetingType:**

- Using `TargetMeetingType Current` gibt an, dass Skype for Business Besprechungen Skype for Business Besprechungen bleiben und Teams Besprechungen Teams Besprechungen bleiben. Audiokonferenzkoordinaten können jedoch geändert werden, und alle lokalen Skype for Business Besprechungen würden zu Skype for Business Online migriert. Dies ist der Standardwert für TargetMeetingType.
- Using `TargetMeetingType Teams` gibt an, dass jede vorhandene Besprechung zu Teams migriert werden muss, unabhängig davon, ob die Besprechung in Skype for Business online oder lokal gehostet wird und unabhängig davon, ob Audiokonferenzupdates erforderlich sind.

**SourceMeetingType:**

- Die Verwendung `SourceMeetingType SfB` gibt an, dass nur Skype for Business Besprechungen (lokal oder online) aktualisiert werden sollten.
- Die Verwendung `SourceMeetingType Teams` gibt an, dass nur Teams Besprechungen aktualisiert werden sollten.
- Die Verwendung `SourceMeetingType All` gibt an, dass sowohl Skype for Business Besprechungen als auch Teams Besprechungen aktualisiert werden sollten. Dies ist der Standardwert für SourceMeetingType.

Das folgende Beispiel zeigt, wie Sie die Besprechungsmigration für Benutzer ashaw@contoso.com initiieren, sodass alle Besprechungen zu Teams migriert werden:

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

## <a name="managing-mms"></a>Verwalten von MMS

Mit Windows PowerShell können Sie den Status der laufenden Migrationen überprüfen, die Besprechungsmigration manuell auslösen und die Migration insgesamt deaktivieren.

### <a name="check-the-status-of-meeting-migrations"></a>Überprüfen des Status von Besprechungsmigrationen

Sie verwenden das `Get-CsMeetingMigrationStatus` Cmdlet, um den Status von Besprechungsmigrationen zu überprüfen. Unten sind einige Beispiele aufgeführt.

- Um einen Zusammenfassungsstatus aller MMS-Migrationen abzurufen, führen Sie den folgenden Befehl aus, der eine tabellarische Ansicht aller Migrationszustände bereitstellt:

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed        2
    Succeeded   131
    ```

- Um vollständige Details aller Migrationen innerhalb eines bestimmten Zeitraums zu erhalten, verwenden Sie die und `EndTime` parameter`StartTime`. Der folgende Befehl gibt beispielsweise vollständige Details zu allen Migrationen zurück, die vom 1. Oktober 2018 bis zum 8. Oktober 2018 stattgefunden haben.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```

- Verwenden Sie `Identity` den Parameter, um den Status der Migration für einen bestimmten Benutzer zu überprüfen. Beispielsweise gibt der folgende Befehl den Status des Benutzers ashaw@contoso.com zurück:

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```

Wenn fehlgeschlagene Migrationen angezeigt werden, ergreifen Sie Maßnahmen, um diese Probleme so schnell wie möglich zu beheben, da die Benutzer sich erst bei den von diesen Benutzern organisierten Besprechungen einwählen können, bis Sie sie beheben. Wenn `Get-CsMeetingMigrationStatus` Migrationen in einem fehlerhaften Zustand angezeigt werden, führen Sie die folgenden Schritte aus:

1. Stellen Sie fest, welche Benutzer betroffen sind. Führen Sie den folgenden Befehl aus, um die Liste der betroffenen Benutzer und den spezifischen gemeldeten Fehler zu erhalten:

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```

2. Überprüfen Sie für jeden betroffenen Benutzer den Wert der LastMessage-Eigenschaft, um zu ermitteln, warum die Besprechungsmigration fehlgeschlagen ist und welche Korrekturmaßnahmen ausgeführt werden müssen. Nachdem Korrekturmaßnahmen ergriffen wurden, lösen Sie die Besprechungsmigration für die betroffenen Benutzer erneut mithilfe des `Start-CsExMeetingMigration` PowerShell-Cmldets aus, wie oben beschrieben.

3. Wenn die Migration immer noch nicht funktioniert, haben Sie zwei Optionen:

    - Weisen Sie die Benutzer an, neue Skype-Besprechungen zu erstellen.
    - [Wenden Sie sich an den Support](/microsoft-365/Admin/contact-support-for-business-products).

Das `Get-CsMeetingMigrationStatus` Cmdlet kann verwendet werden, um den Status von Migrationen abzurufen, die innerhalb der letzten 150 Tage ausgelöst wurden. Datensätze für Migrationen, die älter als 150 Tage sind, werden aus dem System gelöscht.

### <a name="enabling-and-disabling-mms"></a>Aktivieren und Deaktivieren von MMS

MMS ist standardmäßig für alle Organisationen aktiviert, kann aber wie folgt deaktiviert werden:

- Vollständig für den Mandanten deaktivieren.
- Nur für Änderungen im Zusammenhang mit Audiokonferenzen deaktivieren. In diesem Fall wird MMS weiterhin ausgeführt, wenn ein Benutzer von der lokalen Umgebung in die Cloud migriert wird oder wenn Sie den TeamsOnly-Modus oder den SfBWithTeamsCollabAndMeetings-Modus in `TeamsUpgradePolicy`gewähren.

Sie können z. B. alle Besprechungen manuell migrieren oder MMS vorübergehend deaktivieren, während Sie wesentliche Änderungen an den Audiokonferenzeinstellungen für Ihre Organisation vornehmen.

Führen Sie den folgenden Befehl aus, um festzustellen, ob MMS für Ihre Organisation aktiviert ist. MMS ist aktiviert, wenn der `MeetingMigrationEnabled` Parameter ist `$true`.

```PowerShell
Get-CsTenantMigrationConfiguration
```

Wenn MMS in der Organisation aktiviert ist und Sie überprüfen möchten, ob es für Audiokonferenzupdates aktiviert ist, überprüfen Sie den Wert des `AutomaticallyMigrateUserMeetings` Parameters in der Ausgabe von `Get-CsOnlineDialInConferencingTenantSettings`. Um MMS für Audiokonferenzen zu aktivieren oder zu deaktivieren, verwenden Sie `Set-CsOnlineDialInConferencingTenantSettings`. Um z. B. MMS für Audiokonferenzen zu deaktivieren, führen Sie den folgenden Befehl aus:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
