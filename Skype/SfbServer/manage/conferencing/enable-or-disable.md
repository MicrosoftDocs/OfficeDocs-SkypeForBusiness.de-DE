---
title: Aktivieren oder Deaktivieren von Einwahlkonferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Systemsteuerung oder die Verwaltungsshell verwenden, um Einwahlkonferenzen in Skype for Business Server zu aktivieren oder zu deaktivieren.'
ms.openlocfilehash: 8ce0fcfb4f785397075aa9d7b89b94eacb096167
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818556"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren von Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Systemsteuerung oder die Verwaltungsshell verwenden können, um Einwahlkonferenzen in Skype for Business Server zu aktivieren oder zu deaktivieren.
  
Sie können Einwahlkonferenzen über die Skype for Business Server-Systemsteuerung oder über die Skype for Business Server-Verwaltungsshell aktivieren.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Aktivieren oder Deaktivieren von Einwahlkonferenzen mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.
    
4. Wählen Sie in der Liste der Konferenzrichtlinien die Richtlinie aus, für die Sie Einwahlkonferenzen zulassen möchten, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**. 
    
5. Wenn Sie Benutzern erlauben möchten, per Einwahl an einer Besprechung teilzunehmen, aktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.
    
6. Klicken Sie auf **Commit ausführen**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Aktivieren oder Deaktivieren von Einwahlkonferenzen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zur Aktivierung oder Deaktivierung von Einwahlkonferenzen das Cmdlet **Set-CsConferencingPolicy** mit den EnableDialInConferencing-Parametern wie folgt:
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Weitere Informationen finden Sie unter [Satz-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

