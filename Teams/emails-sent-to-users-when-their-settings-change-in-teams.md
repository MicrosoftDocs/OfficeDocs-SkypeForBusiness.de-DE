---
title: E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen in Microsoft Teams ändern
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erfahren Sie, welche Informationen automatisch per E-Mail an Benutzer gesendet werden, wenn sich ihre Dial-in-Konferenzeinstellungen in Microsoft Teams ändern. '
ms.openlocfilehash: 47cd5812ab1abda51deca8b50d13765badc982e1
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "37571879"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen in Microsoft Teams ändern

E-Mails werden automatisch an Benutzer gesendet, die [für Audiokonferenzen aktiviert](set-up-audio-conferencing-in-teams.md) sind und Microsoft als Audiokonferenzanbieter verwenden.

Standardmäßig gibt es vier Arten von E-Mails, die an die für Audiokonferenzen aktivierten Benutzer gesendet werden. Wenn Sie die Anzahl der an die Benutzer gesendeten E-Mails begrenzen möchten, können Sie die E-Mails deaktivieren. Audiokonferenzen in Office 365 sendet in den folgenden Fällen E-Mails an Benutzer:

- **Den Benutzern wird eine Lizenz für Audiokonferenzen zugewiesen, oder Sie ändern den Audiokonferenzanbieter in Microsoft.**

     Diese E-Mail enthält die Konferenzkennung, die standardmäßige Konferenztelefonnummer für die Besprechungen, die Audiokonferenz-PIN für den Benutzer sowie Anweisungen und den Link zum Besprechungsaktualisierungstool für Skype for Business Online, das zum Aktualisieren vorhandener Besprechungen für den Benutzer verwendet wird. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md) oder [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

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

    Dies geschieht, wenn die Lizenz für **Audiokonferenzen** von einem Benutzer entfernt wird, wenn der Audiokonferenzanbieter eines Benutzers von Microsoft in einen Drittanbieter für Audiokonferenzen geändert wird oder wenn der Anbieter auf **Keiner** festgelegt wird. Diese E-Mail enthält Anweisungen und Informationen für den Benutzer, damit er mit dem Besprechungsaktualisierungstool für Skype for Business Online spezifische Informationen für Audiokonferenzen wie beispielsweise die standardmäßige Konferenztelefonnummer oder die Konferenzkennung entfernen kann.

    Siehe [Zuweisen von Lizenzen zu Benutzern in Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    Hier ist ein Beispiel für diese E-Mail:

     !["Dial-In-Konferenzen" ist deaktiviert.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Vornehmen von Änderungen an den gesendeten E-Mails

Sie können Änderungen an der e-Mail vornehmen, die automatisch an Benutzer gesendet wird. Standardmäßig wird der Absender der e-Mails von Office 365, aber Sie können den Anzeigenamen mithilfe von Windows PowerShell ändern. Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Wie gehen Sie vor, wenn keine E-Mails an die Benutzer gesendet werden sollen?

Wenn Sie das Senden von E-Mails an die Benutzer deaktivieren, werden auch dann keine E-Mails gesendet, wenn Benutzern eine Lizenz zugewiesen wird. In diesem Fall werden die Konferenzkennung, die standardmäßige Konferenztelefonnummer und vor allem die Audiokonferenz-PIN nicht an die Benutzer gesendet. Dann müssen Sie die Benutzer informieren, indem Sie ihnen eine separate E-Mail senden oder sie anrufen.

Standardmäßig werden E-Mails an die Benutzer gesendet. Wenn Sie nicht möchten, dass die Benutzer E-Mails für Audiokonferenzen erhalten, können Sie Microsoft Teams oder Windows PowerShell verwenden. 

![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert**.

4. Klicken Sie auf **Speichern**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Verwenden von Windows PowerShell**

Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).


## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mit Windows PowerShell ändern. 

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).


## <a name="related-topics"></a>Verwandte Themen

[Aktivieren und Deaktivieren der bei geänderten Audiokonferenzeinstellungen gesendeten E-Mails](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
