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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Zusammenfassung: Erfahren Sie mehr über den Elementdienst, der Teil der Repository-API für das Anrufqualitätsdashboard ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 3be67c2455a299c6643238b966c9cb04545bc5d6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628667"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Item Service for Call Quality Dashboard (CQD)
 
**Zusammenfassung:** Erfahren Sie mehr über den Elementdienst, der Teil der Repository-API für das Anrufqualitäts-Dashboard ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Elementdienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard.
  
## <a name="item-service"></a>Elementdienst

Die Repository-API bietet einen einfachen Inhaltsverwaltungsdienst, der als Elementdienst bezeichnet wird und zum Speichern von anwendungsdefinierten Inhalten für Benutzer verwendet werden kann. 
  
Der Systeminhalt gehört dem Systembenutzer und wird von allen Benutzern mit schreibgeschütztem Zugriff freigegeben. Dedizierte Benutzerinhalte gehören normalen Benutzern, und nur die Besitzer können sie ändern oder löschen, aber alle Benutzer haben weiterhin schreibgeschützten Zugriff darauf.
  
> [!NOTE]
> Diese API-Dokumentation behandelt schreibgeschützte Vorgänge der Repository-API. 
  
Das Anrufqualitätsdashboard speichert Berichte und Abfragen als Elemente in der Repositorydatenbank. Ein Element kann optionale Unterelemente haben, und das Anrufqualitätsdashboard organisiert Berichte und Abfragen in einer hierarchischen Struktur mithilfe des Features "Untergeordnete Elemente".
  
Der Elementdienst umfasst die folgenden Konzepte:
  
- **Element** – das grundlegende Element des Repositorys. Jedes Element gehört genau einem Benutzer.
    
- **Unterelement** – die grundlegende Organisationsmechanismen des Repositorys. Das Element kann null, ein oder mehrere untergeordnete Elemente aufweisen.
    
- **"Item Ancestors"** – die Liste der Elemente, beginnend mit dem Element am häufigsten, das das Standardelement des Benutzers ist und zu einem bestimmten Element führt.
    
- **Elementinhalt** – der anwendungsspezifische Inhalt, der in Elementen gespeichert ist. Das Anrufqualitätsdashboard speichert JSON-Darstellungen von Berichten und Abfragen in Inhalten.
    
Die REST-Vorgänge sind in der folgenden Tabelle enthalten.
  

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Elementen](get-items.md) <br/> |Abrufen von Elementen gibt alle Elemente im Repository zurück.  <br/> |
|[Abrufen eines Elements](get-item.md) <br/> |Element abrufen gibt ein bestimmtes Element zurück.  <br/> |
|[Abrufen von untergeordneten Elementen](get-sub-items.md) <br/> |Dient zum Abrufen Sub-Items gibt die Unterelemente eines bestimmten Elements zurück.  <br/> |
|[Abrufen von übergeordneten Elementen](get-item-ancestors.md) <br/> |Get Item Ancestors returns a specific Item's ancestors.  <br/> |
|[Aktualisieren von Elementen](update-item.md) <br/> |Aktualisieren eines bestimmten Elements im Repository.  <br/> |
   

