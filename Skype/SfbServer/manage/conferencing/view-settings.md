---
title: Anzeigen von Konfigurationseinstellungen für Besprechungen in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Zusammenfassung: Informationen zum Anzeigen von besprechungskonfigurationseinstellungen in Skype für Business Server 2015.'
ms.openlocfilehash: 382e50a0f41301953f4313c5019d1eb0d27804e5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Anzeigen von Konfigurationseinstellungen für Besprechungen in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen zum Anzeigen von besprechungskonfigurationseinstellungen in Skype für Business Server 2015.
  
Sie können anzeigen besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Anzeigen von besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung
<a name="BKMK_ViewJoinSettings"> </a>

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.
    
4. Klicken Sie auf der Seite **Besprechungskonfiguration** auf die Besprechungskonfiguration, die Sie anzeigen möchten.
    
5. Aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **Details anzeigen**.
    
    **Bearbeiten Besprechungskonfiguration - \<Richtlinie\> ** die Einstellungen für die ausgewählte Richtlinie wird geöffnet.
    
    Ausführliche Informationen zum Konfigurieren der Einstellungen finden Sie unter [Create besprechungskonfigurationseinstellungen in Skype für Business Server 2015](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Anzeigen von besprechungskonfigurationseinstellungen mithilfe von Skype für Business Server-Verwaltungsshell
<a name="BKMK_ViewJoinSettings"> </a>

Verwenden Sie Das Cmdlet **Get-CsMeetingConfiguration**, um Informationen über sämtliche Besprechungskonfigurationseinstellungen anzuzeigen.
  
```
Get-CsMeetingConfiguration
```

Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:
  
```
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

```

Weitere Informationen sowie eine vollständige Liste der Parameter finden Sie unter [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

