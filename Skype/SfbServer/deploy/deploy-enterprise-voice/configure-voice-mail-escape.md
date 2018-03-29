---
title: Konfigurieren von Voicemail Escape in Skype for Business 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Zusammenfassung: Erfahren Sie, wie mithilfe der Skype für Business Server-Verwaltungsshell des Wechsels der Voicemail in Skype für Business Server 2015 konfigurieren.'
ms.openlocfilehash: 07586f38127b2831ecdb2900f005ff43b4184292
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-voice-mail-escape-in-skype-for-business-2015"></a><span data-ttu-id="52ba3-103">Konfigurieren von Voicemail Escape in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="52ba3-103">Configure voice mail escape in Skype for Business 2015</span></span>
 
<span data-ttu-id="52ba3-104">**Zusammenfassung:** Erfahren Sie, wie mithilfe der Skype für Business Server-Verwaltungsshell des Wechsels der Voicemail in Skype für Business Server 2015 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="52ba3-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server 2015 by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="52ba3-105">Wenn ein Benutzer Gleichzeitiges Klingeln an ein Mobiltelefon konfiguriert, wird ein Anrufer in der Regel an den Benutzer Persönliche Voicemail weitergeleitet werden, wenn das Mobiltelefon deaktiviert, nicht genügend Batterie oder außerhalb des gültigen Bereichs aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="52ba3-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="52ba3-106">Mit Skype für Business Server können Benutzer Ihre geschäftliche Anrufe an ihre corporate Voicemail-System weitergeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="52ba3-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="52ba3-107">Ein Zeitgebers konfiguriert werden kann, insbesondere wenn von der Netzbetreiber Voicemail innerhalb des Bereichs definierte Zeit der Anruf entgegengenommen wurde, wird Skype für Business Server aus der Netzbetreiber Voicemail-Systems (und persönliche Voicemail des Benutzers), während des Benutzers getrennt verbleibenden Endpunkte in der corporate System weiter angeboten werden soll.</span><span class="sxs-lookup"><span data-stu-id="52ba3-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="52ba3-108">Auf diese Weise ist der Anrufer automatisch an den Benutzer im Unternehmen Voicemail weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="52ba3-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>
  
<span data-ttu-id="52ba3-109">Diese Konfiguration erfolgt mithilfe der Skype für Business Server-Verwaltungsshell-Cmdlet **Set-CsVoicePolicy**auf Ebene der VoIP-Richtlinie mit den folgenden Parametern.</span><span class="sxs-lookup"><span data-stu-id="52ba3-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>
  
### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="52ba3-110">So konfigurieren Sie Voicemail Escape</span><span class="sxs-lookup"><span data-stu-id="52ba3-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="52ba3-111">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="52ba3-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="52ba3-112">Geben Sie die folgenden Parameter für **Set-CsVoicePolicy** an:</span><span class="sxs-lookup"><span data-stu-id="52ba3-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
   - <span data-ttu-id="52ba3-113">**EnableVoicemailEscapeTimer**: Aktiviert oder deaktiviert den Escape-Timer.</span><span class="sxs-lookup"><span data-stu-id="52ba3-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
   - <span data-ttu-id="52ba3-p102">**PSTNVoicemailEscapeTimer**: Gibt den Timeoutwert in Millisekunden an. Der Standardwert lautet 1500 Millisekunden und der Wert kann zwischen 0 und 8000 Millisekunden liegen.</span><span class="sxs-lookup"><span data-stu-id="52ba3-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>
    
## <a name="example"></a><span data-ttu-id="52ba3-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52ba3-116">Example</span></span>

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000

Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

```

## <a name="see-also"></a><span data-ttu-id="52ba3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52ba3-117">See also</span></span>

#### 

[<span data-ttu-id="52ba3-118">Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="52ba3-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](http://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

