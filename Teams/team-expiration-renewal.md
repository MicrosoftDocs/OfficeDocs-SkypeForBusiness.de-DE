---
title: Ablauf und Verlängerung des Teams in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über ablaufende und erneuerte Teams und wie Sie die Ablaufrichtlinie für Microsoft 365-Gruppen verwenden, um nicht verwendete Teams in Microsoft Teams automatisch zu bereinigen.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1a322e07df81727c75c05ebb16c4cdabc0916a4
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564173"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Ablauf und Verlängerung des Teams in Microsoft Teams

Organisationen mit einer großen Anzahl von Teams verfügen häufig über Teams, die nie tatsächlich verwendet werden. Dies kann aus mehreren Gründen geschehen, einschließlich Produktexperimenten, kurzfristiger Teamzusammenarbeit oder Teambesitzern, die die Organisation verlassen. Im Laufe der Zeit können sich solche Teams ansammeln und eine Belastung für Mandantenressourcen schaffen.  

Um die Anzahl nicht verwendeter Teams einzuschränken, können Sie als Administrator die [Ablaufrichtlinie für Microsoft 365-Gruppen](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) verwenden, um nicht verwendete Teams automatisch zu bereinigen. Da Teams von Gruppen unterstützt werden, gelten die Ablaufrichtlinien für Gruppen automatisch auch für Teams.

Wenn Sie eine Ablaufrichtlinie auf ein Team anwenden, erhält ein Teambesitzer eine Benachrichtigung über die Teamverlängerung 30 Tage, 15 Tage und 1 Tag vor dem Ablaufdatum des Teams. Wenn der Teambesitzer die Benachrichtigung erhält, kann er in den Teameinstellungen auf " **Jetzt verlängern** " klicken, um das Team zu erneuern.

![Screenshot der Schaltfläche "Jetzt verlängern", um ein Team in den Teameinstellungen zu verlängern.](media/team-expiration.png "Screenshot der Schaltfläche &quot;Jetzt verlängern&quot; zum Verlängern eines Teams in den Teameinstellungen")

Wenn der Teambesitzer das Team nicht verlängert und es bis zum Ende der Ablaufrichtlinie keine weiteren Aktivitäten im Team gibt, wird das Team in den Status "vorläufig gelöscht" versetzt, was bedeutet, dass es innerhalb der nächsten 30 Tage wiederhergestellt werden kann.

## <a name="team-auto-renewal"></a>Automatische Teamverlängerung

Es kann vorkommen, dass ein Teambesitzer das Team möglicherweise nicht verlängern kann, weil er vergessen hat, zu verlängern, oder weil er abwesend war, als die Verlängerung fällig war. In diesen Szenarien kann ein Team, das aktiv verwendet wird, aufgrund von Ablaufrichtlinien gelöscht werden, die für das Team gelten.  

Um ein versehentliches Löschen zu verhindern, wird die automatische Verlängerung automatisch für ein Team in der Ablaufrichtlinie der Gruppe aktiviert. Wenn die Gruppenablaufrichtlinie eingerichtet ist, wird jedes Team, das mindestens einen Kanalbesuch von einem Teammitglied vor seinem Ablaufdatum hat, automatisch ohne manuellen Eingriff des Teambesitzers erneuert.

## <a name="known-issues"></a>Bekannte Probleme

**Ablaufdatum des Teams und der zugrunde liegenden Gruppe stimmen nicht überein**

Bevor ein Team erneuert wird, wird die Gruppe, die das Team unterstützt, zuerst erneuert. Im Rahmen der Verlängerung wird für die Gruppe ein neues Ablaufdatum für ein zukünftiges Datum festgelegt. Dieses neue Datum ist in Teams möglicherweise nicht sofort sichtbar. Die Synchronisierung kann bis zu 24 Stunden dauern. Wenn eine Abweichung zwischen dem Ablaufdatum für ein Team und dessen zugrunde liegende Gruppe angezeigt wird, warten Sie 24 Stunden, bevor Sie weiteren Support anfordern.