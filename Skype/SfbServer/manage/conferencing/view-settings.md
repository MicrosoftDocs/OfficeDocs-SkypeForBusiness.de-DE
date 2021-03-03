---
title: Anzeigen von Besprechungskonfigurationseinstellungen in Skype for Business Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Zusammenfassung: Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server anzeigen.'
ms.openlocfilehash: e30543c566775d38e20e2103c4cc0f41278c1020
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827925"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Anzeigen von Besprechungskonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server anzeigen.
  
Sie können die Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell anzeigen.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Anzeigen von Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung
<a name="BKMK_ViewJoinSettings"> </a>

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste **auf "Konferenzen"** und dann auf **"Besprechungskonfiguration".**
    
4. Klicken Sie auf der Seite "Besprechungskonfiguration" auf die Besprechungskonfiguration, die Sie anzeigen möchten. 
    
5. Aktivieren **Sie im Dateifilter** bearbeiten das Kontrollkästchen **Details** anzeigen.
    
    **Besprechungskonfiguration \<policy\> bearbeiten –** wird geöffnet, in dem die Einstellungen für die ausgewählte Richtlinie angezeigt werden.
    
    Weitere Informationen zum Konfigurieren der Einstellungen finden Sie unter ["Erstellen von Besprechungskonfigurationseinstellungen in Skype for Business Server".](create-settings.md)
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Anzeigen von Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell
<a name="BKMK_ViewJoinSettings"> </a>

Verwenden Sie zum Anzeigen von Informationen zu allen Besprechungskonfigurationseinstellungen das **Cmdlet "Get-CsMeetingConfiguration":**
  
```
Get-CsMeetingConfiguration
```

Dieser Befehl gibt Informationen wie die folgenden zurück:
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

Weitere Informationen, einschließlich einer vollständigen Liste der Parameter, finden Sie unter [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

