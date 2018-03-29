---
title: VoipDetails-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Jeder Datensatz steht für einen Aufruf von zwei Teilnehmern in der mindestens ein Benutzer einen VoIP-Benutzer ist.
ms.openlocfilehash: 8f28ec3ac1d4049f24c5af5b768026bdd8a98486
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-table"></a>VoipDetails-Tabelle
 
Jeder Datensatz steht für einen Aufruf von zwei Teilnehmern in der mindestens ein Benutzer einen VoIP-Benutzer ist.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Zeitpunkt der sitzungsanforderung. Zusammen mit **SessionIdSeq** verwendet zur eindeutigen Identifizierung eine Sitzung. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |ID-Nummer, um die Sitzung zu identifizieren. In Verbindung mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Finden Sie unter der [Dialogs-Tabelle in Skype für Business Server 2015](dialogs.md) Weitere Informationen. <br/> |
|**FromNumberId** <br/> |int  <br/> |Fremdschlüssel  <br/> |**PhoneId** des Anrufers. Finden Sie weitere Informationen der [Phones-Tabelle](phones.md) . Wenn nicht NULL und **FromGatewayId** ist nicht NULL, wurde der Anrufer eine PSTN-Benutzer. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Fremdschlüssel  <br/> |**PhoneId** , der den Empfänger des Anrufs. Finden Sie weitere Informationen der [Phones-Tabelle](phones.md) . Wenn nicht NULL und **ToGatewayId** ist nicht NULL, wurde der Empfänger des Anrufs eine PSTN-Benutzer. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Der Vermittlungsserver den Anruf stammt. Finden Sie weitere Informationen den [MediationServers-Tabelle](mediationservers.md) . <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Der Vermittlungsserver aufgerufen wird, sollte. Finden Sie weitere Informationen den [MediationServers-Tabelle](mediationservers.md) . <br/> |
|**FromGatewayId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Gateway der Anruf stammt. [Gateways-Tabelle in Skype für Business Server 2015](gateways.md) Weitere Informationen finden Sie. <br/> |
|**ToGatewayId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Gateway der Anruf wird zu übertragen. [Gateways-Tabelle in Skype für Business Server 2015](gateways.md) Weitere Informationen finden Sie. <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Fremdschlüssel  <br/> |Der URI des Benutzers, der den Anruf getrennt, wenn der Benutzer einen URI verfügt. Finden Sie in der [Tabelle Benutzer](users.md) Weitere Informationen. <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Fremdschlüssel  <br/> |ID des Telefons, die der Anruf beendet wurde von einem Telefon getrennt. Finden Sie weitere Informationen der [Phones-Tabelle](phones.md) . <br/> |
|**ZuletztGeändertUm** <br/> |DateTime  <br/> ||Für die interne Verwendung durch den Überwachungsdienst.  <br/> Dieses Feld wurde in Skype für Business Server 2015 eingeführt.  <br/> |
   

