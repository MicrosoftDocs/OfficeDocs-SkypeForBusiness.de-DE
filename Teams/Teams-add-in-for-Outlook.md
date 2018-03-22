---
title: Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Microsoft Teams installiert in Outlook ein Add-In, mit dem Benutzer Microsoft Teams-Besprechungen über Outlook planen können.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 811c27a48a0e9bbccfbea7ac12e54ef0697b3f2b
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="d5711-103">Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook</span><span class="sxs-lookup"><span data-stu-id="d5711-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="d5711-104">Das Microsoft Teams-Besprechungs-Add-In wird für Benutzer, auf deren Windows-PC Microsoft Teams und entweder Office 2013 oder Office 2016 installiert ist, automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="d5711-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="d5711-105">Die Benutzer sehen auf dem Menüband „Kalender“ in Outlook das Microsoft Teams-Besprechungs-Add-In.</span><span class="sxs-lookup"><span data-stu-id="d5711-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Screenshot des Microsoft Teams-Add-Ins auf dem Outlook-Menüband](media/Teams-add-in-for-Outlook.png)

<span data-ttu-id="d5711-107">Wenn Benutzer das Microsoft Teams-Besprechungs-Add-In nicht sehen, weisen Sie sie an, Outlook und Microsoft Teams zu schließen, den Microsoft Teams-Client neu zu starten, sich bei Microsoft Teams anzumelden und den Outlook-Client zu starten (in dieser Reihenfolge).</span><span class="sxs-lookup"><span data-stu-id="d5711-107">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="d5711-108">Das Microsoft Teams-Besprechungs-Add-In für Outlook ist für Mac-Benutzer zurzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d5711-108">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="d5711-109">Authentifizierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="d5711-109">Authentication requirements</span></span>

<span data-ttu-id="d5711-110">Benutzer des Microsoft Teams-Besprechungs-Add-Ins müssen sich mit moderner Authentifizierung bei Microsoft Teams anmelden.</span><span class="sxs-lookup"><span data-stu-id="d5711-110">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="d5711-111">Wenn sich Benutzer nicht mit dieser Methode anmelden, können sie zwar den Microsoft Teams-Client verwenden, aber sie können keine Microsoft Teams-Onlinebesprechungen mit dem Outlook-Add-In planen.</span><span class="sxs-lookup"><span data-stu-id="d5711-111">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="d5711-112">Dies können Sie mit einer der folgenden Methoden korrigieren:</span><span class="sxs-lookup"><span data-stu-id="d5711-112">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="d5711-113">Wenn die moderne Authentifizierung für Ihre Organisation nicht konfiguriert ist, sollten Sie sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d5711-113">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="d5711-114">Wenn die moderne Authentifizierung konfiguriert ist, aber die Benutzer den Vorgang im Dialogfeld abgebrochen haben, weisen Sie die Benutzer an, sich mit mehrstufiger Authentifizierung erneut anzumelden.</span><span class="sxs-lookup"><span data-stu-id="d5711-114">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="d5711-115">Weitere Informationen zum Konfigurieren der Authentifizierung finden Sie unter [Identitätsmodelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d5711-115">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="d5711-116">Aktivieren von privaten Besprechungen</span><span class="sxs-lookup"><span data-stu-id="d5711-116">Enable private meetings</span></span>

<span data-ttu-id="d5711-117">Die Option „Allow scheduling for private meetings“ (Planen von privaten Besprechungen zulassen) muss im [Office 365 Admin Center](https://portal.office.com/adminportal/home) aktiviert sein, damit das Plug-In bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d5711-117">Allow scheduling for private meetings must be enabled from the [Office 365 admin center](https://portal.office.com/adminportal/home) for the plug-in to get deployed.</span></span>

![Screenshot der Einstellungen im Abschnitt „Anrufe und Besprechungen“ im Office 365 Admin Center](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="d5711-119">Der Microsoft Teams-Client ermittelt, ob die Benutzer die 32-Bit- oder 64-Bit-Version benötigen, und installiert dann das richtige Add-In.</span><span class="sxs-lookup"><span data-stu-id="d5711-119">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="d5711-120">Möglicherweise müssen die Benutzer Outlook nach einer Installation oder einem Upgrade von Microsoft Teams neu starten, um das aktuelle Add-In zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d5711-120">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="d5711-121">Weitere Überlegungen</span><span class="sxs-lookup"><span data-stu-id="d5711-121">Other considerations</span></span>

<span data-ttu-id="d5711-122">Die Funktionen des Microsoft Teams-Besprechungs-Add-Ins werden noch weiterentwickelt. Beachten Sie daher Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d5711-122">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="d5711-123">Einige Funktionen von Onlinebesprechungen, beispielsweise Aufzeichnung, Umfragen und Whiteboards, sind noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d5711-123">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="d5711-124">Besprechungsoptionen sind zurzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d5711-124">Meeting options are currently not available.</span></span>
- <span data-ttu-id="d5711-125">Sie können zurzeit nur Personen aus Ihrer Firma einladen, da die Teilnahme externer Benutzer an Besprechungen noch nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="d5711-125">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="d5711-126">Das Add-In ist für geplante Besprechungen mit bestimmten Teilnehmern gedacht, nicht für Besprechungen in einem Kanal.</span><span class="sxs-lookup"><span data-stu-id="d5711-126">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="d5711-127">Kanalbesprechungen müssen in Microsoft Teams geplant werden.</span><span class="sxs-lookup"><span data-stu-id="d5711-127">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="d5711-128">Zurzeit ist das Microsoft Teams-Besprechungs-Add-In in Outlook nur für Windows-Benutzer verfügbar, aber die Unterstützung für Mac wird noch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d5711-128">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="d5711-129">Das Add-In funktioniert nicht, wenn sich im Netzwerkpfad zwischen dem PC des Benutzers und den Microsoft Teams-Diensten ein Authentifizierungsproxy befindet.</span><span class="sxs-lookup"><span data-stu-id="d5711-129">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>

<span data-ttu-id="d5711-130">Eine allgemeine Anleitung zum Deaktivieren von Add-Ins finden Sie unter [Anzeigen, Verwalten und Installieren von Add-Ins in Office-Programmen](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="d5711-130">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="d5711-131">Weitere Informationen zu [Besprechungen und Anrufen in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)</span><span class="sxs-lookup"><span data-stu-id="d5711-131">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

