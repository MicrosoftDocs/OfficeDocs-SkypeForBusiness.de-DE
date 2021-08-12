---
title: Exportieren oder Importieren einer VoIP-Routenkonfigurationsdatei in Skype for Business
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine VoIP-Routing-Konfigurationsdatei in Skype for Business Server mithilfe der Skype for Business Server Systemsteuerung exportieren oder importieren.'
ms.openlocfilehash: bef3e1caf80ecc2dc065949dcec684ad6e342902cfabf0e9daebab237d09c7ca
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320817"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exportieren oder Importieren einer VoIP-Routenkonfigurationsdatei in Skype for Business
 
**Zusammenfassung:** Erfahren Sie, wie Sie eine VoIP-Routing-Konfigurationsdatei in Skype for Business Server mithilfe der Skype for Business Server Systemsteuerung exportieren oder importieren.
  
Wenn Sie Ihre VoIP-Routingkonfiguration speichern möchten, ohne sie zu veröffentlichen, führen Sie die folgenden Schritte aus, um eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen. 
  
Wenn Sie eine VoIP-Routingkonfigurationsdatei (VCFG) importieren, aber in der Zwischenzeit Änderungen an der VoIP-Routingkonfiguration auf dem Server vorgenommen wurden, weisen die Seiten in der **VoIP-Routinggruppe** in Skype for Business Server Systemsteuerung darauf hin, dass keine Änderungen am VoIP-Routing vorgenommen wurden. Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.
  
Wenn Sie nicht übernommene Änderungen an den Einstellungen auf einer beliebigen Seite innerhalb der Gruppe vorgenommen haben, werden die Änderungen in der exportierten VoIP-Konfigurationsdatei (VCFG) gespeichert. Auf diese Weise können Sie während mehrerer Sitzungen Änderungen an der VoIP-Routingkonfiguration vornehmen, bevor Sie die Änderungen veröffentlichen. 
  
### <a name="to-export-a-voice-routing-configuration"></a>So exportieren Sie eine VoIP-Routingkonfiguration

1. Melden Sie sich am Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Rolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** an.
    
2. Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie im Menü **Aktionen** auf **Konfiguration exportieren**.
    
5. Geben Sie einen Speicherort und Dateinamen an, und klicken Sie auf **Speichern**.
    
### <a name="to-import-a-voice-routing-configuration"></a>So importieren Sie eine VoIP-Routingkonfiguration

1. Melden Sie sich am Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Rolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** an.
    
2. Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie im Menü **Aktionen** auf **Konfiguration importieren**.
    
5. Suchen Sie nach der Konfigurationsdatei, die Sie importieren möchten, und klicken Sie dann auf **Öffnen**.
    
6. Klicken Sie auf **Commit** und anschließend auf **Commit für alle**.
    
    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Konfigurationsdatei importieren, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.
  

