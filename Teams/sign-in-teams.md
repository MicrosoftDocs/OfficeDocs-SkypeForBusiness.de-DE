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
description: So melden Sie sich bei Microsoft Teams mit moderner Authentifizierung an.
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79f04161c070ff4818fdb2dfc212e5c3fc98b2b0
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845136"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="0f037-103">Anmelden bei Microsoft Teams mit moderner Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0f037-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="0f037-104">Microsoft Teams verwendet moderne Authentifizierung, um die Anmeldung einfach und sicher zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="0f037-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="0f037-105">Um zu erfahren, wie sich Benutzer bei Teams anmelden, lesen Sie bitte [Anmelden in Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span><span class="sxs-lookup"><span data-stu-id="0f037-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="0f037-106">So funktioniert moderne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0f037-106">How modern authentication works</span></span>

<span data-ttu-id="0f037-107">Bei der modernen Authentifizierung handelt es sich um einen Prozess, der Teams mitteilt, dass Benutzer ihre Anmeldeinformationen (wie Ihre geschäftliche E-Mail-Adresse und das Kennwort) bereits anderswo eingegeben haben, und dass Sie diese nicht erneut eingeben müssen, um die App zu starten.</span><span class="sxs-lookup"><span data-stu-id="0f037-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="0f037-108">Das Erlebnis hängt von einigen Faktoren ab, beispielsweise wenn Benutzer mit Windows oder auf einem Mac arbeiten.</span><span class="sxs-lookup"><span data-stu-id="0f037-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="0f037-109">Es hängt auch davon ab, ob Ihre Organisation die einstufige Authentifizierung oder die mehrstufige Authentifizierung aktiviert hat (die mehrstufige Authentifizierung umfasst in der Regel die Überprüfung von Anmeldeinformationen über ein Telefon, die Eingabe eines eindeutigen Codes, die Eingabe eines PIN-Codes oder die Verwendung eines Fingerabdrucks).</span><span class="sxs-lookup"><span data-stu-id="0f037-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="0f037-110">Hier ist eine Übersicht über jedes Szenario moderner Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="0f037-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="0f037-111">Windows-Benutzer</span><span class="sxs-lookup"><span data-stu-id="0f037-111">Windows users</span></span> 

- <span data-ttu-id="0f037-112">Wenn Benutzer sich bereits über ihr Office 365 Enterprise-Konto bei anderen Office-Anwendungen angemeldet haben, werden sie beim Start von Teams direkt zur App weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0f037-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="0f037-113">Sie müssen ihre Anmeldeinformationen nicht eingeben.</span><span class="sxs-lookup"><span data-stu-id="0f037-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="0f037-114">Wenn Benutzer nicht woanders in ihrem Office 365 Enterprise-Konto angemeldet sind, werden sie beim Start von Teams gebeten, entweder eine ein- oder mehrstufige Authentifizierung (SFA oder MFA) anzugeben, je nachdem was Ihre Organisation für den Prozess festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="0f037-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="0f037-115">Wenn Benutzer bei einem domänengebundenen Computer angemeldet sind, werden sie beim Start von Teams möglicherweise aufgefordert, einen weiteren Authentifizierungsschritt durchzuführen, je nachdem, ob sich Ihre Organisation für MFA entschieden hat oder ob ihr Computer bereits MFA zum Anmelden erfordert.</span><span class="sxs-lookup"><span data-stu-id="0f037-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="0f037-116">Wenn ihr Computer bereits MFA zur Anmeldung erfordert, startet die App automatisch, wenn  sie Teams öffnen.</span><span class="sxs-lookup"><span data-stu-id="0f037-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="0f037-117">Wenn Benutzer bei einem von der Domäne verbundenen Computer angemeldet sind und nicht möchten, dass der Benutzername auf dem Anmeldebildschirm der Teams vorinstalliert ist, können Administratoren die folgende Windows-Registrierung so einrichten, dass die vorauffüllung des Benutzernamens (User Name, UPN) deaktiviert wird:</span><span class="sxs-lookup"><span data-stu-id="0f037-117">If users are signed in to a domain-joined computer and you don't want their user name pre-populated on the Teams sign-in screen, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="0f037-118">Computer \ HKEY_CURRENT_USER \software\microsoft\office\teams</span><span class="sxs-lookup"><span data-stu-id="0f037-118">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="0f037-119">SkipUpnPrefill (REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="0f037-119">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="0f037-120">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="0f037-120">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f037-121">Das Überspringen von Benutzernamen-Pre-Fill für Benutzernamen, die in ". local" oder ". Corp" enden, ist standardmäßig aktiviert, daher müssen Sie keinen Registrierungsschlüssel festlegen, um diese zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0f037-121">Skipping user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span> 


### <a name="mac-users"></a><span data-ttu-id="0f037-122">Mac-Benutzer</span><span class="sxs-lookup"><span data-stu-id="0f037-122">Mac users</span></span> 

<span data-ttu-id="0f037-123">Wenn Benutzer Teams starten, kann ihr Computer ihre Anmeldeinformationen nicht von ihrem Office 365 Enterprise-Konto oder einer ihrer anderen Office-Anwendungen abrufen.</span><span class="sxs-lookup"><span data-stu-id="0f037-123">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="0f037-124">Stattdessen wird eine Aufforderung zur Eingabe von SFA oder MFA angezeigt (abhängig von den Einstellungen Ihrer Organisation).</span><span class="sxs-lookup"><span data-stu-id="0f037-124">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="0f037-125">Sobald die Benutzer ihre Anmeldeinformationen eingegeben haben, werden sie nicht mehr aufgefordert, sie erneut anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0f037-125">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="0f037-126">Von diesem Zeitpunkt an startet Teams automatisch, wenn sie am gleichen Computer arbeiten.</span><span class="sxs-lookup"><span data-stu-id="0f037-126">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="0f037-127">Kontowechsel nach Abschluss der modernen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0f037-127">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="0f037-128">Wenn Benutzer an einem domänengebundenen Computer arbeiten (z.B. wenn ihr Mandant Kerberos aktiviert hat), können sie nach Abschluss der modernen Authentifizierung nicht mehr zwischen Benutzerkonten wechseln.</span><span class="sxs-lookup"><span data-stu-id="0f037-128">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="0f037-129">Wenn Benutzer nicht an einem domänengebundenen Computer arbeiten, können sie zwischen Konten wechseln.</span><span class="sxs-lookup"><span data-stu-id="0f037-129">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="0f037-130">Abmeldung von Microsoft Teams nach Abschluss der modernen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0f037-130">Signing out of Microsoft Teams after completing modern authentication</span></span>
<span data-ttu-id="0f037-131">Um sich von Teams abzumelden, können Benutzer auf ihr Profilbild oben in der App klicken und dann **Abmelden** wählen. Sie können auch mit der rechten Maustaste auf das App-Symbol in der Taskleiste klicken und dann **Abmelden** wählen. Sobald sie sich von Teams abgemeldet haben, müssen sie ihre Anmeldeinformationen erneut eingeben, um die App zu starten.</span><span class="sxs-lookup"><span data-stu-id="0f037-131">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="0f037-132">URLs und IP-Adressbereiche</span><span class="sxs-lookup"><span data-stu-id="0f037-132">URLs and IP address ranges</span></span>
<span data-ttu-id="0f037-133">Für Teams ist eine Internet Verbindung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0f037-133">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="0f037-134">Wenn Sie Endpunkte verstehen möchten, die für Kunden mit Teams in Office 365-Plänen, Behörden und anderen Clouds erreichbar sein sollten, lesen Sie die [hier verfügbaren Anleitungen](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="0f037-134">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, please read the [guidance available here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="0f037-135">Darüber hinaus müssen Sie auch den Zugriff auf https://ssl.gstatic.comaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0f037-135">In addition to this, you'd need to also allow access to https://ssl.gstatic.com.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="0f037-136">Problembehandlung bei der modernen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0f037-136">Troubleshooting modern authentication</span></span>

<span data-ttu-id="0f037-137">Moderne Authentifizierung ist für alle Organisationen verfügbar, die Teams verwenden. Wenn Benutzer also nicht in der Lage sind, den Prozess abzuschließen, liegt möglicherweise ein Problem mit Ihrer Domäne oder dem Office 365 Enterprise-Konto Ihrer Organisation vor.</span><span class="sxs-lookup"><span data-stu-id="0f037-137">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="0f037-138">Weitere Informationen finden Sie unter [Warum habe ich Probleme bei der Anmeldung bei Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="0f037-138">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>

