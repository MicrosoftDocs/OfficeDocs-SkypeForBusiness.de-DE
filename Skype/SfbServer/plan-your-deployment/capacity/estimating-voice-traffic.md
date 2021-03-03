---
title: Schätzen der Sprachnutzung und des Datenverkehrs für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Sie können die folgende Metrik verwenden, um den Benutzerdatenverkehr an jedem Standort und die Anzahl der Ports zu schätzen, die zur Unterstützung dieses Datenverkehrs erforderlich sind.
ms.openlocfilehash: c631361a7ef6d4706632f59366adac3384a6d255
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827685"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Schätzen der Sprachnutzung und des Datenverkehrs für Skype for Business Server
 
Sie können die folgende Metrik verwenden, um den Benutzerdatenverkehr an jedem Standort und die Anzahl der Ports zu schätzen, die zur Unterstützung dieses Datenverkehrs erforderlich sind.
  
> Für **geringes Datenaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.
> 
> Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.
> 
> Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.
    
Die Anzahl der Ports wiederum bestimmt die Anzahl der Vermittlungsserver und Gateways, die erforderlich sind. Die PSTN-Gateways( Public Switched Telephone Network), die von den meisten Organisationen als Bereitstellungsumfang zwischen 2 ports und bis zu 960 Ports in Betracht ziehen. (Es gibt noch größere Gateways, die jedoch hauptsächlich von Telefoniedienstanbietern verwendet werden.)
  
Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.
  

