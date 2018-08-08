---
title: Exportieren oder Importieren einer VoIP-routenkonfigurationsdatei in Skype für Unternehmen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Zusammenfassung: Informationen Sie zum Exportieren oder importieren eine Konfigurationsdatei VoIP routing in Skype für Business Server mithilfe der Skype für Business Server-Systemsteuerung.'
ms.openlocfilehash: 462bcf471e4a43bfedf32b0d062731ea7cbd06f9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965408"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exportieren oder Importieren einer VoIP-routenkonfigurationsdatei in Skype für Unternehmen
 
**Zusammenfassung:** Informationen Sie zum Exportieren oder importieren eine Konfigurationsdatei VoIP routing in Skype für Business Server mithilfe der Skype für Business Server-Systemsteuerung.
  
Wenn Sie Ihre VoIP-Routingkonfiguration speichern möchten, ohne sie zu veröffentlichen, führen Sie die folgenden Schritte aus, um eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen. 
  
Wenn Sie eine VoIP-routing Konfigurationsdatei (.vcfg) importieren, aber die VoIP-Routingkonfiguration auf dem Server in der Zwischenzeit Änderungen vorgenommen wurden, werden die Seiten in der Gruppe **VoIP-Routing** in Skype Business Server-Systemsteuerung anzugeben, dass es VoIP-routing ohne Commit geändert wurden. Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.
  
Wenn Sie an den Einstellungen auf eine beliebige Seite innerhalb der Gruppe ohne Commit Änderungen vorgenommen haben, werden die Änderungen in der exportierten VoIP-Konfigurationsdatei (.vcfg) gespeichert. So können Sie VoIP-routing konfigurationsänderungen während mehrerer Sitzungen vor dem Veröffentlichen der Änderungen vornehmen. 
  
### <a name="to-export-a-voice-routing-configuration"></a>So exportieren Sie eine VoIP-Routingkonfiguration

1. Melden Sie sich als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.
    
2. Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie im Menü **Aktionen** auf **Konfiguration exportieren**.
    
5. Geben Sie einen Speicherort und Dateinamen an und klicken Sie auf **Speichern**.
    
### <a name="to-import-a-voice-routing-configuration"></a>So importieren Sie eine VoIP-Routingkonfiguration

1. Melden Sie sich als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.
    
2. Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie im Menü **Aktionen** auf **Konfiguration importieren**.
    
5. Suchen Sie nach der Konfigurationsdatei, die Sie importieren möchten, und klicken Sie dann auf **Öffnen**.
    
6. Klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
    
    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Konfigurationsdatei importieren, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md) in der Betriebsdokumentation.
  

