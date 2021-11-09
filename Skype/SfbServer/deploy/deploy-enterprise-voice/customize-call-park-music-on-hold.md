---
title: Anpassen der Wartemusik für das Parken von Anrufen inSkype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Passen Sie die Wartemusik für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP an.
ms.openlocfilehash: 9a17bddf45911974687fb374e9fd5da65b94787c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865312"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>Anpassen der Wartemusik für das Parken von Anrufen inSkype for Business
 
Passen Sie die Wartemusik für das Parken von Anrufen in Skype for Business Server Enterprise-VoIP an.
  
Sie können ihre eigene Musikdatei für die Wartemusik anstelle der Standardmusikdatei angeben, die mit Skype for Business Server ausgeliefert wird. Verwenden Sie zum Anpassen der Wartemusik das Cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.
  
> [!NOTE]
> Wenn Sie die Wartemusik anpassen und dieselbe Musik für mehrere Standorte verwenden möchten, müssen Sie die Musikdatei für jeden Standort konfigurieren, auf dem die Anwendung zum Parken von Anrufen ausgeführt wird. 
  
### <a name="to-customize-the-music-file"></a>So passen Sie die Musikdatei an

1. Melden Sie sich bei dem Computer an, auf dem Skype for Business Server Verwaltungsshell als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **"Stellvertretungs-Setupberechtigungen"** beschrieben.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Führen Sie Folgendes aus: 
    
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