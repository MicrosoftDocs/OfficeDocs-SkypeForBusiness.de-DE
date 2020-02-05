---
title: Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server mithilfe des Skype for Business Server-Control Panels Änderungen an der sprach Routing-Konfiguration überprüfen, veröffentlichen oder stornieren können.'
ms.openlocfilehash: 12cf80c2a14d3bad532aaf21a942536f44537300
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766958"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Änderungen an der sprach Routingkonfiguration in Skype for Business Server über die Skype for Business Server-Systemsteuerung überprüfen, veröffentlichen oder stornieren können.
  
Wenn Sie Änderungen an den Konfigurationseinstellungen auf den Seiten in der Gruppe **VoIP-Routing** vorgenommen haben, führen Sie zum Überprüfen, Veröffentlichen oder Verwerfen der ausstehenden Änderungen die folgenden Schritte aus.
  
> [!IMPORTANT]
> Stellen Sie sicher, dass jeweils nur ein Benutzer Änderungen an den Konfigurationseinstellungen für das VoIP-Routing vornimmt. 
  
> [!NOTE]
> Alle ausstehenden Änderungen müssen gleichzeitig über den Befehl **Commit für alle Element ausführen** veröffentlicht werden. Es ist nicht möglich, nur ausgewählte ausstehende Änderungen zu veröffentlichen. Führen Sie den Befehl **Noch nicht übernommene Änderungen überprüfen** aus, bevor Sie ausstehende Änderungen veröffentlichen, und verwerfen Sie Konfigurationsänderungen, die nicht veröffentlicht werden sollen.
  
> [!NOTE]
> Wenn Sie die Seiten in der Gruppe **VoIP-Routing** verlassen, bevor Sie für ausstehende Änderungen ein Commit ausführen, gehen alle ausstehenden Änderungen verloren. Sie können die aktuelle Konfiguration (einschließlich ausstehender Änderungen) jedoch in eine VoIP-Konfigurationsdatei exportieren und die aktualisierte Konfiguration anschließend importieren und veröffentlichen. Ausführliche Informationen finden Sie unter [exportieren oder Importieren einer sprach Routen-Konfigurationsdatei in Skype for Business](voice-route-configuration-import-export.md). 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>So überprüfen, veröffentlichen oder verwerfen Sie Konfigurationsänderungen für das VoIP-Routing

1. Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder CsAdministrator beim Computer an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Nehmen Sie die gewünschten Konfigurationsänderungen an den Einstellungen auf den einzelnen Seiten der Gruppe **VoIP-Routing** vor.
    
5. Wählen Sie im Menü **Commit** die Option **Noch nicht übernommene Änderungen überprüfen** aus, um ausstehende Änderungen zu überprüfen, ohne sie zu veröffentlichen.
    
6. Führen Sie eine der folgenden Aktionen aus, um ausstehende Änderungen zu verwerfen:
    
   - Wählen Sie im Menü **Commit** die Option **Alle noch nicht übernommenen Änderungen verwerfen** aus.
    
   - Wechseln Sie auf der Seite **VoIP-Routing** zur Registerkarte mit ausstehenden Änderungen, die verworfen werden sollen, wählen Sie das Element mit den ausstehenden Änderungen aus, klicken Sie auf **Commit** und klicken Sie dann auf **Ausgewählte Änderungen verwerfen**.
    
7. Nachdem Sie alle ausstehenden Änderungen überprüft und die Änderungen verworfen haben, die nicht veröffentlicht werden sollen, klicken Sie auf **Commit** und dann auf **Commit für alle Element ausführen**.
    
8. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde**, das eine Liste aller ausstehenden Änderungen enthält, auf **OK**. 
    
    Wenn die Änderungen von der Skype for Business Server-Systemsteuerung übernommen wurden, wird die Meldung **erfolgreich veröffentlichte sprach Routingkonfiguration** angezeigt.
    

