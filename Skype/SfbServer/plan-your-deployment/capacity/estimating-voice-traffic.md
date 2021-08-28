---
title: Schätzen der VoIP-Nutzung und des Datenverkehrs für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Sie können die folgende Metrik verwenden, um den Benutzerdatenverkehr an jedem Standort und die Anzahl der Ports zu schätzen, die zur Unterstützung dieses Datenverkehrs erforderlich sind.
ms.openlocfilehash: 8661bf6c0222228ec22f582ebae0167cd23242a8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629547"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Schätzen der VoIP-Nutzung und des Datenverkehrs für Skype for Business Server
 
Sie können die folgende Metrik verwenden, um den Benutzerdatenverkehr an jedem Standort und die Anzahl der Ports zu schätzen, die zur Unterstützung dieses Datenverkehrs erforderlich sind.
  
> Für **geringes Datenaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.
> 
> Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.
> 
> Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.
    
Die Anzahl der Ports bestimmt wiederum die Anzahl der erforderlichen Vermittlungsserver und Gateways. Die PSTN-Gateways (Public Switched Telephone Network), die die meisten Organisationen in Betracht ziehen, einen Bereich von 2 Ports bis zu 960 Ports bereitzustellen. (Es gibt noch größere Gateways, die jedoch hauptsächlich von Telefoniedienstanbietern verwendet werden.)
  
Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.
  

