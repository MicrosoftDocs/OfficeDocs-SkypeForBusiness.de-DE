---
title: Tabelle "UserStatistics"
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
description: Die Tabelle "UserStatistics" ist eine Tabelle mit Unterstützung. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813105"
---
# <a name="userstatistics-table"></a>Tabelle "UserStatistics"
 
Die Tabelle "UserStatistics" ist eine Tabelle mit Unterstützung. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**LastLogInTime** <br/> |Datum/Uhrzeit  <br/> ||Zeitpunkt der letzten Anmeldung des Benutzers.  <br/> |
|**LastConfOrganizedTime** <br/> |Datum/Uhrzeit  <br/> ||Zeitpunkt, zu dem der Benutzer zuletzt eine Konferenz organisiert hat.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |Datum/Uhrzeit  <br/> ||Zeitpunkt, zu dem der Benutzer zuletzt einen Anruffehler erlebt hat.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |Datum/Uhrzeit  <br/> ||Zeitpunkt, zu dem der Benutzer zuletzt einen Anruffehler als Konferenzorganisator hatte.  <br/> |
   

