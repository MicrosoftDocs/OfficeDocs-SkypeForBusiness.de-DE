---
title: Clientversionskonfiguration Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Konfigurationseinstellungen für Clientversionen dienen zum Aktivieren oder deaktivieren Sie die Versionskontrolle für Clients. Die globale clientversionskonfiguration mit Skype für Business Server installiert und wird zum Aktivieren oder Deaktivieren der clientversionskontrolle für die gesamte serverbereitstellung verwendet. Wenn die Konfiguration Global aktiviert ist, werden alle clientversionsrichtlinien, die Sie direkt wirksam wird, wenn Benutzer versuchen, melden Sie sich. Sie können die globale clientversionskonfiguration deaktivieren, wenn keine clientversionskontrolle erfolgen soll.
ms.openlocfilehash: 19c7cda4924148c6129e3fc3847c2770c51708d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Clientversionskonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionskonfiguration
 
Konfigurationseinstellungen für Clientversionen dienen zum Aktivieren oder deaktivieren Sie die Versionskontrolle für Clients. Die globale clientversionskonfiguration mit Skype für Business Server installiert und wird zum Aktivieren oder Deaktivieren der clientversionskontrolle für die gesamte serverbereitstellung verwendet. Wenn die Konfiguration Global aktiviert ist, werden alle clientversionsrichtlinien, die Sie direkt wirksam wird, wenn Benutzer versuchen, melden Sie sich. Sie können die globale clientversionskonfiguration deaktivieren, wenn keine clientversionskontrolle erfolgen soll. 
  
Sie können auch standortspezifische Clientversionskonfigurationen erstellen, um die Clientversionskontrolle pro Standort aktivieren und deaktivieren zu können. Standortspezifische Konfigurationen haben Vorrang vor der globalen Konfiguration.
  
## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Clientversionskonfiguration erstellen** oder **Clientversionskonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:
  
- Hinzufügen oder Ändern des Namens der Clientversionskonfiguration
    
- Aktivieren und Deaktivieren der Clientversionskontrolle global oder für einen bestimmten Standort
    
- Hinzufügen oder Ändern der Standardaktion für die Clientversionskonfiguration
    
## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.
  
- **Bereich** Gibt den Bereich (Global oder Standort) der clientversionskonfiguration an.
    
- **Name** Sie können hinzufügen oder Ändern des Namens der clientversionskonfiguration.
    
- **Versionskontrolle aktivieren** Sie können aktivieren oder Deaktivieren der clientversionskontrolle global oder für den Standort, je nach der Konfiguration.
    
- **Standardaktion** Sie können die Standardaktion auswählen, die angewendet werden, wenn ein Benutzer versucht, melden Sie sich unter Verwendung einer Clientanwendung keine bestimmte clientversionsrichtlinie vorhanden ist. Sie haben folgende Optionen:
    
  - **Zulassen** Ermöglicht den Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste nicht übereinstimmt.
    
  - **Blockieren** Verhindert, dass die Clients anmelden, wenn die Clientversion keinem Filter in der Liste nicht übereinstimmt.
    
  - **Mit URL blockieren** Verhindert, dass die Clients anmelden, wenn die Clientversion keinem Filter in der Liste stimmt nicht überein, und enthält eine Fehlermeldung, die mit einer URL, in dem eine neuere heruntergeladen werden kann.
    
  - **Mit URL zulassen** Ermöglicht den Client die Anmeldung, wenn die Clientversion keinem Filter in der Liste stimmt nicht überein, und eine Fehlermeldung enthält, die eine URL enthält, in dem eine neuere heruntergeladen werden kann.
    
  - **URL** Wenn Sie **mit URL blockieren** oder **mit URL zulassen**ausgewählt haben, können Sie die URL zum Einschließen in die Fehlermeldung angeben.
    
Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von clientversionskonfigurationen finden Sie unter [Ändern der Standardaktion für Clients nicht explizit unterstützt oder eingeschränkt](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in der Betriebsdokumentation.

