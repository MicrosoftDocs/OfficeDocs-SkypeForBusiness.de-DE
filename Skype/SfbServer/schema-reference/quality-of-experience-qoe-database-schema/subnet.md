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
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Die Subnet-Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für ein Subnetz, das in der Netzwerk Konfigurationseinstellung definiert ist.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294635"
---
# <a name="subnet-table"></a>Subnet-Tabelle
 
Die Subnet-Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für ein Subnetz, das in der Netzwerk Konfigurationseinstellung definiert ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primär, fremd  <br/> |Ganzzahlige Darstellung für die Subnetz-IP-Adresse.  <br/> |
|**Subnetzmaske** <br/> |int  <br/> ||Subnetzmaske  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Fremd  <br/> |Wird in der [UserSite-Tabelle](usersite.md)referenziert.  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||Die Beschreibung für das Subnetz.  <br/> |
   

