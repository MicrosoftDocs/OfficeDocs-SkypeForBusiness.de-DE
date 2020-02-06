---
title: Subnet-Tabelle
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Die Subnet-Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für ein Subnetz, das in der Netzwerk Konfigurationseinstellung definiert ist.
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805203"
---
# <a name="subnet-table"></a>Subnet-Tabelle
 
Die Subnet-Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für ein Subnetz, das in der Netzwerk Konfigurationseinstellung definiert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primär, fremd  <br/> |Ganzzahlige Darstellung für die Subnetz-IP-Adresse.  <br/> |
|**Subnetzmaske** <br/> |int  <br/> ||Subnetzmaske  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Fremd  <br/> |Wird in der [UserSite-Tabelle](usersite.md)referenziert.  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||Die Beschreibung für das Subnetz.  <br/> |
   

