---
title: Liste der Kompatibilitätstabellen für den Server für beständigen Chat in Skype for Business Server
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
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Das Datenbankschema für die Kompatibilität des beständigen Chats besteht aus den folgenden Tabellen.
ms.openlocfilehash: b41d8a3f3c5e42f9e4c29eeb6cb81774b5b177aee18c67dc52bc4c9009f67c8e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303668"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Liste der Kompatibilitätstabellen für den Server für beständigen Chat in Skype for Business Server
 
Das Datenbankschema für die Kompatibilität des beständigen Chats besteht aus den folgenden Tabellen.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Liste der Kompatibilitätstabellen für Persistent Chat Server

|**Table**|**Beschreibung**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Enthält die Genehmigungsereignisse, die noch nicht vom konfigurierten Adapter verarbeitet wurden.  <br/> Diese Tabelle enthält Ereignisse im Zusammenhang mit beständigem Chat, z. B. Chatnachrichten und Dateidownloads. (Teilnehmerereignisse werden von der tblComplianceParticipant-Tabelle nachverfolgt.)  <br/> (Die Server, von denen die Ereignisse in dieser Tabelle verarbeitet wurden, werden in der tblComplianceFanout-Tabelle aufgelistet.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Enthält die Server, von denen ein Genehmigungsereignis verarbeitet wurde. Diese Tabelle steht in engem Zusammenhang mit der tblComplianceData-Tabelle.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Enthält aktuelle Teilnehmer pro Chat-Dienst und pro Server. Es wird basierend auf Denk- und Teilcomplianceereignissen verwaltet, die vom Dienst für beständigen Chat empfangen wurden.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Enthält poolweite Informationen zum Kompatibilitätszustand.  <br/> |
   

