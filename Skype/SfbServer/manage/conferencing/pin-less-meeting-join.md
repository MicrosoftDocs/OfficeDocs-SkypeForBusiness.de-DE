---
title: Konfigurieren der PIN-nen besprechungsleeren Teilnahme an Skype for Business Server
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Pin-n-nen Besprechungs-Join-Option in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 76a2fb401c684e0eb685b733cb1b0a63ecbd9907
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119394"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Konfigurieren der PIN-nen besprechungsleeren Teilnahme an Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Option pin-n-niger Besprechungs beitreten in Skype for Business Server konfigurieren.
  
Wenn ein Einwahlanrufer versucht, an einer Besprechung teil zu nehmen, platziert der Konferenz-automatische Telefonzentrale(CAA)-Dienst den Anrufer in einem Haltestift, der sich von der Lobby &#x2014; wenn ein Sprecher noch nicht an einem Anruf teilhabt und der Einwahlanrufer keine Führungs-PIN eingegeben hat. Mit der OPTION PIN-loser Besprechungs beitreten können Einwahlanrufer an einer Besprechung teilnehmen, ohne eine Führungs-PIN ein eingeben zu müssen, auch wenn sie die erste Person bei einem Anruf sind. 
  
Beachten Sie beim Konfigurieren dieses Features Folgendes:
  
- Gilt nur für private Besprechungen.
    
- Ermöglicht PSTN-Anrufern, in privaten Besprechungen ohne anwesenheit authentifizierte Benutzer zu bleiben.
    
- Nachdem die Einstellung geändert wurde, gilt sie für alle vorhandenen und neuen privaten Besprechungen.
    
- Kann entweder auf der Website des Organisators oder auf globaler Ebene aktiviert werden.
    
- Optionen für die Personen, die die Lobby umgehen können, können für eine der folgenden Optionen festgelegt werden: 
    
  - **Jeder aus meiner Organisation mit Anrufern kommt direkt an**
    
  - **Jeder (keine Einschränkungen) mit Anrufern wird direkt angezeigt** (Dies ist die Standardeinstellung).)
    
- Wenn der DIENST für die Aktivierung der PIN-en-nen Teilnahme konfiguriert ist, fordert er weiterhin eine Führungs-PIN an. Benutzer können an der Besprechung teilnehmen, unabhängig davon, ob eine PIN eingegeben wurde. Durch die Beibehaltung der Möglichkeit, eine Führungs-PIN ein eingeben zu können, kann sich ein Einwahlanrufer jedoch bei Bedarf als Führungsspitze authentifizieren und die Besprechung verwalten.
    
## <a name="configure-pin-less-meeting-join"></a>Konfigurieren des PIN-entigen Besprechungs-Joins

Verwenden Sie das [Cmdlet Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) mit dem Parameter AllowAnonymousPstnActivation, um den PIN-loser Besprechungs beitritt für Ihre Benutzer zu aktivieren:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Mit dem folgenden Befehl wird z. B. die PIN-ige Besprechungssitzung für den Standort "Redmond" aktiviert:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Aus Sicherheitsgründen können Sie bei aktivierter PIN-weniger Besprechungssitzung das Einwählen anonymer Benutzer einschränken, indem Sie sicherstellen, dass conferencingPolicy wie folgt festgelegt ist:
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Weitere Informationen finden Sie unter [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
