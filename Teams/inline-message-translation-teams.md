---
title: Aktivieren der Inline Nachrichtenübersetzung in Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Inlineübersetzung in Microsoft Teams verwenden.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b6da80dda90c57a55a75c885b42bc08a824b613
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245349"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a>Aktivieren der Inline Nachrichtenübersetzung in Microsoft Teams 
=================================================

Die Inlineübersetzung von Nachrichten ist eine neue Microsoft Teams-Funktion, mit der Benutzer Microsoft Teams-Nachrichten automatisch in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) übersetzen lassen können, die in ihren persönlichen Spracheinstellungen für Office 365 festgelegt ist.

Die Inlineübersetzung von Nachrichten wird standardmäßig für Ihre Organisation eingeführt. Wenn Sie zulassen möchten, dass Benutzer dieses Feature innerhalb des Teams-Clients verwenden können, müssen Sie diese Einstellung aktivieren.

> [!NOTE]
>Dieser Rollout ist von Office 365-Abonnements in unseren Office 365 Government Community Cloud-und Office 365 Germany-Umgebungen ausgeschlossen.

## <a name="use-powershell-to-turn-on-inline-message-translation"></a>Verwenden von PowerShell zum Aktivieren der Inline Nachrichtenübersetzung

Sie können die Nachrichten Richtlinie verwenden, um die Übersetzung der Inline Nachricht zu aktivieren.

Aktivieren Sie die Richtlinie mit dem Cmdlet " [Satz-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) ". Die Anwendung der Richtlinie dauert einige Minuten. Benutzer müssen sich möglicherweise abmelden und sich wieder bei Teams anmelden.

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a>Verwenden des Microsoft Teams admin Centers zum Aktivieren der Inline Nachrichtenübersetzung

Wählen Sie im **Microsoft Teams Admin Center**im linken Navigationsbereich **Messaging Richtlinien** aus, und erstellen Sie dann entweder eine neue Richtlinie oder bearbeiten Sie eine vorhandene Richtlinie, und legen Sie die Option **** **Benutzer können Nachrichten übersetzen** auf ein.

> [!NOTE]
> Der Dienst führt die Übersetzung durch und übergibt ihn an den Client, ohne dass dies Auswirkungen auf die in den Konformitätsdaten Sätzen erfassten Inhalte hat. Weitere Informationen zur Übersetzung finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).