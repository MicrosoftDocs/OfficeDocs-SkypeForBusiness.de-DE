---
title: Details zur QoE-Ansicht
ms.reviewer: ''
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
ms.openlocfilehash: f384f75ecc0c8a0dfdb2cdaedacdcef81bdba9b4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876549"
---
# <a name="qoe-view-details"></a>Details zur QoE-Ansicht
 
Ansichten beschäftigen sich mit die am häufigsten verwendeten Szenarien zum Zurückgeben von Daten aus der QoE-SQL-Datenbank. Es empfiehlt sich Ansichten, die zum Erstellen von benutzerdefinierten Berichten anstelle der direkte Zugriff auf die Datenbanktabellen verwendet; Dies liegt daran Ansichten zum Aufrechterhalten der Abwärtskompatibilität Kompatibilität mit zukünftigen Versionen mehr wahrscheinlich eine Rolle spielen.
  
|**Name der Ansicht**|**Beschreibung**|
|:-----|:-----|
|[AudioStreamDetail-Ansicht](audiostreamdetail.md) <br/> |Speichert Informationen zu jedem Audiostream in der Datenbank an.  <br/> |
|[MediaLine-Ansicht](medialine.md) <br/> |Speichert Informationen zu jeder medienzeile in der Datenbank an. Eine audiositzung enthält in der Regel eine Audiomedien-Zeile. Eine Audio- und Videokonferenzen (A / V) Sitzung in der Regel enthält eine Audiomedien Zeile und eine Videomedien Zeile; die Sitzung kann jedoch zwei Videomedien Zeilen enthalten, wenn ein Konferenzgerät verwendet wird oder Katalogansicht verwendet wird.  <br/> |
|[NetworkConfigurationSettings-Ansicht](networkconfigurationsettings.md) <br/> |Speichert Informationen über die Netzwerkkonfiguration.  <br/> |
|[Session-Ansicht](session-0.md) <br/> |Speichert Informationen über Sitzungen, die Datensätze in der Datenbank verfügen.  <br/> |
|[UserAgent-Ansicht](useragent-0.md) <br/> |Speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, die Datensätze in der Datenbank verfügen.  <br/> |
|[VideoStreamDetail-Ansicht](videostreamdetail.md) <br/> |Speichert Informationen zu jedem Videostream in der Datenbank an.  <br/> |
   

