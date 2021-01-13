---
title: Skype Room System- und Skype for Business-Verbundpartner
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: In diesem Thema erfahren Sie, wie Sie Skype Room System für Skype for Business-Verbundpartner einrichten.
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820805"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Room System- und Skype for Business-Verbundpartner
 
In diesem Thema erfahren Sie, wie Sie Skype Room System für Skype for Business-Verbundpartner einrichten.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Room System- und Skype for Business-Verbundpartner

Skype Room System basiert auf dem Link "An Skype for Business Meeting teilnehmen" in der Kalender-Besprechungsanfrage. Der Link zum Beitreten befindet sich in der Regel im Textkörper einer Besprechungsanfrage. Skype Room System hängt jedoch davon ab, dass dieser Link in den MAPI-Eigenschaften der Nachricht vorhanden ist. Wenn diese Besprechungsanfrage an Remoteorganisationen (Skype for Business-Verbundpartner) gesendet wird, zeigt das Skype Room System der Remoteorganisation standardmäßig den Link für den Besprechungsteilzug nicht im Kalender an. Tatsächlich können alle Benutzer von Outlook in der Remoteorganisation nicht mit einem rechtsklicken auf das Kalenderelement oder innerhalb der Besprechungserinnerung an der Skype for Business-Besprechung teilnehmen. Sie müssen die Besprechungs-Einladung öffnen und im Nachrichtentext auf "An Skype for Business Meeting teilnehmen" klicken. 
  
Der Grund für diese Einschränkung ist, dass Outlook und Microsoft Exchange keine spezielle Methode zum Packen von Informationen zum Senden von Nachrichten über das Internet verwenden. Diese Als TNEF (Transport Neutral Encapsulation Format) bezeichnete Methode ist für extern von einer Exchange-Organisation gesendete Nachrichten standardmäßig deaktiviert. Damit ein Link zum Beitreten zu einer Besprechung auf einem Remote-Skype Room System angezeigt wird, muss die sendende Organisation TNEF mithilfe des folgenden Befehls aktivieren:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Nachdem TNEF für die Remoteorganisation aktiviert wurde, werden alle über das Internet an die Organisation gesendeten Nachrichten als Anlage im TNEF-Format gesendet. Wenn TNEF aktiviert ist, kann Skype Room System, wenn eine Skype for Business-Besprechungsanfrage an den Skype for Business-Verbundpartner gesendet wird, die Teilnahme an Skype for Business Meeting rendern, und Remotebenutzer können an Skype for Business-Besprechungen teilnehmen. 
