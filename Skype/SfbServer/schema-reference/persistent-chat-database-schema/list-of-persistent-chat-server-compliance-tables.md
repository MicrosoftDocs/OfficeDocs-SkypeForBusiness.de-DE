---
title: Liste der beständigen Chat Server-Kompatibilitätstabellen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Das Compliance-Datenbankschema für beständige Chats besteht aus den folgenden Tabellen.
ms.openlocfilehash: a992f00718d831af1b5a30f08baaf779ea3ee2c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814763"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Liste der beständigen Chat Server-Kompatibilitätstabellen in Skype for Business Server
 
Das Compliance-Datenbankschema für beständige Chats besteht aus den folgenden Tabellen.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Liste der Kompatibilitätstabellen für beständigen Chat Server

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Enthält die Konformitätsereignisse, die vom konfigurierten Adapter noch nicht verarbeitet wurden.  <br/> Diese Tabelle enthält dauerhafte Chat bezogene Ereignisse wie Chatnachrichten und Dateidownloads. (Teilnehmer-Ereignisse werden von der tblComplianceParticipant-Tabelle nachverfolgt.)  <br/> (Die Server, die die Ereignisse in dieser Tabelle verarbeitet haben, werden in der tblComplianceFanout-Tabelle aufgelistet.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Enthält die Server, die ein Compliance-Ereignis verarbeitet haben. Diese Tabelle ist eng mit der tblComplianceData-Tabelle gekoppelt.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Enthält aktuelle Teilnehmer pro Chatdienst und pro Server. Sie wird auf der Grundlage von Join-und Part-Konformitäts Ereignissen verwaltet, die vom beständigen Chat Dienst empfangen werden.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Enthält Informationen zum Kompatibilitätszustand des Pools.  <br/> |
   

