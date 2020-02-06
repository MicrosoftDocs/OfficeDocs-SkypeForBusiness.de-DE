---
title: Schätzen der sprach Nutzung und des Datenverkehrs für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Sie können die folgende Metrik verwenden, um den Benutzerdatenverkehr an jeder Website und die Anzahl der Ports zu schätzen, die für die Unterstützung des Datenverkehrs erforderlich sind.
ms.openlocfilehash: f324a3030a8265288a30062fdfc1040a1aea8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816064"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Schätzen der sprach Nutzung und des Datenverkehrs für Skype for Business Server
 
Sie können die folgende Metrik verwenden, um den Benutzerdatenverkehr an jeder Website und die Anzahl der Ports zu schätzen, die für die Unterstützung des Datenverkehrs erforderlich sind.
  
> Für **geringes Datenverkehrsaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.
> 
> Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.
> 
> Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.
    
Die Anzahl der Ports wiederum bestimmt die Anzahl der Vermittlungsserver und Gateways, die erforderlich sind. Die PSTN-Gateways (Public Switched Telephone Network), die in den meisten Organisationen für die Bereitstellung von Bereichsgröße von 2 Anschlüssen bis zu 960-Ports in Frage kämen. (Es gibt sogar größere Gateways, die aber hauptsächlich von Telefondienstanbietern verwendet werden.)
  
Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.
  

