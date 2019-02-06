---
title: Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 10/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams installiert in Outlook ein Add-In, mit dem Benutzer Microsoft Teams-Besprechungen über Outlook planen können.
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: e892e5c615fce6ed8c65fdfaeadbacba88e1ec5c
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753750"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="f7999-103">Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook</span><span class="sxs-lookup"><span data-stu-id="f7999-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f7999-104">Das Microsoft Teams-Besprechungs-Add-In wird für Benutzer, auf deren Windows-PC Microsoft Teams und entweder Office 2013 oder Office 2016 installiert ist, automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="f7999-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="f7999-105">Die Benutzer sehen auf dem Menüband „Kalender“ in Outlook das Microsoft Teams-Besprechungs-Add-In.</span><span class="sxs-lookup"><span data-stu-id="f7999-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Screenshot des Microsoft Teams-Add-Ins auf dem Outlook-Menüband](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> <span data-ttu-id="f7999-107">Windows 7-Benutzer müssen das [Update für universelle C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) für Teams Meeting-add-in zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f7999-107">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>

<span data-ttu-id="f7999-108">Wenn Benutzer das Microsoft Teams-Besprechungs-Add-In nicht sehen, weisen Sie sie an, Outlook und Microsoft Teams zu schließen, den Microsoft Teams-Client neu zu starten, sich bei Microsoft Teams anzumelden und den Outlook-Client zu starten (in dieser Reihenfolge).</span><span class="sxs-lookup"><span data-stu-id="f7999-108">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="f7999-109">Das Microsoft Teams-Besprechungs-Add-In für Outlook ist für Mac-Benutzer zurzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7999-109">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="f7999-110">Authentifizierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="f7999-110">Authentication requirements</span></span>

<span data-ttu-id="f7999-111">Benutzer des Microsoft Teams-Besprechungs-Add-Ins müssen sich mit moderner Authentifizierung bei Microsoft Teams anmelden.</span><span class="sxs-lookup"><span data-stu-id="f7999-111">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="f7999-112">Wenn sich Benutzer nicht mit dieser Methode anmelden, können sie zwar den Microsoft Teams-Client verwenden, aber sie können keine Microsoft Teams-Onlinebesprechungen mit dem Outlook-Add-In planen.</span><span class="sxs-lookup"><span data-stu-id="f7999-112">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="f7999-113">Dies können Sie mit einer der folgenden Methoden korrigieren:</span><span class="sxs-lookup"><span data-stu-id="f7999-113">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="f7999-114">Wenn die moderne Authentifizierung für Ihre Organisation nicht konfiguriert ist, sollten Sie sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f7999-114">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="f7999-115">Wenn die moderne Authentifizierung konfiguriert ist, aber die Benutzer den Vorgang im Dialogfeld abgebrochen haben, weisen Sie die Benutzer an, sich mit mehrstufiger Authentifizierung erneut anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f7999-115">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="f7999-116">Weitere Informationen zum Konfigurieren der Authentifizierung finden Sie unter [Identitätsmodelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f7999-116">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="f7999-117">Aktivieren von privaten Besprechungen</span><span class="sxs-lookup"><span data-stu-id="f7999-117">Enable private meetings</span></span>

<span data-ttu-id="f7999-118">Zulassen Sie, dass in der Microsoft-Teams-Verwaltungskonsole für das plug-in bereitgestellt Planung für private Konferenzen aktiviert werden muss.</span><span class="sxs-lookup"><span data-stu-id="f7999-118">Allow scheduling for private meetings must be enabled in the Microsoft Teams admin center for the plug-in to get deployed.</span></span> <span data-ttu-id="f7999-119">Wechseln Sie in der Verwaltungskonsole zu **Besprechungen** > **Besprechungsrichtlinien**, und wechseln Sie in den Abschnitt **Allgemein** **Planen von privaten Besprechungen zulassen** auf On.)</span><span class="sxs-lookup"><span data-stu-id="f7999-119">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Screenshot der Einstellungen in der Verwaltungskonsole von Microsoft-Teams.](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="f7999-121">Der Microsoft Teams-Client ermittelt, ob die Benutzer die 32-Bit- oder 64-Bit-Version benötigen, und installiert dann das richtige Add-In.</span><span class="sxs-lookup"><span data-stu-id="f7999-121">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="f7999-122">Möglicherweise müssen die Benutzer Outlook nach einer Installation oder einem Upgrade von Microsoft Teams neu starten, um das aktuelle Add-In zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f7999-122">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="f7999-123">Weitere Überlegungen</span><span class="sxs-lookup"><span data-stu-id="f7999-123">Other considerations</span></span>

<span data-ttu-id="f7999-124">Die Funktionen des Microsoft Teams-Besprechungs-Add-Ins werden noch weiterentwickelt. Beachten Sie daher Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f7999-124">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="f7999-125">Einige Funktionen von Onlinebesprechungen, beispielsweise Aufzeichnung, Umfragen und Whiteboards, sind noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7999-125">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="f7999-126">Besprechungsoptionen sind zurzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7999-126">Meeting options are currently not available.</span></span>
- <span data-ttu-id="f7999-127">Das Add-In ist für geplante Besprechungen mit bestimmten Teilnehmern gedacht, nicht für Besprechungen in einem Kanal.</span><span class="sxs-lookup"><span data-stu-id="f7999-127">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="f7999-128">Kanalbesprechungen müssen in Microsoft Teams geplant werden.</span><span class="sxs-lookup"><span data-stu-id="f7999-128">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="f7999-129">Zurzeit ist das Microsoft Teams-Besprechungs-Add-In in Outlook nur für Windows-Benutzer verfügbar, aber die Unterstützung für Mac wird noch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f7999-129">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="f7999-130">Das Add-In funktioniert nicht, wenn sich im Netzwerkpfad zwischen dem PC des Benutzers und den Microsoft Teams-Diensten ein Authentifizierungsproxy befindet.</span><span class="sxs-lookup"><span data-stu-id="f7999-130">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="f7999-131">Das Add-in wird schrittweise eingeführt werden und möglicherweise nicht für Ihre Organisation noch verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f7999-131">The add-in is being rolled out incrementally and might not be available for your organization yet.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f7999-132">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f7999-132">Troubleshooting</span></span>

<span data-ttu-id="f7999-133">Wenn Sie die Besprechung Teams add-in für Outlook installieren nicht, versuchen Sie diese Schritte zur Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="f7999-133">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="f7999-134">Stellen Sie sicher, dass alle verfügbaren Updates für Outlook-Desktopclient angewendet wurden</span><span class="sxs-lookup"><span data-stu-id="f7999-134">Ensure all available updates for Outlook desktop client have been applied</span></span> 
- <span data-ttu-id="f7999-135">Starten Sie den Desktopclient Teams neu.</span><span class="sxs-lookup"><span data-stu-id="f7999-135">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="f7999-136">Melden Sie sich ab und dann wieder anmelden auf dem Desktopclient Teams.</span><span class="sxs-lookup"><span data-stu-id="f7999-136">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="f7999-137">Starten Sie den desktop Outlook-Client neu.</span><span class="sxs-lookup"><span data-stu-id="f7999-137">Restart the Outlook desktop client.</span></span> <span data-ttu-id="f7999-138">(Stellen Sie sicher, dass Outlook nicht im Admin-Modus ausgeführt wird.)</span><span class="sxs-lookup"><span data-stu-id="f7999-138">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="f7999-139">Stellen Sie sicher, dass der Kontoname angemeldeten Benutzer keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f7999-139">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="f7999-140">(Dies ist ein bekanntes Problem und wird in einem zukünftigen Update behoben werden.)</span><span class="sxs-lookup"><span data-stu-id="f7999-140">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="f7999-141">Stellen Sie sicher, dass einmaliges Anmelden (SSO) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f7999-141">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="f7999-142">Eine allgemeine Anleitung zum Deaktivieren von Add-Ins finden Sie unter [Anzeigen, Verwalten und Installieren von Add-Ins in Office-Programmen](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="f7999-142">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="f7999-143">Weitere Informationen zu [Besprechungen und Anrufen in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)</span><span class="sxs-lookup"><span data-stu-id="f7999-143">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

