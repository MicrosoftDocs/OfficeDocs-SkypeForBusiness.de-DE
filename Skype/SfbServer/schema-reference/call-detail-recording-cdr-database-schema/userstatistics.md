---
title: UserStatistics-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Die UserStatistics-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung eines einzelnen Benutzers des Systems. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 45f34a1e8905d19b5ce48d94824591f25ec1ef28
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213039"
---
# <a name="userstatistics-table"></a>UserStatistics-Tabelle
 
Die UserStatistics-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung eines einzelnen Benutzers des Systems. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Benutzer-ID** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Benutzer identifiziert.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Zuletzt der Benutzer angemeldet.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Zuletzt organisiert der Benutzer eine Konferenz.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Zuletzt der Benutzer einen anruffehler.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Zuletzt der Benutzer einen anruffehler als Konferenzorganisator.  <br/> |
   

