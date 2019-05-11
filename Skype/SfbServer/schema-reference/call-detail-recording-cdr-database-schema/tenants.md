---
title: Tenants-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Die Mandanten-Tabelle ist eine unterstützende Tabelle, die eine Liste der verschiedenen Mandanten gespeichert. Jeder Datensatz in der Tabelle steht für einen Mandanten.
ms.openlocfilehash: 68050ce76cc41d3fd66931fbdc0b0d3168786bc8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930206"
---
# <a name="tenants-table"></a>Tenants-Tabelle
 
Die Mandanten-Tabelle ist eine unterstützende Tabelle, die eine Liste der verschiedenen Mandanten gespeichert. Jeder Datensatz in der Tabelle steht für einen Mandanten.
  
> [!NOTE]
> In der lokalen Bereitstellung verwendet CDR die integrierte Mandanten-ID, um verschiedene Authentifizierungstyp wie öffentliche Instant Messaging-Diensten Federated und anonym anzuzeigen. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diese Mandanten-ID identifiziert  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  00000000-0000-0000-0000-000000000000-Enterprise <br/>  00000000-0000-0000-0000-000000000001-Verbund <br/>  00000000-0000-0000-0000-000000000002 - anonyme <br/>  00000000-0000-0000-0000-000000000003-öffentliche Instant Messaging-Diensten <br/> |
   

