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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.custom: ''
description: 'Zusammenfassung: Erfahren Sie, wie Sie Benutzereinstellungen migrieren und Benutzer nach Teams verschieben.'
ms.openlocfilehash: d29fa49e3521e93cb1818c70adb37cfb5019660b
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705844"
---
# <a name="move-users-from-on-premises-to-teams"></a>Verschieben von Benutzern aus lokalen Bereitstellungen nach Microsoft Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Wenn ein Benutzer von der lokalen Umgebung zu "Nur Teams" verschoben wird, wird die Skype for Business des Benutzers von lokal in online verschoben, und dem Benutzer wird "TeamsUpgradePolicy" mit "mode=TeamsOnly" zugewiesen.  Nachdem ein Benutzer aus der lokalen Umgebung in den TeamsOnly-Modus verschoben wird:

- Alle eingehenden Anrufe und Chats von Benutzern (obgleich aus Skype for Business oder Teams gesendet) werden im Team-Client des Benutzers eintreffen.
- Der Benutzer kann mit anderen Benutzern interagieren, die Skype for Business verwenden (egal ob online oder lokal).
- Der Benutzer kann mit Benutzern in Verbundorganisationen kommunizieren.
- Neue Besprechungen, die von diesem Benutzer geplant werden, sind Teams-Besprechungen.
- Benutzer können weiterhin an Skype for Business-Besprechungen teilnehmen. Ab Oktober 2022 können TeamsOnly-Benutzer in Hybridorganisationen jedoch nur anonym an Skype for Business Besprechungen teilnehmen. Ausführliche Informationen finden Sie [unter Was nach der Pensionierung zu erwarten](/microsoftteams/skype-for-business-online-retirement#what-to-expect-post-retirement) ist.
- Die für die Zukunft geplanten bereits vorhandenen Benutzerbesprechungen werden von der lokalen Umgebung zu Teams migriert.
- Kontakte, die lokal vorhanden waren, sind in Teams kurz nachdem sich der Benutzer zum ersten Mal angemeldet hat verfügbar.
- Benutzer können weder Anrufe oder Chats aus Skype for Business initiieren noch neue Besprechungen in Skype for Business planen. Wenn sie versuchen, den Skype for Business-Client zu öffnen, werden sie umgeleitet, um Teams wie unten gezeigt zu verwenden. Wenn der Teams-Client nicht installiert ist, wird er über den Browser an die Webversion von Teams weitergeleitet.<br><br>
    ![Nachricht, die einen Benutzer zu Teams umleitet.](../media/go-to-teams-page.png)

Überprüfen Sie vor dem Verschieben von Benutzern unbedingt die [Voraussetzungen](move-users-between-on-premises-and-cloud.md#prerequisites) , um Benutzer in die Cloud zu verschieben. Lesen Sie außerdem die [Migrations- und Interoperabilitätsanleitungen für Organisationen, die Teams zusammen mit Skype for Business verwenden](/microsoftteams/migration-interop-guidance-for-teams-with-skype).


> [!NOTE]
> Der einheitliche Kontaktspeicher sollte für das lokale SfB-Konto deaktiviert werden, damit der Kontakt nach Teams verschoben wird.

> [!IMPORTANT]
>
> - Beim Verschieben eines Benutzers aus der lokalen Umgebung in die Cloud mit Move-CsUser werden Benutzern automatisch der TeamsOnly-Modus zugewiesen, und ihre Besprechungen aus der lokalen Umgebung werden automatisch in Teams-Besprechungen konvertiert, unabhängig davon, ob der `-MoveToTeams` Wechsel tatsächlich angegeben ist. (Dies umfasst Migrationen von Lync Server 2013, für die der `-MoveToTeams` Wechsel nie ausgeführt wurde.)  Wenn diese Option zuvor nicht angegeben wurde, wurden Benutzer von Skype for Business Server lokal zu Skype for Business Online umgestellt, und ihr Modus blieb unverändert. Dies wurde in Vorbereitung auf die Einstellung von Skype for Business Online geändert.
> - Das Verschieben von Benutzern zwischen Ihrer lokalen Bereitstellung und Teams *erfordert* jetzt aktualisierte Mindestversionen der lokalen Komponenten Skype for Business Server oder Lync Server, die nicht mehr auf der Skype for Business Online-Legacyinfrastruktur basiert. Ausführliche Informationen finden [Sie unter Voraussetzungen](move-users-between-on-premises-and-cloud.md#prerequisites).

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Direktes Verschieben eines Benutzers von Skype for Business lokal zu "Nur Teams"

Mit den lokalen Administratortools in Skype for Business Server und Lync Server 2013 können Sie Benutzer in einem einzigen Schritt vom lokalen in den TeamsOnly-Modus verschieben, indem Sie entweder das cmdlet Move-CsUser in PowerShell oder die Skype for Business Server Systemsteuerung verwenden, wie unten beschrieben. Es ist nicht mehr erforderlich, den `-MoveToTeams` Wechsel anzugeben, und das Verhalten, um direkt von der lokalen Umgebung zu "Teams Only" zu wechseln, ist jetzt automatisch, unabhängig davon, welche Version von Skype for Business Server oder Lync Server verwendet wird. 

Sie müssen über ausreichende Berechtigungen sowohl in der lokalen Umgebung als auch im Clouddienst (Microsoft 365 oder Office 365) verfügen, wie in [den erforderlichen Administratoranmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) beschrieben. Sie können entweder ein einzelnes Konto verwenden, das über Berechtigungen in beiden Umgebungen verfügt, oder Sie können ein lokales Skype for Business Server Verwaltungsshell-Fenster mit lokalen Anmeldeinformationen starten und den `-Credential` Parameter verwenden, um Anmeldeinformationen für ein Microsoft 365 mit der erforderlichen Administrativen Rolle anzugeben.

Darüber hinaus müssen Sie sicherstellen, dass dem Benutzer eine Lizenz für Teams (zusätzlich zu Skype for Business Online) gewährt wurde. Deaktivieren Sie nicht die Skype for Business Online-Lizenz.

### <a name="move-to-teams-using-move-csuser"></a>Wechseln Sie mit Move-CsUser zu Teams

Move-CsUser ist in einem lokalen Skype for Business Server-Verwaltungsshell-PowerShell-Fenster oder in einem Lync Server-Verwaltungsshell-PowerShell-Fenster verfügbar. So verschieben Sie einen Benutzer mit Move-CsUser in den TeamsOnly-Modus:
- Geben Sie den Zu verschiebenden Benutzer mithilfe des Parameters an `Identity` .
- Geben Sie den `-Target` Parameter mit dem Wert "sipfed.online.lync" an.<span> com" (oder ähnlichen Wert, wenn Ihr Mandant Government Cloud ist).
- Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen sowohl in der lokalen Umgebung als auch im Clouddienst (Microsoft 365) verfügen, verwenden Sie den `-credential` Parameter, um ein Konto mit ausreichenden Berechtigungen in Microsoft 365 zur Verfügung zu stellen.
- Wenn das Konto mit Berechtigungen in Microsoft 365 nicht auf "onmicrosoft" endet.<span> com", müssen Sie den `-HostedMigrationOverrideUrl` Parameter mit dem richtigen Wert angeben, wie unter ["Erforderliche Administratoranmeldeinformationen"](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) beschrieben.
- Stellen Sie sicher, dass der Computer, auf dem die lokalen Verwaltungstools ausgeführt werden, das neueste CU für Ihre Version von Skype for Business Server oder Lync Server 2013 verwendet, um sicherzustellen, dass OAuth für die Authentifizierung verwendet wird. 

Die folgende Cmdlet-Sequenz kann verwendet werden, um einen Benutzer nach TeamsOnly zu verschieben. Dabei wird davon ausgegangen, dass die Microsoft 365-Anmeldeinformationen ein separates Konto sind und als Eingabe für die Get-Credential Eingabeaufforderung bereitgestellt werden. Das Verhalten ist identisch, unabhängig davon, ob `-MoveToTeams` ein Schalter angegeben ist oder nicht.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> Da es unterschiedliche Umstände gibt, die unterschiedliche Parameter erfordern, lautet der Standardbefehl für die meisten Fälle:

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Wechseln Sie mithilfe der Skype for Business Server-Systemsteuerung zu Teams

1. Öffnen Sie die Skype for Business Server Systemsteuerung-App.
2. Wählen Sie im linken Navigationsbereich **"Benutzer"** aus.
3. Verwenden Sie **Suchen**, um die Benutzer zu finden, die Sie zu Teams verschieben möchten.
4. Wählen Sie die Benutzer aus, und wählen Sie dann in der Dropdownliste **Aktion** über der Liste die Option Ausgewählte Benutzer in Teams **verschieben oder Ausgewählte** Benutzer in **Skype for Business Online verschieben aus**.   Beide Optionen verschieben Benutzer jetzt direkt zu TeamsOnly.
5. Klicken Sie im Assistenten auf **Weiter**.
6. Wenn Sie dazu aufgefordert werden, melden Sie sich bei Microsoft 365 mit einem Konto an, das auf „.onmicrosoft.com“ endet und über ausreichende Berechtigungen verfügt.
7. Klicken Sie auf **Weiter** und dann noch einmal auf **Weiter**, um den Benutzer zu verschieben.
8. Statusmeldungen zu Erfolg oder Misserfolg werden oben in der Hauptanwendung des Control Panels angezeigt, nicht im Assistenten.
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Benachrichtigen Ihrer Skype for Business lokalen Benutzer über den bevorstehenden Wechsel zu Teams

Mit den lokalen Administratortools in Skype for Business Server 2015 mit CU8 und in Skype for Business Server 2019 können Sie lokale Skype for Business Benutzer über ihren bevorstehenden Wechsel zu Teams informieren. Wenn Sie diese Benachrichtigungen aktivieren, wird Benutzern eine Benachrichtigung in ihrem Skype for Business-Client (Win32, Mac, Web und Mobil) angezeigt, wie unten dargestellt. Wenn Benutzer auf die Schaltfläche " **Testen** " klicken, wird der Teams-Client gestartet, wenn er installiert ist. andernfalls werden Benutzer in ihrem Browser zur Webversion von Teams navigiert. Wenn Benachrichtigungen aktiviert sind, laden Win32-Skype for Business Clients standardmäßig den Teams-Client im Hintergrund herunter, sodass der Rich-Client verfügbar ist, bevor der Benutzer in den TeamsOnly-Modus verschoben wird. Sie können dieses Verhalten jedoch auch deaktivieren.  Benachrichtigungen werden mithilfe der lokalen Version von `TeamsUpgradePolicy`konfiguriert, und der automatische Download für Win32-Clients wird über das lokale `TeamsUpgradeConfiguration` Cmdlet gesteuert.


![Benachrichtigung über den bevorstehenden Wechsel zu Teams.](../media/teams-upgrade-notification.png)

Um lokale Benutzer darüber zu informieren, dass sie bald auf Teams aktualisiert werden, erstellen Sie eine neue Instanz von TeamsUpgradePolicy mit NotifySfBUsers=true. Weisen Sie diese Richtlinie dann den Benutzern zu, die Sie benachrichtigen möchten, indem Sie die Richtlinie entweder direkt dem Benutzer zuweisen oder indem Sie die Richtlinie auf Standort-, Pool- oder globaler Ebene festlegen. Die folgenden Cmdlets erstellen und gewähren eine Richtlinie auf Benutzerebene:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Der automatische Download von Teams über den Skype for Business Win32-Client wird über das lokale Cmdlet "TeamsUpgradeConfiguration" mit dem Parameter "DownloadTeams" gesteuert. Sie erstellen diese Konfiguration auf globaler, Standort- und Poolebene. Der folgende Befehl erstellt beispielsweise die Konfiguration für den Standort Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Standardmäßig ist der Wert von DownloadTeams "True". Es wird jedoch *nur* berücksichtigt, wenn NotifySfbUser = True für einen bestimmten Benutzer gilt.

## <a name="see-also"></a>Siehe auch

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Koexistenz mit Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
