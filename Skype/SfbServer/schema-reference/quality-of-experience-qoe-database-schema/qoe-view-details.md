---
title: Anzeigen von Details QoE
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Ansichten beschäftigen sich mit die am häufigsten verwendeten Szenarien zum Zurückgeben von Daten aus der QoE-SQL-Datenbank. Es empfiehlt sich Ansichten, die zum Erstellen von benutzerdefinierten Berichten anstelle der direkte Zugriff auf die Datenbanktabellen verwendet; Dies liegt daran Ansichten zum Aufrechterhalten der Abwärtskompatibilität Kompatibilität mit zukünftigen Versionen mehr wahrscheinlich eine Rolle spielen.
ms.openlocfilehash: 72fe0a1cd4bd3319bbb6907a23bda0932b3ef619
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="qoe-view-details"></a>Anzeigen von Details QoE
 
Ansichten beschäftigen sich mit die am häufigsten verwendeten Szenarien zum Zurückgeben von Daten aus der QoE-SQL-Datenbank. Es empfiehlt sich Ansichten, die zum Erstellen von benutzerdefinierten Berichten anstelle der direkte Zugriff auf die Datenbanktabellen verwendet; Dies liegt daran Ansichten zum Aufrechterhalten der Abwärtskompatibilität Kompatibilität mit zukünftigen Versionen mehr wahrscheinlich eine Rolle spielen.
  
|**Name der Ansicht**|**Beschreibung**|
|:-----|:-----|
|[AudioStreamDetail-Ansicht](audiostreamdetail.md) <br/> |Speichert Informationen zu jedem Audiostream in der Datenbank an.  <br/> |
|[MediaLine-Ansicht](medialine.md) <br/> |Speichert Informationen zu jeder medienzeile in der Datenbank an. Eine audiositzung enthält in der Regel eine Audiomedien-Zeile. Eine Audio- und Videokonferenzen (A / V) Sitzung in der Regel enthält eine Audiomedien Zeile und eine Videomedien Zeile; die Sitzung kann jedoch zwei Videomedien Zeilen enthalten, wenn ein Konferenzgerät verwendet wird oder Katalogansicht verwendet wird.  <br/> |
|[NetworkConfigurationSettings-Ansicht](networkconfigurationsettings.md) <br/> |Speichert Informationen über die Netzwerkkonfiguration.  <br/> |
|[Session-Ansicht](session-0.md) <br/> |Speichert Informationen über Sitzungen, die Datensätze in der Datenbank verfügen.  <br/> |
|[UserAgent-Ansicht](useragent-0.md) <br/> |Speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, die Datensätze in der Datenbank verfügen.  <br/> |
|[VideoStreamDetail-Ansicht](videostreamdetail.md) <br/> |Speichert Informationen zu jedem Videostream in der Datenbank an.  <br/> |
   

