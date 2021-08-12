---
title: UserStatistics-Tabelle
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Die UserStatistics-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: d0d3fde20f7c8c94629f75ff00f310111cac16d386fc0b0373ee07b5c2a35fb5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302209"
---
# <a name="userstatistics-table"></a>UserStatistics-Tabelle
 
Die UserStatistics-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |Ganzzahl  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**LastLogInTime** <br/> |Datum/Uhrzeit  <br/> ||Zeitpunkt, zu dem sich der Benutzer zuletzt angemeldet hat.  <br/> |
|**LastConfOrganizedTime** <br/> |Datum/Uhrzeit  <br/> ||Das letzte Mal, dass der Benutzer eine Konferenz organisiert hat.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |Datum/Uhrzeit  <br/> ||Beim letzten Auftreten eines Anruffehlers für den Benutzer.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |Datum/Uhrzeit  <br/> ||Das letzte Mal, dass der Benutzer als Konferenzorganisator einen Anruffehler auftrat.  <br/> |
   

