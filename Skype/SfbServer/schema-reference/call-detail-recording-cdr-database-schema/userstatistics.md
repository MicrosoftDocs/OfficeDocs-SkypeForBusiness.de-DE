---
title: UserStatistics-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Die UserStatistics-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 4dcd7c8d14bdaf3c8a9844aab3057d356a53fc91
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857212"
---
# <a name="userstatistics-table"></a>UserStatistics-Tabelle
 
Die UserStatistics-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**LastLogInTime** <br/> |Datum/Uhrzeit  <br/> ||Zeitpunkt, zu dem sich der Benutzer zuletzt angemeldet hat.  <br/> |
|**LastConfOrganizedTime** <br/> |Datum/Uhrzeit  <br/> ||Das letzte Mal, dass der Benutzer eine Konferenz organisiert hat.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |Datum/Uhrzeit  <br/> ||Beim letzten Auftreten eines Anruffehlers für den Benutzer.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |Datum/Uhrzeit  <br/> ||Das letzte Mal, dass der Benutzer als Konferenzorganisator einen Anruffehler auftrat.  <br/> |
   

