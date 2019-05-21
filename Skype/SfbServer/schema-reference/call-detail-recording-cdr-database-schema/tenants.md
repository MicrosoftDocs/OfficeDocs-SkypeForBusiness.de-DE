---
title: Tenants-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Die Tabelle Mandanten ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Mandanten gespeichert ist. Jeder Datensatz in der Tabelle steht für einen Mandanten.
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295769"
---
# <a name="tenants-table"></a>Tenants-Tabelle
 
Die Tabelle Mandanten ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Mandanten gespeichert ist. Jeder Datensatz in der Tabelle steht für einen Mandanten.
  
> [!NOTE]
> In der lokalen Bereitstellung verwendet CdR die integrierte Mandanten-ID, um einen anderen Authentifizierungstyp anzugeben, beispielsweise öffentliche im-Konnektivität, Federated und Anonymous. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Mandanten** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die diese Mandanten-ID kennzeichnet.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  00000000-0000-0000-0000-000000000000-Enterprise <br/>  00000000-0000-0000-0000-000000000001-Federated <br/>  00000000-0000-0000-0000-000000000002-anonym <br/>  00000000-0000-0000-0000-000000000003 – Konnektivität für öffentliche Chats <br/> |
   

