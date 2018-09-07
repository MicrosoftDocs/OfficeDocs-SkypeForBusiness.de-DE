---
title: Verwenden von Inline-Nachricht Übersetzung in Microsoft-Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Priority
search.appverid: MET150
description: Informationen Sie zum Verwenden von Inline-Übersetzung in Microsoft-Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb7876d015fb736785fdaab99b1ed71b8e05b9dc
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855821"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Verwenden von Inline-Nachricht Übersetzung in Microsoft-Teams 
=================================================

Inline-Nachricht Übersetzung ist ein neues Microsoft-Teams-Feature, mit dem Benutzer Teams Nachrichten automatisch in die [Sprache](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) , die durch ihre persönliche Sprachoptionen für Office 365 angegebenen übersetzen kann.

Inline-Nachricht Übersetzung ist standardmäßig für Ihre Organisation eingeführt. Wenn Sie Benutzern die Verwendung dieses Features innerhalb des Teams Clients zulassen möchten, müssen Sie diese Einstellung aktivieren mithilfe von PowerShell. Derzeit, diese Option ist nicht verfügbar in den Microsoft-Teams und Skype für Business Admin Center, werden jedoch bald.

> [!NOTE]
>Einführung wird von Office 365-Abonnements in unserer Community-Cloud der Office 365 Government und Office 365 Deutschland Umgebungen ausgeschlossen. 

## <a name="enable-by-using-powershell"></a>Aktivieren mithilfe von PowerShell

Sie können das Feature zum Inline-Nachricht Übersetzung mithilfe der Gruppenrichtlinien Messaging aktivieren. 

1. Aktivieren Sie die Richtlinie mit dem Cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .
2. Die Richtlinie hat ein paar Minuten anwenden. Benutzer müssen sich abmelden und wieder anmelden, um Teams.

## <a name="enable-by-using-the-teams-admin-center"></a>Aktivieren Sie mithilfe der Verwaltungskonsole Teams

Die Option aktivieren Sie das Feature zum Inline-Nachricht Übersetzung mithilfe der Verwaltungskonsole Teams wird in Kürze bereitgestellt.

> [!NOTE]
>Übersetzung ist ausschließlich mithilfe der clientseitigen und hat keine Auswirkung auf die Inhalte in die Compliance-Datensätze erfasst. Weitere Informationen zur Übersetzung hierzu finden Sie unter [Was ist Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).