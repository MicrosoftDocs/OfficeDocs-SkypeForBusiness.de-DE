---
title: Mandantentabelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Bei der Tenants-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der eine Liste verschiedener Mandanten gespeichert ist. Jeder Datensatz in der Tabelle steht für einen Mandanten.
ms.openlocfilehash: 2705b44830efef4a8f921bf9ccc9c7b8e49f72ec
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583789"
---
# <a name="tenants-table"></a>Mandantentabelle
 
Bei der Tenants-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der eine Liste verschiedener Mandanten gespeichert ist. Jeder Datensatz in der Tabelle steht für einen Mandanten.
  
> [!NOTE]
> Bei der lokalen Bereitstellung wird die integrierte Mandanten-ID von der Aufzeichnung von Kommunikationsdatensätzen (KDS) zur Angabe verschiedener Authentifizierungstypen verwendet, wie z. B. Verbindung mit öffentlichen Chatdiensten, Partner und Anonym. 
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diese Mandanten-ID identifiziert.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  00000000-0000-0000-0000-000000000000 - Enterprise <br/>  00000000-0000-0000-0000-000000000001 - Verbund <br/>  00000000-0000-0000-0000-000000000002 - Anonym <br/>  00000000-0000-0000-0000-000000000003 – Verbindung mit öffentlichen Chatdiensten <br/> |
   

