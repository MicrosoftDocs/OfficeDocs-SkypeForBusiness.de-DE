---
title: Ändern von Konferenzrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server ändern.'
ms.openlocfilehash: 9cfb13436a01439a8d5ea152ca1d8ac543bc0e88
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991810"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Ändern von Konferenzrichtlinien in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Konferenzrichtlinien in Skype for Business Server ändern.
  
Sie können Konferenzrichtlinien über die Skype for Business Server-Systemsteuerung oder über die Skype for Business Server-Verwaltungsshell ändern.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Ändern von Konferenzrichtlinien mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie auf der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Konferenzrichtlinie**.
    
4. Klicken Sie in der Liste mit den Konferenzrichtlinien auf die Richtlinie, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.
    
5. Ändern Sie im Abschnitt **Konferenzrichtlinie bearbeiten** eine beliebige der Richtlinieneinstellungen. Hiervon ausgenommen ist der Richtlinienname, dieser kann nicht geändert werden.
    
6. Klicken Sie auf **Commit ausführen**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Ändern von Konferenzrichtlinien mithilfe der Skype for Business Server-Verwaltungsshell

Wenn Sie Konferenzrichtlinien ändern möchten, verwenden Sie das Cmdlet " **Satz-CsConferencingPolicy** ".
  
Im folgenden Beispiel wird ein Eigenschaftswert der Konferenzrichtlinien-SalesConferencingPolicy geändert. Mit dem Befehl wird der Wert der AllowConferenceRecording-Eigenschaft auf false festgelegt:
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Weitere Informationen, einschließlich der vollständigen Syntax und einer Liste von Parametern, finden Sie unter [CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

