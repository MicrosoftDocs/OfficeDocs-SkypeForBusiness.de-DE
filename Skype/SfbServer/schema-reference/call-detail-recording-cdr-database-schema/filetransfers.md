---
title: Dateiübertragungen (Ansicht)
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Die Filetransfer-Ansicht speichert Informationen zu Peer-to-Peer-Dateiübertragungssitzungen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: d650c04b8dada5828eed5d7bc3039cb77570ce2b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815203"
---
# <a name="filetransfers-view"></a>Dateiübertragungen (Ansicht)
 
Die Filetransfer-Ansicht speichert Informationen zu Peer-to-Peer-Dateiübertragungssitzungen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
> [!NOTE]
> Die Dateiübertragungen-Ansicht enthält alle Spalten in der [SessionDetails-Ansicht](sessiondetails-0.md) sowie die unten aufgeführten Spalten.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Der Name der übertragenen Datei.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Wird verwendet, um jede nach Verfolgungs Nachricht als zugeordnet zu kennzeichnen.  <br/> |
|**Fileidentity** <br/> |uniqueidentifier  <br/> |Eindeutiger Bezeichner zur Unterscheidung Zwischendatei Übertragungen mit demselben Dateinamen.  <br/> |
|**Annehmen** <br/> |bit  <br/> |Kann "wahr" oder "Null" sein. Ist "true", ist "ablehnen" und "Abbrechen" NULL.  <br/> |
|**Ablehnen** <br/> |bit  <br/> |Kann "wahr" oder "Null" sein. Ist "true", ist "akzeptieren" und "Abbrechen" NULL.  <br/> |
|**Abbrechen** <br/> |bit  <br/> |Kann "wahr" oder "Null" sein. Ist "true", ist "annehmen und ablehnen" NULL.  <br/> |
   

