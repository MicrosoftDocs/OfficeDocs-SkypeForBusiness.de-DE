---
title: Exportieren oder Importieren einer Konfigurationsdatei für eine Voiceroute in Skype for Business
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
description: 'Zusammenfassung: Informationen zum Exportieren oder Importieren einer Konfigurationsdatei für das Voicerouting in Skype for Business Server mithilfe der Skype for Business Server-Systemsteuerung.'
ms.openlocfilehash: df5ca58ebc7b92fea5236b957f4819ed3602d896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830355"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exportieren oder Importieren einer Konfigurationsdatei für eine Voiceroute in Skype for Business
 
**Zusammenfassung:** Erfahren Sie, wie Sie eine Konfigurationsdatei für das Voicerouting mithilfe der Skype for Business Server-Systemsteuerung in Skype for Business Server exportieren oder importieren.
  
Wenn Sie Ihre Konfiguration für das Voicerouting speichern möchten, ohne sie zu veröffentlichen, führen Sie die folgenden Schritte aus, um eine Momentaufnahme Ihrer Voiceroutingkonfiguration zu speichern und abzurufen. 
  
Wenn Sie eine Konfigurationsdatei für das Voicerouting (VCFG) importieren, aber in der Zwischenzeit Änderungen  an der Konfiguration des Voiceroutings auf dem Server vorgenommen wurden, wird auf den Seiten in der Voiceroutinggruppe in der Skype for Business Server-Systemsteuerung angezeigt, dass noch keine Änderungen am Voicerouting vorgenommen wurden. Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.
  
Wenn Sie noch nicht vorgenommene Änderungen an den Einstellungen auf einer beliebigen Seite innerhalb der Gruppe vorgenommen haben, werden die Änderungen in der exportierten Sprachkonfigurationsdatei (VCFG) gespeichert. Auf diese Weise können Sie Änderungen an der Konfiguration des Voiceroutings während mehrerer Sitzungen vornehmen, bevor Sie die Änderungen veröffentlichen. 
  
### <a name="to-export-a-voice-routing-configuration"></a>So exportieren Sie eine VoIP-Routingkonfiguration

1. Melden Sie sich am Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Rolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie im Menü **Aktionen** auf **Konfiguration exportieren**.
    
5. Geben Sie einen Speicherort und Dateinamen an, und klicken Sie auf **Speichern**.
    
### <a name="to-import-a-voice-routing-configuration"></a>So importieren Sie eine VoIP-Routingkonfiguration

1. Melden Sie sich am Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Rolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie im Menü **Aktionen** auf **Konfiguration importieren**.
    
5. Suchen Sie nach der Konfigurationsdatei, die Sie importieren möchten, und klicken Sie dann auf **Öffnen**.
    
6. Klicken Sie auf **Commit** und anschließend auf **Commit für alle**.
    
    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Konfigurationsdatei importieren, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.
  

