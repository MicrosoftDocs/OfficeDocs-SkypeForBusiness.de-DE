---
title: Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Zusammenfassung: Erfahren Sie, wie Sie Konfigurationsänderungen für das VoIP-Routing in Skype for Business Server mithilfe der Skype for Business Server Systemsteuerung überprüfen, veröffentlichen oder abbrechen.'
---

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konfigurationsänderungen beim VoIP-Routing in Skype for Business Server mithilfe der Skype for Business Server Systemsteuerung überprüfen, veröffentlichen oder abbrechen.
  
Nachdem Sie Änderungen an den Konfigurationseinstellungen auf Seiten in der **VoIP-Routinggruppe** vorgenommen haben, führen Sie dieses Verfahren aus, um die ausstehenden Änderungen zu überprüfen, zu veröffentlichen oder abzubrechen.
  
> [!IMPORTANT]
> Achten Sie darauf, dass nur jeweils ein Benutzer die Konfigurationseinstellungen für das VoIP-Routing ändert. 
  
> [!NOTE]
> Alle ausstehenden Änderungen müssen gleichzeitig veröffentlicht werden, indem Sie den Befehl **"Commit für alle** " ausführen. Ausstehende Änderungen können nicht selektiv veröffentlicht werden. Führen Sie vor dem Veröffentlichen ausstehender Änderungen den Befehl **"Nicht übernommene Änderungen überprüfen** " aus, und brechen Sie alle Konfigurationsänderungen ab, die Sie nicht veröffentlichen möchten.
  
> [!NOTE]
> Wenn Sie vor dem Commit ausstehender Änderungen von den Seiten in der **VoIP-Routinggruppe** weg navigieren, gehen alle ausstehenden Änderungen verloren. Sie können jedoch die aktuelle Konfiguration (einschließlich ausstehender Änderungen) in eine VoIP-Konfigurationsdatei exportieren und dann die aktualisierte Konfiguration importieren und veröffentlichen. Ausführliche Informationen finden Sie unter [Exportieren oder Importieren einer VoIP-Routenkonfigurationsdatei in Skype for Business](voice-route-configuration-import-export.md). 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>So überprüfen, veröffentlichen oder abbrechen Sie Konfigurationsänderungen beim VoIP-Routing

1. Melden Sie sich am Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Rolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** an.
    
2. Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Nehmen Sie die gewünschten Konfigurationsänderungen an den Einstellungen auf jeder Seite der **VoIP-Routinggruppe** vor.
    
5. Wenn Sie ausstehende Änderungen überprüfen möchten, ohne sie zu veröffentlichen, wählen Sie im Menü **"Commit**" die Option "**Nicht übernommene Änderungen überprüfen**" aus.
    
6. Wenn Sie eine der ausstehenden Änderungen abbrechen möchten, führen Sie eine der folgenden Aktionen aus:
    
   - Wählen Sie im Menü **"Commit****" die Option "Alle nicht übernommenen Änderungen abbrechen**" aus.
    
   - Navigieren Sie zur Registerkarte der Seite " **VoIP-Routing** ", die ausstehende Änderungen enthält, die Sie abbrechen möchten, wählen Sie das Element mit den ausstehenden Änderungen aus, klicken Sie auf **"Commit"** und dann auf " **Abbrechen"**.
    
7. Nachdem Sie alle ausstehenden Änderungen überprüft und alle nicht veröffentlichen möchten, klicken Sie auf **"Commit"** und dann auf **"Commit ausführen"**.
    
8. Klicken Sie im Dialogfeld **"Nicht übernommene VoIP-Konfiguration Einstellungen**", in dem eine Liste aller ausstehenden Änderungen angezeigt wird, auf **"OK**". 
    
    Wenn Skype for Business Server Systemsteuerung die Änderungen vorgenommen hat, wird die Meldung "**VoIP-Routingkonfiguration erfolgreich veröffentlicht**" angezeigt.
    

