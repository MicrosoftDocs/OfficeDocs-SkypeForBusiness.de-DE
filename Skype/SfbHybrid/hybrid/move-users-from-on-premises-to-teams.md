---
title: Migrieren von Benutzern von Skype for Business Server 2019 in Microsoft Teams
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Benutzereinstellungen migrieren und Benutzer in Microsoft Teams verschieben.'
ms.openlocfilehash: 49763d7674946eb179188554326863f4860252c3
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130646"
---
# <a name="move-users-from-on-premises-to-teams"></a>Verschieben von Benutzern aus der lokalen Bereitstellung nach Microsoft Teams

Wenn ein Benutzer nur von einem Standort in ein Microsoft Teams verschoben wird, wird der Skype for Business Home des Benutzers von lokal in Online verschoben, und dem Benutzer wird TeamsUpgradePolicy mit Mode = TeamsOnly zugewiesen.  Nachdem ein Benutzer vom lokalen in den TeamsOnly-Modus verschoben wurde:

- Alle eingehenden Anrufe und Chats von anderen Benutzern (unabhängig davon, ob Sie von Skype for Business oder Teams gesendet werden) werden im Microsoft Teams-Client des Benutzers landen.
- Der Benutzer kann mit anderen Benutzern zusammenarbeiten, die Skype for Business verwenden (ob online oder lokal).
- Der Benutzer ist in der Lage, mit Benutzern in Verbundorganisationen zu kommunizieren.
- Neue Besprechungen, die von diesem Benutzer geplant werden, sind Microsoft Teams-Besprechungen.
- Der Benutzer kann weiterhin an allen Skype for Business Besprechungen teilnehmen.
- Die bereits vorhandenen Besprechungen des Benutzers, die für die Zukunft geplant sind, werden von lokalen zu Teams migriert.
- Kontakte, die lokal vorhanden waren, sind in Microsoft Teams verfügbar, kurz nachdem sich der Benutzer zum ersten Mal anmeldet.
- Benutzer können keine Anrufe oder Chats von Skype for Business initiieren und keine neuen Besprechungen in Skype for Business planen. Wenn Sie versuchen, den Skype for Business-Client zu öffnen, werden Sie wie unten dargestellt zur Verwendung von Teams umgeleitet. Wenn der Microsoft Teams-Client nicht installiert ist, werden Sie mithilfe des Browsers an die Webversion von Teams weitergeleitet.<br><br>
    ![Nachrichten, die einen Benutzer zu Teams umleiten](../media/go-to-teams-page.png)

Lesen Sie vor dem Verschieben von Benutzern unbedingt die [Voraussetzungen](move-users-between-on-premises-and-cloud.md#prerequisites) , um Benutzer in die Cloud zu verschieben. Stellen Sie außerdem sicher, dass [Migrations-und Interoperabilitäts Anleitungen für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](/microsoftteams/migration-interop-guidance-for-teams-with-skype), überprüft werden.


> [!NOTE]
> Der Unified Contact Store sollte auf dem SFB-Konto auf dem Prem deaktiviert sein, damit der Kontakt in Microsoft Teams verschoben werden kann.


Es gibt zwei Methoden, um einen Benutzer von lokal in Microsoft Teams zu migrieren:

- Wenn Sie eine frühere Version als Skype for Business Server 2015 ku8 verwenden, erfordert die Verlagerung zwei Schritte (Dies kann bei Bedarf als einzelner Schritt als Skript erstellt werden):
  - Stellen [Sie den Benutzer aus Skype for Business Server (lokal) in Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).
  - Nachdem der Benutzer in Skype for Business Online verwaltet wurde, weisen Sie den Benutzer TeamsUpgradePolicy mit Mode = TeamsOnly zu. Um den TeamsOnly-Modus zu gewähren, führen Sie das folgende Cmdlet aus einem Skype for Business Online PowerShell-Fenster aus: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Wenn Sie über Administrator Tools von Skype for Business Server 2015 ku8 oder höher verfügen, können Sie die obige Methode verwenden, oder Sie können diese Schritte wie unten beschrieben in einem einzigen Schritt durchführen. Darüber hinaus können Sie optional eine Benachrichtigung im Skype for Business-Client bereitstellen, bevor Sie Sie in Microsoft Teams verschieben und optional den Microsoft Teams-Client automatisch vom Skype for Business-Client herunterladen lassen.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Direkte Verlagerung eines Benutzers aus Skype for Business lokal in Microsoft Teams

Mithilfe der lokalen Verwaltungstools in Skype for Business Server 2015 mit ku8 sowie in Skype for Business Server 2019 können Sie Benutzer in einem einzigen Schritt von lokal in den Microsoft Teams-Modus versetzen, indem Sie entweder das Move-CsUser-Cmdlet in PowerShell oder die Skype for Business Server-Systemsteuerung verwenden, wie unten beschrieben.

### <a name="move-to-teams-using-move-csuser"></a>Wechsel zu Microsoft Teams mit Move-CsUser

Move-CsUser steht in einem lokalen Skype for Business-Verwaltungsshell PowerShell-Fenster zur Verfügung. Die folgenden Schritte und die erforderlichen Berechtigungen sind identisch mit dem Verschieben eines Benutzers in Skype for Business Online, es sei denn, Sie müssen auch den MoveToTeams-Switch angeben, und Sie müssen sicherstellen, dass dem Benutzer auch eine Lizenz für Teams erteilt wurde (zusätzlich zu Skype for Business Online).

Sie müssen über ausreichende Berechtigungen sowohl in der lokalen Umgebung als auch im clouddienst (Microsoft 365 oder Office 365) verfügen, wie unter [erforderliche administrative Anmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)beschrieben. Sie können entweder ein einzelnes Konto verwenden, das über Berechtigungen in beiden Umgebungen verfügt, oder Sie können ein lokales Skype for Business Server-Verwaltungsshell-Fenster mit lokalen Anmeldeinformationen starten und den Parameter verwenden, `-Credential` um Anmeldeinformationen für ein Microsoft 365-oder Office 365-Konto mit der erforderlichen Administratorrolle anzugeben.

So stellen Sie einen Benutzer mithilfe von "CsUser" in den Microsoft Teams-Modus um:

- Geben Sie den Benutzer an, der mithilfe des `Identity` Parameters zu navigieren ist.
- Geben Sie den-target-Parameter mit dem Wert "sipfed. online. lync" an. <span> com ".
- Geben Sie den `MoveToTeams` Schalter an.
- Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen sowohl lokal als auch über den clouddienst verfügen (Microsoft 365 oder Office 365), verwenden Sie den- `-credential` Parameter, um ein Konto mit ausreichenden Berechtigungen in Office 365 bereitzustellen.
- Wenn das Konto mit den Berechtigungen in Microsoft 365 oder Office 365 nicht auf "onmicrosoft" endet. <span> com "müssen Sie den `-HostedMigrationOverrideUrl` Parameter mit dem korrekten Wert angeben, wie unter" [erforderliche administrative Anmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)"beschrieben.

Die folgende Cmdlet-Sequenz kann verwendet werden, um einen Benutzer zu TeamsOnly zu migrieren, und nimmt an, dass die Anmeldeinformationen von Microsoft 365 oder Office 365 ein separates Konto sind und als Eingabe für die Get-Credential-Eingabeaufforderung angegeben werden.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Navigieren zu Microsoft Teams mithilfe Skype for Business Server Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung-app.
2. Wählen Sie im linken Navigationsbereich **Benutzer** aus.
3. Verwenden Sie **Suchen** , um die Benutzer zu finden, die Sie in Teams verschieben möchten.
4. Wählen Sie die Benutzer aus, und wählen Sie dann im Dropdownmenü **Aktion** oberhalb der Liste die Option **ausgewählte Benutzer in Teams verlagern** aus.
5. Klicken Sie im Assistenten auf **Weiter**.
6. Wenn Sie dazu aufgefordert werden, melden Sie sich bei Microsoft 365 oder Office 365 mit einem Konto an, das in. onmicrosoft.com endet und über ausreichende Berechtigungen verfügt.
7. Klicken Sie auf **weiter** und dann auf **weiter** , um den Benutzer zu verlagern.
8. Beachten Sie, dass Statusmeldungen bezüglich Erfolg oder Fehler oben in der Hauptsystem Steuerung-APP, nicht im Assistenten angegeben werden.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Benachrichtigen Ihrer Skype for Business lokalen Benutzern über den bevorstehenden Wechsel zu Microsoft Teams

Mithilfe der lokalen Verwaltungstools in Skype for Business Server 2015 mit ku8 sowie Skype for Business Server 2019 können Sie lokale Skype for Business Benutzer über Ihren bevorstehenden Wechsel zu Microsoft Teams informieren. Wenn Sie diese Benachrichtigungen aktivieren, wird den Benutzern eine Benachrichtigung in Ihrem Skype for Business-Client (Win32, Mac, Internet und Mobile) angezeigt, wie unten dargestellt. Wenn Benutzer auf die Schaltfläche " **Testen** " klicken, wird der Microsoft Teams-Client bei der Installation gestartet. Andernfalls werden die Benutzer in Ihrem Browser zur Webversion von Microsoft Teams navigiert. Wenn Benachrichtigungen aktiviert werden, lädt Win32 Skype for Business Clients den Microsoft Teams-Client automatisch herunter, sodass der Rich-Client verfügbar ist, bevor der Benutzer in den Microsoft Teams-Modus verschoben wird. Sie können dieses Verhalten jedoch auch deaktivieren.  Benachrichtigungen werden mit der lokalen Version von konfiguriert `TeamsUpgradePolicy` , und der unbeaufsichtigte Download für Win32-Clients wird über das lokale `TeamsUpgradeConfiguration` Cmdlet gesteuert.

> [!TIP]
> Einige Server müssen möglicherweise neu gestartet werden, damit diese in Skype for Business 2015 mit ku8 funktionieren.

![Benachrichtigung über bevorstehendes umsteigen in Teams](../media/teams-upgrade-notification.png)

Um lokale Benutzer darüber zu informieren, dass Sie bald auf Microsoft Teams aktualisiert werden, erstellen Sie eine neue Instanz von TeamsUpgradePolicy mit NotifySfBUsers = true. Weisen Sie diese Richtlinie dann den Benutzern zu, die Sie benachrichtigen möchten, indem Sie die Richtlinie entweder direkt dem Benutzer zuweisen oder indem Sie die Richtlinie auf Standort-, Pool-oder globaler Ebene festlegen. Mit den folgenden Cmdlets wird eine Richtlinie auf Benutzerebene erstellt und erteilt:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Das automatische Herunterladen von Microsoft Teams über den Skype for Business Win32-Client wird über das lokale TeamsUpgradeConfiguration-Cmdlet mit dem Parameter DownloadTeams gesteuert. Sie erstellen diese Konfiguration auf globaler Ebene, auf Standort-und Poolebene. Mit dem folgenden Befehl wird beispielsweise die Konfiguration für die Website "redmond1" erstellt:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Der Wert von DownloadTeams ist standardmäßig true; Es wird jedoch *nur* dann berücksichtigt, wenn NotifySfbUser = true für einen bestimmten Benutzer ist.

## <a name="see-also"></a>Weitere Artikel

[CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Koexistenz mit Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
