---
title: Leeren des Caches
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Cache löschen", der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806415"
---
# <a name="clear-cache"></a>Leeren des Caches
 
**Zusammenfassung:** Erfahren Sie mehr über den Clear Cache-Vorgang, der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Cache löschen" ist Teil der Daten-API für das Anrufqualitätsdashboard.
  
## <a name="clear-cache"></a>Leeren des Caches

Beim Löschen des Cachevorgangs wird der Cache auf dem Server für Abfragen und Daten gelöscht. Dadurch wird der Cache zurückgesetzt, und wir erhalten im Anschluss für neue Anforderungen neue Daten aus dem QoE-Cube.
  

|**Methode**|**Anforderungs-URI**|**HTTP Version**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – Keine zusätzlichen Header.
  
 **Anforderungstext** – Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – Keine zusätzlichen Header.
  
 **Antworttext** – Keine.
  

