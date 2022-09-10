---
title: E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen ändern
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Erfahren Sie, welche Informationen automatisch per E-Mail an Benutzer gesendet werden, wenn sich ihre Einstellungen für Einwahlkonferenzen in Microsoft Teams ändern. '
ms.openlocfilehash: b2ebb07562300a02058f3bfeaad103347299ba0c
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642136"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen in Microsoft Teams ändern

E-Mails werden automatisch an Benutzer gesendet, die [für Audiokonferenzen](set-up-audio-conferencing-in-teams.md) mit Microsoft als Audiokonferenzanbieter aktiviert sind.

Standardmäßig gibt es vier Arten von E-Mails, die an Ihre Benutzer gesendet werden, die für Audiokonferenzen aktiviert sind. Wenn Sie die Anzahl von E-Mails, die an die Benutzer gesendet werden, einschränken möchten, können Sie diese Einstellung deaktivieren. Audiokonferenzen in Microsoft 365 oder Office 365 senden in folgenden Fällen E-Mails an die E-Mails Ihrer Benutzer:

- **Ihnen wird eine Audiokonferenzlizenz zugewiesen oder wenn Sie den Audiokonferenzanbieter in Microsoft ändern.**

     Diese E-Mail enthält die Konferenz-ID, die Standardtelefonnummer für die Besprechungen, die Audiokonferenz-PIN für den Benutzer sowie die Anweisungen und den Link zum Verwenden des Teams-Besprechungsupdatetools, das zum Aktualisieren vorhandener Besprechungen für den Benutzer verwendet wird. Siehe [Zuweisen von Microsoft Teams-Add-On-Lizenzen](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Weitere Informationen finden Sie [im Artikel "Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer zugewiesen ist](see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams.md) ".

    So kann diese E-Mail aussehen:

     ![Teams Verify License.](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft Teams-Add-On-Lizenzierung](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

- **Sich die Konferenz-ID oder die Standardtelefonnummer eines Benutzers ändert.**

    Diese E-Mail enthält die Konferenz-ID, die Standardtelefonnummer der Konferenz und die Anweisungen und den Link zur Verwendung des Teams-Besprechungsupdatetools, das zum Aktualisieren vorhandener Besprechungen für den Benutzer verwendet wird. Diese E-Mail enthält jedoch nicht die Audiokonferenz-PIN des Benutzers. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).

    So kann diese E-Mail aussehen:

     ![Die Informationen für Dial-In-Konferenzen wurden geändert.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **Die Audiokonferenz-PIN eines Benutzers wird zurückgesetzt.**

    Diese E-Mail enthält die Audiokonferenz-PIN des Organisators, die vorhandene Konferenz-ID und die Standardtelefonnummer der Konferenz für den Benutzer. Siehe [Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md).

     So kann diese E-Mail aussehen:

     ![Die PIN für die Dial-In-Konferenz wurde geändert.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **Die Lizenz eines Benutzers wird entfernt, oder wenn sich der Audiokonferenzanbieter von Microsoft zu einem anderen Anbieter oder keinem anbieter ändert.**

    Dies geschieht, wenn die **Audiokonferenzlizenz** von einem Benutzer entfernt wird oder wenn der Audiokonferenzanbieter auf **"Keine**" festgelegt wird.

    Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Microsoft 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    So kann diese E-Mail aussehen:

     !["Dial-In-Konferenzen" ist deaktiviert.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Änderungen an den E-Mail-Nachrichten, die ihnen geschickt werden

Sie können Änderungen an der E-Mail vornehmen, die automatisch an Benutzer gesendet wird. Standardmäßig stammt der Absender der E-Mails von Microsoft 365 oder Office 365, Aber Sie können den Anzeigenamen mithilfe von Windows PowerShell ändern. Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz](/powershell/module/teams/?view=teams-ps) .

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Wie gehen Sie vor, wenn Sie Benutzern keine E-Mails senden möchten?

Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails an die Benutzer gesendet, auch nicht, wenn ihnen eine Lizenz zugewiesen wird. In diesem Fall werden die Konferenz-ID, die Standardtelefonnummer für Konferenzen und, was noch wichtiger ist, ihre Audiokonferenz-PIN nicht an den Benutzer gesendet. Wenn dies geschieht, müssen Sie dem Benutzer eine separate E-Mail schreiben oder ihn anrufen, um ihm diese Mitteilung zu machen.

Standardmäßig werden E-Mails an Ihre Benutzer gesendet, aber wenn Sie verhindern möchten, dass sie E-Mails für Audiokonferenzen erhalten, können Sie Microsoft Teams oder Windows PowerShell verwenden.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).

2. Klicken Sie oben auf der Seite " **Konferenzbrücken** " auf " **Brückeneinstellungen"**.

3. Aktivieren oder deaktivieren Sie im **Einstellungsbereich "Brücke** " das **automatische Senden von E-Mails an Benutzer, wenn sich ihre Einwahleinstellungen ändern**.

4. Klicken Sie auf **Speichern**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell

Sie können auch das Microsoft Teams PowerShell-Modul verwenden und Folgendes ausführen:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.

Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz](/powershell/module/teams/?view=teams-ps) .

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Standardmäßig stammt der Absender der E-Mails von Microsoft 365 oder Office 365, Aber Sie können die E-Mail-Adresse und den Anzeigenamen mithilfe von Windows PowerShell ändern.

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben erledigen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

- [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Verwandte Themen

[Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
