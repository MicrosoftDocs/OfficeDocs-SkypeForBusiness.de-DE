---
title: Melden Sie sich bei modernen Authentifizierung mit Microsoft-Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Informationen zur Anmeldung bei Microsoft-Teams, mithilfe der modernen Authentifizierung.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01ca138aebae8d0db731118baf3e340aa3332120
ms.sourcegitcommit: bd32d44d27990e373ce6afa38897159473601113
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "26544372"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="fa766-103">Melden Sie sich bei modernen Authentifizierung mit Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="fa766-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="fa766-104">Microsoft-Teams, wird die modernen Authentifizierung, um die Anmeldung einfach und sicher zu halten.</span><span class="sxs-lookup"><span data-stu-id="fa766-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="fa766-105">Um herauszufinden, wie Benutzer Teams anmelden, lesen Sie [Teams anmelden](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span><span class="sxs-lookup"><span data-stu-id="fa766-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="fa766-106">Wie modernen Funktionsweise der Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fa766-106">How modern authentication works</span></span>

<span data-ttu-id="fa766-107">Moderne Authentifizierung ist ein Prozess, der kann Teams wissen, dass Benutzer bereits ihre Anmeldeinformationen (wie ihre geschäftliche e-Mail und Kennwort) an anderer Stelle eingegeben haben und sollte nicht benötigt werden, geben sie erneut aus, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="fa766-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="fa766-108">Die Erfahrung variiert je nach einige Faktoren, wie wenn Benutzer unter Windows oder auf einem Mac arbeiten</span><span class="sxs-lookup"><span data-stu-id="fa766-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="fa766-109">Es wird ebenfalls variieren abhängig davon, ob Ihre Organisation einfache oder mehrstufige Authentifizierung aktiviert hat (Multi-Factor Authentication sind meist Überprüfen der Anmeldeinformationen über ein Telefon, bietet einen eindeutigen Code, indem Sie eine PIN eingeben oder Präsentation eines Fingerabdrucks).</span><span class="sxs-lookup"><span data-stu-id="fa766-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="fa766-110">Nachfolgend finden Sie einen Überblick über jedes Szenario modernen Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fa766-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="fa766-111">Windows-Benutzer:</span><span class="sxs-lookup"><span data-stu-id="fa766-111">Windows users</span></span> 

- <span data-ttu-id="fa766-112">Wenn Benutzer bereits für andere Office-apps über ihr Office 365 Enterprise-Konto beim Starten von Teams angemeldet haben sind die für die app gerade verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa766-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="fa766-113">Es ist nicht erforderlich sind, um ihre Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="fa766-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="fa766-114">Wenn der Benutzer nicht an anderer Stelle, ihre Office 365 Enterprise-Konto angemeldet sind beim Starten von Teams, sie aufgefordert werden, bieten einfache oder mehrstufige Authentifizierung (SFA oder mehrstufiger Authentifizierung das), je nachdem was Ihrem Unternehmen beschlossen wurde, muss auch die Prozess zum unterstützen könnte.</span><span class="sxs-lookup"><span data-stu-id="fa766-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="fa766-115">Wenn Benutzer zu einer Domäne gehörenden Computer beim Starten von Teams angemeldet sind, sie werden möglicherweise aufgefordert, wechseln über eine weitere Authentifizierungsschritt, je nachdem, ob Ihre Organisation mehrstufiger Authentifizierung das erforderlich, um bestätigt oder ihren Computer bereits mehrstufiger Authentifizierung das zur Anmeldung bei erfordert.</span><span class="sxs-lookup"><span data-stu-id="fa766-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="fa766-116">Wenn ihre Computer bereits mehrstufiger Authentifizierung das benötigt So melden Sie sich beginnt beim von Teams, die app automatisch öffnen.</span><span class="sxs-lookup"><span data-stu-id="fa766-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="fa766-117">Mac-Benutzer</span><span class="sxs-lookup"><span data-stu-id="fa766-117">Mac users</span></span> 

<span data-ttu-id="fa766-118">Wenn Benutzer Teams starten, werden ihren Computer kann nicht ihre Anmeldeinformationen für ihre Office 365 Enterprise-Konto oder eine ihrer anderen Office-Anwendung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fa766-118">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="fa766-119">Stattdessen wird gefragt, deren für SFA oder mehrstufiger Authentifizierung das (abhängig von Ihrer Organisation Einstellungen) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa766-119">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="fa766-120">Nachdem Benutzer ihre Anmeldeinformationen eingeben, werden sie wird nicht benötigt diese erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fa766-120">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="fa766-121">Ab diesem Zeitpunkt auf Teams, die automatisch startet immer auf demselben Computer arbeiten.</span><span class="sxs-lookup"><span data-stu-id="fa766-121">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="fa766-122">Wechseln nach Abschluss der modernen Authentifizierung Konten</span><span class="sxs-lookup"><span data-stu-id="fa766-122">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="fa766-123">Wenn Benutzer auf einer Domäne gehörenden Computer (beispielsweise, wenn ihre Mandanten Kerberos aktiviert hat) arbeiten, können nicht sie Benutzerkonten wechseln, sobald sie modernen Authentifizierung abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="fa766-123">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="fa766-124">Wenn Benutzer nicht auf einer Domäne gehörenden Computer arbeiten, können sie Konten wechseln.</span><span class="sxs-lookup"><span data-stu-id="fa766-124">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="fa766-125">Abmelden von Microsoft-Teams, klicken Sie nach Abschluss der modernen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fa766-125">Signing out of Microsoft Teams after completing modern authentication</span></span>

<span data-ttu-id="fa766-126">Um sich abzumelden Teams können Benutzer klicken Sie auf das Profilbild am oberen Rand der app, und wählen Sie dann auf **Abmelden**. Sie können auch auf das app-Symbol in der Taskleiste und wählen Sie dann auf **Abmelden**. Sobald sie abmelden Teams haben, müssen sie ihre Anmeldeinformationen erneut aus, um die app starten eingeben.</span><span class="sxs-lookup"><span data-stu-id="fa766-126">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="fa766-127">Problembehandlung bei modernen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fa766-127">Troubleshooting modern authentication</span></span>

<span data-ttu-id="fa766-128">Moderne Authentifizierung ist für jede Organisation, dass Verwendungsmöglichkeiten Teams, also wenn Benutzer nicht für die Durchführung des Aktivierungsvorgangs können möglicherweise Problem in Ihrer Domäne oder Office 365 Enterprise-Konto Ihrer Organisation verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="fa766-128">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="fa766-129">Weitere Informationen finden Sie unter [Warum treten Probleme bei der Anmeldung an Microsoft-Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span><span class="sxs-lookup"><span data-stu-id="fa766-129">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

