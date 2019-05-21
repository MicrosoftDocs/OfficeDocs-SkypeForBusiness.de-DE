---
title: UserStatistics-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Die Tabelle UserStatistics ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Verwendung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295692"
---
# <a name="userstatistics-table"></a>UserStatistics-Tabelle
 
Die Tabelle UserStatistics ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Verwendung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserID** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Benutzer kennzeichnet.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Zeitpunkt, zu dem sich der Benutzer zuletzt angemeldet hat.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Der letzte Zeitpunkt, zu dem der Benutzer eine Konferenz organisiert hat.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler erlebt hat.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler als Konferenzorganisator erlebt hat.  <br/> |
   

