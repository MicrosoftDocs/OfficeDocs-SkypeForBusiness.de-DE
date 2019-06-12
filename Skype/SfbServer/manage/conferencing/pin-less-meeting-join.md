---
title: Konfigurieren der PIN-losen Besprechungsanmeldung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Option "Pin-less-Besprechungsteilnahme" in Skype for Business Server konfigurieren.'
ms.openlocfilehash: ecd1d2bf184dd6b9e1ff78e16c2ca1eb8da73ef9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280383"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Konfigurieren der PIN-losen Besprechungsanmeldung in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie die Option "Pin-less-Besprechungsteilnahme" in Skype for Business Server konfigurieren.
  
Wenn ein Einwahl-Anrufer versucht, an einer Besprechung teilzunehmen, platziert der Konferenzdienst für die automatische Telefonzentrale (CAA) den Anrufer in einen unterschiedlichen Stift, der sich vom Lobby-#a0 unterscheidet, wenn ein Referent noch keinen Anruf hat und der Einwahl-Anrufer keine führungsnadel eingegeben hat. Die PIN-lose Besprechungsanmeldeoption ermöglicht Einwahl-Anrufern die Teilnahme an einer Besprechung ohne Eingabe einer Leiter-PIN sogar dann, wenn sie nicht als Erste zugeschaltet werden. 
  
Beachten Sie Folgendes, wenn Sie diese Funktion konfigurieren:
  
- Gilt nur für private Besprechungen.
    
- PSTN-Anrufer können in privaten Besprechungen verbleiben, ohne dass authentifizierte Nutzer anwesend sind.
    
- Nach der Änderung der Einstellung gilt sie für alle existierenden und neuen privaten Besprechungen.
    
- Kann entweder am Standort des Organisators oder auf globaler Ebene aktiviert werden.
    
- Optionen dafür, wer die Lobby umgehen kann, können für jeden der folgenden Fälle eingestellt werden: 
    
  - **„Jeder innerhalb meiner Organisation“ mit „Anrufer erhalten direkten Zugang“**
    
  - **„Alle Personen (keine Einschränkungen)“ mit „Anrufer erhalten direkten Zugang“**. (Das ist die Standardeinstellung.)
    
- Wenn die Konfiguration die PIN-lose Anmeldung vorsieht, fordert der CAA-Dienst trotzdem zur Eingabe einer Leiter-PIN auf. Nutzer können mit oder ohne Eingabe einer PIN an der Besprechung teilnehmen. Das Beibehalten der Möglichkeit, eine Führungslinien-PIN einzugeben, ermöglicht es einem Einwahl Anrufer jedoch, sich als Leiter zu authentifizieren und die Besprechung bei Bedarf zu verwalten.
    
## <a name="configure-pin-less-meeting-join"></a>Konfigurieren der PIN-losen Besprechungsanmeldung

Verwenden Sie das Cmdlet " [festlegen-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) " mit dem AllowAnonymousPstnActivation-Parameter wie folgt, um die PIN-less-Besprechung für Ihre Benutzer zu aktivieren:
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Als Beispiel ermöglicht der folgende Befehl die PIN-lose Besprechungsanmeldung für den Standort Redmond:
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Aus Sicherheitsgründen möchten Sie unter Umständen, wenn die PIN-lose Besprechungsanmeldung aktiviert worden ist, dass anonyme Anrufer von der Einwahl ausgeschlossen werden. Stellen Sie zu diesem Zweck sicher, dass die Konferenzrichtlinie wie folgt festgelegt wird:
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Weitere Informationen finden Sie unter [Satz-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

