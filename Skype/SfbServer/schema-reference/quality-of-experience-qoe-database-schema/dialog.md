---
title: Dialog-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a>Dialog-Tabelle
 
The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.
  
|**Column**|**Data Type**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Sequence number to differentiate sessions when they have the same ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||Dialog ID which is globally unique.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |Checksum of the Dialog ID.  <br/> |
   

