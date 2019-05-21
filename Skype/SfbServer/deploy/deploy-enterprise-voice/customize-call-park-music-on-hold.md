---
title: Anpassen der Musik des Anruf Parks im Wartebereich von Skype for Business
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
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Passen Sie die Musik des Anruf Parks in Skype for Business Server Enterprise-VoIP in Wartestellung an.
ms.openlocfilehash: 4111bcc42a3820e3957f526e360264aa7d098d05
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286176"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="447e3-103">Anpassen der Musik des Anruf Parks im Wartebereich von Skype for Business</span><span class="sxs-lookup"><span data-stu-id="447e3-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="447e3-104">Passen Sie die Musik des Anruf Parks in Skype for Business Server Enterprise-VoIP in Wartestellung an.</span><span class="sxs-lookup"><span data-stu-id="447e3-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="447e3-105">Sie können anstelle der im Lieferumfang von Skype for Business Server enthaltene Standardmusik Datei eine eigene Musikdatei angeben, die Sie für die Aufbewahrung von Musik verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="447e3-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="447e3-106">Verwenden Sie zum Anpassen der Wartemusik das Cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="447e3-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="447e3-107">Wenn Sie die Musik im Wartebereich anpassen und für mehrere Websites dieselbe Musik wünschen, müssen Sie die Musikdatei für jede Website konfigurieren, auf der die Anwendung "Parken" ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="447e3-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="447e3-108">So passen Sie die Musikdatei an</span><span class="sxs-lookup"><span data-stu-id="447e3-108">To customize the music file</span></span>

1. <span data-ttu-id="447e3-109">Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter Delegieren von **Setup Berechtigungen**beschrieben.</span><span class="sxs-lookup"><span data-stu-id="447e3-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="447e3-110">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="447e3-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="447e3-111">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="447e3-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="447e3-112">Verwenden Sie das Cmdlet **Get-CsService**, um den Dienst zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="447e3-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="447e3-113">Ausführliche Informationen finden Sie unter [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="447e3-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="447e3-114">Im folgenden Beispiel wird gezeigt, wie die Inhalte der Datei „soothingmusic.wma“ als Bytearray abgerufen und einer Variablen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="447e3-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="447e3-115">Anschließend wird die Audiodatei als Wartemusikdatei für die Funktion zum Parken von Anrufen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="447e3-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="447e3-116">Ausführliche Informationen finden Sie unter [Satz-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="447e3-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="447e3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="447e3-117">See also</span></span>

[<span data-ttu-id="447e3-118">Satz-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="447e3-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="447e3-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="447e3-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
