---
title: Verschieben von Benutzern aus Skype for Business Server 2019 in Teams
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Benutzereinstellungen migrieren und Benutzer zu Teams.'
ms.openlocfilehash: 1d2542d3c5b67e935449b4f6fee60506b9232adc
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306019"
---
# <a name="move-users-from-on-premises-to-teams"></a>Verschieben von Benutzern aus lokalen Bereitstellungen nach Microsoft Teams

Wenn ein Benutzer von lokal nach Teams Nur verschoben wird, wird das Skype for Business-Heim des Benutzers von lokal in online verschoben, und dem Benutzer wird TeamsUpgradePolicy mit mode=TeamsOnly zugewiesen.  Nachdem ein Benutzer vom lokalen in den TeamsOnly-Modus verschoben wurde:

- Alle eingehenden Anrufe und Chats von anderen Benutzern (unabhängig davon, ob sie von Skype for Business oder Teams gesendet werden) werden im Client des Benutzers Teams landen.
- Der Benutzer kann mit anderen Benutzern zusammenarbeiten, die Skype for Business (online oder lokal) verwenden.
- Der Benutzer kann mit Benutzern in Verbundorganisationen kommunizieren.
- Neue Besprechungen, die von diesem Benutzer geplant werden, werden Teams werden.
- Der Benutzer kann weiterhin an Skype for Business teilnehmen.
- Die bereits vorhandenen Besprechungen des Benutzers, die für die Zukunft geplant sind, werden von lokalen zu Teams.
- Kontakte, die lokal vorhanden waren, sind in Teams, nachdem sich der Benutzer zum ersten Mal anmeldet.
- Benutzer können keine Anrufe oder Chats von Skype for Business initiieren und auch keine neuen Besprechungen in Skype for Business. Wenn sie versuchen, den Skype for Business zu öffnen, werden sie umgeleitet, um Teams wie unten gezeigt zu verwenden. Wenn der Teams nicht installiert ist, wird er über seinen Browser Teams die Webversion des Clients geleitet.<br><br>
    ![Nachricht, die einen Benutzer an Teams](../media/go-to-teams-page.png)

Überprüfen Sie vor dem Verschieben von Benutzern unbedingt die Voraussetzungen, [um](move-users-between-on-premises-and-cloud.md#prerequisites) Benutzer in die Cloud zu verschieben. Lesen Sie außerdem migrations- und [interoperabilitätsanleitungen](/microsoftteams/migration-interop-guidance-for-teams-with-skype)für Organisationen, die Teams zusammen mit Skype for Business.


> [!NOTE]
> Unified Contact Store sollte für das on-prem SfB-Konto deaktiviert werden, damit der Kontakt in die Teams.


Es gibt *derzeit zwei* Methoden zum Verschieben eines Benutzers von einem lokalen Teams:

- Wenn Sie eine Version vor Skype for Business Server 2015 CU8 verwenden, erfordert die Bewegung zwei Schritte (die bei Bedarf als ein einziger Schritt gemeinsam ausgeführt werden können):
  - [Verschieben Sie den Benutzer von Skype for Business Server (lokal) zu Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).
  - Sobald der Benutzer in Skype for Business Online homed ist, weisen Sie dem Benutzer TeamsUpgradePolicy mit mode= TeamsOnly zu. Führen Sie zum Gewähren des TeamsOnly-Modus das folgende Cmdlet aus einem Skype for Business Online PowerShell-Fenster aus:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Wenn Sie über Administratortools aus Skype for Business Server 2015 KU8 oder höher verfügen, können Sie die oben beschriebene Methode verwenden, oder Sie können diese Bewegung in einem Schritt wie unten beschrieben tun. Darüber hinaus können Sie optional eine Benachrichtigung innerhalb des Skype for Business-Clients bereitstellen, bevor Sie sie auf Teams Nur verschieben und optional den Teams-Client automatisch vom Skype for Business-Client herunterladen lassen.

> [!NOTE]
> In Vorbereitung auf den bevorstehenden Skype for Business von Skype for Business Online vereinfacht Microsoft den Wechsel von Organisationen zu Teams in naher Zukunft. Wenn ein Benutzer von einer lokalen in eine Teams wird, ist es bald nicht mehr erforderlich, den Umstieg anzugeben, um Benutzer direkt von lokalen zu `-MoveToTeams` `Move-CsUser` TeamsOnly zu verschieben. Wenn diese Option derzeit nicht angegeben ist, wechseln Benutzer von der lokalen Skype for Business Server zu Skype for Business Online, und ihr Modus bleibt unverändert. Wenn ein Benutzer nach dem Ausscheiden aus der lokalen Cloud mit in die Cloud wechselt, wird benutzern automatisch der TeamsOnly-Modus zugewiesen, und ihre Besprechungen werden automatisch in Teams Besprechungen konvertiert, so als ob der , unabhängig davon, ob die Option tatsächlich angegeben `Move-CsUser` `-MoveToTeams switch had been specified` ist. Wir gehen davon aus, dass diese Funktionalität vor dem tatsächlichen Ausstand vom 31. Juli 2021 veröffentlicht wird.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Verschieben eines Benutzers direkt aus Skype for Business lokalen Teams

Mit den lokalen Verwaltungstools in Skype for Business Server 2015 mit CU8 sowie in Skype for Business Server 201 Teams 9 können Sie Benutzer in einem einzigen Schritt mithilfe des cmdlets Move-CsUser in PowerShell oder der Skype for Business Server-Systemsteuerung in einen einzigen Schritt verschieben, wie unten beschrieben.

### <a name="move-to-teams-using-move-csuser"></a>Wechseln zu Teams mithilfe Move-CsUser

Move-CsUser ist über ein lokales Skype for Business Management Shell PowerShell-Fenster verfügbar. Die folgenden Schritte und erforderlichen Berechtigungen sind identisch mit dem Verschieben eines Benutzers zu Skype for Business Online, mit der Ausnahme, dass Sie auch die Option MoveToTeams angeben müssen und sicherstellen müssen, dass dem Benutzer auch eine Lizenz für Teams (zusätzlich zu Skype for Business Online) erteilt wurde.

Sie müssen über ausreichende Berechtigungen sowohl in der lokalen Umgebung als auch im Clouddienst (Microsoft 365 oder Office 365) verfügen, wie unter Erforderliche administrative Anmeldeinformationen [beschrieben.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Sie können entweder ein einzelnes Konto verwenden, das in beiden Umgebungen über Berechtigungen verfügt, oder Sie können ein lokales Skype for Business Server-Verwaltungsshellfenster mit lokalen Anmeldeinformationen starten und den Parameter verwenden, um Anmeldeinformationen für ein Microsoft 365- oder Office 365-Konto mit der erforderlichen Administratorrolle `-Credential` anzugeben.

So verschieben Sie einen Benutzer mithilfe von Move-CsUser Teams in den Modus "Nur":

- Geben Sie den Benutzer an, der mit dem Parameter bewegt `Identity` werden soll.
- Geben Sie den -Target-Parameter mit dem Wert "sipfed.online.lync" an. <span> com".
- Geben Sie die `MoveToTeams` Option an.
- Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen sowohl lokal als auch im Clouddienst (Microsoft 365 oder Office 365) verfügen, verwenden Sie den Parameter, um einem Konto ausreichende Berechtigungen `-credential` in Office 365.
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

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Wechseln zu Teams mithilfe Skype for Business Server Systemsteuerung

1. Öffnen Sie Skype for Business Server Systemsteuerungs-App.
2. Wählen Sie in der linken Navigationsleiste **Benutzer aus.**
3. Verwenden **Sie Suchen,** um die Benutzer zu finden, die Sie zu einem anderen Teams.
4. Wählen Sie die Benutzer aus, und  klicken Sie dann im Dropdownmenü Aktion über der Liste auf Ausgewählte Benutzer in Teams **.**
5. Klicken Sie im Assistenten auf **Weiter**.
6. Wenn Sie dazu aufgefordert werden, melden Sie sich Microsoft 365 oder Office 365 mit einem Konto an, das in .onmicrosoft.com endet und über ausreichende Berechtigungen verfügt.
7. Klicken **Sie auf Weiter,** und klicken Sie dann **noch** einmal, um den Benutzer zu verschieben.
8. Beachten Sie, dass Statusmeldungen zu Erfolg oder Fehler oben in der Systemsteuerungs-App und nicht im Assistenten bereitgestellt werden.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Benachrichtigen Sie Skype for Business lokalen Benutzern über den bevorstehenden Wechsel zu Teams

Die lokalen Verwaltungstools in Skype for Business Server 2015 mit CU8 sowie in Skype for Business Server 2019 ermöglichen es Ihnen, lokale Skype for Business-Benutzer über ihren bevorstehenden Wechsel nach Teams zu benachrichtigen. Wenn Sie diese Benachrichtigungen aktivieren, wird benutzern eine Benachrichtigung im Skype for Business -Client (Win32, Mac, Web und Mobile) angezeigt, wie unten gezeigt. Wenn Benutzer auf **die** Schaltfläche Ausprobieren klicken, wird Teams client gestartet, wenn er installiert ist. Andernfalls werden Benutzer zur Webversion von Teams browser navigiert. Wenn Benachrichtigungen aktiviert sind, laden Win32 Skype for Business-Clients standardmäßig den Teams-Client herunter, sodass der Rich-Client verfügbar ist, bevor der Benutzer in den Teams-Modus wechselt. Sie können dieses Verhalten jedoch auch deaktivieren.  Benachrichtigungen werden mithilfe der lokalen Version von konfiguriert, und der automatische Download für Win32-Clients wird über das lokale `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` Cmdlet gesteuert.

> [!TIP]
> Einige Server müssen möglicherweise neu gestartet werden, damit dies in Skype for Business 2015 mit CU8 funktioniert.

![Benachrichtigung über bevorstehenden Teams](../media/teams-upgrade-notification.png)

Erstellen Sie eine neue Instanz von TeamsUpgradePolicy mit NotifySfBUsers=true, um lokale Benutzer darüber zu informieren, dass sie bald auf Teams aktualisiert werden. Weisen Sie diese Richtlinie dann den Benutzern zu, die Sie benachrichtigen möchten, indem Sie die Richtlinie entweder direkt dem Benutzer zuweisen oder die Richtlinie auf Standort-, Pool- oder globaler Ebene festlegen. Die folgenden Cmdlets erstellen und erteilen eine Richtlinie auf Benutzerebene:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Der automatische Download Teams über den Skype for Business Win32-Client wird über das lokale TeamsUpgradeConfiguration-Cmdlet mit dem Parameter DownloadTeams gesteuert. Sie erstellen diese Konfiguration auf globaler, Standort- und Poolebene. Mit dem folgenden Befehl wird beispielsweise die Konfiguration für den Standort "Redmond1" erstellt:

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
