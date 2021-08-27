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
ms.localizationpriority: medium
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Ansichten gibt es für die gebräuchlichsten Szenarien zur Rückgabe von Daten aus der QoE-SQL-Datenbank. Es wird empfohlen, Ansichten zum Erstellen von benutzerdefinierten Berichten zu verwenden, anstatt direkt auf die Datenbanktabellen zuzugreifen. Dies liegt daran, dass Ansichten mit größerer Wahrscheinlichkeit abwärtskompatibel mit zukünftigen Versionen bleiben.
ms.openlocfilehash: 7bed72ae4fe5a9468d6ac2b18148f62fe9aa0196
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578589"
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
   

