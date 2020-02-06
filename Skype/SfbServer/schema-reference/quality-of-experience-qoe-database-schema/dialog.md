---
title: Dialog-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Die Dialog Tabelle ist eine unterstützende Tabelle; Jeder Datensatz steht für ein SIP-Dialogfeld (Session Initiation Protocol).
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809533"
---
# <a name="dialog-table"></a>Dialog-Tabelle
 
Die Dialog Tabelle ist eine unterstützende Tabelle; Jeder Datensatz steht für ein SIP-Dialogfeld (Session Initiation Protocol).
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Zeitpunkt, zu dem der Quality of Excellence (QoE)-Agent den ersten Bericht von einem Anrufer oder angerufenen erhält. Wird in Verbindung mit SessionSeq verwendet, um eine Sitzung eindeutig zu identifizieren.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Sequenznummer, um Sitzungen zu unterscheiden, wenn Sie dieselbe ConferenceDateTime haben.  <br/> |
|**Dialogfeld-Nr** <br/> |varchar (256)  <br/> ||Dialog Feld-ID, die global eindeutig ist.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |Index  <br/> |Die Prüfsumme der Dialog Feld-ID.  <br/> |
   

