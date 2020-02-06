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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Die Tabelle UserStatistics ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Verwendung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814793"
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
   

