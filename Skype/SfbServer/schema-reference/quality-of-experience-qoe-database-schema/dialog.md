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
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Die Dialog Tabelle ist eine unterstützende Tabelle; Jeder Datensatz steht für ein SIP-Dialogfeld (Session Initiation Protocol).
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294957"
---
# <a name="dialog-table"></a>Dialog-Tabelle
 
Die Dialog Tabelle ist eine unterstützende Tabelle; Jeder Datensatz steht für ein SIP-Dialogfeld (Session Initiation Protocol).
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Zeitpunkt, zu dem der Quality of Excellence (QoE)-Agent den ersten Bericht von einem Anrufer oder angerufenen erhält. Wird in Verbindung mit SessionSeq verwendet, um eine Sitzung eindeutig zu identifizieren.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Sequenznummer, um Sitzungen zu unterscheiden, wenn Sie dieselbe ConferenceDateTime haben.  <br/> |
|**Dialogfeld-Nr** <br/> |varchar (256)  <br/> ||Dialog Feld-ID, die global eindeutig ist.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |Index  <br/> |Die Prüfsumme der Dialog Feld-ID.  <br/> |
   

