---
title: Einbeziehen des Security Desks in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planen Sie, wie Sie den Security Desk Ihrer Organisation in eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP einbeziehen möchten.
ms.openlocfilehash: 19fc8a01fcb51be3ce36435a5a657c3253716b2c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802455"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Einbeziehen des Security Desks in Skype for Business Server
 
Planen Sie, wie Sie den Security Desk Ihrer Organisation in eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP einbeziehen möchten.
  
In Ihrem Unternehmen soll möglicherweise das Sicherheitsdesk in die Konfiguration für Notrufe eingebunden werden. Um entscheiden zu können, wie das Sicherheitsdesk in Ihre E9-1-1-Bereitstellung integriert werden kann, müssen Sie die folgenden Fragen beantworten.
  
**Soll das Sicherheitsdesk benachrichtigt werden, wenn ein Notruf abgesetzt wird?**
  
Sie können die ortungsrichtlinie so konfigurieren, dass Skype for Business Server Sofortnachrichten (im) an die Skype for Business-SIP-Adressen von einem oder mehreren Sicherheitspersonal sendet. Diese Benachrichtigungen enthalten den Namen, die Nummer und den Standort der Person, die den Notruf durchführt, und erleichtert das Sicherheitspersonal bei der Unterstützung der Notfallsituation.
    
**Möchten Sie für Notrufe eine Konferenzschaltung mit dem Sicherheitsdesk einrichten?**
  
Sofern dies vom Anbieter für die Notrufunterstützung unterstützt wird, können Sie in der Ortungsrichtlinie eine Rückrufnummer für Notrufe einschließen. Diese Nummer wird vom Anbieter verwendet, um für Notrufe eine Konferenzschaltung mit dem Sicherheitspersonal einzurichten.
    
> [!NOTE]
> Falls erforderlich, können Sie für jede Ortungsrichtlinie unterschiedliches Notrufpersonal konfigurieren. Auf diese Weise können Sie die Maßnahmen für unterschiedliche Unternehmensbereiche anpassen oder ein unterschiedliches Verhalten für Notrufe konfigurieren, die von innerhalb oder von außerhalb des Netzwerks erfolgen. Geben Sie die Mitarbeiter, die benachrichtigt werden sollen, mithilfe von Verteilergruppen an. 
  

