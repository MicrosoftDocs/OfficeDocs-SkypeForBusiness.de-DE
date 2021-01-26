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
description: Erfahren Sie mehr über Ablauf und Verlängerung von Teams sowie über die Verwendung der Ablaufrichtlinie für Microsoft 365-Gruppen, um nicht verwendete Teams in Microsoft Teams automatisch zu bereinigen.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b111ddd6b874fef22a7d221f6eb932c4c14c7b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809405"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Ablauf und Verlängerung des Teams in Microsoft Teams

Organisationen mit einer großen Anzahl von Teams verfügen häufig über Teams, die nie tatsächlich verwendet werden. Dies kann aus mehreren Gründen geschehen, z. B. aus Produkt experimentieren, aus einer kurzen Teamzusammenarbeit oder aus Teambesitzern, die die Organisation verlassen. Im Laufe der Zeit können sich solche Teams ansammeln und Mandantenressourcen belasten.  

Um die Anzahl der nicht verwendeten Teams einzudämmen, können Sie als Administrator die Ablaufrichtlinie für [Microsoft 365-Gruppen](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) verwenden, um nicht verwendete Teams automatisch zu bereinigen. Da Teams durch Gruppen gesichert werden, gelten Ablaufrichtlinien für Gruppen automatisch auch für Teams.

Wenn Sie eine Ablaufrichtlinie auf ein Team anwenden, erhält ein Teambesitzer 30 Tage, 15 Tage und 1 Tag vor dem Ablaufdatum des Teams eine Benachrichtigung zur Teamverlängerung. Wenn der Teambesitzer die Benachrichtigung erhält, kann er **in** den Teameinstellungen auf "Jetzt verlängern" klicken, um das Team zu verlängern.

![Screenshot der Schaltfläche "Jetzt verlängern" zum Verlängern eines Teams in den Teameinstellungen](media/team-expiration.png "Screenshot der Schaltfläche "Jetzt verlängern" zum Verlängern eines Teams in den Teameinstellungen")

Wenn der Teambesitzer das Team nicht verlängert und es bis zum Ende der Ablaufrichtlinie keine weiteren Aktivitäten für das Team gibt, wird das Team in den Status "Soft-Deleted" gesetzt, was bedeutet, dass es innerhalb der nächsten 30 Tage wiederhergestellt werden kann.

## <a name="team-auto-renewal"></a>Automatische Verlängerung des Teams

Es kann zeiten sein, in denen ein Teambesitzer das Team nicht verlängern kann, weil er vergessen hat, zu verlängern, oder weil er nicht da war, als die Verlängerung fällig war. In diesen Szenarien kann ein aktives Team aufgrund von Ablaufrichtlinien gelöscht werden, die für das Team gelten.  

Um versehentliches Löschen zu verhindern, wird die automatische Verlängerung für ein Team in der Ablaufrichtlinie der Gruppe automatisch aktiviert. Wenn die Gruppenablaufrichtlinie eingerichtet ist, wird jedes Team, das vor dem Ablaufdatum mindestens einen Kanalbesuch von einem Teammitglied hat, automatisch ohne manuelle Maßnahme des Teambesitzers verlängert.

## <a name="known-issues"></a>Bekannte Probleme

**Ablaufdatum von Team und zugrunde liegender Gruppe passt nicht**

Bevor ein Team verlängert wird, wird zuerst die Gruppe, die das Team zurückeriert, erneuert. Im Rahmen der Verlängerung wird für die Gruppe ein neues Ablaufdatum für ein zukünftiges Datum festgelegt. Dieses neue Datum ist in Teams möglicherweise nicht sofort sichtbar. Die Synchronisierung kann bis zu 24 Stunden dauern. Wenn sie eine Abweichung zwischen dem Ablaufdatum für ein Team und seiner zugrunde liegenden Gruppe sehen, warten Sie 24 Stunden, bevor Sie weitere Unterstützung erhalten.
