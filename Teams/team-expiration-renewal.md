---
title: Ablauf und Verlängerung des Teams in Microsoft Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über Ablauf und Verlängerung von Teams und darüber, wie Sie Microsoft 365-Ablaufrichtlinie für Gruppen verwenden, um nicht verwendete Teams automatisch in einem Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb56013f411349907f602ff603441c41e6c68368
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758247"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Ablauf und Verlängerung des Teams in Microsoft Teams

Organisationen mit einer großen Anzahl von Teams verfügen häufig über Teams, die tatsächlich nie verwendet werden. Dies kann aus verschiedenen Gründen geschehen, z. B. aus Produkt experimentieren, aus einer kurzen Teamzusammenarbeit oder aus Teambesitzern, die das Unternehmen verlassen. Im Laufe der Zeit können sich solche Teams ansammeln und Mandantenressourcen belasten.  

Um die Anzahl der nicht verwendeten Teams einzudämmen, können Sie als Administrator eine Microsoft 365 Gruppenablaufrichtlinie verwenden, um nicht verwendete Teams automatisch zu bereinigen. [](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) Da Teams von Gruppen unterstützt werden, gelten Ablaufrichtlinien für Gruppen automatisch auch für Teams.

Wenn Sie eine Ablaufrichtlinie auf ein Team anwenden, erhält ein Teambesitzer 30 Tage, 15 Tage und 1 Tag vor dem Ablaufdatum des Teams eine Benachrichtigung zur Teamverlängerung. Wenn der Teambesitzer die Benachrichtigung erhält, kann er **in** den Teameinstellungen auf Jetzt verlängern klicken, um das Team zu verlängern.

![Screenshot der Schaltfläche "Jetzt verlängern" zum Verlängern eines Teams in den Teameinstellungen](media/team-expiration.png "Screenshot der Schaltfläche &quot;Jetzt verlängern&quot; zum Verlängern eines Teams in den Teameinstellungen")

Wenn der Teambesitzer das Team nicht verlängert und es bis zum Ende der Ablaufrichtlinie keine weiteren Aktivitäten für das Team gibt, wird das Team in den Status "Soft-Deleted" gesetzt, was bedeutet, dass es innerhalb der nächsten 30 Tage wiederhergestellt werden kann.

## <a name="team-auto-renewal"></a>Automatische Teamerneuerung

Es kann zeiten sein, dass ein Teambesitzer das Team nicht verlängern kann, weil er vergessen hat, zu verlängern, oder weil er bei Fälligkeit der Verlängerung nicht da war. In diesen Szenarien kann ein aktives Team aufgrund von Ablaufrichtlinien gelöscht werden, die für das Team gelten.  

Um ein versehentliches Löschen zu verhindern, wird die automatische Verlängerung automatisch für ein Team in der Ablaufrichtlinie für Gruppen aktiviert. Wenn die Ablaufrichtlinie für Gruppen eingerichtet ist, wird jedes Team, das vor dem Ablaufdatum mindestens einen Kanalbesuch von einem teammitglied hat, automatisch ohne manuelle Intervention des Teambesitzers verlängert.

## <a name="known-issues"></a>Bekannte Probleme

**Ablaufdatum der Team- und zugrunde liegenden Gruppe nicht übereinstimmen**

Bevor ein Team erneuert wird, wird zuerst die Gruppe, die das Team zurückseniert, erneuert. Im Rahmen der Verlängerung wird für die Gruppe ein neues Ablaufdatum für ein zukünftiges Datum festgelegt. Dieses neue Datum wird in der aktuellen Version möglicherweise nicht Teams. Die Synchronisierung kann bis zu 24 Stunden dauern. Wenn zwischen dem Ablaufdatum eines Teams und seiner zugrunde liegenden Gruppe ein Unterschied zu erkennen ist, warten Sie 24 Stunden, bevor Sie weitere Unterstützung suchen.