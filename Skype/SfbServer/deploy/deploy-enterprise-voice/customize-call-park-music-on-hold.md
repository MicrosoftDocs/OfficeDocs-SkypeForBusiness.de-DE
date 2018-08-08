---
title: Anpassen des Parkens von Anrufen Musik in der Warteschleife InSkype für Unternehmen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Passen Sie die Musik in der Warteschleife in Skype für Business Server Enterprise-VoIP Parken.
ms.openlocfilehash: e0d1f49a1385eb185f7abb12edb467abb221a411
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001252"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="c24a5-103">Anpassen des Parkens von Anrufen Musik in der Warteschleife InSkype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="c24a5-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="c24a5-104">Passen Sie die Musik in der Warteschleife in Skype für Business Server Enterprise-VoIP Parken.</span><span class="sxs-lookup"><span data-stu-id="c24a5-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="c24a5-105">Sie können angeben, dass eine eigene Musikdatei für Musik in der Warteschleife, anstatt die Musikdatei Standard verwenden, die mit Skype für Business Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24a5-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="c24a5-106">Verwenden Sie das **Set-CsCallParkServiceMusicOnHoldFile** -Cmdlet, um Musik in der Warteschleife anzupassen.</span><span class="sxs-lookup"><span data-stu-id="c24a5-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c24a5-107">Wenn Sie die wartemusik anpassen und die gleiche Musikdatei für mehrere Standorte verwenden möchten, müssen Sie die Musikdatei für jeden Standort konfigurieren, die die Anwendung zum Parken von Anrufen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c24a5-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="c24a5-108">So passen Sie die Musikdatei an</span><span class="sxs-lookup"><span data-stu-id="c24a5-108">To customize the music file</span></span>

1. <span data-ttu-id="c24a5-109">Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="c24a5-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="c24a5-110">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="c24a5-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c24a5-111">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c24a5-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="c24a5-112">Verwenden Sie das Cmdlet " **Get-CsService** ", um den Dienst zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c24a5-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="c24a5-113">Weitere Informationen hierzu finden Sie unter [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c24a5-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="c24a5-114">Im folgenden Beispiel wird gezeigt, wie die Inhalte der Datei „soothingmusic.wma“ als Bytearray abgerufen und einer Variablen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c24a5-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="c24a5-115">Anschließend wird die Audiodatei als Wartemusikdatei für die Funktion zum Parken von Anrufen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c24a5-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="c24a5-116">Weitere Informationen hierzu finden Sie unter [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c24a5-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="c24a5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c24a5-117">See also</span></span>

[<span data-ttu-id="c24a5-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="c24a5-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="c24a5-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="c24a5-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)