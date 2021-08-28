---
title: Aktivieren der Inlinenachrichtenübersetzung
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
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie die Inlineübersetzung in Microsoft Teams Admin Center oder PowerShell Microsoft Teams aktivieren.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bfaa03ff8fa8654fca48fbd2bd31d8d6518e2de
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593079"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Deaktivieren der Inlinenachrichtenübersetzung in Microsoft Teams

Die Übersetzung von Inlinenachrichten ist ein Microsoft Teams-Feature, mit dem [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) Benutzer Nachrichten Teams in die von ihren persönlichen Spracheinstellungen angegebene Sprache übersetzen können.

Die Übersetzung von Inlinenachrichten wird standardmäßig für Ihre Organisation ausgeführt. Sie müssen keine Änderungen vornehmen, wenn Sie es Benutzern gestatten möchten, dieses Feature innerhalb des Teams verwenden.

> [!NOTE]
>Dieses Rollout ist von Office 365 Abonnements in unseren Umgebungen Office 365 Government Community Cloud und Office 365 Deutschland ausgeschlossen.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Verwenden von PowerShell zum Deaktivieren der Übersetzung von Inlinenachrichten

Sie können die Nachrichtenrichtlinie verwenden, um die Übersetzung von Inlinenachrichten zu deaktivieren.

Deaktivieren Sie die Richtlinie mithilfe des [Cmdlets Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) Die Anwendung der Richtlinie dauert ein paar Minuten. Benutzer müssen sich möglicherweise abmelden und wieder bei Ihrem Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Verwenden des Microsoft Teams Admin Centers zum Deaktivieren der Inlinenachrichtenübersetzung

Wählen Sie im **Microsoft Teams Admin** **Center** im linken Navigationsbereich Messagingrichtlinien aus, erstellen Sie dann entweder  eine neue Richtlinie, oder bearbeiten Sie eine vorhandene Richtlinie, und legen Sie die Option Nachrichten übersetzen auf **Aus .**

> [!NOTE]
> Der Dienst führt die Übersetzung durch und stellt sie dem Client ohne Auswirkung auf die in den Compliancedatensätzen erfassten Inhalte zur Verfügung. Weitere Informationen zur Übersetzung finden Sie unter [Was ist Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)