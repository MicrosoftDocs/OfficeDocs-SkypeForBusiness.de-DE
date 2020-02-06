---
title: Anzeigen der Konfigurationseinstellungen für Besprechungen in Skype for Business Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Einstellungen für die besprechungskonfiguration in Skype for Business Server anzeigen können.'
ms.openlocfilehash: 858d1a3d786cb9fe3c6b33daaca8667cab2390f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818456"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Anzeigen der Konfigurationseinstellungen für Besprechungen in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie die Konfigurationseinstellungen für Besprechungen in Skype for Business Server anzeigen können.
  
Sie können die Einstellungen für die besprechungskonfiguration über die Skype for Business Server-Systemsteuerung oder über die Skype for Business Server-Verwaltungsshell anzeigen.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Anzeigen von Einstellungen für die besprechungskonfiguration mithilfe der Skype for Business Server-Systemsteuerung
<a name="BKMK_ViewJoinSettings"> </a>

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.
    
4. Klicken Sie auf der Seite **Besprechungskonfiguration** auf die Besprechungskonfiguration, die Sie anzeigen möchten.
    
5. Aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **Details anzeigen**.
    
    **Besprechungskonfiguration bearbeiten – \<die\> Richtlinie** wird geöffnet und zeigt die Einstellungen für die ausgewählte Richtlinie an.
    
    Details zum Konfigurieren der Einstellungen finden Sie unter [Erstellen von Besprechungs Konfigurationseinstellungen in Skype for Business Server](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Anzeigen von Einstellungen für die besprechungskonfiguration mithilfe der Skype for Business Server-Verwaltungsshell
<a name="BKMK_ViewJoinSettings"> </a>

Verwenden Sie Das Cmdlet **Get-CsMeetingConfiguration**, um Informationen über sämtliche Besprechungskonfigurationseinstellungen anzuzeigen.
  
```
Get-CsMeetingConfiguration
```

Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:
  
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

Weitere Informationen einschließlich einer vollständigen Liste der Parameter finden Sie unter [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

