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
description: Ansichten gibt es für die gebräuchlichsten Szenarien zur Rückgabe von Daten aus der QoE-SQL-Datenbank. Es werden Ansichten empfohlen, die zum Erstellen benutzerdefinierter Berichte verwendet werden, anstatt direkt auf die Datenbanktabellen zu zugreifen. Dies liegt daran, dass Ansichten mit der wahrscheinlicheren Abwärtskompatibilität mit zukünftigen Versionen kompatibel sind.
ms.openlocfilehash: cabe483da624d801b9b87d51ba61caed7a22f7d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834475"
---
# <a name="qoe-view-details"></a>Details zur QoE-Ansicht
 
Ansichten gibt es für die gebräuchlichsten Szenarien zur Rückgabe von Daten aus der QoE-SQL-Datenbank. Es werden Ansichten empfohlen, die zum Erstellen benutzerdefinierter Berichte verwendet werden, anstatt direkt auf die Datenbanktabellen zu zugreifen. Dies liegt daran, dass Ansichten mit der wahrscheinlicheren Abwärtskompatibilität mit zukünftigen Versionen kompatibel sind.
  
|**Sichtname**|**Beschreibung**|
|:-----|:-----|
|[Ansicht "AudioStreamDetail"](audiostreamdetail.md) <br/> |Speichert Informationen zu jedem Audiostream in der Datenbank.  <br/> |
|[MediaLine-Ansicht](medialine.md) <br/> |Speichert Informationen zu jeder Medienzeile in der Datenbank. Eine Audiositzung enthält für gewöhnlich eine Audiomedienzeile. Eine A/V-Sitzung (Audio und Video) enthält meist eine Audiomedienzeile und eine Videomedienzeile, kann jedoch auch zwei Medienzeilen enthalten, wenn ein Konferenzgerät oder eine Galerieansicht verwendet wird.  <br/> |
|[Ansicht "NetworkConfigurationSettings"](networkconfigurationsettings.md) <br/> |Speichert Informationen über die Netzwerkkonfiguration.  <br/> |
|[Sitzungsansicht](session-0.md) <br/> |Speichert Informationen über Sitzungen, zu denen in der Datenbank Datensätze vorhanden sind.  <br/> |
|[Ansicht "UserAgent"](useragent-0.md) <br/> |Speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, zu denen es in der Datenbank Datensätze gibt.  <br/> |
|[VideoStreamDetail-Ansicht](videostreamdetail.md) <br/> |Speichert Informationen zu jedem Videostream in der Datenbank.  <br/> |
   

