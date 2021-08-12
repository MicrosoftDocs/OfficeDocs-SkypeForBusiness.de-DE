---
title: Details zur QoE-Ansicht
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Ansichten gibt es für die gebräuchlichsten Szenarien zur Rückgabe von Daten aus der QoE-SQL-Datenbank. Es wird empfohlen, Ansichten zum Erstellen von benutzerdefinierten Berichten zu verwenden, anstatt direkt auf die Datenbanktabellen zuzugreifen. Dies liegt daran, dass Ansichten mit größerer Wahrscheinlichkeit abwärtskompatibel mit zukünftigen Versionen bleiben.
ms.openlocfilehash: f8d6536522a04623f150ab03ba448af8c55bd401adc8e4484ac47d1cf48ccffa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347720"
---
# <a name="qoe-view-details"></a>Details zur QoE-Ansicht
 
Ansichten gibt es für die gebräuchlichsten Szenarien zur Rückgabe von Daten aus der QoE-SQL-Datenbank. Es wird empfohlen, Ansichten zum Erstellen von benutzerdefinierten Berichten zu verwenden, anstatt direkt auf die Datenbanktabellen zuzugreifen. Dies liegt daran, dass Ansichten mit größerer Wahrscheinlichkeit abwärtskompatibel mit zukünftigen Versionen bleiben.
  
|**Sichtname**|**Beschreibung**|
|:-----|:-----|
|[AudioStreamDetail-Ansicht](audiostreamdetail.md) <br/> |Speichert Informationen zu jedem Audiostream in der Datenbank.  <br/> |
|[MediaLine-Ansicht](medialine.md) <br/> |Speichert Informationen zu jeder Medienzeile in der Datenbank. Eine Audiositzung enthält für gewöhnlich eine Audiomedienzeile. Eine A/V-Sitzung (Audio und Video) enthält meist eine Audiomedienzeile und eine Videomedienzeile, kann jedoch auch zwei Medienzeilen enthalten, wenn ein Konferenzgerät oder eine Galerieansicht verwendet wird.  <br/> |
|[NetworkConfigurationSettings-Ansicht](networkconfigurationsettings.md) <br/> |Speichert Informationen über die Netzwerkkonfiguration.  <br/> |
|[Sitzungsansicht](session-0.md) <br/> |Speichert Informationen über Sitzungen, zu denen in der Datenbank Datensätze vorhanden sind.  <br/> |
|[UserAgent-Ansicht](useragent-0.md) <br/> |Speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, zu denen es in der Datenbank Datensätze gibt.  <br/> |
|[VideoStreamDetail-Ansicht](videostreamdetail.md) <br/> |Speichert Informationen zu jedem Videostream in der Datenbank.  <br/> |
   

