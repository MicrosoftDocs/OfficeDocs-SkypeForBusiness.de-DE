---
title: Konfigurieren der Voicemail-escapefunktion in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Escape-Voicemail in Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell konfigurieren.'
ms.openlocfilehash: 89c449f538fee2f5230cb66a664317cada723220
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289083"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="1c81a-103">Konfigurieren der Voicemail-escapefunktion in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1c81a-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="1c81a-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie die Escape-Voicemail in Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1c81a-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="1c81a-105">Wenn ein Benutzer das gleichzeitige Klingeln auf einem Mobiltelefon konfiguriert, wird ein Anrufer in der Regel an die persönliche Voicemail des Benutzers weitergeleitet, wenn das Mobiltelefon ausgeschaltet ist, der Akku nicht mehr zur verweilen oder außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="1c81a-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="1c81a-106">Mit Skype for Business Server können die Benutzer entscheiden, dass unternehmensbezogene Anrufe an das Voicemailsystem Ihres Unternehmens weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="1c81a-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="1c81a-107">Insbesondere kann ein Zeitgeber konfiguriert werden, und wenn der Anruf von der Voicemail des Netzbetreibers innerhalb des definierten Zeitraums beantwortet wird, trennt sich Skype for Business Server vom Voicemailsystem des Netzbetreibers (und der persönlichen Voicemail des Benutzers), während die verbleibende Endpunkte im Unternehmenssystem Klingeln weiterhin.</span><span class="sxs-lookup"><span data-stu-id="1c81a-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="1c81a-108">Auf diese Weise wird der Anrufer automatisch an die Firmen-Voicemail des Benutzers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="1c81a-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="1c81a-109">Diese Konfiguration wird mit dem Cmdlet "Skype for Business Server-Verwaltungsshell", " **Satz-CsVoicePolicy**", auf der VoIP-Richtlinienebene mit den folgenden Parametern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c81a-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="1c81a-110">So konfigurieren Sie Voicemail Escape</span><span class="sxs-lookup"><span data-stu-id="1c81a-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="1c81a-111">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1c81a-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="1c81a-112">Geben Sie die folgenden Parameter für **Set-CsVoicePolicy** an:</span><span class="sxs-lookup"><span data-stu-id="1c81a-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="1c81a-113">**EnableVoicemailEscapeTimer**: Aktiviert oder deaktiviert den Escape-Timer.</span><span class="sxs-lookup"><span data-stu-id="1c81a-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="1c81a-p102">**PSTNVoicemailEscapeTimer**: Gibt den Timeoutwert in Millisekunden an. Der Standardwert lautet 1500 Millisekunden und der Wert kann zwischen 0 und 8000 Millisekunden liegen.</span><span class="sxs-lookup"><span data-stu-id="1c81a-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="1c81a-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c81a-116">Example</span></span>

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="1c81a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c81a-117">See also</span></span>

[<span data-ttu-id="1c81a-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span><span class="sxs-lookup"><span data-stu-id="1c81a-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

