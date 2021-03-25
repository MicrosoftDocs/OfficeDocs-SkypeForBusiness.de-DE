---
title: Aktivieren oder Deaktivieren von Einwahlkonferenzen in Skype for Business Server
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Zusammenfassung: Informationen zur Verwendung der Systemsteuerung oder Verwaltungsshell zum Aktivieren oder Deaktivieren von Einwahlkonferenzen in Skype for Business Server.'
ms.openlocfilehash: ade7753f480856d68535daadda40eac6296a5d6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119464"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Aktivieren oder Deaktivieren von Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Systemsteuerung oder Verwaltungsshell verwenden, um Einwahlkonferenzen in Skype for Business Server zu aktivieren oder zu deaktivieren.
  
Sie können Einwahlkonferenzen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell aktivieren.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Aktivieren oder Deaktivieren von Einwahlkonferenzen mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste **auf** Konferenzen und dann auf **Konferenzrichtlinie**.
    
4. Wählen Sie in der Liste der Konferenzrichtlinien die Richtlinie aus, für die Sie Einwahlkonferenzen zulassen möchten, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**. 
    
5. Wenn Sie Benutzern erlauben möchten, per Einwahl an einer Besprechung teilzunehmen, aktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.
    
6. Klicken Sie auf **Commit ausführen**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Aktivieren oder Deaktivieren von Einwahlkonferenzen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Aktivieren oder Deaktivieren von Einwahlkonferenzen das **Cmdlet Set-CsConferencingPolicy** mit dem Parameter EnableDialInConferencing wie folgt:
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Weitere Informationen finden Sie unter [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
