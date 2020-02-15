---
title: Audiokonferenzen mit direktem Routing für GCCH und DoD
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: Hier erfahren Sie, wie Sie Audiokonferenzen mit direktem Routing in GCCH-und DoD-Umgebungen verwenden können.
ms.openlocfilehash: a8a9b5a46f1efd88de38fa65e857d3eebbbd6e3d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047186"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="272ae-103">Audiokonferenzen mit direktem Routing für GCC High und DoD</span><span class="sxs-lookup"><span data-stu-id="272ae-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="272ae-104">Audiokonferenz mit direktem Routing für gcc-höchst-und DoD ermöglicht Teilnehmern, mithilfe eines telefongeräts an Teams-Besprechungen in ihrer gcc-oder DoD-Organisation teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="272ae-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="272ae-105">Besprechungsteilnehmer möchten möglicherweise ein Telefongerät verwenden, um an Teams-Besprechungen in Szenarien teilzunehmen, beispielsweise wenn die Internetkonnektivität limitiert ist oder wenn Benutzer unterwegs sind und keinen Zugriff auf Teams haben.</span><span class="sxs-lookup"><span data-stu-id="272ae-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don’t have access to Teams.</span></span> <span data-ttu-id="272ae-106">Teilnehmer können an Besprechungen teilnehmen, indem Sie entweder eine Einwahl Telefonnummer für Ihre Organisation einwählen oder die Besprechung auf Ihrem Telefongerät anrufen.</span><span class="sxs-lookup"><span data-stu-id="272ae-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="272ae-107">Bei Audiokonferenzen mit direktem Routing für gcc-höchst-und DoD verwendet Ihre Organisation eigene Nummern als Einwahlnummern, und alle Auswahlen von Besprechungen zu Telefongeräten werden über direkte Weiterleitung geroutet.</span><span class="sxs-lookup"><span data-stu-id="272ae-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="272ae-108">Um den Dienst zu aktivieren, müssen Organisationen Direktes Routing einrichten und Telefonnummern konfigurieren, die als Einwahl Telefonnummern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="272ae-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="272ae-109">Die Anforderung zur Verwendung des direkten Routings unterscheidet sich vom Audiokonferenzdienst, der für nicht-gcc-Organisationen mit hoher und nicht-DoD-Funktion angeboten wird, bei denen die Einwahl Telefonnummern von Microsoft bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="272ae-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="272ae-110">Bereitstellen von Audiokonferenzen mit direktem Routing für gcc-höchst-und DoD</span><span class="sxs-lookup"><span data-stu-id="272ae-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="272ae-111">Schritt 1: Abrufen von Audiokonferenzen mit Direct Routing für gcc-Lizenzen für höhere oder DoD-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="272ae-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="272ae-112">Wenn Sie Audiokonferenzen in gcc-höchst-oder DoD verwenden möchten, müssen Ihre Organisation und die Benutzer in Ihrer Organisation über eine Audiokonferenz mit zugewiesener Direct Routing-Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="272ae-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="272ae-113">Hier sind die Lizenzen, die Sie benötigen, um Audiokonferenzen mit Direct Routing für gcc-höchst-oder DoD zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="272ae-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="272ae-114">Gcc-höchst: eine Audio-Conferencing-gcc-Lizenz für Ihre Organisation und Audiokonferenz-gcc-Lizenzen für Ihre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="272ae-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="272ae-115">DoD: eine Audio Conferencing-DoD-Mandanten Lizenz für Ihre Organisation und Ihre Audio-Conferencing-DoD-Lizenzen für Ihre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="272ae-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="272ae-116">Zum Aktivieren des Diensts sind eine Mandanten Lizenz und mindestens eine Benutzerlizenz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="272ae-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="272ae-117">Sie können den Dienst nur mit der Mandanten Lizenz oder nur mit Benutzerlizenzen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="272ae-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="272ae-118">Wenden Sie sich an Ihr Konto Team, um Dienstlizenzen für Ihren Mandanten und die Benutzer in Ihrer Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="272ae-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="272ae-119">Benutzer können für Audiokonferenzen mit direktem Routing erst dann aktiviert werden, wenn Einwahl Telefonnummern eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="272ae-119">Users can’t be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="272ae-120">Es wird empfohlen, dass Sie keine Audiokonferenzen mit direktem Routing für gcc-hoch-oder DoD-Lizenzen an Benutzer zuweisen, bis Sie Einwahl Telefonnummern wie in diesem Artikel beschrieben einrichten.</span><span class="sxs-lookup"><span data-stu-id="272ae-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="272ae-121">Schritt 2: Einrichten des direkten Routings</span><span class="sxs-lookup"><span data-stu-id="272ae-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="272ae-122">Informationen zum Einrichten des direkten Routings finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="272ae-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="272ae-123">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="272ae-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="272ae-124">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="272ae-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="272ae-125">Denken Sie beim Einrichten des direkten Routings daran, die in diesen beiden Artikeln beschriebenen "gcc-hoch"-oder DoD-spezifischen FQDNs und Ports zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="272ae-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="272ae-126">Schritt 3: Einrichten von Einwahl Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="272ae-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="272ae-127">Einwahl Telefonnummern sind die Telefonnummern, die ihrer Audiokonferenz-Brücke zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="272ae-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="272ae-128">Diese Nummern werden von Teilnehmern verwendet, um an Besprechungen teilzunehmen, die von Benutzern in Ihrer Organisation geplant wurden.</span><span class="sxs-lookup"><span data-stu-id="272ae-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="272ae-129">Diese Nummern sind auch in den Besprechungseinladungen der Benutzer enthalten, die Besprechungen in Ihrer Organisation planen, und auf der Seite "Ortsnummer suchen".</span><span class="sxs-lookup"><span data-stu-id="272ae-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the “Find a local number” page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="272ae-130">Definieren von Service-Telefonnummern in Ihrem Mandanten</span><span class="sxs-lookup"><span data-stu-id="272ae-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="272ae-131">Sie können das PowerShell-Cmdlet New-csHybridTelephoneNumber verwenden, um Dienst Rufnummern in Ihrem Mandanten zu definieren, die zum Weiterleiten von Anrufen an den Audiokonferenzdienst über direktes Routing verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="272ae-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="272ae-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="272ae-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber “+14250000000”
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="272ae-133">Zuweisen der Telefonnummern für den Service zur Audiokonferenz-Brücke Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="272ae-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="272ae-134">Mithilfe des PowerShell-Cmdlets Register-csOnlineDialInConferencingServiceNumber können Sie der Audiokonferenz-Brücke Ihrer Organisation Service-Telefonnummern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="272ae-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="272ae-135">Sie können die ID Ihrer Audiokonferenz-Bridge mithilfe von Get-CsOnlineDialInConferencingBridge anzeigen.</span><span class="sxs-lookup"><span data-stu-id="272ae-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="272ae-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="272ae-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="272ae-137">Schritt 4: Zuweisen von Audiokonferenzen mit Direct Routing für gcc-höchst-oder DoD-Lizenzen für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="272ae-137">Step 4: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="272ae-138">Informationen zum Zuweisen von Audiokonferenzen mit direktem Routing für gcc-oder DoD-Lizenzen für Ihre Benutzer finden Sie unter [Zuweisen von Lizenzen zu Benutzern in Office 365 for Business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="272ae-138">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="272ae-139">Schritt 5: (optional) Anzeigen einer Liste der Audiokonferenz-Nummern in Teams</span><span class="sxs-lookup"><span data-stu-id="272ae-139">Step 5: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="272ae-140">Wenn Sie die Liste der Audiokonferenz-Nummern Ihrer Organisation anzeigen möchten, wechseln [Sie zu einer Liste der Audiokonferenz-Nummern in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="272ae-140">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="272ae-141">Schritt 6: (optional) festlegen der Sprachen der automatischen Telefonzentrale für die Einwahlnummern für Audiokonferenzen Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="272ae-141">Step 6: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="272ae-142">Informationen zum Ändern der Sprachen der Einwahlnummern für Audiokonferenzen in Ihrer Organisation finden Sie unter [Festlegen von Sprachen für die automatische Telefonzentrale für Audiokonferenzen in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="272ae-142">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span></span>

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="272ae-143">Schritt 7: (optional) Ändern der Einstellungen der Audiokonferenz-Brücke in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="272ae-143">Step 7: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="272ae-144">Informationen zum Ändern der Einstellungen der Audiokonferenz-Brücke in Ihrer Organisation finden Sie unter [Ändern der Einstellungen für eine Audiokonferenz-Brücke](change-the-settings-for-an-audio-conferencing-bridge.md) .</span><span class="sxs-lookup"><span data-stu-id="272ae-144">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="272ae-145">Schritt 8: (optional) festlegen der Telefonnummern, die in den Besprechungseinladungen der Benutzer in Ihrer Organisation enthalten sind</span><span class="sxs-lookup"><span data-stu-id="272ae-145">Step 8: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="272ae-146">Informationen zum Ändern der Gruppe von Telefonnummern, die in den Besprechungseinladungen der Benutzer enthalten sind, finden Sie unter [Festlegen der Telefonnummern, die in Einladungen in Microsoft Teams enthalten](set-the-phone-numbers-included-on-invites-in-teams.md) sind.</span><span class="sxs-lookup"><span data-stu-id="272ae-146">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="272ae-147">Audiokonferenzfunktionen, die in Audiokonferenzen nicht unterstützt werden, mit direktem Routing für gcc-höchst-und DoD-Funktionen</span><span class="sxs-lookup"><span data-stu-id="272ae-147">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="272ae-148">Im folgenden finden Sie Audiokonferenzfunktionen, die bei Audiokonferenzen mit direktem Routing für gcc-höchst-und DoD-Funktionen nicht unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="272ae-148">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="272ae-149">Eingabe-und Exit-Benachrichtigungen mithilfe der namens Aufzeichnung.</span><span class="sxs-lookup"><span data-stu-id="272ae-149">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="272ae-150">Bei Audiokonferenzen mit direktem Routing werden die Eingabe-und Exit-Benachrichtigungen als Töne in der Besprechung abgespielt.</span><span class="sxs-lookup"><span data-stu-id="272ae-150">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="272ae-151">Richtlinien für ausgehende Anruf Einschränkungen für Audiokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="272ae-151">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="272ae-152">Steuerelemente auf Benutzerebene zum Einschränken ausgehender Anrufe gelten nicht für von der direkten Weiterleitung weitergeleitete Anrufe an eingehende Anrufe.</span><span class="sxs-lookup"><span data-stu-id="272ae-152">User-level controls to restrict outbound calls aren’t applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="272ae-153">Deaktivieren Sie die Verwendung von gebührenfreien Nummern für den Besprechungs spezifischen Organisator.</span><span class="sxs-lookup"><span data-stu-id="272ae-153">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="272ae-154">Steuerelemente auf Benutzerebene, um die Verwendung von gebührenfreien Nummern für die Teilnahme an den Besprechungen Ihrer Organisation zu beschränken, gelten nicht für Anrufe, die über direktes Routing weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="272ae-154">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren’t applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="272ae-155">Senden von Benachrichtigungs-e-Mails an Benutzer, wenn sich Ihre Einstellungen ändern</span><span class="sxs-lookup"><span data-stu-id="272ae-155">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="272ae-156">Audiokonferenz-Benachrichtigungs-e-Mails werden für Audiokonferenzen mit direktem Routing für gcc-höchst-und DoD nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="272ae-156">Audio Conferencing notification emails aren’t supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
