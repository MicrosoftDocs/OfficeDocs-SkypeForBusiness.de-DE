---
title: Aus einer Besprechung heraus wählen, damit andere Personen teilnehmen können
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 3c2db9a5-3a19-4e19-b59e-8e5587f25d31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Besprechungsorganisatoren können lernen, wie Sie mithilfe der Teams-App wählen, um andere Personen mit ihren Telefonen an derselben Besprechung teilzunehmen.
ms.openlocfilehash: 575ed18bd3dbd404dba947c0c4556d52e0653200
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788759"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="57399-103">Anrufen aus einer Microsoft Teams-Besprechung, sodass andere Personen teilnehmen können</span><span class="sxs-lookup"><span data-stu-id="57399-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="57399-104">Als Besprechungsorganisator können Sie mithilfe der Teams-App wählen, um andere Personen mit ihren Telefonen an derselben Besprechung teilhaben zu lassen.</span><span class="sxs-lookup"><span data-stu-id="57399-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="57399-105">Wenn Sie eine Person anrufen, empfehlen wir, dass Sie Ihre vollständigen Telefonnummern verwenden (einschließlich des Formats "Land/Region-Code-E. 164").</span><span class="sxs-lookup"><span data-stu-id="57399-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="57399-106">Bitte beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="57399-106">Please note that:</span></span>

- <span data-ttu-id="57399-107">Sie können sich nur dann anrufen, wenn Sie mit Teams an einer Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="57399-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="57399-108">Der Organisator der Besprechung wurde für Audiokonferenzen aktiviert, oder falls keine Audiokonferenz-Lizenz zugewiesen ist, ist es möglich, Anrufe an das öffentlich geschaltete Telefonnetz über Online-Anrufpläne oder direktes Routing zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="57399-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="57399-109">Der Besprechungsorganisator erhält [eine Online-Wähl Richtlinie, die das Auswählen von Konferenzen aktiviert](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="57399-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="57399-110">Gehen Sie wie folgt vor, um die Arbeit zu wählen:</span><span class="sxs-lookup"><span data-stu-id="57399-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="57399-111">**Schritt 1:** Verwenden Sie in der Besprechung den Screenshot **Personen hinzufügen** der ![ Schaltfläche "Personen hinzufügen", ](media/add-people-button.png) um eine Telefonnummer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="57399-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="57399-112">**Schritt 2:** Geben Sie die vollständige Telefonnummer einschließlich der Landes-und Regions Vorwahl in das Feld **jemanden einladen oder Nummer wählen ein** .</span><span class="sxs-lookup"><span data-stu-id="57399-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![Screenshot des Felds "jemanden einladen" oder "Nummer wählen"](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="57399-114">Unterstützte Länder und Regionen</span><span class="sxs-lookup"><span data-stu-id="57399-114">Supported countries and regions</span></span>

<span data-ttu-id="57399-115">Dial-Out ist nur für einige Länder/Regionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="57399-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="57399-116">Eine vollständige Liste finden Sie unter [Verfügbarkeit von Ländern und Regionen für Audiokonferenz-und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="57399-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="57399-117">Zulassen, dass Benutzer sich einwählen</span><span class="sxs-lookup"><span data-stu-id="57399-117">Allow users to dial in</span></span>

<span data-ttu-id="57399-118">Wenn Sie nach Anleitungen zum Einwählen Ihrer Benutzer in eine Teams-Besprechung suchen, lesen Sie [Telefonnummern für Audiokonferenzen in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="57399-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="57399-119">Möchten Sie mehr über Audiokonferenzen erfahren?</span><span class="sxs-lookup"><span data-stu-id="57399-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="57399-120">Testen oder kaufen von Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="57399-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="57399-121">Lizenzierung für Microsoft Teams-Add-On</span><span class="sxs-lookup"><span data-stu-id="57399-121">Microsoft Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
