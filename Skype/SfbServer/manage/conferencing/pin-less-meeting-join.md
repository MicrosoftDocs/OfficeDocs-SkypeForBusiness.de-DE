---
title: Konfigurieren der PIN-losen Besprechungsteilnahme in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Zusammenfassung: Erfahren Sie, wie Sie die PIN-lose Besprechungsteilnahmeoption in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 5e11a727e42ce4d65e21d3e001404a421fc52541
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617891"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Konfigurieren der PIN-losen Besprechungsteilnahme in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die PIN-lose Besprechungsteilnahmeoption in Skype for Business Server konfigurieren.
  
Wenn ein Einwahlanrufer versucht, an einer Besprechung teilzunehmen, platziert der Caa-Dienst (Conference Auto Attendant) den Anrufer in einem Haltestift, der sich vom Wartebereich unterscheidet, &#x2014; wenn ein Referent nicht bereits an einem Anruf teilnimmt und der Einwahlanrufer keine Leiter-PIN eingegeben hat. Mit der PIN-losen Besprechungsteilnahmeoption können Einwahlanrufer an einer Besprechung teilnehmen, ohne eine Leiter-PIN einzugeben, auch wenn sie die erste Person in einem Anruf sind. 
  
Beachten Sie beim Konfigurieren dieses Features Folgendes:
  
- Gilt nur für private Besprechungen.
    
- Ermöglicht PSTN-Anrufern, in privaten Besprechungen zu bleiben, ohne dass authentifizierte Benutzer vorhanden sind.
    
- Nachdem die Einstellung geändert wurde, gilt sie für alle vorhandenen und neuen privaten Besprechungen.
    
- Kann entweder am Standort des Organisators oder auf globaler Ebene aktiviert werden.
    
- Optionen für Personen, die den Wartebereich umgehen können, können für eine der folgenden Optionen festgelegt werden: 
    
  - **Jeder aus meiner Organisation mit Anrufern kommt direkt ein**
    
  - **Jeder (keine Einschränkungen) mit Anrufern wird direkt eingeschaltet** (dies ist die Standardeinstellung.)
    
- Wenn die Konfiguration so konfiguriert ist, dass die PIN-lose Verknüpfung aktiviert ist, fordert der CAA-Dienst weiterhin eine Führungs-PIN an. Benutzer können unabhängig davon, ob eine PIN eingegeben wurde, an der Besprechung teilnehmen. Wenn Sie jedoch die Möglichkeit haben, eine Leiter-PIN einzugeben, kann sich ein Einwahlanrufer als Leiter authentifizieren und die Besprechung bei Bedarf verwalten.
    
## <a name="configure-pin-less-meeting-join"></a>Konfigurieren der PIN-losen Besprechungsteilnahme

Verwenden Sie zum Aktivieren der PIN-losen Besprechungsteilnahme für Ihre Benutzer das Cmdlet ["Set-CsDialInConferencingConfiguration"](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) mit dem Parameter "AllowAnonymousPstnActivation" wie folgt:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Der folgende Befehl aktiviert beispielsweise die PIN-lose Besprechungsteilnahme für den Standort Redmond:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Aus Sicherheitsgründen sollten Sie beim Aktivieren der PIN-losen Besprechungsteilnahme verhindern, dass anonyme Benutzer ausgehende Anrufe ausführen, indem Sie sicherstellen, dass die ConferencingPolicy wie folgt festgelegt ist:
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Weitere Informationen finden Sie unter ["Set-CsConferencingPolicy".](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
