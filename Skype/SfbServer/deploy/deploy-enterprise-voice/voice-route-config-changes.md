---
title: Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Zusammenfassung: Informationen zum Überprüfen, Veröffentlichen oder Abbrechen von Konfigurationsänderungen für das Voicerouting in Skype for Business Server mithilfe der Skype for Business Server-Systemsteuerung.'
ms.openlocfilehash: 6b75b6a1135cf9abde9551112fc9c29579862a8b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830395"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konfigurationsänderungen für das Voicerouting in Skype for Business Server mithilfe der Skype for Business Server-Systemsteuerung überprüfen, veröffentlichen oder abbrechen.
  
Nachdem Sie eine der Konfigurationseinstellungen auf Seiten in der Gruppe **"Voicerouting"** geändert haben, führen Sie dieses Verfahren aus, um die ausstehenden Änderungen zu überprüfen, zu veröffentlichen oder abbricht.
  
> [!IMPORTANT]
> Stellen Sie sicher, dass nur ein Benutzer gleichzeitig die Konfigurationseinstellungen für das Voicerouting ändert. 
  
> [!NOTE]
> Alle ausstehenden Änderungen müssen gleichzeitig durch Ausführen des Befehls "Commit für **alle" veröffentlicht** werden. Ausstehende Änderungen können nicht selektiv veröffentlicht werden. Führen Sie vor dem Veröffentlichen  ausstehender Änderungen den Befehl "Noch nicht abgeschlossene Änderungen überprüfen" aus, und brechen Sie alle Konfigurationsänderungen ab, die Sie nicht veröffentlichen möchten.
  
> [!NOTE]
> Wenn Sie vor dem Commit ausstehender Änderungen von den Seiten in der Gruppe **"Voicerouting"** weg navigieren, gehen alle ausstehenden Änderungen verloren. Sie können jedoch die aktuelle Konfiguration (einschließlich ausstehender Änderungen) in eine Sprachkonfigurationsdatei exportieren und dann die aktualisierte Konfiguration importieren und veröffentlichen. Weitere Informationen finden Sie unter [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md). 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>So überprüfen, veröffentlichen oder brechen Sie Konfigurationsänderungen für das Voicerouting ab

1. Melden Sie sich am Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Rolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Nehmen Sie die Konfigurationsänderungen an den Einstellungen  auf jeder Seite der Voiceroutinggruppe vor.
    
5. Um ausstehende Änderungen zu überprüfen, ohne sie zu veröffentlichen, wählen Sie **im** Menü "Commit" die Option "Noch nicht abgeschlossene **Änderungen überprüfen"** aus.
    
6. Wenn Sie eine der ausstehenden Änderungen abbrechen möchten, gehen Sie wie folgt vor:
    
   - Select **Cancel all uncommitted changes** from the **Commit** menu.
    
   - Navigieren Sie zur  Registerkarte der Seite "Voicerouting", die ausstehende Änderungen enthält, die Sie abbrechen möchten, wählen Sie das Element mit den ausstehenden Änderungen aus, klicken Sie auf **"Commit"** und dann auf "Ausgewählte Änderungen **abbrechen".**
    
7. Nachdem Sie alle ausstehenden Änderungen überprüft und alle, die Sie nicht veröffentlichen möchten, abgebrochen haben, klicken Sie auf **Commit,** und klicken Sie dann auf **Commit für alle**.
    
8. Klicken Sie **im Dialogfeld "Nicht** abgeschlossene Sprachkonfigurationseinstellungen", in dem eine Liste aller ausstehenden Änderungen angezeigt wird, auf **OK**. 
    
    Wenn die Änderungen von der Skype for Business Server-Systemsteuerung vorgenommen wurden, wird die Erfolgreich veröffentlichte Konfigurationsmeldung für das **Sprachrouting** angezeigt.
    

