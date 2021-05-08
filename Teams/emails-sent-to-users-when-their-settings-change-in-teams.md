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
description: 'Erfahren Sie, welche Informationen automatisch per E-Mail an Benutzer gesendet werden, wenn sich ihre Einwahlkonferenzeinstellungen in einer Microsoft Teams. '
ms.openlocfilehash: a9ca30e7e701afca2e42eccfaef4f3d45660cd3a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120756"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen in Microsoft Teams ändern

E-Mails werden automatisch an Benutzer gesendet, die für [Audiokonferenzen](set-up-audio-conferencing-in-teams.md) aktiviert sind und Microsoft als Audiokonferenzanbieter verwenden.

Standardmäßig gibt es vier Arten von E-Mails, die an die Benutzer gesendet werden, die für Audiokonferenzen aktiviert sind. Wenn Sie die Anzahl von E-Mails, die an die Benutzer gesendet werden, einschränken möchten, können Sie diese Einstellung deaktivieren. Audiokonferenzen in Microsoft 365 oder Office 365 E-Mails an die E-Mail-Adresse Ihrer Benutzer senden, wenn:

- **Ihnen wird eine Lizenz für Audiokonferenzen zugewiesen, oder Sie ändern den Audiokonferenzanbieter zu Microsoft.**

     Diese E-Mail enthält die Konferenz-ID, die Standardeinwahlnummer für Besprechungen, die PIN für Audiokonferenzen für den Benutzer sowie Anweisungen und den Link zur Verwendung des Skype for Business Online Meeting Update Tool, das zum Aktualisieren vorhandener Besprechungen für den Benutzer verwendet wird. Weitere Informationen finden Microsoft Teams Zuweisen [von Add-On-Lizenzen oder](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) Zuweisen von [Microsoft als Audiokonferenzanbieter.](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)

    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Sie können dynamische [IDs für Audiokonferenzen in Ihrer Organisation einrichten.](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user) 

    So kann diese E-Mail aussehen:

     ![Skype for Business Verify License](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft Teams- und Add-On-Lizenzierung.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

- **Sich die Konferenz-ID oder die Standardtelefonnummer eines Benutzers ändert.**

    Diese E-Mail umfasst die Konferenz-ID, die Standardeinwahlnummer sowie Anweisungen und die Verknüpfung zum Skype for Business Online Meeting Update Tool, welches zur Aktualisierung bereits für den Benutzer geplanter Besprechungen verwendet wird. Diese E-Mail enthält jedoch nicht die PIN für Audiokonferenzen des Benutzers. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).

    So kann diese E-Mail aussehen:

     ![Die Informationen für Dial-In-Konferenzen wurden geändert.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **Die AUDIOKONFERENZ-PIN eines Benutzers wird zurückgesetzt.**

    Diese E-Mail enthält die AUDIOKONFERENZ-PIN des Organisators, die vorhandene Konferenz-ID und die Standardeinwahlnummer für den Benutzer. Weitere [Informationen finden Sie unter Zurücksetzen der Audiokonferenz-PIN.](reset-the-audio-conferencing-pin-in-teams.md)
    
     So kann diese E-Mail aussehen:
    
     ![Die PIN für die Dial-In-Konferenz wurde geändert.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **Die Lizenz eines Benutzers wird entfernt, oder wenn der Audiokonferenzanbieter von Microsoft zu einem anderen Anbieter wechselt oder Kein.**

    Dies geschieht, wenn die Lizenz für **Audiokonferenzen** von einem Benutzer entfernt wird oder wenn sie den Audiokonferenzanbieter auf **Keine setzt.**

    Weitere Informationen finden Sie unter Zuweisen oder Entfernen [von Microsoft 365 für Unternehmen.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

    So kann diese E-Mail aussehen:

     !["Dial-In-Konferenzen" ist deaktiviert.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Änderungen an den E-Mail-Nachrichten, die ihnen geschickt werden

Sie können Änderungen an der E-Mail vornehmen, die automatisch an die Benutzer gesendet wird. Standardmäßig stammt der Absender der E-Mails von Microsoft 365 E-Office 365, aber Sie können den Anzeigenamen mithilfe der Windows PowerShell. Weitere Informationen Microsoft Teams Sie in der [PowerShell-Referenz.](/powershell/module/teams/?view=teams-ps)

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Wie gehen Sie vor, wenn Sie Benutzern keine E-Mails senden möchten?

Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails an die Benutzer gesendet, auch nicht, wenn ihnen eine Lizenz zugewiesen wird. In diesem Fall werden die Konferenz-ID, die Standardtelefonnummer für Konferenzen und, noch wichtiger, die PIN für Audiokonferenzen nicht an den Benutzer gesendet. Wenn dies geschieht, müssen Sie dem Benutzer eine separate E-Mail schreiben oder ihn anrufen, um ihm diese Mitteilung zu machen.

Standardmäßig werden E-Mails an Ihre Benutzer gesendet. Wenn Sie jedoch verhindern möchten, dass diese E-Mails für Audiokonferenzen erhalten, können Sie die Microsoft Teams oder Windows PowerShell. 

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der **Seite Konferenzbrücken** auf **Einstellungen für Brücke.** 

3. Aktivieren oder **deaktivieren Sie im Bereich** Einstellungen der Brücke die Option Automatisches Senden von E-Mails an Benutzer, wenn sich **deren Einwahleinstellungen ändern.**

4. Klicken Sie auf **Speichern**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Verwenden von Windows PowerShell**

Weitere Informationen Microsoft Teams Sie in der [PowerShell-Referenz.](/powershell/module/teams/?view=teams-ps)


## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Standardmäßig stammt der Absender der E-Mails von Microsoft 365 oder Office 365, aber Sie können die E-Mail-Adresse und den Anzeigenamen mithilfe der Windows PowerShell. 

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie ihre Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:

  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).


## <a name="related-topics"></a>Verwandte Themen

[Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)