---
title: Aktivieren oder Deaktivieren von einwahlkonferenzen in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Zusammenfassung: Erfahren Sie, wie Systemsteuerung oder -Verwaltungsshell zum Aktivieren oder Deaktivieren von einwahlkonferenzen in Skype für Business Server verwenden.'
ms.openlocfilehash: 1392c67e2b432a6acc9bca805367083d311fd7d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919801"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren von einwahlkonferenzen in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zur Verwendung der Systemsteuerung oder -Verwaltungsshell zum Aktivieren oder Deaktivieren von einwahlkonferenzen in Skype für Business Server.
  
Sie können einwahlkonferenzen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell aktivieren.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Aktivieren oder Deaktivieren von einwahlkonferenzen mithilfe von Skype Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.
    
4. Wählen Sie in der Liste der Konferenzrichtlinien die Richtlinie aus, für die Sie Einwahlkonferenzen zulassen möchten, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**. 
    
5. Wenn Sie Benutzern erlauben möchten, per Einwahl an einer Besprechung teilzunehmen, aktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.
    
6. Klicken Sie auf **Commit ausführen**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Aktivieren oder Deaktivieren von einwahlkonferenzen mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie zur Aktivierung oder Deaktivierung von Einwahlkonferenzen das Cmdlet **Set-CsConferencingPolicy** mit den EnableDialInConferencing-Parametern wie folgt:
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Weitere Informationen finden Sie unter [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

