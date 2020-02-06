---
title: Benutzer Dienst für CQD
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Zusammenfassung: erfahren Sie mehr über den Benutzer Dienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 439df99c1c9d66547e681fdea90b33c6295344db
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816654"
---
# <a name="user-service-for-cqd"></a>Benutzer Dienst für CQD
 
**Zusammenfassung:** Erfahren Sie mehr über den Benutzer Dienst, der Teil der Repository-API für das Anruf Qualitäts Dashboard ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Benutzer Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.
  
## <a name="user-service"></a>Benutzerdienst

Die Repository-API bietet ein vereinfachtes Benutzer Verwaltungsmodell, bei dem die Benutzerbereitstellung (Erstellen neuer Benutzerkonten) automatisch und implizit erfolgt. Wenn ein Benutzer zum ersten Mal eine Anforderung an die Repository-API stellt, erstellt das Repository einen neuen Benutzerdatensatz. 
  
Mit dem Dashboard für die Anrufqualität werden auch automatisch benutzerspezifische Elemente für den neuen Benutzer erstellt. Die neuen benutzerspezifischen Elemente sind vollständige Klone der Elemente des Systembenutzers. Auf diese Weise beginnen Benutzer mit eigenen Kopien von Berichten und Abfragen, dass Sie sofort mit dem Customizing beginnen können. 
  
> [!NOTE]
> Mithilfe des Dashboards für die Anrufqualität können Benutzer ihre dedizierten Elemente jederzeit zurücksetzen. 
  
 **Spezielle Benutzer-IDs**
  
Die Repository-API enthält die RESTful-API-URIs, die einen ganzzahligen Wert zur Angabe eines bestimmten Benutzers erwartet. Beispiel: `https://<portal>/QoERepositoryService/repository/user/{userId}`. Hier sollte {UserID} durch einen ganzzahligen Wert wie 0, 1 usw. ersetzt werden.
  
Darüber hinaus akzeptiert die Repository-API zwei spezielle Benutzer-IDs bei {UserID} in URIs.
  
-  *Standard* – stellt den Benutzer dar, der gerade mit der API interagiert. Dies ermöglicht Anwendungen den Zugriff auf den Inhalt des aktuellen Benutzers, ohne den tatsächlichen Benutzer-ID-Wert zu verfolgen. Beispiel: `https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *System* – stellt den Systembenutzer dar. Dies ermöglicht Anwendungen den Zugriff auf die Inhalte des Systembenutzers, ohne den tatsächlichen Benutzer-ID-Wert zu kennen. Beispiel: `https://<portal>/QoERepositoryService/repository/user/system`.
    
Sofern nicht anders angegeben, können die speziellen Benutzer-IDs bei {UserID} in URIs verwendet werden. 
  
Die übrigen Vorgänge sind in der folgenden Tabelle enthalten.
  
|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Benutzern](get-users.md) <br/> |Gibt eine Liste der Benutzer im Repository zurück.  <br/> |
|[Abrufen eines Benutzers](get-user.md) <br/> |Gibt einen Benutzerdatensatz zurück.  <br/> |
   

