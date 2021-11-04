---
title: ConferenceJoinTimeThresholds-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'Die Tabelle ConferenceJoinTimeThresholds enthält die Klassifizierungsgrenzwerte, die vom zusammenfassenden Bericht über den Zeitpunkt des Konferenzbeitritts verwendet werden. Der Bericht über den Zeitpunkt des Konferenzbeitritts enthält eine Zusammenfassung der Zeit, die Benutzer benötigen, um einer Konferenz erfolgreich beizutreten. Diese Zeitwerte werden sowohl als Durchschnitt als auch in einer der folgenden Kategorien gemeldet:'
ms.openlocfilehash: 61267cb92e543da3b07b97bd344bc07d2845d6a6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749904"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>ConferenceJoinTimeThresholds-Tabelle in Skype for Business Server 2015
 
Die Tabelle ConferenceJoinTimeThresholds enthält die Klassifizierungsgrenzwerte, die vom zusammenfassenden Bericht über den Zeitpunkt des Konferenzbeitritts verwendet werden. Der Bericht über den Zeitpunkt des Konferenzbeitritts enthält eine Zusammenfassung der Zeit, die Benutzer benötigen, um einer Konferenz erfolgreich beizutreten. Diese Zeitwerte werden sowohl als Durchschnitt als auch in einer der folgenden Kategorien gemeldet:
  
- Weniger als 2 Sekunden.
    
- Zwischen 2 Sekunden und 5 Sekunden.
    
- Zwischen 5 Sekunden und 10 Sekunden.
    
- Mehr als 10 Sekunden.
    
Die Tabelle ConferenceJoinTimeThresholds enthält die Klassifizierungswerte 2 Sekunden, 5 Sekunden und 10 Sekunden.
  
Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID für die Klassifizierung.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Oberer Grenzwert für die Klassifizierung. Gültige Werte sind: <br/>  2 <br/>  5 <br/>  10 <br/> |
   

