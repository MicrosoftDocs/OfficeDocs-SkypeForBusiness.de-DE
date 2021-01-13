---
title: Tabelle "UriTypes"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: Die Tabelle "UriTypes" enthält die verschiedenen URI (Uniform Resource Identifier)-Typen, die in Skype for Business Server 2015 überwacht werden.
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831685"
---
# <a name="uritypes-table"></a>Tabelle "UriTypes"
 
Die Tabelle "UriTypes" enthält die verschiedenen URI(Uniform Resource Identifier)-Typen, die in Skype for Business Server 2015 überwacht werden.

Wenn die CDR-DB erstellt wird, werden zwei Datensätze zur Darstellung von PhoneUri und UserUri erstellt, und danach erstellte Datensätze werden dynamisch UriTypeId zugewiesen. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |Eindeutige ID, die einem URI-Typ zugewiesen wird.  <br/> Mögliche Werte : 0 bis 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Beschreibungen zu verschiedenen URI-Typen. Die folgenden Werte sind vorab zugewiesen: <br/>  1 – Telefon-URI <br/>  0 – Benutzer-URI <br/> <br/>  Weitere mögliche Typen sind: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
