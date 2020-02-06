---
title: Benutzer Einstellungsdienst für das Anruf Qualitäts Dashboard (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Zusammenfassung: erfahren Sie mehr über den Benutzer Einstellungsdienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 1eef869523bf1590a00ca199727b33ec9e13ccba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816644"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Benutzer Einstellungsdienst für das Anruf Qualitäts Dashboard (CQD)
 
**Zusammenfassung:** Erfahren Sie mehr über den Benutzer Einstellungsdienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Benutzer Einstellungsdienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.
  
## <a name="user-settings-service"></a>Benutzereinstellungsdienst

Benutzereinstellungen sind Schlüssel-Wert-Paare, mit denen Anwendungen Metadaten für verschiedene Zwecke speichern können, einschließlich der Anpassung von Anwendungsverhalten pro Benutzer. Jeder Benutzer erhält einen Speicher für Benutzereinstellungen. Benutzereinstellungen können nur von den Besitzern hinzugefügt, geändert und entfernt werden.
  
 **Globale Einstellungen**
  
Bei globalen Einstellungen handelt es sich um die Benutzereinstellungen des Systembenutzers, und alle Benutzer verfügen über schreibgeschützten Zugriff. Globale Einstellungen sind Konstanten: Sie werden während der Erstellung des Repositorys erstellt, und Sie ändern sich nie.
  
Jeder Benutzer kann die globalen Einstellungen außer Kraft setzen, indem Benutzereinstellungen mit denselben Tasten erstellt werden. Wenn die Anwendung die effektiven Benutzereinstellungen anfordert, gibt die API einen Satz globaler Einstellungen zurück, die mit den Benutzereinstellungen zusammengeführt wurden, wobei jede Benutzereinstellung die jeweilige globale Einstellung ersetzt, wenn die Schlüssel identisch sind. Die API kann auch nur die Benutzereinstellungen zurückgeben, damit Anwendungen herausfinden können, welche Einstellungen überschrieben werden. 
  
Die übrigen Vorgänge sind in der folgenden Tabelle enthalten.

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen der Benutzereinstellungen](get-user-settings.md) <br/> |Abrufen von Benutzereinstellungen gibt eine Liste der Einstellungen für einen bestimmten Benutzer zurück.  <br/> |
|[Abrufen einer Benutzereinstellung](get-user-setting.md) <br/> |Benutzereinstellung abrufen gibt eine Einstellung für einen einzelnen Benutzer zurück.  <br/> |
   

