---
title: Benutzer Einstellungsdienst für das Anruf Qualitäts Dashboard (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Zusammenfassung: erfahren Sie mehr über den Benutzer Einstellungsdienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: e5e068d66adb325900b055a19aedcfaeabf4f2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274485"
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
   

