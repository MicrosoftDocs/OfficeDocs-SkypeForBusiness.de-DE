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
ms.openlocfilehash: 0fabdbde6f8307694457d4861d67c6ed2eb22ac1
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905807"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a>Aktivieren der Inline Nachrichtenübersetzung in Microsoft Teams 
=================================================

Bei der Inline Nachrichtenübersetzung handelt es sich um ein neues Microsoft Teams-Feature, mit dem Benutzer Teams-Nachrichten in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) übersetzen können, die in Ihren persönlichen Spracheinstellungen für Office 365 angegeben ist.

Die Inlineübersetzung von Nachrichten wird standardmäßig für Ihre Organisation eingeführt. Wenn Sie zulassen möchten, dass Benutzer dieses Feature innerhalb des Teams-Clients verwenden können, müssen Sie diese Einstellung aktivieren.

> [!NOTE]
>Dieser Rollout ist von Office 365-Abonnements in unseren Office 365 Government Community Cloud-und Office 365 Germany-Umgebungen ausgeschlossen.

## <a name="use-powershell-to-turn-on-inline-message-translation"></a>Verwenden von PowerShell zum Aktivieren der Inline Nachrichtenübersetzung

Sie können die Nachrichten Richtlinie verwenden, um die Übersetzung der Inline Nachricht zu aktivieren.

Aktivieren Sie die Richtlinie mit dem Cmdlet " [Satz-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) ". Die Anwendung der Richtlinie dauert einige Minuten. Benutzer müssen sich möglicherweise abmelden und sich wieder bei Teams anmelden.

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a>Verwenden des Microsoft Teams admin Centers zum Aktivieren der Inline Nachrichtenübersetzung

Wählen Sie im **Microsoft Teams Admin Center**im linken Navigationsbereich **Messaging Richtlinien** aus, und erstellen Sie dann entweder eine neue Richtlinie oder bearbeiten Sie eine vorhandene Richtlinie, und legen Sie die Option **Benutzer können Nachrichten übersetzen** **auf ein.**

> [!NOTE]
> Der Dienst führt die Übersetzung durch und übergibt ihn an den Client, ohne dass dies Auswirkungen auf die in den Konformitätsdaten Sätzen erfassten Inhalte hat. Weitere Informationen zur Übersetzung finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).