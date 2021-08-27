---
title: Dialogtabelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Bei der Dialog-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird; jeder Datensatz steht für einen SIP-Dialog (Session Initiation Protocol).
ms.openlocfilehash: 0310845ada3b86346ccc6b410a5c7539b16689f3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603724"
---
# <a name="dialog-table"></a>Dialogtabelle
 
Bei der Dialog-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird; jeder Datensatz steht für einen SIP-Dialog (Session Initiation Protocol).
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Zeitpunkt, zu dem der QoE-Agent (Quality of Excellence) den ersten Bericht von einem Anrufer oder Angerufenen empfängt. Wird zusammen mit SessionSeq verwendet, um eine Sitzung eindeutig zu identifizieren.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Sequenznummer zur Unterscheidung von Sitzungen, die dieselbe ConferenceDateTime aufweisen.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||Dialog-ID, die global eindeutig ist.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |Index  <br/> |Prüfsumme der Dialog-ID.  <br/> |
   

