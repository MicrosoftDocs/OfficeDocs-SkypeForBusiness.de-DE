---
title: Liste der kompatibilitätstabellen für Persistent Chat Server in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Das beständigen Chat Compliance-Datenbankschema besteht aus den folgenden Tabellen.
ms.openlocfilehash: e17b2e52bdeb65ff4c77377cb913da212f20ecf0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929889"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Liste der kompatibilitätstabellen für Persistent Chat Server in Skype für Business Server
 
Das beständigen Chat Compliance-Datenbankschema besteht aus den folgenden Tabellen.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Liste der Kompatibilitätstabellen für Persistent Chat Server

|**Tabelle**|**Beschreibung**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Enthält die genehmigungsereignisse, die noch nicht vom konfigurierten Adapter verarbeitet wurden.  <br/> Die folgende Tabelle enthält die Persistent Chat-bezogenen Ereignisse wie Chatnachrichten und Dateidownloads. (Teilnehmer Ereignisse werden von der Tabelle TblComplianceParticipant nachverfolgt.)  <br/> (Die Server, die die Ereignisse in dieser Tabelle verarbeitet wurden, werden in der TblComplianceFanout-Tabelle aufgelistet.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Enthält die Server, die ein kompatibilitätsereignis verarbeitet. In dieser Tabelle ist eng mit der Tabelle "tblcompliancedata" gekoppelt.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Enthält die aktuellen Teilnehmer pro Chatdienst und pro Server. Es wird beibehalten, basierend auf Verbindungs- und Teil Konformitätsereignisse von Persistent Chat-Dienst empfangen wurden.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Enthält poolweite Informationen zum kompatibilitätszustand.  <br/> |
   

