---
title: Verwenden des Besprechungs Migrations Diensts (MMS)
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: Der Meeting Migration Service (MMS) ist ein Dienst, der im Hintergrund ausgeführt wird und automatisch Skype for Business-und Microsoft Teams-Besprechungen für Benutzer aktualisiert. MMS wurde entwickelt, um zu verhindern, dass Benutzer das Besprechungs Migrations Tool ausführen können, um Ihre Skype for Business-und Microsoft Teams-Besprechungen zu aktualisieren.
ms.openlocfilehash: 3f643f20937fd13b0d9576640487da30f17dd7bf
ms.sourcegitcommit: 8db50c46992dccf54c1d4be58d8a0d21ec64ddd0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772279"
---
# <a name="using-the-meeting-migration-service-mms"></a>Verwenden des Besprechungs Migrations Diensts (MMS)

Der Besprechungs Migrationsdienst (MMS) ist ein Dienst, der die vorhandenen Besprechungen eines Benutzers in den folgenden Szenarien aktualisiert:

- Wenn ein Benutzer von lokal in die Cloud migriert wird (ob Skype for Business Online oder TeamsOnly).
- Wenn ein Administrator Änderungen an den Einstellungen für die Audiokonferenz des Benutzers vornimmt 
- Wenn ein Online Benutzer nur auf Teams aktualisiert wird oder wenn der Benutzermodus in TeamsUpgradePolicy auf SfBwithTeamsCollabAndMeetings eingestellt ist
- Wenn Sie PowerShell verwenden 


Standardmäßig wird in jedem dieser Fälle MMS automatisch ausgelöst, obwohl Administratoren ihn auf Mandantenebene deaktivieren können. Darüber hinaus können Administratoren ein PowerShell-Cmdlet verwenden, um die Besprechungs Migration für einen bestimmten Benutzer manuell auszulösen.


**Einschränkungen**: der Besprechungs Migrationsdienst kann nicht verwendet werden, wenn eine der folgenden Bedingungen zutrifft:

- Das Postfach des Benutzers wird lokal in Exchange gehostet.
- Der Benutzer wird von der Cloud zu Skype for Business Server lokal migriert.

In diesen Situationen können Endbenutzer das [Besprechungs Migrations Tool](https://www.microsoft.com/en-us/download/details.aspx?id=51659) verwenden, um stattdessen eigene Besprechungen zu migrieren.

## <a name="how-mms-works"></a>Funktionsweise von MMS

Wenn MMS für einen bestimmten Benutzer ausgelöst wird, wird eine Migrationsanforderung für diesen Benutzer in eine Warteschlange gestellt. Um Rennbedingungen zu vermeiden, wird die Warteschlangen Anforderung absichtlich nicht verarbeitet, bis mindestens 90 Minuten vergangen sind. Nachdem MMS die Anforderung verarbeitet hat, führt Sie die folgenden Aufgaben aus:

1. Durchsucht das Postfach des Benutzers nach allen vorhandenen Besprechungen, die von diesem Benutzer organisiert und in Zukunft geplant werden.
2. Basierend auf den Informationen, die im Postfach des Benutzers gefunden wurden, werden je nach Szenario entweder neue Besprechungen entweder in Teams oder in Skype for Business Online für diesen Benutzer aktualisiert oder geplant.
3. In der e-Mail-Nachricht ersetzt Sie den Online Besprechungs Block in den Besprechungsdetails.
4. Die aktualisierte Version dieser Besprechung wird im Auftrag des Besprechungsorganisators an alle Besprechungs Empfänger gesendet. Besprechungseinladungen erhalten ein Besprechungs Update mit aktualisierten Besprechungs Koordinaten in der e-Mail. 

    ![Der Besprechungsblock, der von MMS aktualisiert wird.](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Ab dem Zeitpunkt, zu dem MMS ausgelöst wird, dauert es in der Regel ca. 2 Stunden, bis die Besprechungen des Benutzers migriert werden. Wenn der Benutzer jedoch eine große Anzahl von Besprechungen hat, kann es länger dauern. Wenn MMS auf einen Fehler beim Migrieren einer oder mehrerer Besprechungen für den Benutzer stößt, wird der Vorgang in regelmäßigen Abständen bis zu 9 Mal im Zeitraum von 24 Stunden wiederholt.

**Hinweise**:

- MMS ersetzt alles im Informationsblock für die Onlinebesprechung, wenn eine Besprechung migriert wird. Wenn daher ein Benutzer diesen Block bearbeitet hat, werden seine Änderungen überschrieben. Alle Inhalte, die sich in den Besprechungsdetails außerhalb des Informationsblocks der Onlinebesprechung befinden, sind nicht betroffen.
- Es werden nur die Skype for Business- oder Microsoft Teams-Besprechungen migriert, die durch Klicken auf die Schaltfläche **Skype-Besprechung hinzufügen** in Outlook im Web oder über das Skype-Besprechungs-Add-In für Outlook geplant wurden. Wenn ein Benutzer die Skype Online-Besprechungsinformationen aus einer Besprechung in eine neue Besprechung kopiert und darin eingefügt hat, wird diese neue Besprechung nicht aktualisiert, da im ursprünglichen Dienst keine Besprechung stattfindet.
- Besprechungsinhalte, die erstellt oder an die Besprechung angefügt wurden (Whiteboards, Umfragen usw.) werden nach der Ausführung von MMS nicht beibehalten. Wenn Ihre Besprechungsorganisatoren im Voraus Inhalte an Besprechungen angehängt haben, müssen diese Inhalte nach der Ausführung von MMS erneut erstellt werden.
- Der Link zu freigegebenen Besprechungsnotizen im Kalenderelement und von innerhalb der Skype-Besprechung wird ebenfalls überschrieben. Beachten Sie, dass die tatsächlichen Besprechungsnotizen, die in OneNote gespeichert sind, weiterhin vorhanden sind. nur der Link zu den freigegebenen Notizen wird überschrieben.
- Besprechungen mit mehr als 250 Teilnehmern (einschließlich des Organisators) werden nicht migriert.
- Einige Unicode-Zeichen im Text der Einladung werden möglicherweise fälschlicherweise auf eines der folgenden Sonderzeichen aktualisiert: ï, ¿, 1/2,.

## <a name="triggering-mms-for-a-user"></a>Auslösen von MMS für einen Benutzer

In diesem Abschnitt wird beschrieben, was passiert, wenn in den folgenden Fällen MMS ausgelöst wird:

- Wenn ein Benutzer von lokal in die Cloud migriert wird
- Wenn ein Administrator Änderungen an den Einstellungen für die Audiokonferenz des Benutzers vornimmt 
- Wenn der Benutzermodus in TeamsUpgradePolicy auf "TeamsOnly" oder "SfBWithTeamsCollabAndMeetings" (entweder mit PowerShell oder dem Team-Administrator Portal) eingestellt ist
- Wenn Sie das PowerShell-Cmdlet verwenden, starten-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Aktualisieren von Besprechungen, wenn Sie einen lokalen Benutzer in die Cloud verschieben

Dies ist das häufigste Szenario, in dem MMS dazu beiträgt, einen reibungsloseren Übergang für Ihre Benutzer zu schaffen. Ohne Besprechungs Migration funktionieren vorhandene Besprechungen, die von einem Benutzer in Skype for Business Server lokal organisiert werden, nicht mehr, nachdem der Benutzer online verschoben wurde. Wenn Sie also die lokalen Verwaltungstools ( `Move-CsUser` oder die Administrator-Systemsteuerung) verwenden, um einen Benutzer in die Cloud zu verschieben, werden vorhandene Besprechungen wie folgt automatisch in die Cloud verschoben:

- Wenn der `MoveToTeams` Schalter in `Move-CsUser` angegeben ist, werden Besprechungen direkt in Teams migriert, und der Benutzer befindet sich im TeamsOnly-Modus. Für die Verwendung dieses Schalters ist Skype for Business Server 2015 mit CU8 oder höher erforderlich. Diese Benutzer können immer noch an einer Skype for Business-Besprechung teilnehmen, zu der Sie eingeladen werden, entweder über den Skype for Business-Client oder die Skype-Besprechungs-app.
- Andernfalls werden Besprechungen in Skype for Business Online migriert.

In beiden Fällen werden die Besprechungen mit Einwahl Koordinaten erstellt, wenn dem Benutzer eine Audiokonferenz-Lizenz zugewiesen wurde, bevor er in die Cloud verschoben wird. Wenn Sie einen Benutzer von lokal in die Cloud verschieben und für diesen Benutzer Audiokonferenzen verwenden möchten, empfiehlt es sich, zunächst die Audiokonferenz zuzuweisen, bevor Sie den Benutzer verschieben, sodass nur 1 Besprechungs Migration ausgelöst wird.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aktualisieren von Besprechungen, wenn sich die Audiokonferenzeinstellungen eines Benutzers ändern

In den folgenden Fällen aktualisiert MMS vorhandene Skype for Business-und Microsoft Teams-Besprechungen, um Einwahl Koordinaten hinzuzufügen, zu entfernen oder zu ändern:

- Wenn Sie einem Benutzer eine Microsoft Audio Conferencing Service-Lizenz zuweisen oder daraus entfernen und dieser Benutzer für einen Audiokonferenz-Anbieter eines Drittanbieters nicht aktiviert ist.
- Wenn Sie den Anbieter für Audiokonferenzen eines Benutzers von einem anderen Anbieter zu Microsoft ändern, sofern dem Benutzer eine Microsoft Audio Conferencing-Lizenz zugewiesen ist. Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Audiokonferenz-Anbieter](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider). Beachten Sie auch, dass die Unterstützung für Audiokonferenz-Anbieter von Drittanbietern [ACP] für das Ende des Lebenszyklus am 1. April 2019 geplant ist, wie [zuvor angekündigt](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).
- Wenn Sie Audiokonferenzen für einen Benutzer aktivieren oder deaktivieren.
- Wenn Sie die Konferenz-ID für einen Benutzer, der für die Verwendung öffentlicher Besprechungen konfiguriert ist, ändern oder zurücksetzen.
- Wenn Sie den Benutzer zu einer neuen Audiokonferenzbrücke verschieben
- Wenn eine Telefonnummer von einer Audiokonferenz-Brücke nicht zugewiesen ist. Hierbei handelt es sich um ein komplexes Szenario, das zusätzliche Schritte erfordert. Weitere Informationen finden Sie unter [Ändern der Telefonnummern auf der Audiokonferenz-Brücke](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

Nicht alle Änderungen an den Audiokonferenzeinstellungen eines Benutzers lösen MMS aus. Insbesondere die folgenden beiden Änderungen führen nicht dazu, dass MMS Besprechungen aktualisiert:

- Ändern der SIP-Adresse für den Besprechungsorganisator (entweder des SIP-Benutzernamens oder der SIP-Domäne)
- Wenn Sie die Besprechungs-URL Ihrer Organisation mithilfe des `Update-CsTenantMeetingUrl` Befehls ändern.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Aktualisieren von Besprechungen beim Zuweisen von TeamsUpgradePolicy

Standardmäßig wird die Besprechungs Migration automatisch ausgelöst, wenn einem Benutzer eine Instanz von `TeamsUpgradePolicy` mit `mode=TeamsOnly` oder `mode= SfBWithTeamsCollabAndMeetings`zugewiesen wird. Wenn Sie keine Besprechungen migrieren möchten, wenn Sie einen dieser Modi gewähren, geben `MigrateMeetingsToTeams $false` Sie in `Grant-CsTeamsUpgradePolicy` (bei Verwendung von PowerShell) an, oder deaktivieren Sie das Kontrollkästchen zum Migrieren von Besprechungen, wenn Sie den Koexistenzmodus eines Benutzers festlegen (wenn Sie das Team-Administratorportal verwenden).

Beachten Sie außerdem Folgendes:

- Die Besprechungs Migration wird nur aufgerufen, wenn `TeamsUpgradePolicy` Sie für einen bestimmten Benutzer erteilen. Wenn Sie mit `TeamsUpgradePolicy` `mode=TeamsOnly` oder `mode=SfBWithTeamsCollabAndMeetings` auf *Mandanten* Ebene gewähren, wird keine Besprechungs Migration aufgerufen.
- Einem Benutzer kann nur der TeamsOnly-Modus gewährt werden, wenn der Benutzer online ist. Benutzer, die lokal gehostet werden, müssen `Move-CsUser` wie zuvor beschrieben verschoben werden.
- Wenn Sie einen anderen Modus als TeamsOnly oder SfBWithTeamsCollabAndMeetings gewähren, werden vorhandene Teams-Besprechungen nicht in Skype for Business-Besprechungen konvertiert.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Manuelles Auslösen der Besprechungs Migration über das PowerShell-Cmdlet

Neben automatischen Besprechungs Migrationen können Administratoren die Besprechungs Migration für einen Benutzer manuell auslösen, indem Sie das Cmdlet `Start-CsExMeetingMigration`ausführen. Mit diesem Cmdlet wird eine Migrationsanforderung für den angegebenen Benutzer in die Warteschlange eingereiht.  Neben dem erforderlichen `Identity` Parameter werden zwei optionale Parameter verwendet, `SourceMeetingType` und `TargetMeetingType`Sie können angeben, wie Besprechungen migriert werden sollen:

**TargetMeetingType:**

- Mit `TargetMeetingType Current` gibt an, dass Skype for Business-Besprechungen weiterhin Skype for Business-Besprechungen und Teams-Besprechungen bleiben Teams. Audiokonferenz-Koordinaten können jedoch geändert werden, und alle lokalen Skype for Business-Besprechungen werden in Skype for Business Online migriert. Dies ist der Standardwert für TargetMeetingType.
- Mit `TargetMeetingType Teams` gibt an, dass eine vorhandene Besprechung in Teams migriert werden muss, unabhängig davon, ob die Besprechung in Skype for Business Online oder lokal gehostet wird, und zwar unabhängig davon, ob Audiokonferenz-Updates erforderlich sind. 

**SourceMeetingType:**
- Die `SourceMeetingType SfB` Verwendung zeigt an, dass nur Skype for Business-Besprechungen (ob lokal oder Online) aktualisiert werden sollen.
- Verwenden `SourceMeetingType Teams` gibt an, dass nur Teams-Besprechungen aktualisiert werden sollen.
- Mit `SourceMeetingType All` gibt an, dass sowohl Skype for Business-Besprechungen als auch Teams-Besprechungen aktualisiert werden sollten. Dies ist der Standardwert für SourceMeetingType.
    

Im folgenden Beispiel wird gezeigt, wie Sie die Besprechungs Migration für Benutzer ashaw@contoso.com initiieren, damit alle Besprechungen in Teams migriert werden:

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Verwalten von MMS

Mithilfe von Windows PowerShell können Sie den Status laufender Migrationen überprüfen, die Besprechungs Migration manuell auslösen und die Migration ganz deaktivieren. 

### <a name="check-the-status-of-meeting-migrations"></a>Überprüfen des Status von Besprechungs Migrationen

Sie verwenden das `Get-CsMeetingMigrationStatus` Cmdlet, um den Status von Besprechungs Migrationen zu überprüfen. Unten sind einige Beispiele aufgeführt.

- Wenn Sie einen Zusammenfassungsstatus aller MMS-Migrationen erhalten möchten, führen Sie den folgenden Befehl aus, der eine tabellarische Ansicht aller Migrations Zustände bietet:

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Verwenden Sie die `StartTime` Parameter und `EndTime` , um alle Informationen zu allen Migrationen innerhalb eines bestimmten Zeitraums abzurufen. Mit dem folgenden Befehl werden beispielsweise alle Informationen zu allen Migrationen zurückgegeben, die vom 1. Oktober 2018 bis zum 8. Oktober 2018 aufgetreten sind.

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Verwenden Sie den `Identity` Parameter, um den Migrationsstatus für einen bestimmten Benutzer zu überprüfen. Beispielsweise gibt der folgende Befehl den Status des Benutzers ashaw@contoso.com zurück:

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Wenn Migrationsfehler angezeigt werden, müssen Sie diese Probleme so schnell wie möglich beheben, da sich die Benutzer erst dann in die von diesen Benutzern organisierten Besprechungen einwählen können, wenn Sie diese beheben. Führen `Get-CsMeetingMigrationStatus` Sie die folgenden Schritte aus, wenn alle Migrationen in einem fehlerhaften Zustand angezeigt werden:
 
1. Stellen Sie fest, welche Benutzer betroffen sind. Führen Sie den folgenden Befehl aus, um die Liste der betroffenen Benutzer und den spezifischen gemeldeten Fehler zu erhalten:

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. Führen Sie für jeden betroffenen Benutzer das Besprechungs Migrations Tool aus, um die Besprechungen manuell zu migrieren.

3. Wenn die Migration auch mit dem Meeting Migration Tool nicht funktioniert, haben Sie zwei Möglichkeiten:

    - Weisen Sie die Benutzer an, neue Skype-Besprechungen zu erstellen.
    - [Wenden Sie sich an den Support](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Aktivieren und Deaktivieren von MMS

MMS ist standardmäßig für alle Organisationen aktiviert, kann aber wie folgt deaktiviert werden:

- Vollständiges Deaktivieren für den Mandanten. 
- Nur für Änderungen deaktivieren, die sich auf Audiokonferenzen beziehen. In diesem Fall wird MMS weiterhin ausgeführt, wenn ein Benutzer von lokal in die Cloud migriert wird oder wenn Sie den TeamsOnly-Modus oder den SfBWithTeamsCollabAndMeetings-Modus `TeamsUpgradePolicy`in gewähren.

So können Sie beispielsweise alle Besprechungen manuell migrieren oder MMS vorübergehend deaktivieren, während Sie wesentliche Änderungen an den Einstellungen für die Audiokonferenz für Ihre Organisation vornehmen.

Führen Sie den folgenden Befehl aus, um festzustellen, ob MMS für Ihre Organisation aktiviert ist. MMS ist aktiviert, wenn `MeetingMigrationEnabled` es sich `$true`um den Parameter handelt.
```
Get-CsTenantMigrationConfiguration
```
Verwenden Sie den `Set-CsTenantMigrationConfiguration` Befehl, um MMS vollständig zu aktivieren oder zu deaktivieren. Wenn Sie beispielsweise MMS deaktivieren möchten, führen Sie den folgenden Befehl aus:

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Wenn MMS in der Organisation aktiviert ist und Sie überprüfen möchten, ob Sie für Audio-Konferenz Updates aktiviert ist, überprüfen Sie `AutomaticallyMigrateUserMeetings` den Wert des Parameters in der Ausgabe von `Get-CsOnlineDialInConferencingTenantSettings`. Verwenden Sie `Set-CsOnlineDialInConferencingTenantSettings`zum Aktivieren oder Deaktivieren von MMS für Audiokonferenzen. Führen Sie beispielsweise den folgenden Befehl aus, um MMS für Audiokonferenzen zu deaktivieren:

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
