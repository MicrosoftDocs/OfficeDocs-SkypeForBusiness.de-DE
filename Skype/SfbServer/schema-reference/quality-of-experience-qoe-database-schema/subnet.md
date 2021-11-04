---
title: Subnetztabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Bei der Subnet-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für ein Subnetz in der Netzwerkkonfigurationseinstellung.
ms.openlocfilehash: b0c10fae89fe76c184e3aaffec4e1166c4cdb94c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768313"
---
# <a name="subnet-table"></a>Subnetztabelle
 
Bei der Subnet-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für ein Subnetz in der Netzwerkkonfigurationseinstellung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Subnetz-IP** <br/> |int  <br/> |Primär, Fremd  <br/> |Ganzzahlige Darstellung der Subnetz-IP.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Subnetzmaske  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Ausländisch  <br/> |Referenziert aus der [UserSite-Tabelle.](usersite.md)  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Beschreibung des Subnetzes.  <br/> |
   

