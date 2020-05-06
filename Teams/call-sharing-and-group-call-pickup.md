---
title: Freigeben von Anrufen und Gruppenanrufannahme
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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Mit der Anruf Freigabe und der Gruppenanruf-Pickup können Benutzer eingehende Anrufe an Kollegen weiterleiten, damit Anrufe aufgenommen werden können, wenn der Benutzer nicht verfügbar ist.
ms.openlocfilehash: 8ed53ca5103d3ee4264e0dc1aef3267172d37527
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042952"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="8aee7-103">Freigeben von Anrufen und Gruppenanrufannahme in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8aee7-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="8aee7-104">Mit den Funktionen für Anruf Freigabe und Gruppenanruf-Abholung von Microsoft Teams können Benutzer Ihre eingehenden Anrufe an Kollegen weitergeben, damit die Kollegen Anrufe entgegennehmen können, die eintreten, während der Benutzer nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8aee7-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="8aee7-105">Die Gruppenanruf Abholung ist weniger störend für Empfänger als andere Formen der Anruf Freigabe (wie Anrufweiterleitung oder gleichzeitiges Klingeln), da Benutzer konfigurieren können, wie Sie über einen eingehenden freigegebenen Anruf benachrichtigt werden möchten (über Audio-und visuelle Benachrichtigung, nur visuell oder Banner in der Teams-APP), und Sie können entscheiden, ob Sie Sie beantworten möchten.</span><span class="sxs-lookup"><span data-stu-id="8aee7-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="8aee7-106">Um Anrufe mit anderen zu teilen, erstellt ein Benutzer eine anrufgruppe und fügt die Benutzer hinzu, deren Anrufe Sie freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="8aee7-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="8aee7-107">Dann wählen Sie eine gleichzeitige Ring-oder Forward-Einstellung aus.</span><span class="sxs-lookup"><span data-stu-id="8aee7-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="8aee7-108">Weitere Informationen finden Sie unter [Anrufweiterleitung und gleichzeitiges anrufen in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="8aee7-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8aee7-109">Benutzer, der Besitzer der anrufgruppe und Mitglieder der anrufgruppe müssen sich nur im Bereitstellungsmodus von Teams befinden.</span><span class="sxs-lookup"><span data-stu-id="8aee7-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="8aee7-110">Weitere Informationen zu den Bereitstellungsmodi für Teams finden Sie Untergrund [Legendes zu Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md) .</span><span class="sxs-lookup"><span data-stu-id="8aee7-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="8aee7-111">Lizenz erforderlich</span><span class="sxs-lookup"><span data-stu-id="8aee7-111">License required</span></span>

<span data-ttu-id="8aee7-112">Für Benutzer muss Enterprise-VoIP aktiviert sein, um die Anruf Freigabe und die Gruppenanruf Abholung einzurichten und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8aee7-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="8aee7-113">Weitere Informationen zum Lizenzierungsmodell finden Sie in der [Microsoft Teams-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="8aee7-113">For additional details on the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="8aee7-114">Konfigurieren der Gruppenanruf Abholung</span><span class="sxs-lookup"><span data-stu-id="8aee7-114">Configure group call pickup</span></span>

<span data-ttu-id="8aee7-115">Um die Gruppenanruf Abholung einzurichten, konfiguriert ein Benutzer zuerst eine anrufgruppe (Dies ist nicht dasselbe wie eine Sicherheitsgruppe oder eine Office 365-Gruppe) und fügt dann die Benutzer hinzu, für die Sie Ihre Anrufe freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="8aee7-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="8aee7-116">Dann wählen Sie eine gleichzeitige Klingel-oder Anruf Weiterleitungseinstellung.</span><span class="sxs-lookup"><span data-stu-id="8aee7-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="8aee7-117">Weitere Informationen und schrittweise Anleitungen finden Sie unter [Anrufweiterleitung und gleichzeitiges anrufen in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="8aee7-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="8aee7-118">Anrufgruppen Erstellung und Benachrichtigungseinstellungen sind benutzergesteuerte Funktionen. Administratoren müssen diese Features nicht für Ihre Benutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8aee7-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="8aee7-119">Anrufgruppen können nicht aus Sicherheitsgruppen oder Microsoft 365-Gruppen erstellt werden. Sie müssen in Teams erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8aee7-119">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="8aee7-120">Administratoren sollten Anrufgruppen über die TeamsCallingPolicy- **AllowCallGroups** -Einstellung für einen Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8aee7-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="8aee7-121">Administratoren können dies auch über das Team-Administratorportal aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8aee7-121">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="8aee7-122">Darüber hinaus kann der konfigurierte Benutzer seine Anrufgruppen auch direkt über den Client konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8aee7-122">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="8aee7-123">Administratoren oder Endbenutzer können die Konfiguration nicht voneinander blockieren, aber Teams-Administratorportal und Teams-Client sollten diese Beziehung an beiden Stellen genau anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8aee7-123">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="8aee7-124">Wichtig: Wenn Administratoren Anrufgruppen für Benutzer deaktivieren (nachdem Sie aktiviert wurde und die Anrufgruppen Beziehungen konfiguriert sind), müssen die Administratoren die Anrufgruppen Beziehungen für Benutzer im Team Admin Center bereinigen, um ein fehlerhaftes Anrufrouting zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="8aee7-124">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="8aee7-125">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8aee7-125">Limitations</span></span>

<span data-ttu-id="8aee7-126">Ein Mandant kann maximal 32.768 Anrufgruppen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8aee7-126">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="8aee7-127">In jeder anrufgruppe können maximal 25 Benutzer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="8aee7-127">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="8aee7-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8aee7-128">More information</span></span>

[<span data-ttu-id="8aee7-129">Anrufweiterleitung und gleichzeitiges Klingeln in Teams</span><span class="sxs-lookup"><span data-stu-id="8aee7-129">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
