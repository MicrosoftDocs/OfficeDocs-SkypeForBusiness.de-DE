---
title: Aktivieren oder Deaktivieren von Einwahlkonferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Systemsteuerung oder Die Verwaltungsshell verwenden, um Einwahlkonferenzen in Skype for Business Server zu aktivieren oder zu deaktivieren.'
ms.openlocfilehash: 84a07645489ad71af9b71ce9f8d8328490ee6df4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850008"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren von Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie mithilfe der Systemsteuerung oder Der Verwaltungsshell Einwahlkonferenzen in Skype for Business Server aktivieren oder deaktivieren.
  
Sie können Einwahlkonferenzen mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell aktivieren.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Aktivieren oder Deaktivieren von Einwahlkonferenzen mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **"Konferenzen"** und dann auf **"Konferenzrichtlinie".**
    
4. Wählen Sie in der Liste der Konferenzrichtlinien die Richtlinie aus, für die Sie Einwahlkonferenzen zulassen möchten, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**. 
    
5. Wenn Sie Benutzern erlauben möchten, per Einwahl an einer Besprechung teilzunehmen, aktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.
    
6. Klicken Sie auf **Commit ausführen**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Aktivieren oder Deaktivieren von Einwahlkonferenzen mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie zum Aktivieren oder Deaktivieren von Einwahlkonferenzen das Cmdlet **"Set-CsConferencingPolicy"** mit dem Parameter "EnableDialInConferencing" wie folgt:
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Weitere Informationen finden Sie unter ["Set-CsConferencingPolicy".](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
