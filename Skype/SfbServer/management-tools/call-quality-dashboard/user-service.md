---
title: Benutzerdienst für CQD
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Zusammenfassung: Erfahren Sie mehr über den Benutzerdienst, der Teil des Dashboards der Repository-API für die Anrufqualität ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803075"
---
# <a name="user-service-for-cqd"></a>Benutzerdienst für CQD
 
**Zusammenfassung:** Erfahren Sie mehr über den Benutzerdienst, der Teil des Dashboards der Repository-API für die Anrufqualität ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Benutzerdienst ist Teil der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="user-service"></a>Benutzerdienst

Die Repository-API bietet ein vereinfachtes Benutzerverwaltungsmodell, bei dem die Benutzerbereitstellung (Das Erstellen neuer Benutzerkonten) automatisch und implizit erfolgt. Wenn ein Benutzer zum ersten Mal eine Anforderung an die Repository-API stellt, erstellt das Repository einen neuen Benutzerdatensatz. 
  
Das Anrufqualitätsdashboard erstellt außerdem automatisch dedizierte Benutzerelemente für den neuen Benutzer. Die neuen dedizierten Benutzerelemente sind vollständige Klone der Elemente des Systembenutzers. Auf diese Weise beginnen Benutzer mit ihren eigenen Kopien von Berichten und Abfragen, die sie sofort anpassen können. 
  
> [!NOTE]
> Mithilfe des Anrufqualitätsdashboards können Benutzer ihre dedizierten Elemente jederzeit zurücksetzen. 
  
 **Spezielle Benutzer-IDs**
  
Die Repository-API enthält REST-API-URIs, die einen ganzzahligen Wert zur Angabe eines bestimmten Benutzers erwarten. Beispiel:  `https://<portal>/QoERepositoryService/repository/user/{userId}` . Hier sollte {userId} durch einen ganzzahligen Wert wie 0, 1 usw. ersetzt werden.
  
Darüber hinaus akzeptiert die Repository-API zwei spezielle Benutzer-IDs unter {userId} in URIs.
  
-  *Default*  – stellt den Benutzer dar, der derzeit mit der API interagiert. Dadurch können Anwendungen auf die Inhalte des aktuellen Benutzers zugreifen, ohne den tatsächlichen Benutzer-ID-Wert nachverfolgt zu werden. Beispiel: `https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *system*  – stellt den Systembenutzer dar. Dadurch können Anwendungen auf die Inhalte des Systembenutzers zugreifen, ohne den tatsächlichen Benutzer-ID-Wert zu kennen. Beispiel: `https://<portal>/QoERepositoryService/repository/user/system`.
    
Sofern nicht anders angegeben, können die speziellen Benutzer-IDs unter {userId} in URIs verwendet werden. 
  
Die REST-Vorgänge sind in der folgenden Tabelle enthalten.
  
|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Benutzern](get-users.md) <br/> |Gibt eine Liste der Benutzer im Repository zurück.  <br/> |
|[Abrufen eines Benutzers](get-user.md) <br/> |Gibt einen Benutzerdatensatz zurück.  <br/> |
   

