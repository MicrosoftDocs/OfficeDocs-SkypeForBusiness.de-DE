---
title: Item Service for Call Quality Dashboard (CQD)
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
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Zusammenfassung: Erfahren Sie mehr über den Elementdienst, der Teil des Repository-API für das Anrufqualitätsdashboard ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827705"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Item Service for Call Quality Dashboard (CQD)
 
**Zusammenfassung:** Erfahren Sie mehr über den Elementdienst, der Teil des Dashboards der Repository-API für die Anrufqualität ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Elementdienst ist Teil der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="item-service"></a>Elementdienst

Die Repository-API bietet einen einfachen Inhaltsverwaltungsdienst, der als Elementdienst bezeichnet wird und zum Speichern von anwendungsdefinierten Inhalten für Benutzer verwendet werden kann. 
  
Die Systeminhalte gehören dem Systembenutzer und werden von allen Benutzern mit schreibgeschützten Zugriff freigegeben. Dedizierte Benutzerinhalte gehören normalen Benutzern, und nur die Besitzer können sie ändern oder löschen, aber alle Benutzer haben weiterhin schreibgeschützten Zugriff auf sie.
  
> [!NOTE]
> Diese API-Dokumentation behandelt schreibgeschützte Vorgänge der Repository-API. 
  
Das Anrufqualitätsdashboard speichert Berichte und Abfragen als Elemente in der Repositorydatenbank. Ein Element kann optionale Unterelemente enthalten, und das Anrufqualitätsdashboard organisiert Berichte und Abfragen in einer hierarchischen Struktur mithilfe der Funktion "Unterelemente".
  
Der Elementdienst umfasst die folgenden Konzepte:
  
- **Element** – das grundlegende Element des Repositorys. Jedes Element gehört genau einem Benutzer.
    
- **Unterelement –** die grundlegende Organisationsmechanik des Repositorys. Element kann null, ein oder mehrere untergeordnete Elemente haben.
    
- **Element-Vorgänger –** die Liste der Elemente, beginnend mit dem obersten Element, bei dem es sich um das Standardelement des Benutzers handelt, das zu einem bestimmten Element führt.
    
- **Elementinhalt** – der anwendungsspezifische Inhalt, der in Elementen gespeichert ist. Das Anrufqualitätsdashboard speichert die JSON-Darstellungen von Berichten und Abfragen in Inhalten.
    
Die REST-Vorgänge sind in der folgenden Tabelle enthalten.
  

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Elementen](get-items.md) <br/> |Get Items returns all Items in the repository.  <br/> |
|[Abrufen eines Elements](get-item.md) <br/> |"Element erhalten" gibt ein bestimmtes Element zurück.  <br/> |
|[Abrufen von untergeordneten Elementen](get-sub-items.md) <br/> |Get Sub-Items returns a specific Item's sub-Items.  <br/> |
|[Abrufen von übergeordneten Elementen](get-item-ancestors.md) <br/> |"Element-Vorgänger" gibt die Vorgänger eines bestimmten Elements zurück.  <br/> |
|[Aktualisieren von Elementen](update-item.md) <br/> |Aktualisieren eines bestimmten Elements im Repository.  <br/> |
   

