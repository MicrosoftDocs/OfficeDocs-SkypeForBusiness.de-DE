---
title: UriTypes-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: Die UriTypes-Tabelle enthält die verschiedenen URI-Typen (Uniform Resource Identifier), die in Skype for Business Server 2015 überwacht werden.
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295748"
---
# <a name="uritypes-table"></a>UriTypes-Tabelle
 
Die UriTypes-Tabelle enthält die verschiedenen URI-Typen (Uniform Resource Identifier), die in Skype for Business Server 2015 überwacht werden.

Wenn die CDR-DB erstellt wird, werden zwei Datensätze erstellt, die PhoneUri und UserUri darstellen, und Datensätze, die danach erstellt wurden, werden dynamisch UriTypeId zugeordnet. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |Eindeutiger Bezeichner, der einem URI-Typ zugewiesen ist.  <br/> Mögliche Werte: 0 bis 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Beschreibungen der verschiedenen URI-Typen. Die folgenden Werte sind bereits zugewiesen: <br/>  1-Phone-URI <br/>  0-Benutzer-URI <br/> <br/>  Weitere mögliche Typen sind: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf: Chat<br/>    conf:focus<br/>   MRAS<br/>
