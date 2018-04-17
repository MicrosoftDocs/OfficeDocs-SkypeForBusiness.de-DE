---
title: Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 04/09/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
localization_priority: Normal
description: Microsoft Teams installiert in Outlook ein Add-In, mit dem Benutzer Microsoft Teams-Besprechungen über Outlook planen können.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 109911e27a881ea09fb9854bb84ab19222722c39
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="62d7d-103">Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook</span><span class="sxs-lookup"><span data-stu-id="62d7d-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="62d7d-104">Das Microsoft Teams-Besprechungs-Add-In wird für Benutzer, auf deren Windows-PC Microsoft Teams und entweder Office 2013 oder Office 2016 installiert ist, automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="62d7d-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="62d7d-105">Die Benutzer sehen auf dem Menüband „Kalender“ in Outlook das Microsoft Teams-Besprechungs-Add-In.</span><span class="sxs-lookup"><span data-stu-id="62d7d-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Screenshot des Microsoft Teams-Add-Ins auf dem Outlook-Menüband](media/Teams-add-in-for-Outlook.png)

<span data-ttu-id="62d7d-107">Wenn Benutzer das Microsoft Teams-Besprechungs-Add-In nicht sehen, weisen Sie sie an, Outlook und Microsoft Teams zu schließen, den Microsoft Teams-Client neu zu starten, sich bei Microsoft Teams anzumelden und den Outlook-Client zu starten (in dieser Reihenfolge).</span><span class="sxs-lookup"><span data-stu-id="62d7d-107">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="62d7d-108">Das Microsoft Teams-Besprechungs-Add-In für Outlook ist für Mac-Benutzer zurzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="62d7d-108">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="62d7d-109">Authentifizierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="62d7d-109">Authentication requirements</span></span>

<span data-ttu-id="62d7d-110">Benutzer des Microsoft Teams-Besprechungs-Add-Ins müssen sich mit moderner Authentifizierung bei Microsoft Teams anmelden.</span><span class="sxs-lookup"><span data-stu-id="62d7d-110">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="62d7d-111">Wenn sich Benutzer nicht mit dieser Methode anmelden, können sie zwar den Microsoft Teams-Client verwenden, aber sie können keine Microsoft Teams-Onlinebesprechungen mit dem Outlook-Add-In planen.</span><span class="sxs-lookup"><span data-stu-id="62d7d-111">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="62d7d-112">Dies können Sie mit einer der folgenden Methoden korrigieren:</span><span class="sxs-lookup"><span data-stu-id="62d7d-112">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="62d7d-113">Wenn die moderne Authentifizierung für Ihre Organisation nicht konfiguriert ist, sollten Sie sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="62d7d-113">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="62d7d-114">Wenn die moderne Authentifizierung konfiguriert ist, aber die Benutzer den Vorgang im Dialogfeld abgebrochen haben, weisen Sie die Benutzer an, sich mit mehrstufiger Authentifizierung erneut anzumelden.</span><span class="sxs-lookup"><span data-stu-id="62d7d-114">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="62d7d-115">Weitere Informationen zum Konfigurieren der Authentifizierung finden Sie unter [Identitätsmodelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="62d7d-115">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="62d7d-116">Aktivieren von privaten Besprechungen</span><span class="sxs-lookup"><span data-stu-id="62d7d-116">Enable private meetings</span></span>

<span data-ttu-id="62d7d-117">Die Option „Allow scheduling for private meetings“ (Planen von privaten Besprechungen zulassen) muss im [Office 365 Admin Center](https://portal.office.com/adminportal/home) aktiviert sein, damit das Plug-In bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="62d7d-117">Allow scheduling for private meetings must be enabled from the [Office 365 admin center](https://portal.office.com/adminportal/home) for the plug-in to get deployed.</span></span>

![Screenshot der Einstellungen im Abschnitt „Anrufe und Besprechungen“ im Office 365 Admin Center](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="62d7d-119">Der Microsoft Teams-Client ermittelt, ob die Benutzer die 32-Bit- oder 64-Bit-Version benötigen, und installiert dann das richtige Add-In.</span><span class="sxs-lookup"><span data-stu-id="62d7d-119">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="62d7d-120">Möglicherweise müssen die Benutzer Outlook nach einer Installation oder einem Upgrade von Microsoft Teams neu starten, um das aktuelle Add-In zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="62d7d-120">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="62d7d-121">Weitere Überlegungen</span><span class="sxs-lookup"><span data-stu-id="62d7d-121">Other considerations</span></span>

<span data-ttu-id="62d7d-122">Die Funktionen des Microsoft Teams-Besprechungs-Add-Ins werden noch weiterentwickelt. Beachten Sie daher Folgendes:</span><span class="sxs-lookup"><span data-stu-id="62d7d-122">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="62d7d-123">Einige Funktionen von Onlinebesprechungen, beispielsweise Aufzeichnung, Umfragen und Whiteboards, sind noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="62d7d-123">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="62d7d-124">Besprechungsoptionen sind zurzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="62d7d-124">Meeting options are currently not available.</span></span>
- <span data-ttu-id="62d7d-125">Sie können zurzeit nur Personen aus Ihrer Firma einladen, da die Teilnahme externer Benutzer an Besprechungen noch nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="62d7d-125">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="62d7d-126">Das Add-In ist für geplante Besprechungen mit bestimmten Teilnehmern gedacht, nicht für Besprechungen in einem Kanal.</span><span class="sxs-lookup"><span data-stu-id="62d7d-126">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="62d7d-127">Kanalbesprechungen müssen in Microsoft Teams geplant werden.</span><span class="sxs-lookup"><span data-stu-id="62d7d-127">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="62d7d-128">Zurzeit ist das Microsoft Teams-Besprechungs-Add-In in Outlook nur für Windows-Benutzer verfügbar, aber die Unterstützung für Mac wird noch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="62d7d-128">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="62d7d-129">Das Add-In funktioniert nicht, wenn sich im Netzwerkpfad zwischen dem PC des Benutzers und den Microsoft Teams-Diensten ein Authentifizierungsproxy befindet.</span><span class="sxs-lookup"><span data-stu-id="62d7d-129">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="62d7d-130">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="62d7d-130">Troubleshooting</span></span>

<span data-ttu-id="62d7d-131">Wenn Sie die Besprechung Teams add-in für Outlook installieren nicht, versuchen Sie diese Schritte zur Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="62d7d-131">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="62d7d-132">Starten Sie den Desktopclient Teams neu.</span><span class="sxs-lookup"><span data-stu-id="62d7d-132">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="62d7d-133">Melden Sie sich ab und dann wieder anmelden auf dem Desktopclient Teams.</span><span class="sxs-lookup"><span data-stu-id="62d7d-133">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="62d7d-134">Starten Sie den desktop Outlook-Client neu.</span><span class="sxs-lookup"><span data-stu-id="62d7d-134">Restart the Outlook desktop client.</span></span> <span data-ttu-id="62d7d-135">(Stellen Sie sicher, dass Outlook nicht im Admin-Modus ausgeführt wird.)</span><span class="sxs-lookup"><span data-stu-id="62d7d-135">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="62d7d-136">Stellen Sie sicher, dass der Kontoname angemeldeten Benutzer keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="62d7d-136">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="62d7d-137">(Dies ist ein bekanntes Problem und wird in einem zukünftigen Update behoben werden.)</span><span class="sxs-lookup"><span data-stu-id="62d7d-137">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="62d7d-138">Stellen Sie sicher, dass einmaliges Anmelden (SSO) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="62d7d-138">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="62d7d-139">Eine allgemeine Anleitung zum Deaktivieren von Add-Ins finden Sie unter [Anzeigen, Verwalten und Installieren von Add-Ins in Office-Programmen](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="62d7d-139">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="62d7d-140">Weitere Informationen zu [Besprechungen und Anrufen in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)</span><span class="sxs-lookup"><span data-stu-id="62d7d-140">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>
