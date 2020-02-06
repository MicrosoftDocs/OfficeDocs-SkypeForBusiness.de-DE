---
title: Media-Tabelle
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Jeder Datensatz steht für einen in einer Peer-to-Peer-Sitzung verwendeten Medientyp. Eine Sitzung wird von mehreren Datensätzen in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird.
ms.openlocfilehash: b96f1e9fccf2ac3416e505eb19a54a5e227bb01f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815043"
---
# <a name="media-table"></a>Media-Tabelle
 
Jeder Datensatz steht für einen in einer Peer-to-Peer-Sitzung verwendeten Medientyp. Eine Sitzung wird von mehreren Datensätzen in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird.
  
> [!NOTE]
> Die Medientabelle sollte nicht verwendet werden, um die Mediendauer einer Sitzung zu berechnen. Diese Tabelle enthält die Signalisierungs Details von Medienaustausch in einer Sitzung. Der Medienaustausch erfolgt über die Einladungs Anfrage, und Startzeit gibt an, wie lange die Einladung gesendet wurde. Die Einladungs Zeit bedeutet nicht unbedingt die Startzeit des Mediums, da Medien erst gestartet werden, nachdem der Sitzungs nehmer die Sitzung akzeptiert hat. Die EndTime bedeutet normalerweise die Endzeit dieser Sitzung. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Primär, fremd  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, fremd  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**MediaId** <br/> |tinyint  <br/> |Primär, fremd  <br/> |Eindeutige Nummer, die diesen Medientyp kennzeichnet. Weitere Informationen finden Sie in der [Tabelle medialist](medialist.md) . <br/> |
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |Dies ist der Zeitpunkt, zu dem eine Medienanfrage gesendet wurde, nicht die Startzeit des realen Mediums. **Startzeit** umfasst die Rüstzeit für die Sitzung. <br/> |
|**EndTime** <br/> |datetime  <br/> ||Dies ist die Endzeit der Sitzung.  <br/> |
   

