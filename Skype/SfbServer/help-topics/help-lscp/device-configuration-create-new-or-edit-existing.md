---
title: Gerätekonfiguration neues erstellen oder vorhandenes bearbeiten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: Auf der Seite neue Gerätekonfiguration oder Gerätekonfiguration bearbeiten können Sie eine Sammlung von Einstellungen erstellen oder ändern, die für die Verwaltung von Skype for Business Phone Edition verwendet werden. Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und die Festlegung, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.
ms.openlocfilehash: 95ce62b5d3505e10049d61ead77ce79ee7f2f51b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822928"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration
 
Auf der Seite **neue Gerätekonfiguration** oder **Gerätekonfiguration bearbeiten** können Sie eine Sammlung von Einstellungen erstellen oder ändern, die für die Verwaltung von Skype for Business Phone Edition verwendet werden. Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und die Festlegung, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.
  
## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Gerätekonfiguration** bzw. **Gerätekonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:
  
- Hinzufügen einer neuen Gerätekonfiguration
    
- Ändern der Eigenschaften einer vorhandenen Gerätekonfiguration
    
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.
  
- **Bereich** Identifiziert den Bereich (Global oder Website) der Gerätekonfiguration.
    
- **Name** Sie können den Namen der Gerätekonfiguration hinzufügen oder ändern.
    
- **SIP-Sicherheit** Sie können Transport-und Authentifizierungsanforderungen für Skype for Business Phone Edition-Geräte konfigurieren. Folgende Optionen stehen zur Verfügung:
    
  - **Niedrige** Erlauben Sie jede Art von Autorisierung oder Transport.
    
  - **Medium** NTLM oder Kerberos ist für die Benutzerauthentifizierung erforderlich.
    
  - **Höchst** NTLM oder Kerberos ist für die Benutzerauthentifizierung erforderlich, und für SIP-Verbindungen ist TLS erforderlich.
    
- **Protokollierungsstufe** Sie können die Protokollierung auf dem UC-Gerät aktivieren. Gültige Werte sind: „Aus“, „Niedrig“, „Mittel“ und „Hoch“. Der Standardwert lautet „Aus“.
    
- **Sprach Quality of Service (QoS)** Sie können den DSCP-Wert angeben, der dem VoIP-Datenverkehr von einem Skype for Business Phone Edition-Gerät zugewiesen ist. Der Standardwert ist 40. 40 ist jedoch nicht der in der Regel für den Audioverkehr verwendete Wert; Stattdessen wird der Audioverkehr fast immer mit dem DSCP-Code 46 markiert. Um die Konsistenz im gesamten Netzwerk zu gewährleisten, sollten Sie diesen Wert in 46 ändern.
    
- **Telefonsperre** Sie können angeben, ob UC-Telefone nach einem bestimmten Zeitraum der Inaktivität automatisch gesperrt werden. Sie können die folgenden Einstellungen konfigurieren:
    
  - **Erzwingen der Gerätesperrung** Sie können das Sperren des Geräts erzwingen, indem Sie dieses Kontrollkästchen aktivieren.
    
  - **Minimale PIN-Länge** Sie können die Mindestlänge für die persönliche Identifikationsnummer (PIN) angeben, die zum Entsperren des Telefons verwendet wird. Der zulässige Bereich für die PIN-Länge lautet vier bis 15 Stellen. Die Standardlänge beträgt sechs Stellen.
    
  - **Timeout für Telefonsperre** Sie können die minimale Zeitdauer angeben, bevor sich das Telefon selbst sperrt. Der Bereich für das Timeout lautet 0 bis 60 Minuten und der Standardwert beträgt 10 Minuten. Geben Sie den Wert im Format HH:MM:SS ein.
    
## <a name="see-also"></a>Siehe auch

[Gerätekonfiguration](device-configuration.md)

[Satz-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
