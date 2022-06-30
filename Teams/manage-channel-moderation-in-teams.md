---
title: Einrichten und Verwalten der Kanalmoderation
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Kanäle für die Moderation in Microsoft Teams einrichten, einschließlich der Vorgehensweise zum Hinzufügen von Teammitgliedern als Kanalmoderator.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52fb88d6371c033713c5b14d96ecf2a9211420b0
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562364"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Einrichten und Verwalten der Kanalmoderation in Microsoft Teams

In Microsoft Teams können Teambesitzer die Moderation für einen Standardkanal aktivieren, um zu steuern, wer neue Beiträge starten und auf Beiträge in diesem Kanal antworten kann.

Teambesitzer können Teammitglieder auch als Moderatoren hinzufügen. Ein Teambesitzer verfügt möglicherweise nicht über das Fachwissen auf Kanalebene, um die Kanalmoderation optimal zu unterstützen. Indem bestimmte Teammitglieder einen Kanal moderieren können, wird die Verantwortung für die Verwaltung von Inhalten und Kontext innerhalb eines Kanals zwischen Teambesitzern und Kanalmoderator geteilt. Beispielsweise kann ein Teambesitzer Geschäftsbesitzer oder Inhaltsbesitzer als Moderatoren hinzufügen, wodurch er die Informationsfreigabe in diesem Kanal steuern kann.

> [!NOTE]
> Kanalmoderation ist für Standardkanäle verfügbar. Es ist nicht für den Kanal "Allgemein" oder für private oder freigegebene Kanäle verfügbar.

## <a name="what-can-a-channel-moderator-do"></a>Was kann ein Kanalmoderator tun?

Kanalmoderator können:

- Starten Sie neue Beiträge im Kanal. Wenn die Moderation für einen Kanal aktiviert ist, können nur Moderatoren neue Beiträge in diesem Kanal starten.
- Hinzufügen und Entfernen von Teammitgliedern als Moderatoren zu einem Kanal. Denken Sie daran, dass Teambesitzer standardmäßig Kanalmoderator sind und nicht entfernt werden können.
- Steuern Sie, ob Teammitglieder auf vorhandene Kanalnachrichten antworten können und ob Bots und Connectors Kanalnachrichten senden können.

## <a name="scenarios"></a>Szenarien

Hier sind einige Beispiele dafür, wie Ihre Organisation die Kanalmoderation in Teams verwenden kann.

### <a name="use-a-channel-as-an-announcement-channel"></a>Verwenden eines Kanals als Ankündigungskanal

Das Marketingteam verwendet einen bestimmten Kanal, um wichtige Projektankündigungen und -ergebnisse freizugeben. Manchmal veröffentlichen Teammitglieder Inhalte im Kanal, die in anderen Kanälen besser geeignet sind. Der Teambesitzer möchte die Informationsfreigabe im Kanal auf Ankündigungen beschränken, damit Teammitglieder diesen Kanal verwenden können, um über das Wichtige auf dem Laufenden zu bleiben.

In diesem Szenario fügt der Teambesitzer Marketing-Leads als Moderatoren hinzu, sodass er Ankündigungen im Kanal veröffentlichen kann, und deaktiviert die Möglichkeit für Teammitglieder, auf Nachrichten in diesem Kanal zu antworten.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>Verwenden eines Kanals für Kursdiskussionen in Teams für Education

In Teams für Education möchte ein wissenschaftlicher Lehrer einen Kanal verwenden, um Schüler in fokussierte Diskussionen zu bestimmten Unterrichtsthemen einzubeziehen.

In diesem Szenario ermöglicht der Lehrer den Lehrassistenten, den Kanal zu moderieren. Die Lehrassistenten können dann neue Beiträge erstellen, um Diskussionen mit Schülern zu initiieren und zu fördern.

## <a name="manage-channel-moderation"></a>Kanalmoderation verwalten

Wechseln Sie in Teams zum Kanal, klicken Sie auf **"Weitere Optionen" ...** >  **Kanal verwalten**. Von hier aus können Sie die Moderation aktivieren und deaktivieren, Teammitglieder als Moderatoren hinzufügen und Einstellungen festlegen.

Kanalmoderation ist eine Einstellung pro Kanal. Es gibt keine Einstellung auf Mandantenebene für die Kanalmoderation. Wenn Sie möchten, dass wir eine Moderationseinstellung auf Mandantenebene hinzufügen, fordern Sie sie im [Teams-Feedbackportal](https://feedbackportal.microsoft.com/feedback/forum/ad198462-1c1c-ec11-b6e7-0022481f8472) an.

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![Einstellungen für die Verwaltung von Kanalmoderationen in Teams.](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>Aktivieren oder Deaktivieren der Moderation für einen Kanal

Standardmäßig ist die Moderation deaktiviert, was bedeutet, dass die üblichen Kanaleinstellungen für Teambesitzer und Teammitglieder gelten. Sie können z. B. neue Beiträge nur auf Teammitglieder beschränken oder zulassen, dass jeder, auch Gäste, neue Beiträge startet.

Um die Moderation für einen Kanal zu aktivieren, klicken Sie unter **Kanalmoderation** **auf "Ein**". Wenn die Kanalmoderation aktiviert ist, können nur Moderatoren neue Beiträge starten. 

### <a name="add-or-remove-channel-moderators"></a>Hinzufügen oder Entfernen von Kanalmoderator

Klicken Sie unter **"Wer sind die Moderatoren?"** auf **"Verwalten**", und fügen Sie dann Teammitglieder als Moderatoren hinzu oder entfernen Sie sie. Teambesitzer und Moderatoren können andere Moderatoren hinzufügen und entfernen.  

### <a name="set-team-member-permissions"></a>Festlegen von Teammitgliedsberechtigungen

Aktivieren Sie unter **"Teammitgliedsberechtigungen**" die Kontrollkästchen neben den Aktivitäten, die Sie zulassen möchten.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Teams und Kanäle in Teams](teams-channels-overview.md)
