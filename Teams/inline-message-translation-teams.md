---
title: Verwenden der Inlineübersetzung von Nachrichten in Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Inlineübersetzung in Microsoft Teams verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 466160616adea80a2fcb6a3bfd035ca397d73754
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754426"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Verwenden der Inlineübersetzung von Nachrichten in Microsoft Teams 
=================================================

Die Inlineübersetzung von Nachrichten ist eine neue Microsoft Teams-Funktion, mit der Benutzer Microsoft Teams-Nachrichten automatisch in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) übersetzen lassen können, die in ihren persönlichen Spracheinstellungen für Office 365 festgelegt ist.

Die Inlineübersetzung von Nachrichten wird standardmäßig für Ihre Organisation eingeführt. Wenn Sie Benutzern die Verwendung dieses Features innerhalb des Teams Clients zulassen möchten, müssen Sie diese Einstellung aktivieren.

> [!NOTE]
>Einführung wird von Office 365-Abonnements in unserer Community-Cloud der Office 365 Government und Office 365 Deutschland Umgebungen ausgeschlossen.

## <a name="enable-by-using-powershell"></a>Aktivieren mithilfe von PowerShell

Sie können das Feature zum Inline-Nachricht Übersetzung mithilfe der Gruppenrichtlinien Messaging aktivieren.

1. Aktivieren Sie die Richtlinie mit dem Cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .
2. Die Richtlinie hat ein paar Minuten anwenden. Benutzer müssen sich abmelden und wieder anmelden, um Teams.

## <a name="enable-by-using-the-microsoft-teams-admin-center"></a>Aktivieren Sie mithilfe der Verwaltungskonsole von Microsoft-Teams

Wählen Sie in der **Microsoft-Teams, Administrationscenter**in der linken Leiste **Messaging Policies** , klicken Sie dann entweder eine neue Richtlinie erstellen oder Bearbeiten einer vorhandenen Richtlinie und legen Sie die Option **Benutzer zulassen, um Nachrichten zu übersetzen** , **Klicken Sie auf**.

> [!NOTE]
>Übersetzung wird vom Dienst erfolgt, und an den Client Layoutelemente ohne Auswirkung auf die Inhalte in die Compliance-Datensätze erfasst übermittelt. Weitere Informationen zur Übersetzung hierzu finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).