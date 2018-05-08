---
title: Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype for Business 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Zusammenfassung: Informationen Sie zum Überprüfen, veröffentlichen oder verwerfen routing Änderungen VoIP-Konfiguration in Skype für Business Server 2015 mithilfe der Skype für Business Server-Systemsteuerung.'
ms.openlocfilehash: 34da8d44a778d5a469cc7069e0024dd3b43517ab
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business-2015"></a>Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype for Business 2015
 
**Zusammenfassung:** Informationen Sie zum Überprüfen, veröffentlichen oder verwerfen routing Änderungen VoIP-Konfiguration in Skype für Business Server 2015 mithilfe der Skype für Business Server-Systemsteuerung.
  
Wenn Sie Änderungen an den Konfigurationseinstellungen auf den Seiten in der Gruppe **VoIP-Routing** vorgenommen haben, führen Sie zum Überprüfen, Veröffentlichen oder Verwerfen der ausstehenden Änderungen die folgenden Schritte aus.
  
> [!IMPORTANT]
> Stellen Sie sicher, dass jeweils nur ein Benutzer Änderungen an den Konfigurationseinstellungen für das VoIP-Routing vornimmt. 
  
> [!NOTE]
> Alle ausstehenden Änderungen müssen gleichzeitig über den Befehl **Commit für alle Element ausführen** veröffentlicht werden. Es ist nicht möglich, nur ausgewählte ausstehende Änderungen zu veröffentlichen. Führen Sie den Befehl **Noch nicht übernommene Änderungen überprüfen** aus, bevor Sie ausstehende Änderungen veröffentlichen, und verwerfen Sie Konfigurationsänderungen, die nicht veröffentlicht werden sollen.
  
> [!NOTE]
> Wenn Sie die Seiten in der Gruppe **VoIP-Routing** verlassen, bevor Sie für ausstehende Änderungen ein Commit ausführen, gehen alle ausstehenden Änderungen verloren. Sie können die aktuelle Konfiguration (einschließlich ausstehender Änderungen) jedoch in eine VoIP-Konfigurationsdatei exportieren und die aktualisierte Konfiguration anschließend importieren und veröffentlichen. Weitere Informationen hierzu finden Sie unter [Exportieren oder Importieren einer VoIP-routenkonfigurationsdatei in Skype für Business 2015](voice-route-configuration-import-export.md). 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>So überprüfen, veröffentlichen oder verwerfen Sie Konfigurationsänderungen für das VoIP-Routing

1. Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder CsAdministrator beim Computer an.
    
2. Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Nehmen Sie die gewünschten Konfigurationsänderungen an den Einstellungen auf den einzelnen Seiten der Gruppe **VoIP-Routing** vor.
    
5. Wählen Sie im Menü **Commit** die Option **Noch nicht übernommene Änderungen überprüfen** aus, um ausstehende Änderungen zu überprüfen, ohne sie zu veröffentlichen.
    
6. Führen Sie eine der folgenden Aktionen aus, um ausstehende Änderungen zu verwerfen:
    
   - Wählen Sie im Menü **Commit** die Option **Alle noch nicht übernommenen Änderungen verwerfen** aus.
    
   - Wechseln Sie auf der Seite **VoIP-Routing** zur Registerkarte mit ausstehenden Änderungen, die verworfen werden sollen, wählen Sie das Element mit den ausstehenden Änderungen aus, klicken Sie auf **Commit** und klicken Sie dann auf **Ausgewählte Änderungen verwerfen**.
    
7. Nachdem Sie alle ausstehenden Änderungen überprüft und die Änderungen verworfen haben, die nicht veröffentlicht werden sollen, klicken Sie auf **Commit** und dann auf **Commit für alle Element ausführen**.
    
8. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde**, das eine Liste aller ausstehenden Änderungen enthält, auf **OK**. 
    
    Wenn Skype Business Server-Systemsteuerung Änderungen verpflichtet hat, wird die Meldung **VoIP-Routingkonfiguration erfolgreich veröffentlicht** angezeigt.
    

