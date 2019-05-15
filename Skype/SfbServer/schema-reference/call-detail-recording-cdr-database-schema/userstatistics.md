---
title: UserStatistics-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Die UserStatistics-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung eines einzelnen Benutzers des Systems. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: c2e0acffa7b75b3c54781e3e4e9a8b033be5e440
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929980"
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
   

