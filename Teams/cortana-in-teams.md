---
title: Cortana-VoIP-Unterstützung in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Informationen zur Verwendung der Cortana-Sprachunterstützung für Teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785389"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="896df-103">Cortana-Sprachunterstützung in Teams</span><span class="sxs-lookup"><span data-stu-id="896df-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="896df-104">Cortana-VoIP-Unterstützung wird in den mobilen Microsoft Teams IOS-und Android-Apps sowie auf Microsoft Teams-Displays nur für Benutzer in den Vereinigten Staaten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="896df-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="896df-105">Sie ist derzeit nicht für gcc-, gcc-höchst-, DoD-, edu-Mandanten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="896df-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="896df-106">Die Erweiterung auf weitere Sprachen und Regionen erfolgt in zukünftigen Versionen.</span><span class="sxs-lookup"><span data-stu-id="896df-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="896df-107">Cortana-VoIP-Unterstützung in der mobilen Teams-APP und auf Anzeigegeräten von Microsoft Teams ermöglicht es Microsoft 365 Enterprise-Benutzern, Kommunikations-, Zusammenarbeits-und Besprechungs bezogene Aufgaben mithilfe der gesprochenen natürlichen Sprache zu rationalisieren.</span><span class="sxs-lookup"><span data-stu-id="896df-107">Cortana voice assistance in the Teams mobile app and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="896df-108">Benutzer können mit Cortana sprechen, indem Sie die Schaltfläche Mikrofon in der oberen rechten Ecke der mobilen App für Teams auswählen oder indem Sie in der Microsoft Teams-Anzeige &#8220;Cortana&#8221; sagen.</span><span class="sxs-lookup"><span data-stu-id="896df-108">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams display.</span></span> <span data-ttu-id="896df-109">Damit Sie schnell und einfach mit Ihrem Team in Kontakt treten können, können Benutzer Abfragen wie &#8220;Megan&#8221; anrufen oder &#8220;eine Nachricht an meine nächste Besprechungs&#8221; senden.</span><span class="sxs-lookup"><span data-stu-id="896df-109">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="896df-110">Benutzer können auch an Besprechungen teilnehmen, indem Sie &#8220;teilnehmen an meiner nächsten Besprechung&#8221; und die Sprachunterstützung verwenden, um Dateien freizugeben, Ihren Kalender zu überprüfen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="896df-110">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="896df-111">Diese sprach Unterstützungsfunktionen werden mithilfe von [Cortana Enterprise-Services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) bereitgestellt, die vollständig den Datenschutz-, Sicherheits-und Compliance-Zusagen von Office 365 entsprechen, wie Sie in den [Online Services-Bedingungen (Ost)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)widergespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="896df-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="896df-112">Das Bild zeigt das Senden eines Chats mithilfe von Cortana auf einem mobilen Gerät.</span><span class="sxs-lookup"><span data-stu-id="896df-112">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Abbildung zeigt eine Abfolge von mobilen Bildschirmen mit einer Cortana-Chat-Sitzung](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="896df-114">Administratorsteuerung und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="896df-114">Admin control and limitations</span></span>

<span data-ttu-id="896df-115">Cortana-VoIP-Unterstützung in Teams wird mithilfe von Diensten bereitgestellt, die vollständig den Datenschutz-, Sicherheits-und Compliance-Zusagen von Office 365 auf Unternehmensebene entsprechen, wie Sie in den Online Services-Bedingungen (Ost) widergespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="896df-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="896df-116">Das Feature wird standardmäßig für Mandanten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="896df-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="896df-117">Mandantenadministratoren können steuern, wer in Ihrem Mandanten Cortana-VoIP-Unterstützung in Teams mithilfe einer Richtlinie (TeamsCortanaPolicy) verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="896df-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="896df-118">Diese Richtlinie kann entweder auf Ebene des Benutzerkontos oder auf Mandantenebene eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="896df-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="896df-119">Administratoren können das CortanaVoiceInvocationMode-Feld in diesem Richtliniensteuerelement verwenden, um zu ermitteln, ob Cortana deaktiviert ist, nur mit dem Aufruf von Schaltflächen aufrufen oder mit Wake Word-Aufruf aktiviert ist (gilt für Geräte, die es unterstützen, wie die Microsoft Teams-Anzeige).</span><span class="sxs-lookup"><span data-stu-id="896df-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="896df-120">Administratoren können die folgenden PowerShell-Cmdlets zum Verwalten dieser Richtlinie verwenden (die Richtlinie steht derzeit im Microsoft Teams Admin Center nicht zur Verfügung).</span><span class="sxs-lookup"><span data-stu-id="896df-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="896df-121">Neu – CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="896df-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="896df-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="896df-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="896df-123">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="896df-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="896df-124">Satz-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="896df-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="896df-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="896df-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="896df-126">Mit dem folgenden Befehl wird beispielsweise eine neue Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221;, in der Cortana-VoIP-Unterstützung in Microsoft Teams deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="896df-126">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="896df-127">In diesem Beispiel wird das Aktualisieren einer vorhandenen Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221; und das Aktivieren von Cortana-VoIP-Unterstützung in Microsoft Teams mit nur Tasten Aufruf veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="896df-127">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="896df-128">Benutzer können Cortana aufrufen, indem Sie die Cortana MIC-Schaltfläche in Teams auswählen.</span><span class="sxs-lookup"><span data-stu-id="896df-128">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="896df-129">Wake Word (&#8220;Hey Cortana&#8221; oder &#8220;Cortana&#8221;)-Aufruf wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="896df-129">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="896df-130">In diesem Beispiel wird die Aktualisierung der Richtlinie und die Aktivierung der Cortana-VoIP-Unterstützung sowohl beim Drücken als auch beim Aktivieren des Word-Aufrufs veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="896df-130">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="896df-131">Zum Zeitpunkt der ersten Veröffentlichung für Microsoft 365 Enterprise-Benutzer in den USA in englischer Sprache unterstützt die Mobile Teams-App keine Aktivierung des Aktivierungs Worts, wird aber in Zukunft unterstützt.</span><span class="sxs-lookup"><span data-stu-id="896df-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span> <span data-ttu-id="896df-132">Die Wake Word-Aktivierung funktioniert auf den Anzeigegeräten von Microsoft Teams bei der ersten Version.</span><span class="sxs-lookup"><span data-stu-id="896df-132">Wake word activation will work on Microsoft Teams display devices at initial release.</span></span>

## <a name="user-control"></a><span data-ttu-id="896df-133">Benutzersteuerelement</span><span class="sxs-lookup"><span data-stu-id="896df-133">User control</span></span>

<span data-ttu-id="896df-134">Einzelne Benutzer können die Cortana-Sprachunterstützung in der mobilen Teams-App ausprobieren, indem Sie die Schaltfläche Mikrofon auswählen.</span><span class="sxs-lookup"><span data-stu-id="896df-134">Individual users can try out Cortana voice assistance in the Teams mobile app by selecting the microphone button.</span></span> <span data-ttu-id="896df-135">Sie können Cortana-Sprachunterstützung auf Microsoft Teams-Anzeigegeräten ausprobieren, indem Sie einfach &#8220;Cortana. &#8221; Sie können auch steuern, ob Cortana in Teams für Ihr Gerät aktiviert ist, indem Sie eine Einstellung in der mobilen Teams-APP oder in der Microsoft Teams-Anzeige verwenden.</span><span class="sxs-lookup"><span data-stu-id="896df-135">They can try out Cortana voice assistance on Microsoft Teams display devices by simply saying &#8220;Cortana.&#8221; They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app or on the Microsoft Teams display.</span></span>

1. <span data-ttu-id="896df-136">Öffnen Sie die Mobile Teams-APP, oder wechseln Sie zum Bildschirm Ambient (Home) der Microsoft Teams-Anzeige.</span><span class="sxs-lookup"><span data-stu-id="896df-136">Open the Teams mobile app, or go to the ambient (home) screen of the Microsoft Teams display.</span></span>

2. <span data-ttu-id="896df-137">Wechseln Sie in der mobilen Teams-APP zu **Einstellungen** .</span><span class="sxs-lookup"><span data-stu-id="896df-137">In the Teams mobile app, go to **Settings** .</span></span> <span data-ttu-id="896df-138">Wählen Sie in der Microsoft Teams-Anzeige den Avatar des Benutzers aus, und wählen Sie dann Einstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="896df-138">On the Microsoft Teams display, select the user avatar, and then select Settings.</span></span> <span data-ttu-id="896df-139">Wenn Cortana aktiviert ist, sagen Sie &#8220;Cortana, wechseln Sie zu Einstellungen. &#8221;</span><span class="sxs-lookup"><span data-stu-id="896df-139">If Cortana is enabled, say, &#8220;Cortana, go to Settings.&#8221;</span></span>

3. <span data-ttu-id="896df-140">Wählen Sie **Cortana** aus.</span><span class="sxs-lookup"><span data-stu-id="896df-140">Select **Cortana** .</span></span>

4. <span data-ttu-id="896df-141">Verschieben Sie den Umschalter auf **ein** oder **aus** , je nachdem, ob Sie Cortana-VoIP-Unterstützung auf dem Gerät wünschen.</span><span class="sxs-lookup"><span data-stu-id="896df-141">Move the toggle to **On** or **Off** , depending on whether you want Cortana voice assistance on the device.</span></span>
