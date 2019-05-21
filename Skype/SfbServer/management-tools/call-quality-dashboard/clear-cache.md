---
title: Leeren des Caches
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Löschen des Caches, der Teil der Daten-API für das Dashboard für die Anrufqualität ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 38648e1a910f93a30bd6da8807321acad0330e62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274835"
---
# <a name="clear-cache"></a>Leeren des Caches
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang zum Löschen des Caches, der Teil der Daten-API für das Dashboard für die Anrufqualität ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Vorgang zum Löschen des Caches ist Teil der Daten-API für das Dashboard für die Anrufqualität.
  
## <a name="clear-cache"></a>Leeren des Caches

Löschen des Cache Vorgangs löscht den Cache auf dem Server für Abfragen und Daten. Dadurch wird der Cache zurückgesetzt, und wir erhalten neue Daten aus dem QoE-Cube später für neue Anforderungen.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Bereitstellen  <br/> |https://\<-\>Portal/QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** -None.
  
 **Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.
  
 **Anforderungstext** – keine.
  
 **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.
  
 **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – keine zusätzlichen Überschriften.
  
 **Antworttext** – keine.
  

