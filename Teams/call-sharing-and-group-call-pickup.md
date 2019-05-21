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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Mit der Anruf Freigabe und der Gruppenanruf-Pickup können Benutzer eingehende Anrufe an Kollegen weiterleiten, damit Anrufe aufgenommen werden können, wenn der Benutzer nicht verfügbar ist.
ms.openlocfilehash: 02c6605f3a5ea1df3457eaadea9956727431a827
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283479"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="c7907-103">Freigeben von Anrufen und Gruppenanrufannahme in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c7907-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="c7907-104">Mit den Funktionen für Anruf Freigabe und Gruppenanruf-Abholung von Microsoft Teams können Benutzer Ihre eingehenden Anrufe an Kollegen weitergeben, damit die Kollegen Anrufe entgegennehmen können, die eintreten, während der Benutzer nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c7907-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="c7907-105">Die Gruppenanruf Abholung ist weniger störend für die Empfänger als andere Formen der Anruf Freigabe (wie Anrufweiterleitung oder gleichzeitiges Klingeln), da Benutzer konfigurieren können, wie Sie über einen eingehenden freigegebenen Anruf benachrichtigt werden möchten (über Audio-und visuelle Benachrichtigung, nur visuell, oder Banner in der Teams-APP), und Sie können entscheiden, ob Sie Sie beantworten möchten.</span><span class="sxs-lookup"><span data-stu-id="c7907-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="c7907-106">Um Anrufe mit anderen zu teilen, erstellt ein Benutzer eine anrufgruppe und fügt die Benutzer hinzu, deren Anrufe Sie freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="c7907-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="c7907-107">Dann wählen Sie eine gleichzeitige Ring-oder Forward-Einstellung aus.</span><span class="sxs-lookup"><span data-stu-id="c7907-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="c7907-108">Weitere Informationen finden Sie unter [Anrufweiterleitung und gleichzeitiges anrufen in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="c7907-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7907-109">Benutzer, der Besitzer der anrufgruppe und Mitglieder der anrufgruppe müssen sich nur im Bereitstellungsmodus von Teams befinden.</span><span class="sxs-lookup"><span data-stu-id="c7907-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="c7907-110">Weitere Informationen zu den Bereitstellungsmodi für Teams finden Sie Untergrund Legendes zu [Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md) .</span><span class="sxs-lookup"><span data-stu-id="c7907-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="c7907-111">Lizenz erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7907-111">License required</span></span>

<span data-ttu-id="c7907-112">Für Benutzer muss Enterprise-VoIP aktiviert sein, um die Anruf Freigabe und die Gruppenanruf Abholung einzurichten und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7907-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="c7907-113">Weitere Informationen zum Lizenzierungsmodell finden Sie unter [Office 365-Lizenzierung für Microsoft Teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c7907-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="c7907-114">Konfigurieren der Gruppenanruf Abholung</span><span class="sxs-lookup"><span data-stu-id="c7907-114">Configure group call pickup</span></span>

<span data-ttu-id="c7907-115">Um die Gruppenanruf Abholung einzurichten, konfiguriert ein Benutzer zuerst eine anrufgruppe (Dies ist nicht dasselbe wie eine Sicherheitsgruppe oder eine Office 365-Gruppe) und fügt dann die Benutzer hinzu, für die Sie Ihre Anrufe freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="c7907-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="c7907-116">Dann wählen Sie eine gleichzeitige Klingel-oder Anruf Weiterleitungseinstellung.</span><span class="sxs-lookup"><span data-stu-id="c7907-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="c7907-117">Weitere Informationen und schrittweise Anleitungen finden Sie unter [Anrufweiterleitung und gleichzeitiges anrufen in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="c7907-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="c7907-118">Anrufgruppen Erstellung und Benachrichtigungseinstellungen sind benutzergesteuerte Funktionen. Administratoren müssen diese Features nicht für Ihre Benutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c7907-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="c7907-119">Anrufgruppen können nicht aus Sicherheitsgruppen oder Office 365-Gruppen erstellt werden. Sie müssen in Teams erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c7907-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="c7907-120">Administratoren sollten Anrufgruppen über die TeamsCallingPolicy- **AllowCallGroups** -Einstellung für einen Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c7907-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="c7907-121">Administratoren können nur steuern, ob dieser Benutzer Anrufgruppen konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="c7907-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="c7907-122">Sobald das Bit auf "true" festgelegt ist, können Administratoren den Benutzer nicht daran hindern, die Benutzer der anrufgruppe Ihrer Wahl zu konfigurieren und hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c7907-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="c7907-123">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c7907-123">Limitations</span></span>

<span data-ttu-id="c7907-124">Ein Mandant kann maximal 32.768 Anrufgruppen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c7907-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="c7907-125">In jeder anrufgruppe können maximal 5 Benutzer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="c7907-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="c7907-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7907-126">More information</span></span>

[<span data-ttu-id="c7907-127">Anrufweiterleitung und gleichzeitiges Klingeln in Teams</span><span class="sxs-lookup"><span data-stu-id="c7907-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)