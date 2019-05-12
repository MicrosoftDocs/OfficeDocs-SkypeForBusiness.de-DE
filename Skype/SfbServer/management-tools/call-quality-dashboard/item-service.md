---
title: Dienst für Anruf Qualitätsdashboard (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Zusammenfassung: Informationen Sie zu den Element-Dienst, der Teil der Repository-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: cbebdcfcac62eae375c13785b8d9866d055c2b50
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897499"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Dienst für Anruf Qualitätsdashboard (CQD)
 
**Zusammenfassung:** Informationen Sie zu den Element-Dienst, der Teil der Repository-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.
  
## <a name="item-service"></a>Elementdienst

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
|[Abrufen eines Elements](get-item.md) <br/> |Möchten Sie gibt ein bestimmtes Element erhalten.  <br/> |
|[Abrufen von untergeordneten Elementen](get-sub-items.md) <br/> |Rufen Sie ein bestimmtes Element Unterelemente Unterelemente gibt.  <br/> |
|[Abrufen von übergeordneten Elementen](get-item-ancestors.md) <br/> |Get-Element Vorgänger gibt ein bestimmtes Element Vorgänger zurück.  <br/> |
|[Aktualisieren von Elementen](update-item.md) <br/> |Aktualisieren Sie ein bestimmtes Element im Repository.  <br/> |
   

