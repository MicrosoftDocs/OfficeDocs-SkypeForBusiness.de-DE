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
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686441"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="4594a-103">Cortana-Sprachunterstützung in Teams</span><span class="sxs-lookup"><span data-stu-id="4594a-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="4594a-104">Cortana-VoIP-Unterstützung wird in Microsoft Teams IOS-und Android-mobilen apps, Microsoft Teams-Räumen unter Windows und auf Microsoft Teams-Displays nur für Benutzer in den Vereinigten Staaten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4594a-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, Microsoft Teams Rooms on Windows, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="4594a-105">Sie ist derzeit nicht für gcc-, gcc-höchst-, DoD-, edu-Mandanten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4594a-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="4594a-106">Die Erweiterung auf weitere Sprachen und Regionen erfolgt in zukünftigen Versionen.</span><span class="sxs-lookup"><span data-stu-id="4594a-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="4594a-107">Cortana Voice-Unterstützung in Microsoft Teams Rooms wird unter Vorschau veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="4594a-107">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="4594a-108">In der Preview-Version wird Cortana nur in den USA mit der Sprache en-US auf Geräten unterstützt, die Rallye-Mikrofone verbunden haben.</span><span class="sxs-lookup"><span data-stu-id="4594a-108">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="4594a-109">Cortana-VoIP-Unterstützung in der mobilen Teams-APP, in Microsoft Teams-Räumen unter Windows und auf Microsoft Teams-Anzeigegeräten können Microsoft 365 Enterprise-Benutzer die Kommunikation, Zusammenarbeit und Besprechungs bezogene Aufgaben mithilfe der gesprochenen natürlichen Sprache rationalisieren.</span><span class="sxs-lookup"><span data-stu-id="4594a-109">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="4594a-110">Benutzer können mit Cortana sprechen, indem Sie die Schaltfläche Mikrofon in der oberen rechten Ecke der mobilen App für Teams auswählen oder indem Sie &#8220;Cortana&#8221; im Microsoft Teams-Chatroom oder bei Verwendung einer Microsoft Teams-Anzeige sagen.</span><span class="sxs-lookup"><span data-stu-id="4594a-110">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="4594a-111">Damit Sie schnell und einfach mit Ihrem Team in Kontakt treten können, können Benutzer Abfragen wie &#8220;Megan&#8221; anrufen oder &#8220;eine Nachricht an meine nächste Besprechungs&#8221; senden.</span><span class="sxs-lookup"><span data-stu-id="4594a-111">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="4594a-112">Benutzer können auch an Besprechungen teilnehmen, indem Sie &#8220;teilnehmen an meiner nächsten Besprechung&#8221; und die Sprachunterstützung verwenden, um Dateien freizugeben, Ihren Kalender zu überprüfen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="4594a-112">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="4594a-113">Diese sprach Unterstützungsfunktionen werden mithilfe von [Cortana Enterprise-Services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) bereitgestellt, die vollständig den Datenschutz-, Sicherheits-und Compliance-Zusagen von Office 365 entsprechen, wie Sie in den [Online Services-Bedingungen (Ost)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)widergespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="4594a-113">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="4594a-114">Das Bild zeigt das Senden eines Chats mithilfe von Cortana auf einem mobilen Gerät.</span><span class="sxs-lookup"><span data-stu-id="4594a-114">The image shows sending a chat using Cortana on a mobile device.</span></span>

![eine Sequenz von mobilen Bildschirmen mit einer Cortana-Chat-Sitzung](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="4594a-116">Administratorsteuerung und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4594a-116">Admin control and limitations</span></span>

<span data-ttu-id="4594a-117">Cortana-VoIP-Unterstützung in Teams wird mithilfe von Diensten bereitgestellt, die vollständig den Datenschutz-, Sicherheits-und Compliance-Zusagen von Office 365 auf Unternehmensebene entsprechen, wie Sie in den Online Services-Bedingungen (Ost) widergespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="4594a-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="4594a-118">Das Feature wird standardmäßig für Mandanten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4594a-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="4594a-119">Mandantenadministratoren können steuern, wer in Ihrem Mandanten Cortana-VoIP-Unterstützung in Teams mithilfe einer Richtlinie (TeamsCortanaPolicy) verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="4594a-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="4594a-120">Diese Richtlinie kann entweder auf Ebene des Benutzerkontos oder auf Mandantenebene eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4594a-120">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="4594a-121">Administratoren können das CortanaVoiceInvocationMode-Feld in diesem Richtliniensteuerelement verwenden, um zu ermitteln, ob Cortana deaktiviert ist, nur mit nur einem Push-Button-Aufruf aktiviert ist, oder aber auch mit Wake-Word-Aufruf (gilt für Geräte, die es unterstützen, wie die Microsoft Teams-Anzeige).</span><span class="sxs-lookup"><span data-stu-id="4594a-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="4594a-122">Administratoren können die folgenden PowerShell-Cmdlets zum Verwalten dieser Richtlinie verwenden (die Richtlinie steht derzeit im Microsoft Teams Admin Center nicht zur Verfügung).</span><span class="sxs-lookup"><span data-stu-id="4594a-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="4594a-123">Neu – CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="4594a-123">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="4594a-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="4594a-124">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="4594a-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="4594a-125">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="4594a-126">Satz-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="4594a-126">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="4594a-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="4594a-127">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="4594a-128">Mit dem folgenden Befehl wird beispielsweise eine neue Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221;, in der Cortana-VoIP-Unterstützung in Microsoft Teams deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4594a-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="4594a-129">In diesem Beispiel wird das Aktualisieren einer vorhandenen Richtlinie mit dem Namen &#8220;EmployeeCortanaPolicy&#8221; und das Aktivieren von Cortana-VoIP-Unterstützung in Microsoft Teams mit nur Tasten Aufruf veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4594a-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="4594a-130">Benutzer können Cortana aufrufen, indem Sie die Cortana MIC-Schaltfläche in Teams auswählen.</span><span class="sxs-lookup"><span data-stu-id="4594a-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="4594a-131">Wake Word (&#8220;Hey Cortana&#8221; oder &#8220;Cortana&#8221;)-Aufruf wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4594a-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="4594a-132">In diesem Beispiel wird die Aktualisierung der Richtlinie und die Aktivierung der Cortana-VoIP-Unterstützung sowohl beim Drücken als auch beim Aktivieren des Word-Aufrufs veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4594a-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="4594a-133">Zu dem Zeitpunkt, an dem die erste Version für Microsoft 365 Enterprise-Benutzer in den USA in Englisch verfügbar ist, stehen die folgenden Funktionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="4594a-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="4594a-134">Die Mobile Teams-App unterstützt nicht die Aktivierung von Aktivierungs Word, wird aber in Zukunft unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4594a-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="4594a-135">Microsoft Teams Rooms auf Anzeigegeräten für Windows und Microsoft Teams unterstützen die Aktivierung von Aktivierungs Word.</span><span class="sxs-lookup"><span data-stu-id="4594a-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="4594a-136">Benutzersteuerelement</span><span class="sxs-lookup"><span data-stu-id="4594a-136">User control</span></span>

<span data-ttu-id="4594a-137">Einzelne Benutzer können Cortana-Sprachunterstützung auf verschiedenen Geräten ausprobieren:</span><span class="sxs-lookup"><span data-stu-id="4594a-137">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="4594a-138">Wählen Sie die Schaltfläche Mikrofon in der mobilen Teams-App aus.</span><span class="sxs-lookup"><span data-stu-id="4594a-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="4594a-139">Wählen Sie die Schaltfläche Mikrofon aus, oder sagen Sie "Cortana" in den Microsoft Teams-Räumen.</span><span class="sxs-lookup"><span data-stu-id="4594a-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="4594a-140">Sagen Sie "Cortana" auf den Microsoft Teams-Anzeigegeräten.</span><span class="sxs-lookup"><span data-stu-id="4594a-140">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="4594a-141">Sie können steuern, ob Cortana in Teams für Ihr Gerät aktiviert ist, indem Sie eine Einstellung auf dem Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="4594a-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="4594a-142">Mobile Teams-APP oder Microsoft Teams-Anzeige</span><span class="sxs-lookup"><span data-stu-id="4594a-142">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="4594a-143">Öffnen Sie die Mobile Teams-app.</span><span class="sxs-lookup"><span data-stu-id="4594a-143">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="4594a-144">Wählen Sie **Einstellungen**  >  **Cortana** aus.</span><span class="sxs-lookup"><span data-stu-id="4594a-144">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="4594a-145">Verschieben Sie die Umschaltfläche **ein** -oder **ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="4594a-145">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="4594a-146">Microsoft Teams-Anzeige</span><span class="sxs-lookup"><span data-stu-id="4594a-146">Microsoft Teams display</span></span>

  1. <span data-ttu-id="4594a-147">Wechseln Sie zum Bildschirm Ambient (Home) der Microsoft Teams-Anzeige.</span><span class="sxs-lookup"><span data-stu-id="4594a-147">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="4594a-148">Wählen Sie den Avatar des Benutzers aus, und wählen Sie dann **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="4594a-148">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="4594a-149">Wenn Cortana aktiviert ist, sagen Sie "Cortana, wechseln Sie zu Einstellungen."</span><span class="sxs-lookup"><span data-stu-id="4594a-149">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="4594a-150">Verschieben Sie die Umschaltfläche **ein** -oder **ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="4594a-150">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="4594a-151">Microsoft Teams-Räume unter Windows</span><span class="sxs-lookup"><span data-stu-id="4594a-151">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="4594a-152">Änderungen auf Geräteebene sind verfügbar, wenn Cortana auf Mandantenebene aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4594a-152">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="4594a-153">Cortana wird standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4594a-153">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="4594a-154">Um Cortana auf Geräteebene zu aktivieren, müssen diese XML-Attribute in der SkypeSettings-XML-Datei hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="4594a-154">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="4594a-155">Änderungen auf Besprechungs Ebene sind verfügbar, wenn Cortana auf Geräteebene aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4594a-155">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="4594a-156">Um die Cortana-Sprachunterstützung während einer Besprechung zu aktivieren, verschieben Sie **die Umschaltfläche** ein-oder **ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="4594a-156">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="4594a-157">Sobald die Besprechung beendet ist, kehrt Cortana zu den Einstellungen für die Geräteebene zurück.</span><span class="sxs-lookup"><span data-stu-id="4594a-157">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
