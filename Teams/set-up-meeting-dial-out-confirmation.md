---
title: Einrichten von Besprechungs Dial-Out – Bestätigung für Ihre Benutzer in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Teams einrichten, um eine Auswahl Bestätigung anzufordern, um zu verhindern, dass Voicemailsysteme eine Verbindung mit Besprechungen herstellen, wenn die angerufene Person den Anruf nicht annehmen kann.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a7d36d499ff7466fc1e0441bfd37bd7e6f863ae
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339473"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="5473a-103">Einrichten der Anruf Bestätigung für Besprechungen für Ihre Benutzer in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5473a-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="5473a-104">Die Wahlmöglichkeiten für Besprechungen und Anrufe an mich sind sehr hilfreich, um Teilnehmer zur Teilnahme an einer Besprechung einzuladen sowie für vorhandene Teilnehmer, die über ein herkömmliches oder Mobiltelefon an einer Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="5473a-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="5473a-105">Wenn die angerufene Person jedoch nicht in der Lage ist, den Anruf zu beantworten, und der Anruf von einem Voicemailsystem beantwortet wird, ist das Voicemailsystem mit der Besprechung verbunden, und die Teilnehmer können Sie anhören, bis Sie aus der Besprechung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="5473a-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="5473a-106">Um zu verhindern, dass Voicemailsysteme mit Besprechungen verbunden werden, wenn eine Anruf Abwahl an eine Telefonnummer gesendet wird und die angerufene Person den Anruf nicht annehmen kann, können Sie Teams so einrichten, dass Sie eine Bestätigung der angerufenen Person anfordern, um an der Besprechung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="5473a-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="5473a-107">Wenn die angerufene Person den Anruf nicht annehmen kann und der Anruf von einem Voicemailsystem beantwortet wird, wird das Voicemailsystem nicht mit der Besprechung verbunden, da es keine Bestätigung zur Teilnahme an ihm bietet.</span><span class="sxs-lookup"><span data-stu-id="5473a-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="5473a-108">Wenn diese Funktion aktiviert ist, müssen Personen, die einen Anruf oder Anruf annehmen, bestätigen, dass Sie an der Besprechung teilnehmen möchten, indem Sie auf Ihrem traditionellen oder mobilen Telefon 1 drücken.</span><span class="sxs-lookup"><span data-stu-id="5473a-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="5473a-109">Wenn Sie diese Funktion für alle Besprechungen in Ihrer Organisation aktivieren möchten ```EnableDialOutJoinConfirmation``` , setzen Sie den Parameter des Cmdlets ```true```" [Satz-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) " auf.</span><span class="sxs-lookup"><span data-stu-id="5473a-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="5473a-110">Führen Sie dazu den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="5473a-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="5473a-111">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="5473a-111">Related topics</span></span>

- [<span data-ttu-id="5473a-112">Einrichten der Funktion „Rückruf“ für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="5473a-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="5473a-113">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5473a-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)