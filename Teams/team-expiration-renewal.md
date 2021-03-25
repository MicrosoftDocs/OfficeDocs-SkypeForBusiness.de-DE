---
title: Ablauf und Verlängerung des Teams in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über Ablauf und Verlängerung des Teams und darüber, wie Sie die Ablaufrichtlinie für Microsoft 365-Gruppen verwenden, um nicht verwendete Teams in Microsoft Teams automatisch zu bereinigen.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 606d957b703725d631beec38237f4d9b4272433e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116953"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Ablauf und Verlängerung des Teams in Microsoft Teams

Organisationen mit einer großen Anzahl von Teams verfügen häufig über Teams, die niemals tatsächlich verwendet werden. Dies kann aus mehreren Gründen geschehen, z. B. produktexperimentieren, kurzfristige Teamzusammenarbeit oder Teambesitzer, die die Organisation verlassen. Im Laufe der Zeit können sich solche Teams ansammeln und die Mandantenressourcen belasten.  

Um die Anzahl der nicht verwendeten Teams einzudämmen, können Sie als Administrator die Ablaufrichtlinie für [Microsoft 365-Gruppen](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) verwenden, um nicht verwendete Teams automatisch zu bereinigen. Da Teams von Gruppen unterstützt werden, gelten Gruppenablaufrichtlinien automatisch auch für Teams.

Wenn Sie eine Ablaufrichtlinie auf ein Team anwenden, erhält ein Teambesitzer eine Benachrichtigung über die Teamverlängerung 30 Tage, 15 Tage und 1 Tag vor dem Ablaufdatum des Teams. Wenn der Teambesitzer die Benachrichtigung erhält, kann er **in** den Teameinstellungen auf Jetzt verlängern klicken, um das Team zu verlängern.

![Screenshot der Schaltfläche "Jetzt verlängern", um ein Team in den Teameinstellungen zu verlängern](media/team-expiration.png "Screenshot der Schaltfläche "Jetzt verlängern", um ein Team in den Teameinstellungen zu verlängern")

Wenn der Teambesitzer das Team nicht verlängert und es bis zum Ende der Ablaufrichtlinie keine weiteren Aktivitäten im Team gibt, wird das Team in einen "soft-deleted"-Zustand gesetzt, was bedeutet, dass es innerhalb der nächsten 30 Tage wiederhergestellt werden kann.

## <a name="team-auto-renewal"></a>Automatische Verlängerung des Teams

Es kann zeiten sein, in denen ein Teambesitzer das Team möglicherweise nicht verlängern kann, weil er vergessen hat, zu verlängern, oder weil er bei der fälligen Verlängerung nicht mehr da war. In diesen Szenarien kann ein aktives Team aufgrund von Ablaufrichtlinien gelöscht werden, die für das Team gelten.  

Um ein versehentliches Löschen zu verhindern, wird die automatische Verlängerung automatisch für ein Team in der Gruppenablaufrichtlinie aktiviert. Wenn die Gruppenablaufrichtlinie eingerichtet ist, wird jedes Team, das vor dem Ablaufdatum mindestens einen Kanalbesuch von einem Teammitglied hat, ohne manuelles Eingreifen des Teambesitzers automatisch verlängert.

## <a name="known-issues"></a>Bekannte Probleme

**Ablaufdatum des Teams und der zugrunde liegenden Gruppe nicht übereinstimmen**

Bevor ein Team verlängert wird, wird zuerst die Gruppe, die das Team zurücksennt, erneuert. Im Rahmen der Verlängerung wird für die Gruppe ein neues Ablaufdatum für ein zukünftiges Datum festgelegt. Dieses neue Datum ist in Teams möglicherweise nicht sofort sichtbar. Die Synchronisierung kann bis zu 24 Stunden dauern. Wenn zwischen dem Ablaufdatum eines Teams und seiner zugrunde liegenden Gruppe eine Diskrepanz zu sehen ist, warten Sie 24 Stunden, bevor Sie weitere Unterstützung erhalten.