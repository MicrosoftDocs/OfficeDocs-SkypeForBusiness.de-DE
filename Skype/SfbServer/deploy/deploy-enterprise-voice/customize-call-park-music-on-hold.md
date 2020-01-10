---
title: Anpassen der Musik des Anruf Parks im Wartebereich von Skype for Business
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
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Passen Sie die Musik des Anruf Parks in Skype for Business Server Enterprise-VoIP in Wartestellung an.
ms.openlocfilehash: f071b83e155e2ddfb057619eb95773e4386b67c0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001005"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Anpassen der Musik des Anruf Parks im Wartebereich von Skype for Business
 
Passen Sie die Musik des Anruf Parks in Skype for Business Server Enterprise-VoIP in Wartestellung an.
  
Sie können anstelle der im Lieferumfang von Skype for Business Server enthaltene Standardmusik Datei eine eigene Musikdatei angeben, die Sie für die Aufbewahrung von Musik verwenden möchten. Verwenden Sie zum Anpassen der Wartemusik das Cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Wenn Sie die Musik im Wartebereich anpassen und für mehrere Websites dieselbe Musik wünschen, müssen Sie die Musikdatei für jede Website konfigurieren, auf der die Anwendung "Parken" ausgeführt wird. 
  
### <a name="to-customize-the-music-file"></a>So passen Sie die Musikdatei an

1. Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **Delegieren von Setup Berechtigungen**beschrieben.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie folgenden Befehl aus:
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Verwenden Sie das Cmdlet **Get-CsService**, um den Dienst zu ermitteln. Ausführliche Informationen finden Sie unter [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps). 
  
    Im folgenden Beispiel wird gezeigt, wie die Inhalte der Datei „soothingmusic.wma“ als Bytearray abgerufen und einer Variablen zugewiesen werden. Anschließend wird die Audiodatei als Wartemusikdatei für die Funktion zum Parken von Anrufen zugewiesen. Ausführliche Informationen finden Sie unter [Satz-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Siehe auch

[Satz-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
