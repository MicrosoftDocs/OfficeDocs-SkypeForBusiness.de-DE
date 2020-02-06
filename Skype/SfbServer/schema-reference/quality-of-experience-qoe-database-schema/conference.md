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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Die Konferenz Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für eine Konferenz oder eine Peer-to-Peer-Sitzung.
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810303"
---
# <a name="conference-table"></a>Conference-Tabelle
 
Die Konferenz Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für eine Konferenz oder eine Peer-to-Peer-Sitzung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diesen Konferenz Eintrag kennzeichnet.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |eindeutigen  <br/> |Konferenz-URI, wenn es sich um eine Konferenz handelt, oder wenn es sich um eine Peer-to-Peer-Sitzung handelt.  <br/> |
|**Prüfsumme** <br/> |int  <br/> |Index  <br/> |Die Prüfsumme des Konferenz-URIs. Diese wird intern verwendet.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Nur für interne Verwendung.  <br/> |
   

