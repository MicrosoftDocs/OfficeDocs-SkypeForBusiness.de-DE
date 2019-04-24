---
title: UriTypes-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes-Tabelle sind die unterschiedlichen URI (Uniform Resource Identifier) Typen in Skype für Business Server 2015 überwacht.
ms.openlocfilehash: cb9c131901a322f9d22c8d29aa52a73dc27c9ea1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212761"
---
# <a name="uritypes-table"></a>UriTypes-Tabelle
 
UriTypes-Tabelle sind die unterschiedlichen URI (Uniform Resource Identifier) Typen in Skype für Business Server 2015 überwacht.

Wenn der CDR-DB erstellt wird, werden zwei Datensätze zur Darstellung von PhoneUri und UserUri erstellt, und Einträge erstellt, die dynamisch UriTypeId zugeordnet sind. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |Eindeutiger Bezeichner, einem URI-Typ zugewiesen sind.  <br/> Mögliche Werte - zwischen 0 und 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Eine Beschreibung der verschiedenen URI. Die folgenden Werte sind zugeordnete: <br/>  1 – Telefon-Uri <br/>  0 - Benutzer-Uri <br/> <br/>  Andere mögliche Typen sind: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:Chat<br/>    conf:focus<br/>   MRAS<br/>
