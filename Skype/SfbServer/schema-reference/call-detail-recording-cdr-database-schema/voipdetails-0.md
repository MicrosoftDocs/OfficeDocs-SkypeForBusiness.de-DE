---
title: VoipDetails-Tabelle
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: 'Jeder Datensatz steht für einen Anruf mit zwei Teilnehmern, wovon  mindestens einer ein VoIP-Benutzer ist.'
---

# <a name="voipdetails-table"></a>VoipDetails-Tabelle
 
Jeder Datensatz steht für einen Anruf mit zwei Teilnehmern, wovon  mindestens einer ein VoIP-Benutzer ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Dialogs-Tabelle in Skype for Business Server 2015](dialogs.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie [in der Dialogs-Tabelle in Skype for Business Server 2015](dialogs.md). <br/> |
|**FromNumberId** <br/> |int  <br/> |Ausländisch  <br/> |**PhoneId** des Anrufers. Weitere Informationen finden Sie in der [Tabelle "Telefone](phones.md) ". Wenn nicht NULL und **FromGatewayId** ist nicht NULL, handelt es sich beim Anrufer um einen PSTN-Benutzer. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Ausländisch  <br/> |**PhoneId** des Anrufempfängers. Weitere Informationen finden Sie in der [Tabelle "Telefone](phones.md) ". Wenn nicht NULL und **FromGatewayId** ist nicht NULL, handelt es sich beim Anrufempfänger um einen PSTN-Benutzer. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Ausländisch  <br/> |Der Vermittlungsserver, von dem der Anruf kommt. Weitere Informationen finden Sie in der [MediationServers-Tabelle](mediationservers.md) . <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Ausländisch  <br/> |Der Vermittlungsserver, an den der Anruf geht. Weitere Informationen finden Sie in der [MediationServers-Tabelle](mediationservers.md) . <br/> |
|**FromGatewayId** <br/> |int  <br/> |Ausländisch  <br/> |Das Gateway, von dem der Anruf kommt. Weitere Informationen finden Sie [in der Gateways-Tabelle in Skype for Business Server 2015](gateways.md). <br/> |
|**ToGatewayId** <br/> |int  <br/> |Ausländisch  <br/> |Das Gateway, an das der Anruf geht. Weitere Informationen finden Sie [in der Gateways-Tabelle in Skype for Business Server 2015](gateways.md). <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Ausländisch  <br/> |URI des Benutzers, der den Anruf unterbrochen hat, sofern der Benutzer über einen URI verfügt. Weitere Informationen finden Sie in der [Tabelle "Benutzer](users.md) ". <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Ausländisch  <br/> |ID des Telefons, das den Anruf unterbrochen hat, sofern der Anruf von einem Telefon unterbrochen wurde. Weitere Informationen finden Sie in der [Tabelle "Telefone](phones.md) ". <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype for Business Server 2015 eingeführt.  <br/> |
   

