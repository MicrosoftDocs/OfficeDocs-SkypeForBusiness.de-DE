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
ms.openlocfilehash: 69c6e8046b185cc8dbc85ac0c99dc5b4cfa6fe2a
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851568"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Verwenden der Inlineübersetzung von Nachrichten in Microsoft Teams 
=================================================

Die Inlineübersetzung von Nachrichten ist eine neue Microsoft Teams-Funktion, mit der Benutzer Microsoft Teams-Nachrichten automatisch in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) übersetzen lassen können, die in ihren persönlichen Spracheinstellungen für Office 365 festgelegt ist.

Die Inlineübersetzung von Nachrichten wird standardmäßig für Ihre Organisation eingeführt. Wenn Sie Benutzern die Verwendung der Funktion im Microsoft Teams-Client ermöglichen möchten, müssen Sie diese Einstellung mithilfe von PowerShell aktivieren. Zurzeit ist diese Option im Admin Center für Microsoft Teams und Skype for Business nicht verfügbar, sie wird aber bald hinzugefügt.

> [!NOTE]
>Dieser Rollout ist von Office 365-Abonnements in Office 365 Government Community Cloud- und Office 365 Deutschland-Umgebungen ausgeschlossen. 

## <a name="enable-by-using-powershell"></a>Aktivieren mithilfe von PowerShell

Sie können die Funktion für die Inlineübersetzung von Nachrichten mithilfe der Nachrichtenrichtlinie aktivieren. 

1. Aktivieren Sie die Richtlinie mit dem [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)-Cmdlet.
2. Die Anwendung der Richtlinie dauert ein paar Minuten. Die Benutzer müssen sich möglicherweise bei Microsoft Teams abmelden und dann wieder anmelden.

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a>Aktivieren Sie mithilfe der Microsoft-Teams & Skype für Business Admin Center

So aktivieren Sie das Inline-Nachricht Übersetzung Feature mithilfe der Microsoft-Teams & Skype für Business Admin Center die Option wird in Kürze bereitgestellt.

> [!NOTE]
>Die Übersetzung findet ausschließlich auf dem Client statt und hat keine Auswirkungen auf in den Compliance-Datensätzen erfasste Inhalte. Weitere Informationen zur Übersetzung finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).