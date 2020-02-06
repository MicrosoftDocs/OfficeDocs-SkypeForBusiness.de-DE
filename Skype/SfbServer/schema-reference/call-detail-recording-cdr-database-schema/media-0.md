---
title: Medienansicht
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: In der Medienansicht werden Informationen zu einem Medientyp gespeichert, der in einer Peer-to-Peer-Sitzung verwendet wird. Eine Sitzung wird von mehreren Datensätzen in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 26ef344b5fade02168fb8737fe00049e44e24892
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815053"
---
# <a name="media-view"></a>Medienansicht
 
In der Medienansicht werden Informationen zu einem Medientyp gespeichert, der in einer Peer-to-Peer-Sitzung verwendet wird. Eine Sitzung wird von mehreren Datensätzen in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
> [!NOTE]
> Die Medienansicht sollte nicht verwendet werden, um die Mediendauer einer Sitzung zu berechnen. Diese Ansicht enthält die Signalisierungs Details von Medienaustausch in einer Sitzung. Der Medienaustausch erfolgt über die Einladungs Anfrage, und Startzeit gibt an, wie lange die Einladung gesendet wurde. Die Einladungs Zeit bedeutet nicht unbedingt die Startzeit des Mediums, da Medien erst nach Annahme der Sitzung gestartet werden. 
  
Die Medienansicht enthält alle Spalten in der SessionDetails- [Ansicht](sessiondetails-0.md) sowie die nachstehend aufgeführten.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Medientyp. Weitere Informationen finden Sie in der [Tabelle medialist](medialist.md) . <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |Zeit, zu der eine Medienanfrage gesendet wurde.  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |Endzeit der Sitzung.  <br/> |
   

