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
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016837"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Verwenden der Inlineübersetzung von Nachrichten in Microsoft Teams 
=================================================

Die Inlineübersetzung von Nachrichten ist eine neue Microsoft Teams-Funktion, mit der Benutzer Microsoft Teams-Nachrichten automatisch in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) übersetzen lassen können, die in ihren persönlichen Spracheinstellungen für Office 365 festgelegt ist.

Inline-Nachricht Übersetzung ist standardmäßig für Ihre Organisation eingeführt. Wenn Sie Benutzern die Verwendung dieses Features innerhalb des Teams Clients zulassen möchten, müssen Sie diese Einstellung aktivieren mithilfe von PowerShell. Derzeit, diese Option ist nicht verfügbar in den Microsoft-Teams und Skype für Business Admin Center, werden jedoch bald.

> [!NOTE]
>Dieser Rollout ist von Office 365-Abonnements in Office 365 Government Community Cloud- und Office 365 Deutschland-Umgebungen ausgeschlossen. 

## <a name="enable-by-using-powershell"></a>Aktivieren mithilfe von PowerShell

Sie können die Funktion für die Inlineübersetzung von Nachrichten mithilfe der Nachrichtenrichtlinie aktivieren. 

1. Aktivieren Sie die Richtlinie mit dem [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)-Cmdlet.
2. Die Richtlinie hat ein paar Minuten anwenden. Benutzer müssen sich abmelden und wieder anmelden, um Teams.

## <a name="enable-by-using-the-teams-admin-center"></a>Aktivieren über das Teams Admin Center

Die Option zum Aktivieren der Funktion für die Inlineübersetzung von Nachrichten über das Teams Admin Center wird in Kürze hinzugefügt.

> [!NOTE]
>Übersetzung ist ausschließlich mithilfe der clientseitigen und hat keine Auswirkung auf die Inhalte in die Compliance-Datensätze erfasst. Weitere Informationen zur Übersetzung hierzu finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).