---
title: Aktivieren der Übersetzung von Inline Nachrichten
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Inline Übersetzung in Microsoft Teams mit dem Microsoft Teams Admin Center oder PowerShell aktivieren.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395384"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Deaktivieren der Inline Nachrichtenübersetzung in Microsoft Teams
=================================================

Inline-Nachrichtenübersetzung ist eine Microsoft Teams-Funktion, mit der Benutzer Teams-Nachrichten in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) übersetzen können, die in Ihren persönlichen Spracheinstellungen angegeben ist.

Inline-Nachrichtenübersetzung wird standardmäßig für Ihre Organisation bereit gesetzt. Sie müssen keine Änderungen vornehmen, wenn Sie Benutzern erlauben möchten, diese Funktion innerhalb des Teams-Clients zu verwenden.

> [!NOTE]
>Dieser Rollout ist von Office 365-Abonnements in unseren Office 365 Government Community Cloud-und Office 365 Germany-Umgebungen ausgeschlossen.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Verwenden von PowerShell zum Deaktivieren der Inline Nachrichtenübersetzung

Sie können die Nachrichten Richtlinie verwenden, um die Inline Nachrichtenübersetzung zu deaktivieren.

Deaktivieren Sie die Richtlinie mit dem Cmdlet " [Satz-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) ". Die Anwendung der Richtlinie dauert einige Minuten. Benutzer müssen sich möglicherweise abmelden und sich wieder bei Teams anmelden.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Verwenden des Microsoft Teams admin Centers zum Deaktivieren der Inline Nachrichtenübersetzung

Wählen Sie im **Microsoft Teams Admin Center**im linken Navigationsbereich **Messaging Richtlinien** aus, erstellen Sie dann entweder eine neue Richtlinie, oder bearbeiten Sie eine vorhandene Richtlinie, und legen Sie die Option **Nachrichten übersetzen** auf **aus**.

> [!NOTE]
> Der Dienst führt die Übersetzung durch und übergibt ihn an den Client, ohne dass dies Auswirkungen auf die in den Konformitätsdaten Sätzen erfassten Inhalte hat. Weitere Informationen zur Übersetzung finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)
