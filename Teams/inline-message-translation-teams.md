---
title: Verwenden der Inlineübersetzung von Nachrichten in Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
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
ms.openlocfilehash: 9097e7421bb65b1a9ce0900df097080a6cfc2023
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296396"
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

## <a name="enable-by-using-the-teams-admin-center"></a>Aktivieren über das Teams Admin Center

Die Option zum Aktivieren der Funktion für die Inlineübersetzung von Nachrichten über das Teams Admin Center wird in Kürze hinzugefügt.

> [!NOTE]
>Die Übersetzung findet ausschließlich auf dem Client statt und hat keine Auswirkungen auf in den Compliance-Datensätzen erfasste Inhalte. Weitere Informationen zur Übersetzung finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).