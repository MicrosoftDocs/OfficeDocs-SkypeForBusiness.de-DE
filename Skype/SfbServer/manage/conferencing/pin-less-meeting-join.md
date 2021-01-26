---
title: Konfigurieren der PIN-igen Besprechungssitzung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Option zum Beitreten zu Besprechungen ohne PIN in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 794bf13d92857a18254f903a1c5dcca98d0a1ec0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827985"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Konfigurieren der PIN-igen Besprechungssitzung in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Option zum Beitreten zu Besprechungen ohne PIN in Skype for Business Server konfigurieren.
  
Wenn ein Einwahlanrufer versucht, an einer Besprechung teil zu nehmen, platziert der Konferenz-automatische Telefonzentrale-Dienst (Conference automatische Telefonzentrale, CAA) den Anrufer in einem Haltestift, der sich von der Lobby &#x2014; unterscheiden, wenn ein Sprechleiter noch nicht an einem Anruf teilhabt und der Einwahlanrufer keine Leiter-PIN eingegeben hat. Die Pin-los-Option für den Besprechungsteiltritt ermöglicht Einwahlanrufern die Teilnahme an einer Besprechung ohne Eingabe einer Leiter-PIN, auch wenn sie die erste Person eines Anrufs sind. 
  
Beachten Sie beim Konfigurieren dieses Features Folgendes:
  
- Gilt nur für private Besprechungen.
    
- Ermöglicht PSTN-Anrufern, in privaten Besprechungen ohne anwesenheitsauthentierte Benutzer zu bleiben.
    
- Nachdem die Einstellung geändert wurde, gilt sie für alle vorhandenen und neuen privaten Besprechungen.
    
- Kann entweder am Standort des Organisators oder auf globaler Ebene aktiviert werden.
    
- Optionen für personen, die die Lobby umgehen können, können für eine der folgenden Optionen festgelegt werden: 
    
  - **Jeder aus meiner Organisation mit Anrufern kommt direkt an**
    
  - **Jeder (keine Einschränkungen) mit Anrufern wird direkt ein -** dies ist die Standardeinstellung.)
    
- Wenn die Konfiguration zum Aktivieren der PIN-entigen Verknüpfung konfiguriert ist, fordert der Zertifizierungsstellendienst weiterhin eine Führungs führungs führungs-PIN an. Benutzer können unabhängig davon, ob eine PIN eingegeben wurde, an der Besprechung teilnehmen. Durch die Beibehaltung der Möglichkeit zur Eingabe einer Leiter-PIN kann sich ein Einwahlanrufer jedoch bei Bedarf als Leiter authentifizieren und die Besprechung verwalten.
    
## <a name="configure-pin-less-meeting-join"></a>Konfigurieren der PIN-igen Besprechungssitzung

Verwenden Sie das Cmdlet ["Set-CsDialInConferencingConfiguration"](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) mit dem Parameter "AllowAnonymousPstnActivation" wie folgt, um die Pin-n-ige Besprechungssitzung für Ihre Benutzer zu aktivieren:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Der folgende Befehl aktiviert z. B. den PIN-igen Besprechungs beitritt für den Standort "Redmond":
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Aus Sicherheitsgründen können Sie beim Einwählen anonymer Benutzer bei aktivierter BESPRECHUNG ohne PIN das Herauswählen durch anonyme Benutzer einschränken, indem Sie sicherstellen, dass die Konferenzpolicy wie folgt festgelegt ist:
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Weitere Informationen finden Sie unter [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

