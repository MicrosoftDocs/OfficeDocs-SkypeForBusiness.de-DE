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
description: Dialog-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Session Initiation Protocol (SIP)-Dialogfeld.
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a>Dialog-Tabelle
 
Dialog-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Session Initiation Protocol (SIP)-Dialogfeld.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Zeitpunkt der Agent für die Qualität der Betriebsprozesse (QoE) den ersten Bericht vom Anrufer oder angerufenen empfängt Zeit. In Verbindung mit SessionSeq verwendet, um eine Sitzung eindeutig zu identifizieren.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Sequenznummer zur Unterscheidung von Sitzungen, wenn sie die dieselbe ConferenceDateTime aufweisen.  <br/> |
|**Dialog-ID** <br/> |varchar(256)-Wert  <br/> ||Dialog-ID der global eindeutig ist.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |Index  <br/> |Prüfsumme der Dialog-ID.  <br/> |
   

