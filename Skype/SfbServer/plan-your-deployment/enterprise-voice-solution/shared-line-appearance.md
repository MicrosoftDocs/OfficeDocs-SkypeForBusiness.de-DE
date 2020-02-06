---
title: Planen der Funktion „Gemeinsame Leitungen“ in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: In diesem Thema erfahren Sie, wie Sie in Skype for Business Server 2015, dem kumulativen Update vom November 2015, die gemeinsame Leitungsdarstellung (SLA) planen.
ms.openlocfilehash: 14f0f6cbd163ecff42543d3ad57bed0020434cfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802435"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Planen der Funktion „Gemeinsame Leitungen“ in Skype for Business Server 2015
 
In diesem Thema erfahren Sie, wie Sie in Skype for Business Server 2015, dem kumulativen Update vom November 2015, die gemeinsame Leitungsdarstellung (SLA) planen. 
  
Die Darstellung der freigegebenen Zeile ist eine Funktion in Skype for Business für die Behandlung mehrerer Anrufe an eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird. SLA kann alle Enterprise-VoIP-aktivierten Skype for Business-Benutzer als freigegebene Nummer mit mehreren Zeilen konfigurieren, um auf mehrere Anrufe zu reagieren. Die Anrufe werden für die freigegebene Nummer nicht tatsächlich empfangen, sondern an Benutzer weitergeleitet, die als Stellvertretungen für die freigegebene Nummer fungieren. Jeder Delegierte kann den Anruf annehmen, während die restlichen Teilnehmer eine Benachrichtigung auf dem Telefon erhalten, wer den Anruf aufgenommen hat und welche Zeile damit ausgelastet ist. Die Anzahl der Zeilen und die Stellvertretungen können für eine freigegebene Nummer in SLA konfiguriert werden. Darüber hinaus können erweiterte Optionen wie BusyOption (was in einer Situation geschieht, wenn alle Zeilen ausgelastet sind) und MissedCallOption (der Fall, in dem keiner der Stellvertretungen einen Anruf annimmt) auch für eine freigegebene Nummer konfiguriert werden.
  
SLA wird nur auf den folgenden Telefongeräten unterstützt (es wird nicht für Skype for Business-Clients auf Computern, Mobiltelefonen oder anderen Geräten unterstützt): 
  
- Polycom VVX300 mit Firmwareupdate 5.4.1
    
- Polycom VVX400 mit Firmwareupdate 5.4.1
    
- Polycom VVX500 mit Firmwareupdate 5.4.1
    
- Polycom VVX600 mit Firmwareupdate 5.4.1
    
SLA ist ein neues Feature in Skype for Business Server, 2015, Kumulatives Update vom November. 
  
Informationen zum Bereitstellen von SLA finden Sie unter [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).
  
## <a name="feature-list"></a>Liste der Funktionen

Das Einrichten einer SLA-Gruppe macht Folgendes möglich:
  
- Alle Stellvertretungen in der Gruppe können eingehende Anrufe für dieselbe gemeinsam genutzte Nummer annehmen. Diese Anrufe können Festnetz- oder SIP-Anrufe sein.
    
- Stellvertretungen können Anrufe halten und annehmen.
    
- Stellvertretungen können Anrufe an eine Nummer außerhalb der SLA-Gruppe weiterleiten.
    
- Stellvertretungen bekommen angezeigt, wie viele Anrufe es aktuell für die gemeinsam genutzte Nummer gibt, und sie können den Status jedes einzelnen Anrufs einsehen.
    
- Sie können eine maximale Anzahl gleichzeitiger Anrufe für die gemeinsam genutzte Nummer konfigurieren. Sie können auch einstellen, wie zusätzliche Anrufe behandelt werden sollen, wenn die maximale Anzahl erreicht worden ist. Zusätzliche Anrufe können mit einem Besetztzeichen abgewiesen, an eine alternative Nummer oder an Voicemail weitergeleitet werden.
    
- Sie können konfigurieren, wie entgangene Anrufe (solche, die nach einer festgelegten Zeit nicht angenommen worden sind) behandelt werden sollen. Wenn Sie Voicemail für die Gruppenidentität aktivieren, gehen entgangene Anrufe automatisch an die Voicemail. Wenn Voicemail für die Gruppenidentität (gemeinsam genutzte Nummer) nicht aktiviert ist, können Sie wählen, ob entgangene Anrufe mit einem Besetztzeichen abgewiesen, an eine alternative Nummer weitergeleitet oder getrennt werden sollen.
    

