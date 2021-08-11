---
title: Subnetztabelle
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
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Bei der Subnet-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für ein Subnetz in der Netzwerkkonfigurationseinstellung.
ms.openlocfilehash: 10df067fe95f244aea2fa9987b4962efaef9fbe32fbbfbe5b0e9f6ed9f6392e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279961"
---
# <a name="subnet-table"></a>Subnetztabelle
 
Bei der Subnet-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für ein Subnetz in der Netzwerkkonfigurationseinstellung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Subnetz-IP** <br/> |Ganzzahl  <br/> |Primär, Fremd  <br/> |Ganzzahlige Darstellung der Subnetz-IP.  <br/> |
|**SubnetMask** <br/> |Ganzzahl  <br/> ||Subnetzmaske  <br/> |
|**UserSiteKey** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Referenziert aus der [UserSite-Tabelle.](usersite.md)  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Beschreibung des Subnetzes.  <br/> |
   

