---
title: User Einstellungen Service for Call Quality Dashboard (CQD)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Zusammenfassung: Erfahren Sie mehr über den Benutzer-Einstellungen-Dienst, der Teil der Repository-API für das Anrufqualitätsdashboard ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 010ac5ee79ee03c8ff1137be80f2e2e520d27e77
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762283"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>User Einstellungen Service for Call Quality Dashboard (CQD)
 
**Zusammenfassung:** Erfahren Sie mehr über den Benutzer-Einstellungen-Dienst, der Teil der Repository-API für das Anrufqualitäts-Dashboard ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Benutzer-Einstellungen-Dienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard.
  
## <a name="user-settings-service"></a>Benutzereinstellungsdienst

Benutzereinstellungen sind Schlüssel-Wert-Paare, die Anwendungen zum Speichern von Metadaten für verschiedene Zwecke verwenden können, einschließlich der Anpassung des Anwendungsverhaltens pro Benutzer. Jeder Benutzer erhält einen Speicher für Benutzereinstellungen. Nur die Besitzer können Benutzereinstellungen hinzufügen, ändern und entfernen.
  
 **Globale Einstellungen**
  
Globale Einstellungen sind die Benutzereinstellungen, die dem Systembenutzer gehören, und alle Benutzer haben schreibgeschützten Zugriff darauf. Globale Einstellungen sind Konstanten: Sie werden während der Repositoryerstellung erstellt und ändern sich nie.
  
Jeder Benutzer kann globale Einstellungen überschreiben, indem er Benutzereinstellungen mit denselben Schlüsseln erstellt. Wenn die Anwendung die effektiven Benutzereinstellungen anfordert, gibt die API eine Reihe von globalen Einstellungen zurück, die mit den Benutzereinstellungen zusammengeführt werden, wobei jede Benutzereinstellung die entsprechende globale Einstellung ersetzt, wenn die Schlüssel identisch sind. Die API kann auch nur die Benutzereinstellungen zurückgeben, damit Anwendungen herausfinden können, welche Einstellungen überschrieben werden. 
  
Die REST-Vorgänge sind in der folgenden Tabelle enthalten.

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen der Benutzereinstellungen](get-user-settings.md) <br/> |Abrufen von Benutzer Einstellungen gibt eine Liste der Einstellungen für einen angegebenen Benutzer zurück.  <br/> |
|[Abrufen einer Benutzereinstellung](get-user-setting.md) <br/> |"Benutzereinstellung abrufen" gibt eine einzelne Benutzereinstellung zurück.  <br/> |
   

