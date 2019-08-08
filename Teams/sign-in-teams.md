---
title: Anmelden bei Microsoft Teams mit moderner Authentifizierung
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: So können Sie sich mithilfe der modernen Authentifizierung bei Microsoft Teams anmelden.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af7ecffc6dbed108fdc3ec68802aac39aa4f54c4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242511"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="adc8b-103">Anmelden bei Microsoft Teams mit moderner Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adc8b-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="adc8b-104">Microsoft Teams verwendet die moderne Authentifizierung, um die Anmelde Erfahrung einfach und sicher zu halten.</span><span class="sxs-lookup"><span data-stu-id="adc8b-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="adc8b-105">Wenn Sie sehen möchten, wie sich Benutzer bei Teams anmelden, lesen Sie [Anmelden bei Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span><span class="sxs-lookup"><span data-stu-id="adc8b-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="adc8b-106">Funktionsweise der modernen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adc8b-106">How modern authentication works</span></span>

<span data-ttu-id="adc8b-107">Die moderne Authentifizierung ist ein Prozess, bei dem Teams wissen, dass Benutzer ihre Anmeldeinformationen (wie Ihre geschäftliche e-Mail-Adresse und Ihr Kennwort) bereits an einem anderen Ort eingegeben haben, und Sie sollten nicht verpflichtet werden, Sie erneut einzugeben, um die APP zu starten.</span><span class="sxs-lookup"><span data-stu-id="adc8b-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="adc8b-108">Die Erfahrung hängt von einigen Faktoren ab, wie etwa, wenn Benutzer in Windows oder auf einem Mac arbeiten.</span><span class="sxs-lookup"><span data-stu-id="adc8b-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="adc8b-109">Es hängt auch davon ab, ob Ihre Organisation die einstufige Authentifizierung oder die mehrstufige Authentifizierung aktiviert hat (die mehrstufige Authentifizierung umfasst in der Regel die Überprüfung von Anmeldeinformationen über ein Telefon, die Bereitstellungeines eindeutigen Codes, das Eingeben einer PIN oder präsentieren eines Fingerabdrucks)</span><span class="sxs-lookup"><span data-stu-id="adc8b-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="adc8b-110">Hier finden Sie einen Überblick über die einzelnen modernen Authentifizierungsszenarien.</span><span class="sxs-lookup"><span data-stu-id="adc8b-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="adc8b-111">Windows-Benutzer:</span><span class="sxs-lookup"><span data-stu-id="adc8b-111">Windows users</span></span> 

- <span data-ttu-id="adc8b-112">Wenn sich Benutzer bereits über Ihr Office 365 Enterprise-Konto bei anderen Office-Apps angemeldet haben, werden Sie beim Starten von Teams direkt zur APP weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="adc8b-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="adc8b-113">Sie müssen Ihre Anmeldeinformationen nicht eingeben.</span><span class="sxs-lookup"><span data-stu-id="adc8b-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="adc8b-114">Wenn Benutzer nicht bei Ihrem Office 365 Enterprise-Konto angemeldet sind, wenn Sie Ihre Teams starten, werden Sie aufgefordert, eine Einzelfaktor-oder mehrstufige Authentifizierung (SFA oder MFA) bereitzustellen, je nachdem, was Ihre Organisation entschieden hat, wie Sie die zu bestehender Prozess.</span><span class="sxs-lookup"><span data-stu-id="adc8b-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="adc8b-115">Wenn Benutzer bei einem mit der Domäne verbundenen Computer angemeldet sind, werden Sie möglicherweise aufgefordert, einen weiteren Authentifizierungsschritt zu durchlaufen, je nachdem, ob Ihre Organisation MFA erfordert oder wenn Ihr Computer bereits MFA zur Anmeldung benötigt.</span><span class="sxs-lookup"><span data-stu-id="adc8b-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="adc8b-116">Wenn Ihr Computer bereits MFA zur Anmeldung benötigt, wird die APP automatisch gestartet, wenn Sie Teams öffnen.</span><span class="sxs-lookup"><span data-stu-id="adc8b-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="adc8b-117">Mac-Benutzer</span><span class="sxs-lookup"><span data-stu-id="adc8b-117">Mac users</span></span> 

<span data-ttu-id="adc8b-118">Wenn Benutzer Teams starten, kann Ihr Computer Ihre Anmeldeinformationen nicht von Ihrem Office 365 Enterprise-Konto oder einer anderen Office-Anwendung abrufen.</span><span class="sxs-lookup"><span data-stu-id="adc8b-118">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="adc8b-119">Stattdessen sehen Sie eine Aufforderung, in der Sie nach SFA oder MFA gefragt werden (je nach den Einstellungen Ihrer Organisation).</span><span class="sxs-lookup"><span data-stu-id="adc8b-119">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="adc8b-120">Nachdem die Benutzer ihre Anmeldeinformationen eingegeben haben, müssen Sie Sie nicht erneut angeben.</span><span class="sxs-lookup"><span data-stu-id="adc8b-120">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="adc8b-121">Ab diesem Zeitpunkt werden die Teams automatisch gestartet, wenn Sie am gleichen Computer arbeiten.</span><span class="sxs-lookup"><span data-stu-id="adc8b-121">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="adc8b-122">Wechseln von Konten nach Abschluss der modernen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adc8b-122">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="adc8b-123">Wenn Benutzer an einem Computer mit einer Domäne arbeiten (Wenn beispielsweise der Mandant Kerberos aktiviert hat), können Benutzerkonten nicht gewechselt werden, nachdem Sie die moderne Authentifizierung abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="adc8b-123">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="adc8b-124">Wenn Benutzer nicht an einem Computer mit Domänenbeitritt arbeiten, können Sie die Konten wechseln.</span><span class="sxs-lookup"><span data-stu-id="adc8b-124">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="adc8b-125">Abmelden bei Microsoft Teams nach Abschluss der modernen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adc8b-125">Signing out of Microsoft Teams after completing modern authentication</span></span>
<span data-ttu-id="adc8b-126">Zum Abmelden von Teams können Benutzer oben in der APP auf Ihr Profilbild klicken und dann Abmelden auswählen. \*\*\*\* Sie können auch mit der rechten Maustaste auf das App-Symbol in der Taskleiste \*\*\*\* klicken und dann Abmelden auswählen. Nachdem Sie sich bei Microsoft Teams abgemeldet haben, müssen Sie Ihre Anmeldeinformationen erneut eingeben, um die APP zu starten.</span><span class="sxs-lookup"><span data-stu-id="adc8b-126">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="adc8b-127">Problembehandlung bei der modernen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adc8b-127">Troubleshooting modern authentication</span></span>

<span data-ttu-id="adc8b-128">Die moderne Authentifizierung ist für alle Organisationen verfügbar, in denen Teams verwendet werden, wenn Benutzer den Vorgang also nicht abschließen können, liegt möglicherweise ein Fehler mit Ihrer Domäne oder dem Office 365 Enterprise-Konto Ihrer Organisation vor.</span><span class="sxs-lookup"><span data-stu-id="adc8b-128">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="adc8b-129">Weitere Informationen finden Sie unter [Warum habe ich Probleme bei der Anmeldung bei Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span><span class="sxs-lookup"><span data-stu-id="adc8b-129">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

