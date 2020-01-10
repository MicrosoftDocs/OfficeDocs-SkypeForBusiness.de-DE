---
title: Anzeigen von PSTN-Nutzungsdaten Sätzen in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die PSTN-Nutzungsdatensätze mithilfe des Skype for Business Server-Control Panels oder der Skype for Business Server-Verwaltungsshell anzeigen können.'
ms.openlocfilehash: 96a96898bf728b4f05ba473bc750635e41be19fa
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002725"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="70399-103">Anzeigen von PSTN-Nutzungsdaten Sätzen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="70399-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="70399-104">**Zusammenfassung:** Informationen zum Anzeigen von PSTN-Nutzungsdaten Sätzen mithilfe des Skype for Business Server-Control Panels oder der Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="70399-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="70399-p101">Ein PSTN-Verwendungsdatensatz gibt eine Anrufklasse (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche) an, die von den verschiedenen Nutzern oder Nutzergruppen in einer Organisation getätigt werden dürfen. Ausführliche Informationen finden Sie unter [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="70399-p101">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization. For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="70399-107">So zeigen Sie einen PSTN-Verwendungs Eintrag mithilfe der Skype for Business Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="70399-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="70399-108">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="70399-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="70399-109">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **PSTN-Verwendung**.</span><span class="sxs-lookup"><span data-stu-id="70399-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="70399-110">Markieren Sie auf der Seite **PSTN-Verwendung** den PSTN-Verwendungsdatensatz, den Sie anzeigen möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="70399-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70399-111">Auf einer schreibgeschützten Seite des ausgewählten PSTN-Verwendungsdatensatzes werden die zugehörigen Routen und VoIP-Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="70399-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="70399-112">So zeigen Sie die Informationen zur PSTN-Nutzung mithilfe der Cmdlets der Skype for Business Server-Verwaltungsshell an</span><span class="sxs-lookup"><span data-stu-id="70399-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="70399-113">Wenn Sie Informationen zu allen PSTN-Nutzungen anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="70399-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```powershell
  Get-CsPstnUsage
  ```

    <span data-ttu-id="70399-114">Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="70399-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="70399-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70399-115">See also</span></span>

[<span data-ttu-id="70399-116">Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="70399-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

