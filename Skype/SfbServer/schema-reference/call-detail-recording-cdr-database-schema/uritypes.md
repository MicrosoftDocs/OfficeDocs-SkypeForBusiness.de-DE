---
title: UriTypes-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: Die UriTypes-Tabelle enthält die verschiedenen URI-Typen (Uniform Resource Identifier), die in Skype for Business Server 2015 überwacht werden.
ms.openlocfilehash: ed0cc7e62aba47af6622f821af785d8daf571649
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859762"
---
# <a name="uritypes-table"></a>UriTypes-Tabelle
 
Die UriTypes-Tabelle enthält die verschiedenen URI-Typen (Uniform Resource Identifier), die in Skype for Business Server 2015 überwacht werden.

Wenn die KDS-Datenbank erstellt wird, werden zwei Datensätze zur Darstellung von PhoneUri und UserUri erstellt, und danach erstellte Datensätze werden dynamisch UriTypeId zugewiesen. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |Tinyint  <br/> |Primary  <br/> |Eindeutige ID, die einem URI-Typ zugewiesen wird.  <br/> Mögliche Werte - 0 bis 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Beschreibungen zu verschiedenen URI-Typen. Die folgenden Werte sind vorab zugewiesen: <br/>  1 - Telefon URI <br/>  0 – Benutzer-URI <br/> <br/>  Weitere mögliche Typen sind: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
