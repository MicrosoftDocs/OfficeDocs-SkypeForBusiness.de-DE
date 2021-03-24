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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Benutzereinstellungen migrieren und Benutzer zu Teams verschieben.'
ms.openlocfilehash: 4a57d802d6405652724ce28ed2d26221dcc8db0f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110651"
---
# <a name="move-users-from-on-premises-to-teams"></a>Verschieben von Benutzern aus lokalen Bereitstellungen nach Microsoft Teams

Wenn ein Benutzer von lokal zu Teams Only verschoben wird, wird das Skype for Business-Heim des Benutzers von lokal in online verschoben, und dem Benutzer wird TeamsUpgradePolicy mit mode=TeamsOnly zugewiesen.  Nachdem ein Benutzer vom lokalen in den TeamsOnly-Modus verschoben wurde:

- Alle eingehenden Anrufe und Chats von anderen Benutzern (unabhängig davon, ob sie von Skype for Business oder Teams gesendet werden) werden im Teams-Client des Benutzers landen.
- Der Benutzer kann mit anderen Benutzern zusammenarbeiten, die Skype for Business (online oder lokal) verwenden.
- Der Benutzer kann mit Benutzern in Verbundorganisationen kommunizieren.
- Neue Besprechungen, die von diesem Benutzer geplant werden, sind Teams-Besprechungen.
- Der Benutzer kann weiterhin an allen Skype for Business-Besprechungen teilnehmen.
- Die bereits vorhandenen Besprechungen des Benutzers, die für die Zukunft geplant sind, werden von lokalen zu Teams migriert.
- Kontakte, die lokal vorhanden waren, sind in Teams kurz nachdem sich der Benutzer zum ersten Mal anmeldet.
- Benutzer können weder Anrufe oder Chats von Skype for Business initiieren noch neue Besprechungen in Skype for Business planen. Wenn sie versuchen, den Skype for Business-Client zu öffnen, werden sie umgeleitet, um Teams wie unten gezeigt zu verwenden. Wenn der Teams-Client nicht installiert ist, wird er über seinen Browser an die Webversion von Teams geleitet.<br><br>
    ![Nachricht, die einen Benutzer an Teams umleite](../media/go-to-teams-page.png)

Überprüfen Sie vor dem Verschieben von Benutzern unbedingt die Voraussetzungen, [um](move-users-between-on-premises-and-cloud.md#prerequisites) Benutzer in die Cloud zu verschieben. Lesen Sie außerdem die [Migrations- und Interoperabilitätsanleitungen für Organisationen, die Teams zusammen mit Skype for Business verwenden.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)


> [!NOTE]
> Der einheitliche Kontaktspeicher sollte auf dem vorkonsistenten SfB-Konto deaktiviert werden, damit der Kontakt nach Teams verschoben werden kann.


Es gibt zwei Methoden zum Verschieben eines Benutzers von lokalen zu Teams:

- Wenn Sie eine Version früher als Skype for Business Server 2015 CU8 verwenden, erfordert die Bewegung zwei Schritte (die bei Bedarf als ein einziger Schritt gemeinsam ausgeführt werden können):
  - [Verschieben Sie den Benutzer von Skype for Business Server (lokal) zu Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).
  - Nachdem der Benutzer in Skype for Business Online zu Hause ist, weisen Sie dem Benutzer TeamsUpgradePolicy mit mode= TeamsOnly zu. Führen Sie das folgende Cmdlet aus einem Skype for Business Online PowerShell-Fenster aus, um den TeamsOnly-Modus zu gewähren: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Wenn Sie über Administratortools von Skype for Business Server 2015 CU8 oder höher verfügen, können Sie die oben beschriebene Methode verwenden, oder Sie können diese Bewegung in einem Schritt wie unten beschrieben tun. Darüber hinaus können Sie optional eine Benachrichtigung innerhalb des Skype for Business-Clients bereitstellen, bevor Sie sie zu Teams Only verschieben, sowie optional den Teams-Client automatisch vom Skype for Business-Client herunterladen lassen.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Verschieben eines Benutzers direkt aus Skype for Business lokal zu Teams Only

Mit den lokalen Verwaltungstools in Skype for Business Server 2015 mit CU8 sowie in Skype for Business Server 2019 können Sie Benutzer in einem einzigen Schritt mithilfe des cmdlets Move-CsUser in PowerShell oder der Skype for Business Server-Systemsteuerung in einen einzigen Schritt verschieben, wie unten beschrieben.

### <a name="move-to-teams-using-move-csuser"></a>Wechseln zu Teams mithilfe Move-CsUser

Move-CsUser ist über ein lokales Skype for Business Management Shell PowerShell-Fenster verfügbar. Die folgenden Schritte und erforderlichen Berechtigungen sind identisch mit dem Verschieben eines Benutzers zu Skype for Business Online, mit der Ausnahme, dass Sie auch die Option MoveToTeams angeben müssen und sicherstellen müssen, dass dem Benutzer auch eine Lizenz für Teams (zusätzlich zu Skype for Business Online) erteilt wurde.

Sie müssen über ausreichende Berechtigungen sowohl in der lokalen Umgebung als auch im Clouddienst (Microsoft 365 oder Office 365) verfügen, wie unter Erforderliche administrative Anmeldeinformationen [beschrieben.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Sie können entweder ein einzelnes Konto mit Berechtigungen in beiden Umgebungen verwenden oder ein lokales Skype for Business Server Management Shell-Fenster mit lokalen Anmeldeinformationen starten und den Parameter verwenden, um Anmeldeinformationen für ein `-Credential` Microsoft 365- oder Office 365-Konto mit der erforderlichen Administratorrolle anzugeben.

So verschieben Sie einen Benutzer mithilfe von Move-CsUser in den Modus "Teams Only":

- Geben Sie den Benutzer an, der mit dem Parameter bewegt `Identity` werden soll.
- Geben Sie den -Target-Parameter mit dem Wert "sipfed.online.lync" an. <span> com".
- Geben Sie die `MoveToTeams` Option an.
- Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen sowohl lokal als auch im Clouddienst verfügen (Microsoft 365 oder Office 365), verwenden Sie den Parameter, um ein Konto mit ausreichenden Berechtigungen `-credential` in Office 365 zu versorgen.
- Wenn das Konto mit Berechtigungen in Microsoft 365 oder Office 365 nicht in "onmicrosoft" endet. <span> com", müssen Sie den Parameter mit dem richtigen Wert angeben, wie `-HostedMigrationOverrideUrl` unter Erforderliche administrative [Anmeldeinformationen beschrieben.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

Die folgende Cmdletsequenz kann verwendet werden, um einen Benutzer zu TeamsOnly zu verschieben, und es wird davon ausgegangen, dass die Microsoft 365- oder Office 365-Anmeldeinformationen ein separates Konto sind und als Eingabe für die Eingabeaufforderung Get-Credential werden.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> Da unterschiedliche Umstände unterschiedliche Parameter erfordern, ist der Standardbefehl in den meisten Fällen:

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Wechseln zu Teams mithilfe der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerungs-App.
2. Wählen Sie in der linken Navigationsleiste **Benutzer aus.**
3. Verwenden **Sie Suchen,** um die Benutzer zu finden, die Sie zu Teams verschieben möchten.
4. Wählen Sie die Benutzer aus, und  wählen Sie dann im Dropdownmenü Aktion über der Liste ausgewählte Benutzer **in Teams verschieben aus.**
5. Klicken Sie im Assistenten auf **Weiter**.
6. Wenn Sie dazu aufgefordert werden, melden Sie sich bei Microsoft 365 oder Office 365 mit einem Konto an, das in .onmicrosoft.com endet und über ausreichende Berechtigungen verfügt.
7. Klicken **Sie auf Weiter,** und klicken Sie dann **noch** einmal, um den Benutzer zu verschieben.
8. Beachten Sie, dass Statusmeldungen zu Erfolg oder Fehler oben in der Systemsteuerungs-App und nicht im Assistenten bereitgestellt werden.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Benachrichtigen Ihrer lokalen Skype for Business-Benutzer über den bevorstehenden Wechsel zu Teams

Mit den lokalen Verwaltungstools in Skype for Business Server 2015 mit CU8 sowie in Skype for Business Server 2019 können Sie lokale Skype for Business-Benutzer über ihren bevorstehenden Wechsel zu Teams benachrichtigen. Wenn Sie diese Benachrichtigungen aktivieren, wird benutzern eine Benachrichtigung im Skype for Business-Client (Win32, Mac, Web und Mobile) angezeigt, wie unten gezeigt. Wenn Benutzer auf die Schaltfläche **Testen** klicken, wird der #A0 gestartet, wenn er installiert ist. Andernfalls werden Benutzer in ihrem Browser zur Webversion von Teams navigiert. Wenn Benachrichtigungen aktiviert sind, laden Win32 Skype for #A0 standardmäßig den #A1 automatisch herunter, damit der Rich-Client verfügbar ist, bevor der Benutzer in den Modus "Teams Only" wechselt. Sie können dieses Verhalten jedoch auch deaktivieren.  Benachrichtigungen werden mithilfe der lokalen Version von konfiguriert, und der automatische Download für Win32-Clients wird über das lokale `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` Cmdlet gesteuert.

> [!TIP]
> Einige Server müssen möglicherweise neu gestartet werden, damit dies in Skype for Business 2015 mit CU8 funktioniert.

![Benachrichtigung über bevorstehenden Wechsel zu Teams](../media/teams-upgrade-notification.png)

Erstellen Sie eine neue Instanz von TeamsUpgradePolicy mit NotifySfBUsers=true, um lokale Benutzer darüber zu informieren, dass sie bald auf Teams aktualisiert werden. Weisen Sie diese Richtlinie dann den Benutzern zu, die Sie benachrichtigen möchten, indem Sie die Richtlinie entweder direkt dem Benutzer zuweisen oder die Richtlinie auf Standort-, Pool- oder globaler Ebene festlegen. Die folgenden Cmdlets erstellen und erteilen eine Richtlinie auf Benutzerebene:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Der automatische Download von Teams über den Skype for Business Win32-Client wird über das lokale TeamsUpgradeConfiguration-Cmdlet mit dem Parameter DownloadTeams gesteuert. Sie erstellen diese Konfiguration auf globaler, Standort- und Poolebene. Mit dem folgenden Befehl wird beispielsweise die Konfiguration für den Standort "Redmond1" erstellt:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Standardmäßig ist der Wert von DownloadTeams True. Es wird jedoch nur *berücksichtigt,* wenn NotifySfbUser = True für einen bestimmten Benutzer ist.

## <a name="see-also"></a>Siehe auch

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Koexistenz mit Skype for Business](/microsoftteams/coexistence-chat-calls-presence)