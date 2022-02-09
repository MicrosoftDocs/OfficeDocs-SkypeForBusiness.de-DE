---
title: Schätzen der VoIP-Nutzung und des Datenverkehrs für Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: d12ed7bcb19ab7399b15767a99ac6b13301e0c21
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402809"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Schätzen der VoIP-Nutzung und des Datenverkehrs für Skype for Business Server
 
Sie können die folgende Metrik verwenden, um den Benutzerdatenverkehr an jedem Standort und die Anzahl der Ports zu schätzen, die zur Unterstützung dieses Datenverkehrs erforderlich sind.
  
> Für **geringes Datenaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.
> 
> Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.
> 
> Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.
    
Die Anzahl der Ports bestimmt wiederum die Anzahl der erforderlichen Vermittlungsserver und Gateways. PsTN-Gateways (Public Switched Telephone Network), für die die meisten Organisationen eine Breite von 2 Ports bis zu 960 Ports in Betracht ziehen. (Es gibt noch größere Gateways, die jedoch hauptsächlich von Telefoniedienstanbietern verwendet werden.)
  
Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.
  

