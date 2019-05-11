---
title: ContentTypes-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Die ContentTypes-Tabelle ist eine unterstützende Tabelle, die eine Liste der Inhaltstypen in Peer-zu-Peer-Sitzungen und konferenzsitzungen verwendeten gespeichert. Jeder Datensatz in der Tabelle steht für einen Inhaltstyp.
ms.openlocfilehash: e30f5f142b9b1e166266cf8d45fe7657fee1b1b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901080"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>ContentTypes-Tabelle in Skype für Business Server 2015
 
Die ContentTypes-Tabelle ist eine unterstützende Tabelle, die eine Liste der Inhaltstypen in Peer-zu-Peer-Sitzungen und konferenzsitzungen verwendeten gespeichert. Jeder Datensatz in der Tabelle steht für einen Inhaltstyp.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die den Inhaltstyp identifiziert.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Name des Inhaltstyps.  <br/> |
   

