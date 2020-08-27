---
title: Cortana-Sprachassistent in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Informationen zur Verwendung von Cortana Voice Assistant in Teams
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
ms.openlocfilehash: f820bf6c44eae2cfbdb13a683d017be2f93d6756
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255549"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="e77ea-103">Cortana-Sprachunterstützung in Teams</span><span class="sxs-lookup"><span data-stu-id="e77ea-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="e77ea-104">Cortana-VoIP-Unterstützung wird nur für Benutzer in den USA in den mobilen Microsoft Teams IOS-und Android-Apps unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e77ea-104">Cortana voice assistance is supported on Microsoft Teams iOS and Android mobile apps only for users in the United States.</span></span> <span data-ttu-id="e77ea-105">Sie ist derzeit nicht für gcc-, gcc-höchst-, DoD-, edu-Mandanten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e77ea-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="e77ea-106">Die Erweiterung auf weitere Sprachen und Regionen erfolgt in zukünftigen Versionen.</span><span class="sxs-lookup"><span data-stu-id="e77ea-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="e77ea-107">Cortana-VoIP-Unterstützung in der mobilen Teams-App ermöglicht es Microsoft 365 Enterprise-Benutzern, Kommunikations-, Zusammenarbeits-und Besprechungs bezogene Aufgaben mithilfe der gesprochenen natürlichen Sprache zu rationalisieren.</span><span class="sxs-lookup"><span data-stu-id="e77ea-107">Cortana voice assistance in the Teams mobile app enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="e77ea-108">Benutzer können mit Cortana sprechen, indem Sie auf die Schaltfläche Mikrofon klicken, die sich in der oberen rechten Ecke der Mobile-App für Teams befindet.</span><span class="sxs-lookup"><span data-stu-id="e77ea-108">Users can speak to Cortana by clicking on the microphone button located in the upper right of the Teams mobile app.</span></span> <span data-ttu-id="e77ea-109">Wenn Sie unterwegs schnell eine Verbindung mit Ihrem Team herstellen möchten, können Benutzer Abfragen wie &#8220;Megan&#8221; anrufen oder &#8220;eine Nachricht an meine nächste Besprechungs&#8221; senden.</span><span class="sxs-lookup"><span data-stu-id="e77ea-109">To quickly connect with their team while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="e77ea-110">Benutzer können auch an Besprechungen teilnehmen, indem Sie &#8220;teilnehmen an meiner nächsten Besprechung&#8221; und die Sprachunterstützung verwenden, um Dateien freizugeben, Ihren Kalender zu überprüfen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="e77ea-110">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="e77ea-111">Diese sprach Unterstützungsfunktionen werden mithilfe von [Cortana Enterprise-Services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) bereitgestellt, die vollständig den Datenschutz-, Sicherheits-und Compliance-Zusagen von Office 365 entsprechen, wie Sie in den [Online Services-Bedingungen (Ost)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)widergespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="e77ea-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365’s privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="e77ea-112">Das Bild zeigt das Senden eines Chats in Cortana auf einem mobilen Gerät.</span><span class="sxs-lookup"><span data-stu-id="e77ea-112">The image shows sending a chat in Cortana on a mobile device.</span></span>

![Abbildung zeigt eine Abfolge von mobilen Bildschirmen mit einer Cortana-Chat-Sitzung](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="e77ea-114">Administratorsteuerung und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e77ea-114">Admin control and Limitations</span></span>

<span data-ttu-id="e77ea-115">Cortana-VoIP-Unterstützung in Teams wird mithilfe von Diensten bereitgestellt, die vollständig den Datenschutz-, Sicherheits-und Compliance-Zusagen von Office 365 auf Unternehmensebene entsprechen, wie Sie in den Online Services-Bedingungen (Ost) widergespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="e77ea-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="e77ea-116">Das Feature wird standardmäßig für Mandanten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e77ea-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="e77ea-117">Mandantenadministratoren können steuern, wer in Ihrem Mandanten Cortana-VoIP-Unterstützung in Teams mithilfe einer Richtlinie (TeamsCortanaPolicy) verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="e77ea-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="e77ea-118">Diese Richtlinie kann entweder auf Ebene des Benutzerkontos oder auf Mandantenebene eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e77ea-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="e77ea-119">Administratoren können das CortanaVoiceInvocationMode-Feld in diesem Richtliniensteuerelement verwenden, um zu ermitteln, ob Cortana deaktiviert ist, nur mit einem Push-Schaltflächen Aufruf oder mit Wake Word-Aufruf aktiviert ist (gilt für Geräte, die das Programm unterstützen).</span><span class="sxs-lookup"><span data-stu-id="e77ea-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it).</span></span>

<span data-ttu-id="e77ea-120">Administratoren können die folgenden PowerShell-Cmdlets zum Verwalten dieser Richtlinie verwenden (die Richtlinie steht derzeit im Microsoft Teams Admin Center nicht zur Verfügung).</span><span class="sxs-lookup"><span data-stu-id="e77ea-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="e77ea-121">Neu – CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="e77ea-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="e77ea-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="e77ea-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="e77ea-123">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="e77ea-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="e77ea-124">Satz-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="e77ea-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="e77ea-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="e77ea-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="e77ea-126">Mit dem folgenden Befehl wird beispielsweise eine neue Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221;, in der Cortana-Sprachassistent in Microsoft Teams deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e77ea-126">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistant in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="e77ea-127">In diesem Beispiel wird das Aktualisieren einer vorhandenen Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221; und das Aktivieren des Cortana-Sprachassistenten in Microsoft Teams mit nur einem Tasten Aufruf veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e77ea-127">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistant in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="e77ea-128">Benutzer können Cortana aufrufen, indem Sie in Teams auf die Cortana MIC-Schaltfläche tippen.</span><span class="sxs-lookup"><span data-stu-id="e77ea-128">Users will be able to invoke Cortana by tapping on the Cortana mic button in Teams.</span></span> <span data-ttu-id="e77ea-129">Wake Word (&#8220;Hey Cortana&#8221;) Aufruf wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e77ea-129">Wake word (&#8220;Hey Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="e77ea-130">Dieses Beispiel zeigt, wie Sie die Richtlinie aktualisieren und den Cortana-Sprachassistenten sowohl mit der Schaltfläche als auch mit dem Wake-Word-Aufruf aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e77ea-130">This example shows updating the policy and enabling Cortana voice assistant with both push button and wake-word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="e77ea-131">Zum Zeitpunkt der ersten Veröffentlichung für Microsoft 365 Enterprise-Benutzer in den USA in englischer Sprache unterstützt die Mobile Teams-App keine Aktivierung des Aktivierungs Worts, wird aber in Zukunft unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e77ea-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span>

## <a name="user-control"></a><span data-ttu-id="e77ea-132">Benutzersteuerelement</span><span class="sxs-lookup"><span data-stu-id="e77ea-132">User control</span></span>

<span data-ttu-id="e77ea-133">Einzelne Benutzer können die Cortana-Sprachunterstützung in der mobilen Mobile-App testen, indem Sie auf die Schaltfläche "Mikrofon" klicken.</span><span class="sxs-lookup"><span data-stu-id="e77ea-133">Individual users can try out Cortana voice assistance in the Teams mobile app by clicking the microphone button.</span></span> <span data-ttu-id="e77ea-134">Sie können auch steuern, ob Cortana in Teams für Ihr Gerät mithilfe einer Einstellung in der mobilen Teams-App aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e77ea-134">They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app.</span></span>

1. <span data-ttu-id="e77ea-135">Öffnen Sie die Mobile Teams-app.</span><span class="sxs-lookup"><span data-stu-id="e77ea-135">Open the Teams mobile app.</span></span>

2. <span data-ttu-id="e77ea-136">Wechseln Sie zu **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e77ea-136">Go to **Settings**.</span></span>

3. <span data-ttu-id="e77ea-137">Wählen Sie **Cortana**aus.</span><span class="sxs-lookup"><span data-stu-id="e77ea-137">Select **Cortana**.</span></span>

4. <span data-ttu-id="e77ea-138">Verschieben Sie den Umschalter auf **ein** oder **aus**, je nachdem, ob Sie Cortana-VoIP-Unterstützung auf dem Gerät wünschen.</span><span class="sxs-lookup"><span data-stu-id="e77ea-138">Move the toggle to **On** or **Off**, depending on whether you want Cortana voice assistance on the device.</span></span>
