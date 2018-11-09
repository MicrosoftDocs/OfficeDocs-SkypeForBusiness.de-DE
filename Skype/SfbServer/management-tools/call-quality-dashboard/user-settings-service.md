---
title: Einstellungen Benutzerdienst für Anruf Qualitätsdashboard (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Zusammenfassung: Erfahren Sie mehr über die Benutzerdienst Einstellungen, die Teil der Repository-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 00d0662e777ef2f13c9783fe4b79d5c582faa8af
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035610"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Einstellungen Benutzerdienst für Anruf Qualitätsdashboard (CQD)
 
**Zusammenfassung:** Informationen Sie zu den Benutzerdienst Einstellungen, der Teil der Repository-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Die User Settings Service ist Bestandteil der Repository-API für die Qualitätsdashboard aufrufen.
  
## <a name="user-settings-service"></a>Benutzerdienst-Einstellungen

Benutzereinstellungen sind Schlüssel-Wert-Paaren, die Anwendungen verwenden können, um Metadaten für verschiedene Zwecke einschließlich Anpassung der Anwendung Verhaltensweisen jeden Benutzer einzeln zu speichern. Jeder Benutzer erhält einen Speicher für benutzereinstellungen. Nur die Besitzer können hinzufügen, ändern und Entfernen von benutzereinstellungen.
  
 **Globale Einstellungen**
  
Globale Einstellungen werden die benutzereinstellungen Besitz des Systembenutzers, und alle Benutzer haben schreibgeschützten Zugriff auf diese. Globale Einstellungen werden Konstanten: werden während der Erstellung Repository erstellt, und sie nie ändern.
  
Jeder Benutzer überschreibbar globale Einstellungen, indem Sie benutzereinstellungen mit demselben Schlüssel erstellen. Bei der Anwendung die benutzereinstellungen für eine effektive anfordert, gibt die API einen Satz von globalen Einstellungen mit den benutzereinstellungen für mit jedem benutzereinstellung Ablösen der jeweiligen globale Einstellung, wenn Schlüssel identisch sind zusammengeführt. Die API kann auch nur die für die Benutzer zurückgegeben, damit Sie ermitteln können, welche Einstellungen außer Kraft gesetzt werden. 
  
In der folgenden Tabelle sind die REST-Vorgänge enthalten.

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Benutzereinstellungen](get-user-settings.md) <br/> |Get-Benutzereinstellungen gibt eine Liste der Einstellungen für einen angegebenen Benutzer zurück.  <br/> |
|[Get-Benutzereinstellung](get-user-setting.md) <br/> |Rufen Sie die Einstellung für Benutzer gibt eine Einstellung für die einzelnen Benutzer.  <br/> |
   

