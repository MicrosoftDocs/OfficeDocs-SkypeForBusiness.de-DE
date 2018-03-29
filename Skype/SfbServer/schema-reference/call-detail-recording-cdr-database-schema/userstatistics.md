---
title: UserStatistics-Tabelle
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
ms.openlocfilehash: c4a7952eada01033836811555d2e448d13133a27
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
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
   

