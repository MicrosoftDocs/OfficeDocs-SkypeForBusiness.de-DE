---
title: Benutzereinstellungsdienst für das Anrufqualitätsdashboard (CQD)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Zusammenfassung: Erfahren Sie mehr über den Benutzereinstellungsdienst, der Teil des Dashboards der Repository-API für die Anrufqualität ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803036"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Benutzereinstellungsdienst für das Anrufqualitätsdashboard (CQD)
 
**Zusammenfassung:** Erfahren Sie mehr über den Benutzereinstellungsdienst, der Teil des Repository-API für das Anrufqualitätsdashboard ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Benutzereinstellungsdienst ist Teil der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="user-settings-service"></a>Benutzereinstellungsdienst

Benutzereinstellungen sind Schlüssel-Wert-Paare, die Anwendungen zum Speichern von Metadaten für verschiedene Zwecke verwenden können, einschließlich der Anpassung des Anwendungsverhaltens pro Benutzer. Jeder Benutzer erhält einen Speicher für Benutzereinstellungen. Nur die Besitzer können Benutzereinstellungen hinzufügen, ändern und entfernen.
  
 **Globale Einstellungen**
  
Globale Einstellungen sind die Benutzereinstellungen, die dem Systembenutzer gehören, und alle Benutzer haben schreibgeschützten Zugriff darauf. Globale Einstellungen sind Konstanten: Sie werden während der Repositoryerstellung erstellt und ändern sich nie.
  
Jeder Benutzer kann globale Einstellungen überschreiben, indem er Benutzereinstellungen mit denselben Schlüsseln erstellt. Wenn die Anwendung die effektiven Benutzereinstellungen anfordert, gibt die API eine Reihe globaler Einstellungen zurück, die mit den Benutzereinstellungen zusammengeführt werden, und jede Benutzereinstellung ersetzt die jeweilige globale Einstellung, wenn schlüsselgleich sind. Die API kann auch nur die Benutzereinstellungen zurückgeben, damit Anwendungen herausfinden können, welche Einstellungen überschrieben werden. 
  
Die REST-Vorgänge sind in der folgenden Tabelle enthalten.

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen der Benutzereinstellungen](get-user-settings.md) <br/> |Get User Settings returns a list of settings for a specified user.  <br/> |
|[Abrufen einer Benutzereinstellung](get-user-setting.md) <br/> |"Benutzereinstellung erhalten" gibt eine einzelne Benutzereinstellung zurück.  <br/> |
   

