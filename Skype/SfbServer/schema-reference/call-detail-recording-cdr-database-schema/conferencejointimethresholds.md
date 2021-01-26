---
title: Tabelle "ConferenceJoinTimeThresholds" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'Die Tabelle ConferenceJoinTimeThresholds enthält die Klassifizierungsgrenzwerte, die vom zusammenfassenden Bericht über den Zeitpunkt des Konferenzbeitritts verwendet werden. Der Bericht über den Zeitpunkt des Konferenzbeitritts enthält eine Zusammenfassung der Zeit, die Benutzer benötigen, um einer Konferenz erfolgreich beizutreten. Diese Zeitwerte werden sowohl als Durchschnitt als auch in einer der folgenden Kategorien gemeldet:'
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813305"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Tabelle "ConferenceJoinTimeThresholds" in Skype for Business Server 2015
 
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
|**ThresholdValue** <br/> |int  <br/> || Oberer Grenzwert für die Klassifizierung. Gültige Werte sind: <br/>  2  <br/>  5  <br/>  10  <br/> |
   

