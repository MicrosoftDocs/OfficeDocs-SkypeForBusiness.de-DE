---
title: Conference-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Die Konferenz Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für eine Konferenz oder eine Peer-to-Peer-Sitzung.
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295013"
---
# <a name="conference-table"></a>Conference-Tabelle
 
Die Konferenz Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für eine Konferenz oder eine Peer-to-Peer-Sitzung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Konferenz Eintrag kennzeichnet.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |eindeutigen  <br/> |Konferenz-URI, wenn es sich um eine Konferenz handelt, oder wenn es sich um eine Peer-to-Peer-Sitzung handelt.  <br/> |
|**Prüfsumme** <br/> |int  <br/> |Index  <br/> |Die Prüfsumme des Konferenz-URIs. Diese wird intern verwendet.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Nur für interne Verwendung.  <br/> |
   

