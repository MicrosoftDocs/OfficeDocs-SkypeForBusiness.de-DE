---
title: Einschließen des Sicherheitsdesks in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planen der Einbeziehung des Sicherheitsdesks Ihrer Organisation in eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 63c54bb5cec1b81cfd8783a77ea3a685982a1b9e2e6040bf78880d32c9d1ab56
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290013"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Einschließen des Sicherheitsdesks in Skype for Business Server
 
Planen der Einbeziehung des Sicherheitsdesks Ihrer Organisation in eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP.
  
In Ihrem Unternehmen soll möglicherweise das Sicherheitsdesk in die Konfiguration für Notrufe eingebunden werden. Um entscheiden zu können, wie das Sicherheitsdesk in Ihre E9-1-1-Bereitstellung integriert werden kann, müssen Sie die folgenden Fragen beantworten.
  
**Soll das Sicherheitsdesk benachrichtigt werden, wenn ein Notruf abgesetzt wird?**
  
Sie können die Standortrichtlinie so konfigurieren, dass Skype for Business Server Chatbenachrichtigungen an die Skype for Business SIP-Adressen eines oder mehrerer Sicherheitsmitarbeiter sendet. Diese Warnungen enthalten den Namen, die Nummer und den Standort der Person, die den Notruf abgibt, und erleichtern das Sicherheitspersonal bei der Unterstützung bei der Notfallsituation.
    
**Möchten Sie für Notrufe eine Konferenzschaltung mit dem Sicherheitsdesk einrichten?**
  
Sofern vom Anbieter für die Notrufunterstützung unterstützt, können Sie in der Ortungsrichtlinie eine Rückrufnummer für Notrufe einschließen. Diese Nummer wird vom Anbieter verwendet, um für Notrufe eine Konferenzschaltung mit dem Sicherheitspersonal einzurichten.
    
> [!NOTE]
> Falls erforderlich, können Sie für jede Ortungsrichtlinie unterschiedliches Notrufpersonal konfigurieren. Auf diese Weise können Sie die Maßnahmen für unterschiedliche Unternehmensbereiche anpassen oder ein unterschiedliches Verhalten für Notrufe konfigurieren, die von innerhalb oder von außerhalb des Netzwerks erfolgen. Geben Sie die Mitarbeiter, die benachrichtigt werden sollen, mithilfe von Verteilergruppen an. 
  

