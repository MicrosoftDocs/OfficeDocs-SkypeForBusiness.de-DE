---
title: Teams und Outlook-e-Mail-Integration
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie mehr über die Features von Teams und Outlook-e-Mail-Integration, einschließlich Features, mit denen Benutzerinformationen zwischen e-Mails in Outlook und Chats austauschen oder Konversationen in Teams unterhalten können.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 675834cd36c4e86d34d179e91fe66905e3860b32
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429441"
---
# <a name="teams-and-outlook-email-integration"></a>Teams und Outlook-e-Mail-Integration

Microsoft Teams umfasst Features, die Benutzern in Ihrer Organisation die gemeinsame Nutzung von Informationen zwischen e-Mails in Outlook und Chats oder Kanal Unterhaltungen in Teams und das übernehmen von verpassten Unterhaltungen erleichtern. In diesem Artikel erhalten Sie einen Überblick über diese Features und die anwendbaren Administrator Steuerelemente.

## <a name="share-to-outlook"></a>Freigeben für Outlook

**Freigeben für Outlook** ermöglicht Benutzern das Freigeben einer Kopie einer Teams-Unterhaltung an eine e-Mail in Outlook, ohne Teams verlassen zu müssen. Dieses Feature ist praktisch, wenn Benutzer Konversationen oder Status Updates für Benutzer außerhalb Ihres unmittelbaren Teams oder sogar Ihrer Organisation freigeben müssen. Wechseln Sie in Microsoft Teams zum Anfang der Unterhaltung, wählen Sie **̇ ̇ ̇ Weitere Optionen**aus, und wählen Sie dann in **Outlook freigeben**aus.  Weitere Informationen finden Sie unter [Freigeben für Outlook aus Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Screenshot mit der Funktion "in Outlook freigeben" in Microsoft Teams](media/share-to-outlook.png)

Damit Sie dieses Feature verwenden können, muss Outlook im Web für den Benutzer aktiviert sein. Wenn Outlook im Web deaktiviert ist, wird die Option **für Outlook freigeben** in Teams für den Benutzer nicht angezeigt. Eine schrittweise Anleitung zum Aktivieren und Deaktivieren von Outlook im Web finden Sie unter [Aktivieren oder Deaktivieren von Outlook im Web für ein Postfach](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>Transaktionale Aktivitäts-e-Mails

Benutzer erhalten automatisch umsetzbare verpasste Aktivitäts-e-Mails, die Ihnen helfen, sich über verpasste Unterhaltungen in Teams zu informieren. Die e-Mail-Benachrichtigungen über verpasste Aktivitäten zeigen die neuesten Antworten einer Unterhaltung an, einschließlich Nachrichten, die nach der verpassten Nachricht gesendet wurden, und Benutzer können auf **Antworten** klicken, um direkt in Outlook zu antworten. Weitere Informationen finden Sie unter [Antworten auf verpasste Aktivitäts-e-Mails aus Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381). 

> [!NOTE]
> Dieses Feature wird in Outlook für Mac oder einigen älteren Versionen von Outlook für Windows nicht unterstützt. Weitere Informationen finden Sie unter [umsetzbar Nachrichten in Outlook-und Office 365-Gruppen](https://docs.microsoft.com/outlook/actionable-messages/).

![Screenshot mit einer verpassten Aktivitäts-e-Mail](media/missed-activity-email.png)

![Screenshot, der zeigt, wie Sie auf eine verpasste Aktivitäts-e-Mail Antworten](media/missed-activity-email-reply.png)

Sie können das Cmdlet " [Satz-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) " zusammen mit dem **SmtpActionableMessagesEnabled** -Parameter verwenden, um Umsetz-e-Mails zu deaktivieren. Standardmäßig ist der **SmtpActionableMessagesEnabled** -Parameter auf **true**festgelegt. Durch Festlegen des Parameters auf " **false** " werden umsetzbar e-Mail-Nachrichten in Office 365 deaktiviert. Für Teams-Benutzer bedeutet dies, dass die **Antwort** Option zum direkten Antworten in Outlook in verpassten Aktivitäts-e-Mails nicht zur Verfügung steht. Stattdessen umfassen die e-Mail-verpassten Aktivitäten eine Option **in Teams Antworten** , damit Benutzer in Teams Antworten können.
