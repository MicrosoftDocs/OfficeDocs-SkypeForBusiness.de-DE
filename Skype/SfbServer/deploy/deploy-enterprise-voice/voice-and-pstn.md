---
title: Konfigurieren von VoIP-Richtlinien, PSTN-Nutzungsdaten Sätzen und VoIP-Routen in Skype for Business
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
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie VoIP-Richtlinien, PSTN-Nutzungsdatensätze und VoIP-Routen in Skype for Business Server konfigurieren.'
ms.openlocfilehash: faeb3b0eedead117f36b48e69e000350b4a04710
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766898"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>Konfigurieren von VoIP-Richtlinien, PSTN-Nutzungsdaten Sätzen und VoIP-Routen in Skype for Business
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie VoIP-Richtlinien, PSTN-Nutzungsdatensätze und VoIP-Routen in Skype for Business Server konfigurieren.
  
VoIP-Richtlinien, PSTN-Verwendungsdatensätze und VoIP-Routen stehen in enger Beziehung zueinander. Zur Konfiguration von VoIP-Richtlinien wird eine Reihe von Anruffunktionen ausgewählt. Anschließend wird die Richtlinie einem Satz von PSTN-Verwendungsdatensätzen zugewiesen, in denen die Rechte für die Benutzer oder Gruppen festgelegt sind, denen die VoIP-Richtlinie zugewiesen wird. Auch VoIP-Routen werden PSTN-Verwendungsdatensätze zugewiesen, um Routen und die für ihre Verwendung autorisierten Benutzer einander zuzuordnen. Benutzer können also nur Anrufe über Routen tätigen, für die sie passende PSTN-Verwendungsdatensätze besitzen.
  
Der empfohlene Workflow für eine neue Enterprise-VoIP-Bereitstellung besteht darin, zunächst eine VoIP-Richtlinie mit den geeigneten PSTN-Verwendungsdatensätzen zu konfigurieren und anschließend den einzelnen PSTN-Verwendungsdatensätzen die entsprechenden Routen zuzuordnen. 
  
> [!NOTE]
> Sie können auch VoIP-Richtlinien mit dem *Benutzer* Bereich erstellen und diese einzelnen Benutzern oder Gruppen zuweisen.
  
Die einzelnen Schritte zur Durchführung dieser Aufgaben finden Sie in den Verfahren in diesem Abschnitt.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)
    
- [Konfigurieren der Voicemail-escapefunktion in Skype for Business](configure-voice-mail-escape.md)
    
- [Anzeigen von PSTN-Nutzungsdaten Sätzen in Skype for Business](view-pstn-usage-records.md)
    
- [Erstellen oder Ändern einer VoIP-Route in Skype for Business](create-or-modify-a-voice-route.md)
    
- [Exportieren oder Importieren einer sprach Routen-Konfigurationsdatei in Skype for Business](voice-route-configuration-import-export.md)
    
- [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md)
    

