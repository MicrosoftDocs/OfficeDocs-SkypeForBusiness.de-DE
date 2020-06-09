---
title: Ablauf und Erneuerung von Teams in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über das Ablaufdatum und die Erneuerung von Teams und wie Sie die Microsoft 365-oder Microsoft 365-Gruppen Ablaufrichtlinie verwenden, um nicht verwendete Teams in Microsoft Teams automatisch zu bereinigen.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34984c545e3e6593c9d5168a81d3465ce391dab2
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638554"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Ablauf und Erneuerung von Teams in Microsoft Teams

Organisationen mit einer hohen Anzahl von Teams verfügen häufig über Teams, die nie tatsächlich verwendet werden. Dies kann aus verschiedenen Gründen geschehen, darunter Produkt Experimente, kurzfristige Teamzusammenarbeit oder Teambesitzer, die das Unternehmen verlassen. Im Laufe der Zeit können sich solche Teams akkumulieren und eine Belastung für Mandanten Ressourcen verursachen.  

Wenn Sie die Anzahl der nicht verwendeten Teams als Administrator einschränken möchten, können Sie die [Microsoft 365-oder Microsoft 365-Gruppen Ablaufrichtlinie](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) verwenden, um nicht verwendete Teams automatisch zu bereinigen. Da Teams von Gruppen gesichert werden, gelten Gruppen Ablaufrichtlinien automatisch auch für Teams.

Wenn Sie eine Ablaufrichtlinie auf ein Team anwenden, erhält ein Teambesitzer eine Benachrichtigung für die Team Erneuerung 30 Tage, 15 Tage und einen Tag vor dem Ablaufdatum des Teams. Wenn der Teambesitzer die Benachrichtigung erhält, kann er in den Team Einstellungen auf **jetzt verlängern** klicken, um das Team zu erneuern.

![Screenshot der Schaltfläche "jetzt verlängern" zum Verlängern eines Teams in den Team Einstellungen](media/team-expiration.png "Screenshot der Schaltfläche "jetzt verlängern" zum Verlängern eines Teams in den Team Einstellungen")

Wenn der Teambesitzer das Team nicht erneuert, wird das Team in einen "Soft-Deleted"-Zustand versetzt, was bedeutet, dass es in den nächsten 30 Tagen wiederhergestellt werden kann.

## <a name="team-auto-renewal"></a>Automatische Verlängerung des Teams

Es kann vorkommen, dass ein Teambesitzer nicht in der Lage ist, das Team zu erneuern, weil er vergessen hat, zu verlängern oder abwesend zu sein, als die Verlängerung fällig wurde. In diesen Szenarien kann ein Team, das aktiv verwendet wird, aufgrund von Ablaufrichtlinien, die für das Team gelten, gelöscht werden.  

Um versehentliches Löschen zu verhindern, wird die automatische Verlängerung für ein Team in der Gruppen Ablaufrichtlinie automatisch aktiviert. Wenn die Gruppen Ablaufrichtlinie eingerichtet ist, wird jedes Team, das mindestens einen Kanal Besuch von einem Teammitglied vor seinem Ablaufdatum hat, automatisch verlängert, ohne dass ein manueller Eingriff des Team Besitzers erfolgt.

## <a name="known-issues"></a>Bekannte Probleme

**Das Ablaufdatum für das Team und die zugrunde liegende Gruppe stimmen nicht überein**

Bevor ein Team erneuert wird, wird die Gruppe, die das Team zurückgibt, zuerst erneuert. Im Rahmen der Verlängerung wird für die Gruppe ein neues Ablaufdatum für ein zukünftiges Datum gesetzt. Dieses neue Datum ist möglicherweise nicht sofort in Teams sichtbar. Die Synchronisierung kann bis zu 24 Stunden dauern. Wenn Sie eine Diskrepanz zwischen dem Ablaufdatum eines Teams und der zugrunde liegenden Gruppe sehen, warten Sie 24 Stunden, bevor Sie weitere Unterstützung suchen.
