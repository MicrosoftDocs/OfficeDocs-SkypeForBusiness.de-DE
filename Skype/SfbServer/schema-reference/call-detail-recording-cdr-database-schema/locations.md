---
title: Locations-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Jeder Datensatz steht für einen Verweis auf den Speicherort in ein Notruf, wie ein Anruf E9-1-1.
ms.openlocfilehash: 180a094ef10cc54b4fd65a30adb0909789afa3d6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876944"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Locations-Tabelle in Skype für Business Server 2015
 
Jeder Datensatz steht für einen Verweis auf den Speicherort in ein Notruf, wie ein Anruf E9-1-1.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primär, Fremd  <br/> |Zeitpunkt der sitzungsanforderung. Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**Standort** <br/> |nvarchar(max)  <br/> ||Standort des Notrufs.  <br/> |
   

