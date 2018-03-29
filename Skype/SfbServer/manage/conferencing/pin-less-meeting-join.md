---
title: Konfigurieren der PIN-losen Besprechungsanmeldung in Skype for Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Zusammenfassung: Informationen zum Konfigurieren des PIN-kleiner meeting Verknüpfungsoption in Skype für Business Server 2015.'
ms.openlocfilehash: 6e9e26f856fec85b3f7436684d1b084eb3873ba9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Konfigurieren der PIN-losen Besprechungsanmeldung in Skype for Business Server
 
**Zusammenfassung:** Informationen zum Konfigurieren des PIN-kleiner meeting Verknüpfungsoption in Skype für Business Server 2015.
  
Wenn ein Anrufer einwählen versucht, an einer Besprechung teilnehmen, platziert (Conference Auto Attendant, CAA)-Dienst den Anrufer in einen Stift Betrieb, der sich aus dem Wartebereich & #x 2014 unterscheidet. Wenn Referent noch nicht auf einen Anruf ist, und der Zugriffsnummer für Einwahl Anrufer eine PIN in leitender Position nicht eingegeben hat. Die PIN-lose Besprechungsanmeldeoption ermöglicht Einwahl-Anrufern die Teilnahme an einer Besprechung ohne Eingabe einer Leiter-PIN sogar dann, wenn sie nicht als Erste zugeschaltet werden. 
  
Beachten Sie Folgendes, wenn Sie diese Funktion konfigurieren:
  
- Gilt nur für private Besprechungen.
    
- PSTN-Anrufer können in privaten Besprechungen verbleiben, ohne dass authentifizierte Nutzer anwesend sind.
    
- Nach der Änderung der Einstellung gilt sie für alle existierenden und neuen privaten Besprechungen.
    
- Kann entweder am Standort des Organisators oder auf globaler Ebene aktiviert werden.
    
- Optionen dafür, wer die Lobby umgehen kann, können für jeden der folgenden Fälle eingestellt werden: 
    
  - **„Jeder innerhalb meiner Organisation“ mit „Anrufer erhalten direkten Zugang“**
    
  - **„Alle Personen (keine Einschränkungen)“ mit „Anrufer erhalten direkten Zugang“**. (Das ist die Standardeinstellung.)
    
- Wenn die Konfiguration die PIN-lose Anmeldung vorsieht, fordert der CAA-Dienst trotzdem zur Eingabe einer Leiter-PIN auf. Nutzer können mit oder ohne Eingabe einer PIN an der Besprechung teilnehmen. Die Möglichkeit, geben Sie eine PIN in leitender Position beibehalten kann jedoch einen Anrufer einwählen, zur Authentifizierung als Leiter und Verwalten der Besprechung bei Bedarf.
    
## <a name="configure-pin-less-meeting-join"></a>Konfigurieren der PIN-losen Besprechungsanmeldung

Um PIN weniger Besprechungsteilnahme für Ihre Benutzer zu aktivieren, verwenden Sie das Cmdlet " [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) " wie folgt mit dem Parameter AllowAnonymousPstnActivation aus:
  
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

Weitere Informationen finden Sie unter [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

