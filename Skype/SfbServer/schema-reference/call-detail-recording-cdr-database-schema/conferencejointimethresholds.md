---
title: ConferenceJoinTimeThresholds-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'Die Tabelle "ConferenceJoinTimeThresholds" enthält die Klassifizierungs Grenzen, die vom Zusammenfassungsbericht "Konferenzteilnahme Zeit" verwendet werden. Der Bericht "Konferenz Teilzeit-Zusammenfassung" fasst die Zeitspanne zusammen, die der Benutzer für eine erfolgreiche Teilnahme an einer Konferenz benötigt. Diese Zeitwerte werden sowohl als Mittelwert als auch in einer der folgenden Kategorien angezeigt:'
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296497"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>ConferenceJoinTimeThresholds-Tabelle in Skype for Business Server 2015
 
Die Tabelle "ConferenceJoinTimeThresholds" enthält die Klassifizierungs Grenzen, die vom Zusammenfassungsbericht "Konferenzteilnahme Zeit" verwendet werden. Der Bericht "Konferenz Teilzeit-Zusammenfassung" fasst die Zeitspanne zusammen, die der Benutzer für eine erfolgreiche Teilnahme an einer Konferenz benötigt. Diese Zeitwerte werden sowohl als Mittelwert als auch in einer der folgenden Kategorien angezeigt:
  
- Weniger als 2 Sekunden.
    
- Zwischen 2 Sekunden und 5 Sekunden.
    
- Zwischen 5 Sekunden und 10 Sekunden.
    
- Mehr als 10 Sekunden.
    
Die Tabelle ConferenceJoinTimeThresholds enthält die Klassifizierungs Werte 2 Sekunden, 5 Sekunden und 10 Sekunden.
  
Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Schwellenwert** <br/> |int  <br/> |Primary  <br/> |Eindeutiger Bezeichner für die Klassifizierung.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Obergrenze für die Klassifizierung. Gültige Werte sind: <br/>  2 <br/>  5 <br/>  10 <br/> |
   

