---
title: Gerätekonfiguration Erstellen neuer oder Bearbeiten vorhandener Gerätekonfigurationen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Auf der Seite Neue Gerätekonfiguration oder Gerätekonfiguration bearbeiten können Sie eine Sammlung von Einstellungen erstellen oder ändern, die zum Verwalten von Skype for Business Phone Edition verwendet werden. Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und das Angeben, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.
ms.openlocfilehash: b0973c73580aee3cfc81dfb79ac65613ddfcf204
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119924"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration
 
Auf der Seite  **Neue Gerätekonfiguration** oder Gerätekonfiguration bearbeiten können Sie eine Sammlung von Einstellungen erstellen oder ändern, die zum Verwalten von Skype for Business Phone Edition verwendet werden. Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und das Angeben, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.
  
## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Gerätekonfiguration** bzw. **Gerätekonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:
  
- Hinzufügen einer neuen Gerätekonfiguration
    
- Ändern der Eigenschaften einer vorhandenen Gerätekonfiguration
    
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.
  
- **Bereich** Gibt den Bereich (Global oder Site) der Gerätekonfiguration an.
    
- **Name** Sie können den Namen der Gerätekonfiguration hinzufügen oder ändern.
    
- **SIP-Sicherheit** Sie können Transport- und Authentifizierungsanforderungen für Skype for Business Phone Edition-Geräte konfigurieren. Folgende Optionen stehen zur Verfügung:
    
  - **Niedrig** Zulassen einer beliebigen Art von Autorisierung oder Transport.
    
  - **Mittel** NTLM oder Kerberos ist für die Benutzerauthentifizierung erforderlich.
    
  - **Hoch** NTLM oder Kerberos ist für die Benutzerauthentifizierung erforderlich, und TLS ist für SIP-Verbindungen erforderlich.
    
- **Protokollierungsstufe** Sie können die Protokollierung auf dem UC-Gerät aktivieren. Gültige Werte sind: Aus, Niedrig, Mittel und Hoch. Der Standardwert lautet "Aus".
    
- **Voice Quality of Service (QoS)** Sie können den DSCP-Wert angeben, der dem Sprachdatenverkehr von einem Skype for Business Phone Edition-Gerät zugewiesen ist. Der Standardwert ist 40. 40 ist jedoch nicht der Wert, der normalerweise für den Audiodatenverkehr verwendet wird. Stattdessen wird der Audiodatenverkehr fast immer mit dem DSCP-Code 46 markiert. Um die Konsistenz im gesamten Netzwerk zu gewährleisten, sollten Sie diesen Wert in 46 ändern.
    
- **Telefonsperre** Sie können angeben, ob sich UC-Telefone nach einem bestimmten Zeitraum der Inaktivität automatisch sperren. Sie können die folgenden Einstellungen konfigurieren:
    
  - **Erzwingen der Gerätesperrung** Sie können die Gerätesperrung erzwingen, indem Sie dieses Kontrollkästchen aktivieren.
    
  - **Minimale PIN-Länge** Sie können die Mindestlänge für die persönliche Identifikationsnummer (PIN) angeben, die zum Entsperren des Telefons verwendet wird. Der zulässige Bereich für die PIN-Länge lautet vier bis 15 Stellen. Die Standardlänge besteht aus sechs Stellen.
    
  - **Zeit-Out für Telefonsperren** Sie können die Mindestdauer angeben, bevor das Telefon selbst gesperrt wird. Der Bereich für das Timeout lautet 0 bis 60 Minuten; der Standardwert liegt bei 10 Minuten. Geben Sie den Wert im Format HH:MM:SS ein.
    
## <a name="see-also"></a>Siehe auch

[Gerätekonfiguration](device-configuration.md)

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)