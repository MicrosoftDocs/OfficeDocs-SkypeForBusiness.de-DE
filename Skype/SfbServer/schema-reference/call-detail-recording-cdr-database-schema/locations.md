---
title: Tabelle "Speicherorte" in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: "Jeder Datensatz stellt den Verweis auf einen Standort in einem Notruf (z.\_B. ein E9-1-1-Anruf) dar."
---

# <a name="locations-table-in-skype-for-business-server-2015"></a>Tabelle "Speicherorte" in Skype for Business Server 2015
 
Jeder Datensatz stellt den Verweis auf einen Standort in einem Notruf (z. B. ein E9-1-1-Anruf) dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Dialogs-Tabelle in Skype for Business Server 2015](dialogs.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Dialogs-Tabelle in Skype for Business Server 2015](dialogs.md). <br/> |
|**Ort** <br/> |nvarchar(max)  <br/> ||Standort des Notrufs.  <br/> |
   

