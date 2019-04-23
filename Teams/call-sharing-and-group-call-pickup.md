---
title: Freigeben von Anrufen und Gruppenanrufannahme in Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Rufen Sie die Freigabe, und Gruppe Anruf Pickup-kann Benutzer eingehende Anrufe mit Kollegen freigeben, sodass Anrufe erst erfasst werden können, wenn der Benutzer nicht verfügbar ist.
ms.openlocfilehash: e822d06e48f3d7df548f0fd0d04645e7e9328598
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993581"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="7e7f8-103">Freigeben von Anrufen und Gruppenanrufannahme in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e7f8-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="7e7f8-104">Der Anruf Freigabe und der Gruppe anrufen pickup Features von Microsoft-Teams können Benutzer freigeben, die ihre eingehenden mit Kollegen Anrufe, sodass die Kollegen Anrufe, die auftreten entgegennehmen können, wenn der Benutzer nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="7e7f8-105">Gruppe Anruf Pickup-ist weniger störende an Empfänger als andere Arten von Anrufen (wie Anruf weiterleiten oder Gleichzeitiges Klingeln) freigeben, da Benutzer konfigurieren können, wie sie einen freigegebenen eingehenden Anruf (über eine Audio- und optische Benachrichtigung nur Visual benachrichtigt werden möchten oder in der app Teams Banner), und sie können entscheiden, ob annehmen des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="7e7f8-106">Um Anrufe für andere Personen freigeben, ein Benutzer erstellt eine anrufgruppe und fügt die Benutzer, denen sie ihre Anrufe mit freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="7e7f8-107">Klicken Sie dann wählen Sie ein Gleichzeitiges Klingeln oder Einstellung weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="7e7f8-108">Einzelheiten finden Sie in der [anrufweiterleitung und Gleichzeitiges Klingeln in Teams aufrufen](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="7e7f8-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e7f8-109">Benutzer, die Besitzer der Gruppe anrufen und Mitglieder der anrufgruppe muss in Teams nur Bereitstellungsmodus.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="7e7f8-110">Weitere Informationen zu Bereitstellungsmethoden Teams finden Sie unter [Grundlegendes zu Microsoft-Teams und Skype für Interoperabilität und Koexistenz Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="7e7f8-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="7e7f8-111">Lizenz erforderlich</span><span class="sxs-lookup"><span data-stu-id="7e7f8-111">License required</span></span>

<span data-ttu-id="7e7f8-112">Benutzer müssen Enterprise-VoIP, die zum Einrichten und verwenden Anruf Freigabe und Anruf Pickup-gruppieren aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="7e7f8-113">Weitere Details zur am Lizenzierungsmodell finden Sie unter [Office 365-Lizenzierung für Microsoft-Teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="7e7f8-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="7e7f8-114">Konfigurieren der Gruppe Anruf Pickup-</span><span class="sxs-lookup"><span data-stu-id="7e7f8-114">Configure group call pickup</span></span>

<span data-ttu-id="7e7f8-115">Zum Einrichten der Gruppe Anruf Pickup-ein Benutzer zuerst konfiguriert eine anrufgruppe (Dies ist nicht dasselbe wie eine Sicherheitsgruppe oder ein Office 365) und fügt dann die Benutzer, die sie ihre Anrufe mit freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="7e7f8-116">Klicken Sie dann, wählen Sie ein Gleichzeitiges Klingeln oder forward Einstellung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="7e7f8-117">Weitere Informationen und schrittweise Verfahren finden Sie unter [anrufweiterleitung und Gleichzeitiges Klingeln in Teams aufrufen](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="7e7f8-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="7e7f8-118">Rufen Sie die Gruppe erstellen und die Benachrichtigung, dass Voreinstellungen benutzergesteuerten Features sind. Administratoren müssen nicht diese Funktionen für die Benutzer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="7e7f8-119">Anruf Gruppen können nicht von Sicherheitsgruppen oder Office 365-Gruppen erstellt werden. Sie müssen in Teams erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="7e7f8-120">Administratoren sollten Anruf Gruppen über die **TeamsCallingPolicy AllowCallGroups** Einstellung für einen Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="7e7f8-121">Administratoren können nur gesteuert wird, ob dieser Benutzer Anruf Gruppen konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="7e7f8-122">Nachdem das Bit Admins "true" festgelegt ist nicht möglich, dass Benutzer aus konfigurieren, und fügen Sie dem Anruf GruppenBenutzer ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="7e7f8-123">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7e7f8-123">Limitations</span></span>

<span data-ttu-id="7e7f8-124">Ein Mandant kann bis zu 32.768 Anruf Gruppen enthalten.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="7e7f8-125">Es können maximal 5 Benutzer in den einzelnen Gruppen Anruf vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="7e7f8-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e7f8-126">More information</span></span>

[<span data-ttu-id="7e7f8-127">Die anrufweiterleitung und Gleichzeitiges Klingeln in Teams</span><span class="sxs-lookup"><span data-stu-id="7e7f8-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)