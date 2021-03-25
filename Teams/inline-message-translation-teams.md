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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie die Inlineübersetzung in Microsoft Teams über das Microsoft Teams Admin Center oder PowerShell aktivieren.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c9e34c5e539d32b25259098973e9bfe6795ad7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120626"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Deaktivieren der Inlinenachrichtenübersetzung in Microsoft Teams
=================================================

Die Inlineübersetzung von Nachrichten ist ein Microsoft Teams-Feature, mit dem Benutzer Teams-Nachrichten in die sprache übersetzen können, die in den persönlichen Spracheinstellungen angegeben ist. [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)

Die Inlinenachrichtenübersetzung wird standardmäßig für Ihre Organisation ausgeführt. Sie müssen keine Änderungen vornehmen, wenn Sie benutzern die Verwendung dieses Features im Teams-Client ermöglichen möchten.

> [!NOTE]
>Dieses Rollout ist in unseren Office 365 Government Community Cloud- und Office 365 Deutschland-Umgebungen von Office 365-Abonnements ausgeschlossen.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Verwenden von PowerShell zum Deaktivieren der Inlinenachrichtenübersetzung

Sie können die Nachrichtenrichtlinie verwenden, um die Inlinenachrichtenübersetzung zu deaktivieren.

Deaktivieren Sie die Richtlinie mithilfe des [Cmdlets Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) Die Anwendung der Richtlinie dauert einige Minuten. Benutzer müssen sich möglicherweise abmelden und sich wieder bei Teams anmelden.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Verwenden des Microsoft Teams Admin Centers zum Deaktivieren der Inlinenachrichtenübersetzung

Wählen Sie im **Microsoft Teams Admin Center** im linken Navigationsbereich Messagingrichtlinien aus, erstellen Sie  dann entweder eine neue Richtlinie, oder bearbeiten Sie eine vorhandene Richtlinie, und legen Sie die Option Nachrichten übersetzen auf **Aus .** 

> [!NOTE]
> Der Dienst führt die Übersetzung durch und übergibt sie ohne Auswirkung auf den Inhalt, der in den Compliancedatensätzen erfasst wurde, an den Client. Weitere Informationen zur Übersetzung finden Sie unter [Was ist Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)