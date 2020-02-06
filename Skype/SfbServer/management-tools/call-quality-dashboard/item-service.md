---
title: Element Dienst für das Anruf Qualitäts Dashboard (CQD)
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
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Zusammenfassung: erfahren Sie mehr über den Element Dienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 5fdf2aedcb1a5e8d7d1929d7af70c5911cae46f0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816714"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Element Dienst für das Anruf Qualitäts Dashboard (CQD)
 
**Zusammenfassung:** Erfahren Sie mehr über den Element Dienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.
  
## <a name="item-service"></a>Elementdienst

Die Repository-API bietet einen einfachen Content Management-Dienst, den so genannten Element Dienst, der zum Speichern von anwendungsdefinierten Inhalten für Benutzer verwendet werden kann. 
  
Der Systeminhalt ist Eigentum des Systembenutzers und wird von allen Benutzern mit schreibgeschütztem Zugriff freigegeben. Dedizierte Benutzer Inhalte gehören normalen Benutzern, und nur die Besitzer können Sie ändern oder löschen, doch alle Benutzer verfügen weiterhin über schreibgeschützten Zugriff.
  
> [!NOTE]
> Diese API-Dokumentation umfasst schreibgeschützte Vorgänge der Repository-API. 
  
Das Dashboard für die Anrufqualität speichert Berichte und Abfragen als Elemente in der Repository-Datenbank. Ein Element kann über optionale untergeordnete Elemente verfügen, und das Dashboard für die Anrufqualität organisiert Berichte und Abfragen in einer hierarchischen Struktur mithilfe von untergeordneten Elementen.
  
Der Element Dienst umfasst die folgenden Konzepte:
  
- **Element** – das grundlegende Element des Repositorys. Jedes Element gehört genau einem Benutzer.
    
- **Unterelement** – die grundlegenden organisatorischen Mechanismen des Repositorys. Das Element kann 0 (null), ein oder mehrere untergeordnete Elemente enthalten.
    
- **Item Ancestors** -die Liste der Elemente, beginnend mit dem obersten Element, das das Standardelement des Benutzers ist und zu einem bestimmten Element führt.
    
- **Elementinhalt** – der anwendungsspezifische Inhalt, der in Elementen gespeichert ist. Das Dashboard für die Anrufqualität speichert JSON-Darstellungen von Berichten und Abfragen in Inhalten.
    
Die übrigen Vorgänge sind in der folgenden Tabelle enthalten.
  

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Elementen](get-items.md) <br/> |Elemente abrufen gibt alle Elemente im Repository zurück.  <br/> |
|[Abrufen eines Elements](get-item.md) <br/> |Element abrufen gibt ein bestimmtes Element zurück.  <br/> |
|[Abrufen von untergeordneten Elementen](get-sub-items.md) <br/> |Abrufen untergeordneter Elemente gibt die untergeordneten Elemente eines bestimmten Elements zurück.  <br/> |
|[Abrufen von übergeordneten Elementen](get-item-ancestors.md) <br/> |Get Item Ancestors gibt die Vorfahren eines bestimmten Elements zurück.  <br/> |
|[Aktualisieren von Elementen](update-item.md) <br/> |Aktualisieren eines bestimmten Elements im Repository  <br/> |
   

