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
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Die Filetransfer-Ansicht speichert Informationen zu Peer-to-Peer-Dateiübertragungssitzungen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296238"
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
   

