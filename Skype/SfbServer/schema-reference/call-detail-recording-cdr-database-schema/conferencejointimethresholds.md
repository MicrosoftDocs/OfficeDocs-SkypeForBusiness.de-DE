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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'Die Tabelle "ConferenceJoinTimeThresholds" enthält die Klassifizierungs Grenzen, die vom Zusammenfassungsbericht "Konferenzteilnahme Zeit" verwendet werden. Der Bericht "Konferenz Teilzeit-Zusammenfassung" fasst die Zeitspanne zusammen, die der Benutzer für eine erfolgreiche Teilnahme an einer Konferenz benötigt. Diese Zeitwerte werden sowohl als Mittelwert als auch in einer der folgenden Kategorien angezeigt:'
ms.openlocfilehash: 1874a94448be5957079b1c53944bc127df761e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815393"
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
   

