---
title: E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen ändern
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Hier erfahren Sie, welche Informationen automatisch per E-Mail an Benutzer gesendet werden, wenn sich ihre Dial-in-Konferenzeinstellungen in Microsoft Teams ändern. '
ms.openlocfilehash: 15c35570d509ae69a41e4c6d9522a5a62d32dd59
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691481"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen in Microsoft Teams ändern

E-Mails werden automatisch an Benutzer gesendet, die [für Audiokonferenzen aktiviert](set-up-audio-conferencing-in-teams.md) sind und Microsoft als Audiokonferenzanbieter verwenden.

Standardmäßig gibt es vier Arten von E-Mails, die an die für Audiokonferenzen aktivierten Benutzer gesendet werden. Wenn Sie die Anzahl der an die Benutzer gesendeten E-Mails begrenzen möchten, können Sie die E-Mails deaktivieren. Audiokonferenzen in Microsoft 365 oder Office 365 senden e-Mail-Nachrichten an die e-Mail-Adresse Ihrer Benutzer:

- **Den Benutzern wird eine Lizenz für Audiokonferenzen zugewiesen, oder Sie ändern den Audiokonferenzanbieter in Microsoft.**

     Diese E-Mail enthält die Konferenzkennung, die standardmäßige Konferenztelefonnummer für die Besprechungen, die Audiokonferenz-PIN für den Benutzer sowie Anweisungen und den Link zum Besprechungsaktualisierungstool für Skype for Business Online, das zum Aktualisieren vorhandener Besprechungen für den Benutzer verwendet wird. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Add-on-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md) oder [Zuweisen von Microsoft als Audiokonferenz-Anbieter](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenzkennungen aktiviert wurde, weisen alle von einem Benutzer geplanten Besprechungen eindeutige Konferenzkennungen auf. Sie können [dynamische Audiokonferenzkennungen in Ihrer Organisation](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user) einrichten. 

    Hier ist ein Beispiel für diese E-Mail:

     ![Bestätigung der Skype for Business-Lizenz](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft Teams-Add-on-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

- **Die Konferenzkennung oder die standardmäßige Konferenztelefonnummer eines Benutzers wird geändert.**

    Diese E-Mail umfasst die Konferenz-ID, die Standardeinwahlnummer sowie Anweisungen und die Verknüpfung zum Skype for Business Online Meeting Update Tool, welches zur Aktualisierung bereits für den Benutzer geplanter Besprechungen verwendet wird. Sie enthält jedoch nicht die Audiokonferenz-PIN des Benutzers. Siehe [Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md).

    Hier ist ein Beispiel für diese E-Mail:

     ![Die Dial-in-Konferenzinformationen wurden geändert.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **Die Audiokonferenz-PIN eines Benutzers wird zurückgesetzt.**

    Diese E-Mail enthält die Audiokonferenz-PIN des Organisators, die vorhandene Konferenzkennung und die standardmäßige Konferenztelefonnummer für den Benutzer. Siehe [Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md).
    
     Hier ist ein Beispiel für diese E-Mail:
    
     ![Die PIN für Dial-in-Konferenzen wurde geändert.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **Die Lizenz eines Benutzers wird entfernt, oder der Audiokonferenzanbieter wird von Microsoft in einen anderen Anbieter oder in „Keiner“ geändert.**

    Dies geschieht, wenn die **Audiokonferenz-** Lizenz von einem Benutzer entfernt wird oder wenn der Audiokonferenz-Anbieter auf **None**festgelegt wird.

    Weitere Informationen finden Sie unter [zuweisen oder Entfernen von Lizenzen für Microsoft 365 for Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    So kann diese E-Mail aussehen:

     !["Dial-In-Konferenzen" ist deaktiviert.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Änderungen an den E-Mail-Nachrichten, die ihnen geschickt werden

Sie können Änderungen an der e-Mail vornehmen, die automatisch an Benutzer gesendet wird. Standardmäßig wird der Absender der e-Mails von Microsoft 365 oder Office 365, aber Sie können den Anzeigenamen mithilfe von Windows PowerShell ändern. Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Wie gehen Sie vor, wenn Sie Benutzern keine E-Mails senden möchten?

Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails an die Benutzer gesendet, auch nicht, wenn ihnen eine Lizenz zugewiesen wird. In diesem Fall werden die Konferenz-ID, die Standard-Konferenztelefonnummer und, was noch wichtiger ist, ihre Audiokonferenz-PIN nicht an den Benutzer gesendet. Wenn dies geschieht, müssen Sie dem Benutzer eine separate E-Mail schreiben oder ihn anrufen, um ihm diese Mitteilung zu machen.

Standardmäßig werden e-Mails an Ihre Benutzer gesendet, aber wenn Sie verhindern möchten, dass Sie e-Mails für Audiokonferenzen empfangen, können Sie Microsoft Teams oder Windows PowerShell verwenden. 

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Konferenz Brücken** auf **Brücken Einstellungen**. 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge Settings** **automatisch e-Mails an Benutzer senden, wenn sich Ihre Einwahleinstellungen ändern**.

4. Klicken Sie auf **Speichern**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Verwenden von Windows PowerShell**

Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .


## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Standardmäßig wird der Absender der e-Mails von Microsoft 365 oder Office 365, aber Sie können die e-Mail-Adresse und den Anzeigenamen mithilfe von Windows PowerShell ändern. 

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).


## <a name="related-topics"></a>Verwandte Themen

[Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
