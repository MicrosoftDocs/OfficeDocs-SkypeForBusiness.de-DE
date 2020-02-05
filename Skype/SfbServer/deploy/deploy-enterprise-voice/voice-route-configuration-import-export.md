---
title: Exportieren oder Importieren einer sprach Routen-Konfigurationsdatei in Skype for Business
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server mithilfe des Skype for Business Server-Control Panels eine sprach Routing-Konfigurationsdatei exportieren oder importieren.'
ms.openlocfilehash: b980aa26f4d67cd1697ec17286e6af7d9e657e15
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766878"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exportieren oder Importieren einer sprach Routen-Konfigurationsdatei in Skype for Business
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie mithilfe des Skype for Business Server-Control Panels eine sprach Routing-Konfigurationsdatei in Skype for Business Server exportieren oder importieren.
  
Wenn Sie Ihre VoIP-Routingkonfiguration speichern möchten, ohne sie zu veröffentlichen, führen Sie die folgenden Schritte aus, um eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen. 
  
Wenn Sie eine sprach Routing-Konfigurationsdatei (. vcfg) importieren, aber in der Zwischenzeit Änderungen an der sprach Routingkonfiguration auf dem Server vorgenommen wurden, zeigen die Seiten in der Gruppe **VoIP-Routing** in der Skype for Business Server-Systemsteuerung an, dass es nicht festgeschriebene Änderungen an der sprach Weiterleitung gibt. Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.
  
Wenn Sie Änderungen an den Einstellungen auf einer beliebigen Seite innerhalb der Gruppe vorgenommen haben, werden die Änderungen in der exportierten sprach Konfigurationsdatei (vcfg) gespeichert. So können Sie während mehrerer Sitzungen Änderungen an der sprach Routingkonfiguration vornehmen, bevor Sie die Änderungen veröffentlichen. 
  
### <a name="to-export-a-voice-routing-configuration"></a>So exportieren Sie eine VoIP-Routingkonfiguration

1. Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie im Menü **Aktionen** auf **Konfiguration exportieren**.
    
5. Geben Sie einen Speicherort und Dateinamen an und klicken Sie auf **Speichern**.
    
### <a name="to-import-a-voice-routing-configuration"></a>So importieren Sie eine VoIP-Routingkonfiguration

1. Melden Sie sich als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.
    
2. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.
    
4. Klicken Sie im Menü **Aktionen** auf **Konfiguration importieren**.
    
5. Suchen Sie nach der Konfigurationsdatei, die Sie importieren möchten, und klicken Sie dann auf **Öffnen**.
    
6. Klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
    
    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Konfigurationsdatei importieren, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.
  

