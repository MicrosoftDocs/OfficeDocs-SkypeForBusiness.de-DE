---
title: Verschieben von Benutzern von Skype für Business Server 2019 Teams
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Zusammenfassung: Informationen Sie zum Migrieren von benutzereinstellungen und Migrieren von Benutzern zu Teams.'
ms.openlocfilehash: 75af7109de60c3d978914585105e4d2fbaad9302
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "29348913"
---
# <a name="move-users-from-on-premises-to-teams"></a>Verschieben von Benutzern von lokalen Teams

Wenn ein Benutzer von lokal auf Teams nur verschoben wird des Benutzers Skype für geschäftlich privat wird lokal auf online aus verschoben, und der Benutzer TeamsUpgradePolicy-Modus erhält TeamsOnly =.  Nachdem ein Benutzer wird vom lokalen TeamsOnly Modus verschoben:

- Alle eingehenden Anrufe und chats von anderen Benutzern (ob von Skype für Geschäftskunden und Teams gesendet), wird in der Client des Benutzers Teams sorgt.
- Der Benutzer wird möglicherweise mit anderen Benutzern zusammenarbeiten, die Skype für Unternehmen (entweder online oder lokal) verwenden.
- Der Benutzer werden kann zur Kommunikation mit Benutzern in Partnerorganisationen.
- Neue geplant, die von diesem Benutzer sind Teams Besprechungen.
- Benutzer kann weiterhin alle Skype für Business-Besprechungen teilnehmen.
- Der Benutzer bereits vorhandenen geplant für die Zukunft werden lokal zu Skype für Business Online migriert.
- Kontakte, die lokal vorhanden war, sind in Teams verfügbar, kurz nachdem der Benutzer zum ersten Mal anmeldet.
- Anrufe oder Chats von Skype für Unternehmen kann nicht gestartet werden, noch neue Besprechungen in Skype für Unternehmen planen. Wenn sie versuchen, die Skype für Business-Client zu öffnen, werden sie umgeleitet, um Teams verwenden (siehe unten). Der Client Teams nicht installiert ist, werden sie auf die Webversion von Teams, die mit ihren Browser weitergeleitet.<br><br>
    ![Umleiten des Benutzers auf Teams Nachricht](../media/go-to-teams-page.png)

Werden Sie vor dem Verschieben alle Benutzer, überprüfen Sie die [erforderlichen Komponenten](move-users-between-on-premises-and-cloud.md#prerequisites) , um Benutzer in der Cloud zu verschieben. Außerdem müssen Sie überprüfen der [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Unternehmen](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Es gibt zwei Methoden zum Verschieben eines Benutzers aus lokal Teams:

- Wenn Sie eine Version vor Skype für Business Server 2015 CU8 verwenden, erfolgt die Verschiebung in zwei Schritten (die in Skripts verwendet werden können, die gemeinsam als einem Schritt ausgeführt werden bei Bedarf):
  - [Der Benutzer von Skype für Business Server (lokal) auf Skype für Business Online verschoben](move-users-from-on-premises-to-skype-for-business-online.md).
  - Nachdem der Benutzer in Skype verwaltet wird, für die Business Online, weisen Sie dem Benutzer TeamsUpgradePolicy Modus = TeamsOnly. Um TeamsOnly Modus zu erteilen, führen Sie das folgende Cmdlet aus einer Skype für Business Online-PowerShell-Fenster:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Wenn Sie die Verwaltungstools von Skype für Business Server 2015 CU8 oder höher verfügen, können können Sie die oben genannten-Methode verwenden, oder Sie diese verschieben in einem Schritt wie unten beschrieben. Darüber hinaus können Sie optional eine Benachrichtigung innerhalb der Skype für Business Client vor dem Verschieben sie in Teams nur sowie optional den Teams Client automatisch von der Skype für Business Client heruntergeladen haben.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Verschieben eines Benutzers direkt von Skype für Unternehmen lokal auf nur Teams

Die lokale-Verwaltungstools in Skype für Business Server 2015 mit CU8 sowie in Skype für Business Server 2019, aktivieren Sie so verschieben Sie Benutzer aus lokal Teams nur im Modus in einem einzigen Schritt über entweder mit dem Cmdlet Move-CsUser in PowerShell oder der Skype für Business SE (engl.) Rver Control Panel, wie unten beschrieben.

### <a name="move-to-teams-using-move-csuser"></a>Mit der Move-CsUser Teams verschieben

Move-CsUser ist von einem lokalen Skype für Business Management Shell PowerShell-Fenster zur Verfügung. Die folgenden Schritte aus und die erforderlichen Berechtigungen sind identisch mit dem Verschieben eines Benutzers zu Skype für Online Business ein, mit der Ausnahme, dass müssen Sie auch die Option MoveToTeams angeben, und Sie müssen sicherstellen, dass der Benutzer auch eine Lizenz für Teams (zusätzlich zum Skype für Unternehmen erteilt wurde Online).

Wie beschrieben in [Administratorrechte erforderlich](move-users-between-on-premises-and-cloud.md#required-administrative-credentials), benötigen Sie ausreichende Berechtigungen in der lokalen Umgebung und der Office 365-Mandanten. Sie können entweder ein einzelnes Konto mit Berechtigungen in beiden Umgebungen verwenden, oder Sie eine lokale Skype für Business Server-Verwaltungsshell-Fenster mit lokalen Anmeldeinformationen starten und verwenden können die `-Credential` Parameter zum Angeben von Anmeldeinformationen für ein Office 365 Konto mit den erforderlichen Office 365-Administratorrolle.

Zum Verschieben eines Benutzers auf den Teams nur mit der Move-CsUser Modus:

- Geben Sie den Benutzer zu verschieben, mit der `Identity` Parameter.
- Geben Sie die - Target-Parameter mit dem Wert "sipfed.online.lync. <span>com ".
- Geben Sie die `MoveToTeams` wechseln.
- Wenn Sie in beiden auf lokalen und Office 365 nicht über ein Konto mit ausreichenden Berechtigungen verfügen, verwenden Sie die `-credential` Parameter für ein Konto mit ausreichenden Berechtigungen in Office 365 bereitstellen.
- Wenn das Konto mit Berechtigungen in Office 365 nicht in "on.microsoft. endet <span>com ", geben Sie die `-HostedMigrationOverrideUrl` Parameter mit den richtigen Wert als Beschreibung in [Administratoranmeldeinformationen erforderlich](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

Die folgende Sequenz Cmdlet zum Verschieben eines Benutzers in TeamsOnly verwendet werden, und geht davon aus, die Office 365-Anmeldeinformationen ist ein separates Konto und als Eingabe für die Aufforderung Get-Credential angegeben.

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Verschieben von Skype Business Server-Systemsteuerung Teams

1. Öffnen Sie die Skype für Business-Serversteuerelement Systemsteuerung app.
2. Wählen Sie im linken Navigationsbereich **Benutzer**.
3. Verwenden Sie **Suchen** , um die Benutzer zu suchen, die Sie in Teams verschieben möchten.
4. Wählen Sie die Benutzer, und wählen Sie dann aus der Dropdownliste **Aktion** über der Liste **ausgewählte Benutzer Teams verschieben**.
5. Klicken Sie im Assistenten auf **Weiter**.
6. Wenn Sie aufgefordert werden, melden Sie sich bei Office 365, mit einem Konto an, die in endet. onmicrosoft.com und über ausreichende Berechtigungen verfügt.
7. Klicken Sie auf **Weiter**, und klicken Sie dann **Weiter** noch einmal den Benutzer zu verschieben.
8. Beachten Sie, dass Statusnachrichten bezüglich Erfolg oder Fehler am oberen Rand der wichtigsten Systemsteuerung app nicht im Assistenten bereitgestellt werden.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Benachrichtigen Sie Ihre Skype für Business lokale Benutzer von bevorstehenden verschieben Teams

Die lokale-Verwaltungstools in Skype für Business Server 2015 mit CU8 sowie in Skype für Business Server 2019, können Sie lokale Skype für geschäftliche Benutzer von bevorstehenden Wechsel zu Teams zu benachrichtigen. Wenn Sie diese Benachrichtigungen aktivieren, wird eine Benachrichtigung in ihren Skype für Business-Client (Win32, Mac, Web und Mobile) angezeigt, wie unten dargestellt. Wenn Benutzer auf die Schaltfläche **ausprobieren** klicken, wird der Teams-Client gestartet werden, falls installiert; Andernfalls werden Benutzern die Webversion von Teams in ihrem Browser navigiert werden. Standardmäßig Wenn Benachrichtigungen aktiviert sind, Win32 Skype für Business-Clients im Hintergrund den Teams-Client herunterladen, damit der rich-Client vor dem Verschieben des Benutzers in Teams nur Modus verfügbar ist; Sie können dieses Verhalten jedoch auch deaktivieren.  Benachrichtigungen konfiguriert werden, mit der lokalen Version von `TeamsUpgradePolicy`, und automatischen Download von Win32-Clients wird gesteuert, über die lokal `TeamsUpgradeConfiguration` Cmdlet.

![Benachrichtigung über bevorstehende ANS Teams](../media/teams-upgrade-notification.png)

Um lokale Benutzer zu benachrichtigen, dass sie bald Teams aktualisiert werden, erstellen Sie eine neue Instanz des TeamsUpgradePolicy mit NotifySfBUsers = True. Weisen Sie dann die Richtlinie für die Benutzer zu benachrichtigen, entweder durch Zuweisen der Richtlinie für den Benutzer direkt oder durch Festlegen von Richtlinien auf Standort-, Pool oder globaler Ebene. Die folgenden Cmdlets erstellen, und gewähren Sie eine Richtlinie auf Benutzerebene:

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Automatische Downloads von Teams über die Skype für Business Win32-Client wird über das lokale TeamsUpgradeConfiguration-Cmdlet mit dem Parameter DownloadTeams gesteuert. Sie erstellen diese Konfiguration auf globaler, Standort- und Poolebene. Der folgende Befehl wird beispielsweise die Konfiguration für den Standort "redmond1" erstellt:

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

Standardmäßig ist der Wert der DownloadTeams True; Es ist jedoch *nur* berücksichtigt, wenn er NotifySfbUser = "true" für einen bestimmten Benutzer.

## <a name="see-also"></a>Siehe auch

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

[GRANT-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy
)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Koexistenz mit Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
