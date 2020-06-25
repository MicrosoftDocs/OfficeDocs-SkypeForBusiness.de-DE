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
description: Erfahren Sie mehr über das Ablaufdatum und die Erneuerung von Teams und die Verwendung der Microsoft 365-Gruppen Ablaufrichtlinie zum automatischen Bereinigen von nicht verwendeten Teams in Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 697e36085169e0666e6a821a66c763be39cf9425
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868522"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="b3975-103">Ablauf und Erneuerung von Teams in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3975-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="b3975-104">Organisationen mit einer hohen Anzahl von Teams verfügen häufig über Teams, die nie tatsächlich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b3975-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="b3975-105">Dies kann aus verschiedenen Gründen geschehen, darunter Produkt Experimente, kurzfristige Teamzusammenarbeit oder Teambesitzer, die das Unternehmen verlassen.</span><span class="sxs-lookup"><span data-stu-id="b3975-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="b3975-106">Im Laufe der Zeit können sich solche Teams akkumulieren und eine Belastung für Mandanten Ressourcen verursachen.</span><span class="sxs-lookup"><span data-stu-id="b3975-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="b3975-107">Wenn Sie die Anzahl der nicht verwendeten Teams als Administrator einschränken möchten, können Sie die [Microsoft 365-Gruppen Ablaufrichtlinie](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) verwenden, um nicht verwendete Teams automatisch zu bereinigen.</span><span class="sxs-lookup"><span data-stu-id="b3975-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="b3975-108">Da Teams von Gruppen gesichert werden, gelten Gruppen Ablaufrichtlinien automatisch auch für Teams.</span><span class="sxs-lookup"><span data-stu-id="b3975-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="b3975-109">Wenn Sie eine Ablaufrichtlinie auf ein Team anwenden, erhält ein Teambesitzer eine Benachrichtigung für die Team Erneuerung 30 Tage, 15 Tage und einen Tag vor dem Ablaufdatum des Teams.</span><span class="sxs-lookup"><span data-stu-id="b3975-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="b3975-110">Wenn der Teambesitzer die Benachrichtigung erhält, kann er in den Team Einstellungen auf **jetzt verlängern** klicken, um das Team zu erneuern.</span><span class="sxs-lookup"><span data-stu-id="b3975-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="b3975-111">![Screenshot der Schaltfläche "jetzt verlängern" zum Verlängern eines Teams in den Team Einstellungen](media/team-expiration.png "Screenshot der Schaltfläche "jetzt verlängern" zum Verlängern eines Teams in den Team Einstellungen")</span><span class="sxs-lookup"><span data-stu-id="b3975-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="b3975-112">Wenn der Teambesitzer das Team nicht erneuert, wird das Team in einen "Soft-Deleted"-Zustand versetzt, was bedeutet, dass es in den nächsten 30 Tagen wiederhergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3975-112">If the team owner doesn't renew the team, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="b3975-113">Automatische Verlängerung des Teams</span><span class="sxs-lookup"><span data-stu-id="b3975-113">Team auto-renewal</span></span>

<span data-ttu-id="b3975-114">Es kann vorkommen, dass ein Teambesitzer nicht in der Lage ist, das Team zu erneuern, weil er vergessen hat, zu verlängern oder abwesend zu sein, als die Verlängerung fällig wurde.</span><span class="sxs-lookup"><span data-stu-id="b3975-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="b3975-115">In diesen Szenarien kann ein Team, das aktiv verwendet wird, aufgrund von Ablaufrichtlinien, die für das Team gelten, gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b3975-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="b3975-116">Um versehentliches Löschen zu verhindern, wird die automatische Verlängerung für ein Team in der Gruppen Ablaufrichtlinie automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b3975-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="b3975-117">Wenn die Gruppen Ablaufrichtlinie eingerichtet ist, wird jedes Team, das mindestens einen Kanal Besuch von einem Teammitglied vor seinem Ablaufdatum hat, automatisch verlängert, ohne dass ein manueller Eingriff des Team Besitzers erfolgt.</span><span class="sxs-lookup"><span data-stu-id="b3975-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b3975-118">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="b3975-118">Known issues</span></span>

<span data-ttu-id="b3975-119">**Das Ablaufdatum für das Team und die zugrunde liegende Gruppe stimmen nicht überein**</span><span class="sxs-lookup"><span data-stu-id="b3975-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="b3975-120">Bevor ein Team erneuert wird, wird die Gruppe, die das Team zurückgibt, zuerst erneuert.</span><span class="sxs-lookup"><span data-stu-id="b3975-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="b3975-121">Im Rahmen der Verlängerung wird für die Gruppe ein neues Ablaufdatum für ein zukünftiges Datum gesetzt.</span><span class="sxs-lookup"><span data-stu-id="b3975-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="b3975-122">Dieses neue Datum ist möglicherweise nicht sofort in Teams sichtbar.</span><span class="sxs-lookup"><span data-stu-id="b3975-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="b3975-123">Die Synchronisierung kann bis zu 24 Stunden dauern. Wenn Sie eine Diskrepanz zwischen dem Ablaufdatum eines Teams und der zugrunde liegenden Gruppe sehen, warten Sie 24 Stunden, bevor Sie weitere Unterstützung suchen.</span><span class="sxs-lookup"><span data-stu-id="b3975-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
