---
title: Anpassen der Wartemusik für das Parken von Anrufen inSkype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Passen Sie die Wartemusik für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP an.
ms.openlocfilehash: 6dc080071df29e12a979e2591a73c02439a0a6271cda45b4105a009d1c70e307
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323537"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Anpassen der Wartemusik für das Parken von Anrufen inSkype for Business
 
Passen Sie die Wartemusik für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP an.
  
Sie können ihre eigene Musikdatei angeben, die für die Wartemusik verwendet werden soll, anstelle der Standardmusikdatei, die mit Skype for Business Server ausgeliefert wird. Verwenden Sie zum Anpassen der Wartemusik das Cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Wenn Sie die Wartemusik anpassen und dieselbe Musik für mehrere Standorte verwenden möchten, müssen Sie die Musikdatei für jeden Standort konfigurieren, auf dem die Anwendung zum Parken von Anrufen ausgeführt wird. 
  
### <a name="to-customize-the-music-file"></a>So passen Sie die Musikdatei an

1. Melden Sie sich bei dem Computer an, auf dem Skype for Business Server Verwaltungsshell als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **"Stellvertretungs-Setupberechtigungen"** beschrieben.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Ausführen:
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > Verwenden Sie das Cmdlet **Get-CsService**, um den Dienst zu ermitteln. Ausführliche Informationen finden Sie unter [Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps). 
  
    Im folgenden Beispiel wird gezeigt, wie die Inhalte der Datei "soothingmusic.wma" als Bytearray abgerufen und einer Variablen zugewiesen werden. Anschließend wird die Audiodatei als Wartemusikdatei für die Funktion zum Parken von Anrufen zugewiesen. Ausführliche Informationen finden Sie unter ["Set-CsCallParkServiceMusicOnHoldFile".](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>Siehe auch

[Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)