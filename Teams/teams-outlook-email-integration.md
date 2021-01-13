---
title: Integration von Teams und Outlook-E-Mail
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie mehr über die Funktionen zur E-Mail-Integration in Teams und Outlook, einschließlich Features, mit denen Benutzer Informationen zwischen E-Mails in Outlook und Chats oder Kanalunterhaltungen in Teams teilen können.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6e260148cfcdb45c516958bae03ecfadc1bbd64
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802395"
---
# <a name="teams-and-outlook-email-integration"></a>Integration von Teams und Outlook-E-Mail

Microsoft Teams enthält Features, die benutzern in Ihrer Organisation das Teilen von Informationen zwischen E-Mails in Outlook und Chats oder Kanalunterhaltungen in Teams und den Zugriff auf verpasste Unterhaltungen ganz einfach machen. Dieser Artikel bietet Ihnen eine Übersicht über diese Features und die Administratorsteuerelemente, die gelten.

## <a name="share-to-outlook"></a>Freigeben für Outlook

**Mit "In Outlook freigeben"** können Benutzer eine Kopie einer Unterhaltung in Teams in einer E-Mail in Outlook freigeben, ohne Teams verlassen zu müssen. Dieses Feature ist praktisch, wenn Benutzer Unterhaltungen oder Statusaktualisierungen mit Benutzern außerhalb ihres unmittelbaren Teams oder sogar Ihrer Organisation teilen müssen. Wechseln Sie in Teams zum oberen Rand der Unterhaltung, wählen Sie **2 2** Weitere Optionen und dann **"In Outlook freigeben" aus.**  Weitere Informationen finden Sie unter ["In Outlook über Teams freigeben".](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)

![Screenshot der Funktion "In Outlook freigeben" in Teams](media/share-to-outlook.png)

Um dieses Feature verwenden zu können, muss Outlook im Web für den Benutzer aktiviert sein. Wenn Outlook im Web deaktiviert ist, wird die Option "In **Outlook** freigeben" in Teams für den Benutzer nicht angezeigt. Schritte zum Aktivieren und Deaktivieren von Outlook im Web finden Sie unter Aktivieren oder Deaktivieren von Outlook im [Web für ein Postfach.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)

## <a name="actionable-activity-emails"></a>E-Mails zu handlungsbehbaren Aktivitäten

Benutzer erhalten automatisch E-Mails zu verpassten Aktivitäten, die ihnen helfen, sich über verpasste Unterhaltungen in Teams zu unterhalten. In den E-Mails zu verpassten Aktivitäten werden die neuesten Antworten aus einer Unterhaltung  angezeigt, einschließlich der Nachrichten, die nach der verpassten Nachricht gesendet wurden, und Benutzer können auf "Antworten" klicken, um direkt in Outlook zu antworten. Weitere Informationen finden Sie unter ["Antworten auf E-Mails zu verpassten Aktivitäten in Outlook".](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) 

> [!NOTE]
> Dieses Feature wird in Outlook für Mac oder einigen älteren Versionen von Outlook für Windows nicht unterstützt. Weitere Informationen finden Sie unter ["Handlungsbehbare Nachrichten" in Outlook und Office 365-Gruppen.](https://docs.microsoft.com/outlook/actionable-messages/)

![Screenshot einer E-Mail mit einer verpassten Aktivität](media/missed-activity-email.png)

![Screenshot, der zeigt, wie Sie auf eine E-Mail mit einer verpassten Aktivität antworten können](media/missed-activity-email-reply.png)

Sie können das [Cmdlet "Set-OrganizationConfig"](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) zusammen mit dem **Parameter "SmtpActionableMessagesEnabled"** verwenden, um E-Mails zu deaktivieren, die ausgeführt werden können. Standardmäßig ist der **Parameter "SmtpActionableMessagesEnabled"** auf **"true" festgelegt.** Wenn Sie den Parameter auf **"False" festlegen,** werden handlungsbehbare E-Mail-Nachrichten in Office 365 deaktiviert. Für Teams-Benutzer bedeutet  dies, dass die Option "Antworten", um direkt in Outlook zu antworten, in E-Mails zu verpassten Aktivitäten nicht verfügbar ist. Stattdessen enthalten die E-Mails zu verpassten Aktivitäten eine **Option "In Teams** antworten", auf die Benutzer in Teams antworten können.
