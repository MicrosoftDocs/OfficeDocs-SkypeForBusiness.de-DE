---
title: Dialogtabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: ab466a158ca059ff3110012a03e5c9c1e39b3d2d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851789"
---
# <a name="dialog-table"></a>Dialogtabelle
 
Bei der Dialog-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird; jeder Datensatz steht für einen SIP-Dialog (Session Initiation Protocol).
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Zeitpunkt, zu dem der QoE-Agent (Quality of Excellence) den ersten Bericht von einem Anrufer oder Angerufenen empfängt. Wird zusammen mit SessionSeq verwendet, um eine Sitzung eindeutig zu identifizieren.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Sequenznummer zur Unterscheidung von Sitzungen, die dieselbe ConferenceDateTime aufweisen.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||Dialog-ID, die global eindeutig ist.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |Index  <br/> |Prüfsumme der Dialog-ID.  <br/> |
   

