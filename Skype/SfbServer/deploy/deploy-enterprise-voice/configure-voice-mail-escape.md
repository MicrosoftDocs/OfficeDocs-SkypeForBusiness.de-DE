---
title: Konfigurieren der Voicemail-escapefunktion in Skype for Business
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Escape-Voicemail in Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell konfigurieren.'
ms.openlocfilehash: 27f283f4bfb64aa950bd9e72a9d6fdc17df91ba0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001215"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="5e024-103">Konfigurieren der Voicemail-escapefunktion in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5e024-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="5e024-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie die Escape-Voicemail in Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5e024-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="5e024-105">Wenn ein Benutzer das gleichzeitige Klingeln auf einem Mobiltelefon konfiguriert, wird ein Anrufer in der Regel an die persönliche Voicemail des Benutzers weitergeleitet, wenn das Mobiltelefon ausgeschaltet ist, der Akku nicht mehr zur verweilen oder außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="5e024-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="5e024-106">Mit Skype for Business Server können die Benutzer entscheiden, dass unternehmensbezogene Anrufe an das Voicemailsystem Ihres Unternehmens weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5e024-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="5e024-107">Insbesondere kann ein Zeitgeber konfiguriert werden, und wenn der Anruf von der Voicemail des Netzbetreibers innerhalb des definierten Zeitraums beantwortet wird, trennt sich Skype for Business Server vom Voicemailsystem des Netzbetreibers (und der persönlichen Voicemail des Benutzers), während die verbleibende Endpunkte im Unternehmenssystem Klingeln weiterhin.</span><span class="sxs-lookup"><span data-stu-id="5e024-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="5e024-108">Auf diese Weise wird der Anrufer automatisch an die Firmen-Voicemail des Benutzers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5e024-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="5e024-109">Diese Konfiguration wird mit dem Cmdlet "Skype for Business Server-Verwaltungsshell", " **Satz-CsVoicePolicy**", auf der VoIP-Richtlinienebene mit den folgenden Parametern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5e024-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="5e024-110">So konfigurieren Sie Voicemail Escape</span><span class="sxs-lookup"><span data-stu-id="5e024-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="5e024-111">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="5e024-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="5e024-112">Geben Sie die folgenden Parameter für **Set-CsVoicePolicy** an:</span><span class="sxs-lookup"><span data-stu-id="5e024-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="5e024-113">**EnableVoicemailEscapeTimer**: Aktiviert oder deaktiviert den Escape-Timer.</span><span class="sxs-lookup"><span data-stu-id="5e024-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="5e024-p102">**PSTNVoicemailEscapeTimer**: Gibt den Timeoutwert in Millisekunden an. Der Standardwert lautet 1500 Millisekunden und der Wert kann zwischen 0 und 8000 Millisekunden liegen.</span><span class="sxs-lookup"><span data-stu-id="5e024-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="5e024-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e024-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="5e024-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e024-117">See also</span></span>

[<span data-ttu-id="5e024-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span><span class="sxs-lookup"><span data-stu-id="5e024-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

