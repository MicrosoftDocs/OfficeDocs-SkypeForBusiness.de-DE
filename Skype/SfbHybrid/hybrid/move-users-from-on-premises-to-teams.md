---
title: Verschieben von Benutzern von Skype for Business Server 2019 zu Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Zusammenfassung: Erfahren Sie, wie Sie Benutzereinstellungen migrieren und Benutzer zu Teams verschieben.'
ms.openlocfilehash: 1b5a2f909a05ffd30902ca4ca32dc5b5621b3013e779cece3f0ffcd2dada731e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324704"
---
# <a name="move-users-from-on-premises-to-teams"></a>Verschieben von Benutzern aus lokalen Bereitstellungen nach Microsoft Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Wenn ein Benutzer von lokal zu Teams Only verschoben wird, wird die Skype for Business des Benutzers von der lokalen Umgebung in die Onlineumgebung verschoben, und dem Benutzer wird TeamsUpgradePolicy mit mode=TeamsOnly zugewiesen.  Nachdem ein Benutzer aus der lokalen Umgebung in den TeamsOnly-Modus verschoben wurde:

- Alle eingehenden Anrufe und Chats von anderen Benutzern (ob von Skype for Business oder Teams gesendet) landen im Teams Client des Benutzers.
- Der Benutzer kann mit anderen Benutzern zusammenarbeiten, die Skype for Business verwenden (ob online oder lokal).
- Der Benutzer kann mit Benutzern in Verbundorganisationen kommunizieren.
- Neue besprechungen, die von diesem Benutzer geplant werden, sind Teams Besprechungen.
- Der Benutzer kann weiterhin an allen Skype for Business Besprechungen teilnehmen.
- Die für die Zukunft geplanten bereits vorhandenen Besprechungen des Benutzers werden von der lokalen Umgebung zu Teams migriert.
- Lokal vorhandene Kontakte sind in Teams verfügbar, kurz nachdem sich der Benutzer zum ersten Mal angemeldet hat.
- Benutzer können weder Anrufe oder Chats von Skype for Business aus initiieren noch neue Besprechungen in Skype for Business planen. Wenn sie versuchen, den Skype for Business Client zu öffnen, werden sie umgeleitet, um Teams wie unten dargestellt zu verwenden. Wenn der Teams-Client nicht installiert ist, wird er über den Browser an die Webversion von Teams weitergeleitet.<br><br>
    ![Nachricht, die einen Benutzer an Teams umleitet](../media/go-to-teams-page.png)

Überprüfen Sie vor dem Verschieben von Benutzern unbedingt die [Voraussetzungen,](move-users-between-on-premises-and-cloud.md#prerequisites) um Benutzer in die Cloud zu verschieben. Überprüfen Sie außerdem die [Migrations- und Interoperabilitätsleitlinien für Organisationen,](/microsoftteams/migration-interop-guidance-for-teams-with-skype)die Teams zusammen mit Skype for Business verwenden.


> [!NOTE]
> Unified Contact Store sollte für das lokale SfB-Konto deaktiviert werden, damit der Kontakt in Teams verschoben werden kann.

> [!IMPORTANT]
>Wenn ein Benutzer mit Move-CsUser von der lokalen Umgebung in die Cloud verschoben wird, wird benutzern jetzt automatisch der TeamsOnly-Modus zugewiesen, und ihre Besprechungen aus der lokalen Umgebung werden automatisch in Teams Besprechungen konvertiert, unabhängig davon, ob der `-MoveToTeams` Switch tatsächlich angegeben ist. (Dies umfasst Migrationen von Lync Server 2013, für die der Switch nie `-MoveToTeams` vorhanden war.)  Wenn dieser Switch nicht angegeben wurde, wurden Benutzer zuvor von Skype for Business Server lokal zu Skype for Business Online migriert, und ihr Modus bleibt unverändert. Dies wurde kürzlich in Vorbereitung auf die Einstellung von Skype for Business Online geändert.


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Verschieben eines Benutzers direkt von Skype for Business lokal zu Teams Only

Mit den lokalen Verwaltungstools in Skype for Business Server und Lync Server 2013 können Sie Benutzer in einem einzigen Schritt vom lokalen in den TeamsOnly-Modus verschieben, indem Sie entweder das Cmdlet Move-CsUser in PowerShell oder die Skype for Business Server Systemsteuerung verwenden, wie unten beschrieben. Es ist nicht mehr erforderlich, den Switch und das Verhalten anzugeben, `-MoveToTeams` um direkt von der lokalen Umgebung zu Teams Nur ist jetzt automatisch, unabhängig davon, welche Version von Skype for Business Server oder Lync Server verwendet wird. 

Sie müssen über ausreichende Berechtigungen sowohl in der lokalen Umgebung als auch im Clouddienst (Microsoft 365 oder Office 365) verfügen, wie unter [Erforderliche Administratoranmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)beschrieben. Sie können entweder ein einzelnes Konto verwenden, das in beiden Umgebungen über Berechtigungen verfügt, oder Sie können ein lokales Skype for Business Server Verwaltungsshell-Fenster mit lokalen Anmeldeinformationen starten und den Parameter verwenden, `-Credential` um Anmeldeinformationen für ein Microsoft 365 mit der erforderlichen Administratorrolle anzugeben.

Darüber hinaus müssen Sie sicherstellen, dass dem Benutzer eine Lizenz für Teams (zusätzlich zu Skype for Business Online) gewährt wurde. Deaktivieren Sie nicht die Skype for Business Onlinelizenz.

### <a name="move-to-teams-using-move-csuser"></a>Wechseln zu Teams mithilfe von Move-CsUser

Move-CsUser ist in einem lokalen Skype for Business Server PowerShell-Fenster der Verwaltungsshell oder in einem PowerShell-Fenster der Lync Server-Verwaltungsshell verfügbar. So verschieben Sie einen Benutzer mit Move-CsUser in den TeamsOnly-Modus:
- Geben Sie den Benutzer an, der mit dem Parameter verschoben werden `Identity` soll.
- Geben Sie den `-Target` Parameter mit dem Wert "sipfed.online.lync" an. <span> `-Target`.
- Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen sowohl im lokalen als auch im Clouddienst (Microsoft 365) verfügen, verwenden Sie den `-credential` Parameter, um einem Konto ausreichende Berechtigungen in Microsoft 365 zur Verfügung zu stellen.
- Wenn das Konto mit Berechtigungen in Microsoft 365 nicht in "onmicrosoft" endet. <span> com" müssen Sie den `-HostedMigrationOverrideUrl` Parameter mit dem richtigen Wert angeben, wie unter [Erforderliche administrative Anmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)beschrieben.

Die folgende Cmdlet-Sequenz kann verwendet werden, um einen Benutzer nach TeamsOnly zu verschieben. Dabei wird davon ausgegangen, dass die Microsoft 365 Anmeldeinformationen ein separates Konto ist und als Eingabe für die Get-Credential Eingabeaufforderung angegeben wird. Das Verhalten ist unabhängig davon, ob `-MoveToTeams` ein Schalter angegeben ist, identisch.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> Da es unterschiedliche Umstände gibt, die unterschiedliche Parameter erfordern, lautet der Standardbefehl für die meisten Fälle:

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Wechseln zu Teams mit Skype for Business Server Systemsteuerung

1. Öffnen Sie die Skype for Business Server Systemsteuerungs-App.
2. Wählen Sie in der linken Navigationsleiste **Benutzer** aus.
3. Verwenden Sie **"Suchen",** um die Benutzer zu suchen, die Sie zu Teams verschieben möchten.
4. Wählen Sie die Benutzer aus, und wählen Sie dann im Dropdownmenü **"Aktion"** über der Liste **"Ausgewählte Benutzer verschieben" in Teams** oder **"Ausgewählte Benutzer in Skype for Business Online verschieben"** aus.   Beide Optionen verschieben Benutzer jetzt direkt zu TeamsOnly.
5. Klicken Sie im Assistenten auf **Weiter**.
6. Wenn Sie dazu aufgefordert werden, melden Sie sich bei Microsoft 365 mit einem Konto an, das auf .onmicrosoft.com endet und über ausreichende Berechtigungen verfügt.
7. Klicken Sie auf **"Weiter"** und dann noch einmal auf **"Weiter",** um den Benutzer zu verschieben.
8. Beachten Sie, dass Statusmeldungen zu Erfolg oder Fehler oben in der Haupt-Systemsteuerungs-App und nicht im Assistenten bereitgestellt werden.
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Benachrichtigen Sie Ihre Skype for Business lokalen Benutzer über den bevorstehenden Umstieg auf Teams

Mit den lokalen Verwaltungstools in Skype for Business Server 2015 mit CU8 und in Skype for Business Server 2019 können Sie lokale Skype for Business Benutzer über ihren bevorstehenden Wechsel zu Teams benachrichtigen. Wenn Sie diese Benachrichtigungen aktivieren, wird benutzern eine Benachrichtigung in ihrem Skype for Business Client (Win32, Mac, Web und Mobile) angezeigt, wie unten dargestellt. Wenn Benutzer auf die Schaltfläche **"Ausprobieren"** klicken, wird der Teams-Client gestartet, wenn er installiert ist. andernfalls werden Benutzer in ihrem Browser zur Webversion von Teams navigiert. Wenn Benachrichtigungen aktiviert sind, laden Win32-Skype for Business-Clients standardmäßig den Teams-Client herunter, sodass der Rich-Client verfügbar ist, bevor der Benutzer in den TeamsOnly-Modus verschoben wird. Sie können dieses Verhalten jedoch auch deaktivieren.  Benachrichtigungen werden mithilfe der lokalen Version von `TeamsUpgradePolicy` konfiguriert, und der automatische Download für Win32-Clients wird über das lokale `TeamsUpgradeConfiguration` Cmdlet gesteuert.

> [!TIP]
> Einige Server müssen möglicherweise neu gestartet werden, damit dies in Skype for Business 2015 mit CU8 funktioniert.

![Benachrichtigung über den bevorstehenden Wechsel zu Teams](../media/teams-upgrade-notification.png)

Um lokale Benutzer zu benachrichtigen, dass sie bald auf Teams aktualisiert werden, erstellen Sie eine neue Instanz von TeamsUpgradePolicy mit NotifySfBUsers=true. Weisen Sie diese Richtlinie dann den Benutzern zu, die Sie benachrichtigen möchten, indem Sie die Richtlinie entweder direkt dem Benutzer zuweisen oder indem Sie die Richtlinie auf Standort-, Pool- oder globaler Ebene festlegen. Mit den folgenden Cmdlets wird eine Richtlinie auf Benutzerebene erstellt und erteilt:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Der automatische Download von Teams über den Skype for Business Win32-Client wird über das lokale Cmdlet "TeamsUpgradeConfiguration" mit dem Parameter "DownloadTeams" gesteuert. Sie erstellen diese Konfiguration auf globaler, Standort- und Poolebene. Mit dem folgenden Befehl wird beispielsweise die Konfiguration für den Standort "Redmond1" erstellt:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Standardmäßig ist der Wert von DownloadTeams "True". Es wird jedoch *nur* berücksichtigt, wenn NotifySfbUser = True für einen bestimmten Benutzer.

## <a name="see-also"></a>Weitere Artikel

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Koexistenz mit Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
