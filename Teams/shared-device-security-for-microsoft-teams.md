---
title: Sicherheitshandbuch für Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Anleitung zur sicheren Verwendung von Microsoft Teams auf einem gemeinsam genutzten Computer am Arbeitsplatz.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3486df0ca12303a9351c756df4184f160e95ab34
ms.sourcegitcommit: 32023931b607542cffadef74383e3ecd47db4ab6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868694"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a><span data-ttu-id="12316-103">Sicheres Verwenden von Microsoft Teams auf gemeinsam genutzten Computern</span><span class="sxs-lookup"><span data-stu-id="12316-103">Use Microsoft Teams securely on shared computers</span></span>

<span data-ttu-id="12316-104">Wenn möglich, wird Unternehmen *empfohlen*, einen Zero Trust-Ansatz für Clientgeräte einzusetzen, indem sie Geräteverwaltungsfunktionen, die Durchsetzung von Gerätezustandsprüfungen und Richtlinien, Verschlüsselung auf Geräteebene und andere Sicherheitsfunktionen nutzen.</span><span class="sxs-lookup"><span data-stu-id="12316-104">When possible, it is *recommended* Enterprises make use of a Zero Trust approach to client devices making use of device management capabilities, device health checks and policy enforcement, device-level encryption, and other security features.</span></span>

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Zero Trust-Abbildung zur Verdeutlichung der Zero Trust-Grundsätze – explizite Überprüfungen, niedrigste Berechtigungen und Annehmen von Sicherheitsverletzungen – in blauen Kreisen.":::

<span data-ttu-id="12316-106">Administratoren können sehr sichere Bedingungen schaffen, indem sie auf Überprüfungen, niedrigste Berechtigungen und Annehmen von Sicherheitsverletzungen *bestehen*. Diese Standards führen zu Aktionen, die das Risiko sowohl für Benutzer als auch für Daten minimieren.</span><span class="sxs-lookup"><span data-stu-id="12316-106">Administrators can create very secure conditions by *insisting* on verification, least privilege, and by assuming compromise -- standards that lead to actions that minimize risk to both users and data.</span></span>

> [!TIP]
> <span data-ttu-id="12316-107">Zur tiefer gehenden Untersuchung der Zero Trust-Grundsätze schauen Sie sich [diese Videos](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537) an.</span><span class="sxs-lookup"><span data-stu-id="12316-107">For a deeper examination of Zero Trust principles, see [these videos](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span></span>

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a><span data-ttu-id="12316-108">Tipps für eine sichere Verwendung von Microsoft Teams auf einem gemeinsam genutzten Computer</span><span class="sxs-lookup"><span data-stu-id="12316-108">Tips for using Microsoft Teams securely from a shared computer</span></span>

<span data-ttu-id="12316-109">Auch wenn dies vielleicht nicht in allen Szenarien möglich oder praktikabel ist, sollten Sicherheitsadministratoren trotzdem unbedingt so gut wie möglich den Anleitungen für die Verwendung von Teams auf einem gemeinsam genutzten Computer oder einem nicht verwalteten Gerät folgen.</span><span class="sxs-lookup"><span data-stu-id="12316-109">Recognizing that this may not be possible or practical in all scenarios, it is still important for security administrators to follow guidance for using Teams from a shared computer or unmanaged device as best they can.</span></span>

<span data-ttu-id="12316-110">Es sollten Pläne entwickelt werden, die den Richtlinien möglichst genau entsprechen.</span><span class="sxs-lookup"><span data-stu-id="12316-110">Plans should be developed to adhere to guidelines as promptly as is possible.</span></span>

1. <span data-ttu-id="12316-111">Nutzen Sie die Sicherheitsfunktionen der Betriebssystemplattform.</span><span class="sxs-lookup"><span data-stu-id="12316-111">Make use of Operating System platform security capabilities.</span></span>
    1. <span data-ttu-id="12316-112">Stellen Sie sicher, dass das Betriebssystem so konfiguriert ist, dass Updates vom Betriebssystemanbieter automatisch installiert werden (für Microsoft-Systeme wird dies über [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq) erreicht).</span><span class="sxs-lookup"><span data-stu-id="12316-112">Ensure that the operating system is configured to install automatic updates from the Operating System provider (for Microsoft systems, this can be accomplished via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span></span> 
    2. <span data-ttu-id="12316-113">Stellen Sie sicher, dass alle Geräteverschlüsselungsfunktionen wie z. B. [**bitlocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) aktiviert sind und der für den Zugriff auf das Gerät verwendete Schlüssel gesichert ist.</span><span class="sxs-lookup"><span data-stu-id="12316-113">Ensure that any device encryption capabilities such as [**bitlocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) are enabled, and the key used to access the device is secured.</span></span>  <span data-ttu-id="12316-114">Beachten Sie, dass die meisten modernen [**Windows 10-Geräte Bitlocker unterstützen**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).</span><span class="sxs-lookup"><span data-stu-id="12316-114">Note that most modern [**Windows 10 devices support bitlocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).</span></span> 
    1. <span data-ttu-id="12316-115">Verwenden Sie Antivirusfunktionen wie diejenigen, die von [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) auf Ihren Geräten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="12316-115">Use anti-virus capabilities such as those offered by [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) on your devices.</span></span>
    1. <span data-ttu-id="12316-116">Die Verwendung von [getrennten Benutzerkonten](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) für jeden Benutzer des Systems wird dringend empfohlen.</span><span class="sxs-lookup"><span data-stu-id="12316-116">Use of [separate user accounts](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) for each user of the system is highly recommended.</span></span>
    1. <span data-ttu-id="12316-117">Vergeben oder verwenden Sie *keine* Administratorrechte für nicht administrative Funktionen (wie z. B. das Surfen im Web, das Ausführen von Teams usw.).</span><span class="sxs-lookup"><span data-stu-id="12316-117">*Do not* grant, or use, administrator privileges for non-administrative functions (such as browsing the web, running Teams, et cetera).</span></span>

2. <span data-ttu-id="12316-118">Nutzen Sie Browsersicherheitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="12316-118">Leverage browser security capabilities.</span></span>
    1. <span data-ttu-id="12316-119">Verwenden Sie private Browsersitzungen, um Daten und Verlauf, die auf der Festplatte verbleiben, zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="12316-119">Use private browsing sessions to minimize data and history that persists to disk.</span></span> <span data-ttu-id="12316-120">Verwenden Sie z. B. [InPrivate-Browsen in Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Inkognitobrowsing in Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en) bzw. die entsprechende Funktionen Ihres Browsers für private Browsersitzungen.</span><span class="sxs-lookup"><span data-stu-id="12316-120">For example, use [inPrivate browsing in Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Incognito browsing in Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), or the capabilities your specific browser for browsing privately.</span></span> 
    1. <span data-ttu-id="12316-121">Es wird empfohlen, das Systemverhalten so zu ändern, dass *standardmäßig* private Browsersitzungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="12316-121">Changing the system behavior to engage private browsing *by default* is recommended.</span></span> 

3. <span data-ttu-id="12316-122">Navigieren Sie zur [Web-App für Teams](https://teams.microsoft.com) (manchmal auch als *Webclient* bezeichnet), und verwenden Sie diese und nicht den herunterladbaren Teams-Client.</span><span class="sxs-lookup"><span data-stu-id="12316-122">Browse to and use the [Teams web app](https://teams.microsoft.com) (sometimes called the *web* client) not the downloadable Teams client.</span></span>

4. <span data-ttu-id="12316-123">Wenn Sie mit der Verwendung des gemeinsam genutzten Computers fertig sind, müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="12316-123">When you are done using the shared system, you must:</span></span> 
    1. <span data-ttu-id="12316-124">[Melden Sie sich bei Microsoft Teams ab](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span><span class="sxs-lookup"><span data-stu-id="12316-124">[Sign out of Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span></span>
    1. <span data-ttu-id="12316-125">Schließen Sie alle Registerkarten und Fenster des Browsers.</span><span class="sxs-lookup"><span data-stu-id="12316-125">Close all browser tabs and windows.</span></span>
    1. <span data-ttu-id="12316-126">Melden Sie sich vom Gerät ab.</span><span class="sxs-lookup"><span data-stu-id="12316-126">Sign out of the device.</span></span>

<span data-ttu-id="12316-127">Die oben aufgeführten Punkte sind keine umfassende Liste der bewährten Methoden oder Sicherheitskontrollen für alle Situationen, und in Ihrer Umgebung können möglicherweise zusätzliche Maßnahmen ergriffen werden (Sicherheitsadministratoren können sich beispielsweise für die Verwendung von sicheren Links und sicheren Anhängen für Teams entscheiden, wenn Sie [Office 365 ATP Plan 1 oder 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) verwenden).</span><span class="sxs-lookup"><span data-stu-id="12316-127">The items above are not a comprehensive list of best practices or security controls covering all cases, and there may be extra actions that can be taken in your environment, (for instance, security administrators may choose to use Safe Links and Safe Attachments for Teams if you have [Office 365 ATP Plan 1 or 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span></span> <span data-ttu-id="12316-128">Diese Schritte sind jedoch ein Ausgangspunkt für die Erstellung von Anleitungen für die Verwendung von Teams auf gemeinsam genutzten Geräten.</span><span class="sxs-lookup"><span data-stu-id="12316-128">However, these steps are a starting point for building guidance for using Teams from shared devices.</span></span>

## <a name="more-information"></a><span data-ttu-id="12316-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12316-129">More Information</span></span>

[<span data-ttu-id="12316-130">Bitlocker in Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="12316-130">Bitlocker in Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[<span data-ttu-id="12316-131">BitLocker für Windows 10 in Intune</span><span class="sxs-lookup"><span data-stu-id="12316-131">Bitlocker for Windows 10 in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/encrypt-devices)

[<span data-ttu-id="12316-132">Sicherheitsmaßnahmen für den Endpunkt in Intune</span><span class="sxs-lookup"><span data-stu-id="12316-132">Endpoint security in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-security)

<span data-ttu-id="12316-133">[Aktivieren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) von Microsoft Defender Antivirus in Windows-Sicherheit und [Ausführen von Scans](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span><span class="sxs-lookup"><span data-stu-id="12316-133">[Enable](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus in your Windows Security and [run scans](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span></span>

[<span data-ttu-id="12316-134">Artikel zum Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="12316-134">Microsoft Defender security center article</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[<span data-ttu-id="12316-135">Teams-Webclient/Teams-Web-App</span><span class="sxs-lookup"><span data-stu-id="12316-135">Teams web client/teams web app</span></span>](https://docs.microsoft.com/microsoftteams/get-clients#web-client)

[<span data-ttu-id="12316-136">Sicherheit und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12316-136">Security and Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-security-guide)
