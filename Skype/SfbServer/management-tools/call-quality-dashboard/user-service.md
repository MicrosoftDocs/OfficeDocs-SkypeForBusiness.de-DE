---
title: Benutzerdienst für CQD
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Zusammenfassung: Erfahren Sie mehr über den Benutzer-Dienst, der Teil der Repository-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 42268078337e41b2dff595f58963f94656c2fd66
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035617"
---
# <a name="user-service-for-cqd"></a>Benutzerdienst für CQD
 
**Zusammenfassung:** Informationen Sie zu den Benutzer-Dienst, der Teil der Repository-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.
  
## <a name="user-service"></a>Benutzerdienst

Repository-API bietet eine vereinfachte Verwaltung Benutzermodell, in dem Benutzer, die Bereitstellung (Erstellen neuer Benutzerkonten) automatische und implizite ist. Wenn ein Benutzer eine Anforderung für Repository-API zum ersten Mal, erstellt das Repository einen neuen Benutzerdatensatz. 
  
Anruf, dass Qualitätsdashboard auch automatisch ein Benutzer erstellt dediziert Elemente für den neuen Benutzer. Der neue dedizierte Benutzerelemente sind vollständige Auslösung von Elementen des Systembenutzers. Auf diese Weise Benutzer mit ihren eigenen Kopien von Berichten und Abfragen, die sie anpassen sofort starten können beginnen. 
  
> [!NOTE]
> Rufen Sie Qualitätsdashboard verwenden, können Benutzer ihre dedizierten Elemente zurückgesetzt jederzeit. 
  
 **Spezielle Benutzer-IDs**
  
Repository-API enthält REST-API-URIs, die einen ganzzahligen Wert an einen bestimmten Benutzer erwartet. Beispiel: `https://<portal>/QoERepositoryService/repository/user/{userId}`. Hier sollte {Benutzer-ID} ersetzt werden, eine ganze Zahl wie 0, 1, usw..
  
Darüber hinaus akzeptiert Repository API zwei spezielle Benutzer-IDs auf {Benutzer-ID} in URIs.
  
-  *Standard* - steht für den Benutzer, die mit der API interagiert. Dies ist die Anwendung den Zugriff auf Inhalt des aktuellen Benutzers ohne Verfolgen von der aktuelle Benutzer-ID-Wert. Beispiel: ` https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *System* - stellt den Systembenutzer dar. Dies ist die Anwendung auf dem des Systembenutzers Inhalt zugreifen, ohne den tatsächlichen Benutzer-ID-Wert. Beispiel: `https://<portal>/QoERepositoryService/repository/user/system`.
    
Sofern nicht anders angegeben, kann die spezielle Benutzer-IDs am {Benutzer-ID} in URIs verwendet werden. 
  
In der folgenden Tabelle sind die REST-Vorgänge enthalten.
  
|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Benutzern](get-users.md) <br/> |Gibt eine Liste der Benutzer im Repository.  <br/> |
|[Benutzer erhalten](get-user.md) <br/> |Gibt einen Benutzerdatensatz zurück.  <br/> |
   

