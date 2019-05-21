---
title: VoipDetails-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Jeder Datensatz steht für 1 2-Party-Anrufe, bei denen mindestens ein Nutzer ein VoIP-Nutzer ist.
ms.openlocfilehash: 7f0be2fb2f14e34cbe989d5912db1f66d3d65d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295678"
---
# <a name="voipdetails-table"></a>VoipDetails-Tabelle
 
Jeder Datensatz steht für 1 2-Party-Anrufe, bei denen mindestens ein Nutzer ein VoIP-Nutzer ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionID** <br/> |datetime  <br/> |Primary  <br/> |Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit **SessionID** -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Tabelle Dialogfelder in Skype for Business Server 2015](dialogs.md) . <br/> |
|**FromNumberId** <br/> |int  <br/> |Fremd  <br/> |**Telefonnummer** des Anrufers. Weitere Informationen finden Sie in der [Tabelle Telefone](phones.md) . Wenn nicht NULL und **FromGatewayId** nicht NULL ist, war der Aufrufer ein PSTN-Benutzer. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Fremd  <br/> |**Telefonnummer** des anrufempfängers. Weitere Informationen finden Sie in der [Tabelle Telefone](phones.md) . Wenn nicht NULL und **togateway** -Nr NULL ist, war der Anrufempfänger ein PSTN-Benutzer. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Fremd  <br/> |Der Vermittlungs Server, aus dem der Anruf kommt. Weitere Informationen finden Sie in der [MediationServers-Tabelle](mediationservers.md) . <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Fremd  <br/> |Der Vermittlungs Server wird aufgerufen. Weitere Informationen finden Sie in der [MediationServers-Tabelle](mediationservers.md) . <br/> |
|**FromGatewayId** <br/> |int  <br/> |Fremd  <br/> |Gateway, aus dem der Anruf kommt. Weitere Informationen finden Sie [in der Tabelle Gateways in Skype for Business Server 2015](gateways.md) . <br/> |
|**Togatewayservernummer** <br/> |int  <br/> |Fremd  <br/> |Gateway, an das der Anruf geht. Weitere Informationen finden Sie [in der Tabelle Gateways in Skype for Business Server 2015](gateways.md) . <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Fremd  <br/> |Der URI des Benutzers, der den Anruf getrennt hat, wenn der Benutzer über einen URI verfügt. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Fremd  <br/> |Die ID des Telefons, das den Anruf getrennt hat, wurde von einem Telefon getrennt. Weitere Informationen finden Sie in der [Tabelle Telefone](phones.md) . <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

