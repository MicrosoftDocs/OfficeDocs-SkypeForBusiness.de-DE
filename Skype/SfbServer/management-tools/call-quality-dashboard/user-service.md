---
title: Benutzerdienst für CQD
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Zusammenfassung: Erfahren Sie mehr über den Benutzerdienst, der Teil der Repository-API für das Anrufqualitätsdashboard ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: e8be18304cad02e1ed39cf84327a58f84d134c6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851008"
---
# <a name="user-service-for-cqd"></a>Benutzerdienst für CQD
 
**Zusammenfassung:** Erfahren Sie mehr über den Benutzerdienst, der Teil der Repository-API für das Anrufqualitäts-Dashboard ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Benutzerdienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard.
  
## <a name="user-service"></a>Benutzerdienst

Die Repository-API bietet ein vereinfachtes Benutzerverwaltungsmodell, bei dem die Benutzerbereitstellung (Erstellen neuer Benutzerkonten) automatisch und implizit erfolgt. Wenn ein Benutzer zum ersten Mal eine Anforderung für die Repository-API stellt, erstellt das Repository einen neuen Benutzerdatensatz. 
  
Das Anrufqualitätsdashboard erstellt auch automatisch dedizierte Elemente für den neuen Benutzer. Die dedizierten Elemente des neuen Benutzers sind vollständige Klone der Elemente des Systembenutzers. Auf diese Weise beginnen Benutzer mit ihren eigenen Kopien von Berichten und Abfragen, die sie sofort anpassen können. 
  
> [!NOTE]
> Mithilfe des Anrufqualitäts-Dashboards können Benutzer ihre dedizierten Elemente jederzeit zurücksetzen. 
  
 **Spezielle Benutzer-IDs**
  
Die Repository-API enthält REST-API-URIs, die einen ganzzahligen Wert zur Angabe eines bestimmten Benutzers erwarten. Beispiel:  `https://<portal>/QoERepositoryService/repository/user/{userId}` . Hier sollte {userId} durch einen ganzzahligen Wert wie 0, 1 usw. ersetzt werden.
  
Darüber hinaus akzeptiert die Repository-API zwei spezielle Benutzer-IDs unter {userId} in URIs.
  
-  *default*  – stellt den Benutzer dar, der derzeit mit der API interagiert. Dadurch können Anwendungen auf die Inhalte des aktuellen Benutzers zugreifen, ohne den tatsächlichen Benutzer-ID-Wert nachzuverfolgen. Beispiel: `https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *system*  – stellt den Systembenutzer dar. Dadurch können Anwendungen auf die Inhalte des Systembenutzers zugreifen, ohne den tatsächlichen Benutzer-ID-Wert zu kennen. Beispiel: `https://<portal>/QoERepositoryService/repository/user/system`.
    
Sofern nicht anders angegeben, können die speziellen Benutzer-IDs unter {userId} in URIs verwendet werden. 
  
Die REST-Vorgänge sind in der folgenden Tabelle enthalten.
  
|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Benutzern](get-users.md) <br/> |Gibt eine Liste der Benutzer im Repository zurück.  <br/> |
|[Abrufen eines Benutzers](get-user.md) <br/> |Gibt einen Benutzerdatensatz zurück.  <br/> |
   

