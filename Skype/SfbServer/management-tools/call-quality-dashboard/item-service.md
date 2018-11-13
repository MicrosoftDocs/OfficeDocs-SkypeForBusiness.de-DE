---
title: Dienst für Anruf Qualitätsdashboard (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Zusammenfassung: Informationen Sie zu den Element-Dienst, der Teil der Repository-API für die Qualitätsdashboard aufrufen, ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: 5990b83e8b16d51be79c5afc80c0c08d53fa50e3
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295219"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Dienst für Anruf Qualitätsdashboard (CQD)
 
**Zusammenfassung:** Informationen Sie zu den Element-Dienst, der Teil der Repository-API für die Qualitätsdashboard aufrufen, ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.
  
Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.
  
## <a name="item-service"></a>Element-Dienst

Repository-API bietet eine einfache Content Management Service, bekannt als Element-Dienst, der zum Speichern von anwendungsdefinierte Inhalt für Benutzer verwendet werden kann. 
  
Den Inhalt des sind Besitz des Systembenutzers und von allen Benutzern mit Lesezugriff gemeinsam genutzt werden. Dedizierten Benutzer Inhalt Besitz regulären Benutzer und nur die Besitzer ändern oder löschen können, aber alle Benutzer weiterhin schreibgeschützten Zugriff auf die Dokumente haben.
  
> [!NOTE]
> Diese API-Dokumentation behandelt schreibgeschützten Vorgängen der Repository-API. 
  
Rufen Sie Elemente in der Repositorydatenbank Qualitätsdashboard speichert Berichte und Abfragen. Ein Element kann optionale untergeordnete Elemente aufweisen, und Aufrufen Qualitätsdashboard organisiert Berichte und Abfragen in einer hierarchischen Struktur Unterelemente-Feature verwenden.
  
Element Service umfasst die folgenden Konzepte:
  
- **Element** - das grundlegende Element des Repositorys. Jedes Element gehört genau einen Benutzer.
    
- **Unterelement** - die grundlegende Organisationseinheit Funktionsweise des Repositorys. Element kann 0 (null) aufweisen, eine oder mehrere untergeordnete Elemente.
    
- **Element Vorgänger** - die Liste der Elemente, die das oberste Element die Standardeinstellung Element des Benutzers, was zu einem bestimmten Element ab.
    
- **Elementinhalts** - die anwendungsspezifischen Inhalt in Elemente gespeichert. Anruf Qualitätsdashboard JSON Darstellungen von Berichten und Abfragen im Inhalt gespeichert.
    
In der folgenden Tabelle sind die REST-Vorgänge enthalten.
  

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Elementen](get-items.md) <br/> |Rufen Sie Elemente gibt alle Elemente im Repository.  <br/> |
|[Element abrufen](get-item.md) <br/> |Möchten Sie gibt ein bestimmtes Element erhalten.  <br/> |
|[Untergeordnete Elemente abrufen](get-sub-items.md) <br/> |Rufen Sie ein bestimmtes Element Unterelemente Unterelemente gibt.  <br/> |
|[Abrufen der Vorgänger des Elements](get-item-ancestors.md) <br/> |Get-Element Vorgänger gibt ein bestimmtes Element Vorgänger zurück.  <br/> |
|[Update-Element](update-item.md) <br/> |Aktualisieren Sie ein bestimmtes Element im Repository.  <br/> |
   

