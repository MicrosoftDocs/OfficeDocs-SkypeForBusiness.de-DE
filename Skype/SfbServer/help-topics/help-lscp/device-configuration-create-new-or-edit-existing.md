---
title: Gerätekonfiguration Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: Klicken Sie auf der Seite neue Gerätekonfiguration oder Gerätekonfiguration bearbeiten können Sie erstellen oder Ändern einer Auflistung von Einstellungen zum Verwalten von Skype für Business Phone Edition verwendet. Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und die Festlegung, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.
ms.openlocfilehash: ed1f002cd0d8c0465a765c04c3efb4367c6f99fb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880742"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration
 
Klicken Sie auf der Seite **Neue Gerätekonfiguration** oder **Gerätekonfiguration bearbeiten** können Sie erstellen oder Ändern einer Auflistung von Einstellungen zum Verwalten von Skype für Business Phone Edition verwendet. Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und die Festlegung, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.
  
## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Gerätekonfiguration** bzw. **Gerätekonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:
  
- Hinzufügen einer neuen Gerätekonfiguration
    
- Ändern der Eigenschaften einer vorhandenen Gerätekonfiguration
    
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.
  
- **Bereich** Gibt den Bereich (Global oder Standort) der Gerätekonfiguration.
    
- **Name** Sie können hinzufügen oder ändern Sie den Namen der Gerätekonfiguration.
    
- **SIP-Sicherheit** Sie können übertragungs- und authentifizierungsanforderungen für Skype für Business Phone Edition-Geräte konfigurieren. Folgende Optionen stehen zur Verfügung:
    
  - **Niedrig** Jede Art von Autorisierung- oder Transporttypen zulassen.
    
  - **Mittel** NTLM oder Kerberos ist erforderlich für die Benutzerauthentifizierung.
    
  - **Hohe** Erforderlich für die Benutzerauthentifizierung ist NTLM oder Kerberos und TLS für SIP-Verbindungen erforderlich ist.
    
- **Protokollierungsstufe** Sie können die Protokollierung für die UC-Gerät aktivieren. Gültige Werte sind: „Aus“, „Niedrig“, „Mittel“ und „Hoch“. Der Standardwert lautet „Aus“.
    
- **VoIP-Dienstqualität (QoS)** Sie können VoIP-Datenverkehr von einem Skype für Business Phone Edition-Gerät ausgehen zugewiesenen DSCP-Wert angeben. Der Standardwert lautet 40. 40 ist jedoch nicht den Wert in der Regel für audio-Datenverkehr verwendet. Stattdessen wird audio-Datenverkehr durch den Code DSCP 46 fast immer markiert. Um die Konsistenz in Ihrem Netzwerk zu verwalten, können Sie diesen Wert auf 46 ändern möchten.
    
- **Telefonsperre** Sie können angeben, ob UC-Telefone selbst automatisch nach einem angegebenen Zeitraum der Inaktivität gesperrt. Sie können die folgenden Einstellungen konfigurieren:
    
  - **Gerätesperre erzwingen** Sie können durch Aktivierung dieses Kontrollkästchens Gerätesperre erzwingen.
    
  - **PIN-Mindestlänge** Sie können die Mindestlänge für die persönliche Identifikationsnummer (PIN) angeben, die zum Entsperren des Telefons verwendet wird. Der zulässige Bereich für die PIN-Länge lautet vier bis 15 Stellen. Die Standardlänge beträgt sechs Stellen.
    
  - **Unter Timeout für Telefonsperre** Sie können die minimale Länge der Zeit, bevor die Telefon Sperren selbst angeben. Der Bereich für das Timeout lautet 0 bis 60 Minuten und der Standardwert beträgt 10 Minuten. Geben Sie den Wert im Format HH:MM:SS ein.
    
## <a name="see-also"></a>Siehe auch

[Gerätekonfiguration](device-configuration.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
