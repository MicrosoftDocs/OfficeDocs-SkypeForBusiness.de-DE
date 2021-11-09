---
title: Subnetztabelle
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Bei der Subnet-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für ein Subnetz in der Netzwerkkonfigurationseinstellung.
ms.openlocfilehash: abbc1317c6a0db1da0b52e5b0eef56abbfad06f5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834843"
---
# <a name="subnet-table"></a>Subnetztabelle
 
Bei der Subnet-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für ein Subnetz in der Netzwerkkonfigurationseinstellung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Subnetz-IP** <br/> |int  <br/> |Primär, Fremd  <br/> |Ganzzahlige Darstellung der Subnetz-IP.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Subnetzmaske  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Ausländisch  <br/> |Referenziert aus der [UserSite-Tabelle.](usersite.md)  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Beschreibung des Subnetzes.  <br/> |
   

