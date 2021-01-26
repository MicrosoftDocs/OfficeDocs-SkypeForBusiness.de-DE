---
title: Gerätekonfiguration Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: Auf der Seite "Neue Gerätekonfiguration" oder "Gerätekonfiguration bearbeiten" können Sie eine Auflistung von Einstellungen erstellen oder ändern, die zum Verwalten der Skype for Business Phone Edition verwendet werden. Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und das Angeben, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.
ms.openlocfilehash: 0b330212c8dc050bb618f28ea6444b1c8e58f040
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830195"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration
 
Auf der Seite  **"Neue Gerätekonfiguration"** oder "Gerätekonfiguration bearbeiten" können Sie eine Auflistung von Einstellungen erstellen oder ändern, die zum Verwalten der Skype for Business Phone Edition verwendet werden. Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und das Angeben, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.
  
## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Gerätekonfiguration** bzw. **Gerätekonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:
  
- Hinzufügen einer neuen Gerätekonfiguration
    
- Ändern der Eigenschaften einer vorhandenen Gerätekonfiguration
    
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.
  
- **Bereich** Gibt den Bereich (Global oder Standort) der Gerätekonfiguration an.
    
- **Name** Sie können den Namen der Gerätekonfiguration hinzufügen oder ändern.
    
- **SIP-Sicherheit** Sie können Transport- und Authentifizierungsanforderungen für Skype for Business Phone Edition-Geräte konfigurieren. Folgende Optionen stehen zur Verfügung:
    
  - **Niedrig** Zulassen einer beliebigen Art von Autorisierung oder Transport.
    
  - **Mittel** NTLM oder Kerberos ist für die Benutzerauthentifizierung erforderlich.
    
  - **Hoch** NTLM oder Kerberos ist für die Benutzerauthentifizierung und TLS für SIP-Verbindungen erforderlich.
    
- **Protokollierstufe** Sie können die Protokollierung auf dem UC-Gerät aktivieren. Gültige Werte sind: Aus, Niedrig, Mittel und Hoch. Der Standardwert lautet "Aus".
    
- **QoS (Voice Quality of Service)** Sie können den DSCP-Wert angeben, der dem Sprachdatenverkehr von einem Skype for Business Phone Edition-Gerät zugewiesen ist. Der Standardwert ist 40. 40 ist jedoch nicht der Wert, der normalerweise für Audiodatenverkehr verwendet wird. Stattdessen wird der Audiodatenverkehr fast immer mit dem DSCP-Code 46 gekennzeichnet. Um die Konsistenz im gesamten Netzwerk zu gewährleisten, sollten Sie diesen Wert in 46 ändern.
    
- **Telefonsperre** Sie können angeben, ob sich UC-Telefone nach einem bestimmten Zeitraum der Inaktivität automatisch sperren. Sie können die folgenden Einstellungen konfigurieren:
    
  - **Erzwingen der Gerätesperre** Sie können die Gerätesperre erzwingen, indem Sie dieses Kontrollkästchen aktivieren.
    
  - **Minimale PIN-Länge** Sie können die Mindestlänge für die persönliche Identifikationsnummer (PIN) angeben, die zum Entsperren des Telefons verwendet wird. Der zulässige Bereich für die PIN-Länge lautet vier bis 15 Stellen. Die Standardlänge besteht aus sechs Stellen.
    
  - **Telefonsperre – Zeit-Out** Sie können die Mindestdauer angeben, bevor das Telefon selbst gesperrt wird. Der Bereich für das Timeout lautet 0 bis 60 Minuten; der Standardwert liegt bei 10 Minuten. Geben Sie den Wert im Format HH:MM:SS ein.
    
## <a name="see-also"></a>Siehe auch

[Gerätekonfiguration](ms.lync.lscp.ClientDeviceCfgMain.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
