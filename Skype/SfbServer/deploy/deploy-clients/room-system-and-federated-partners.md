---
title: Skype Raumsystem und Skype for Business Verbundpartner
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 'In diesem Thema erfahren Sie, wie Sie Skype Raumsystem für Skype for Business Verbundpartner einrichten.'
---

# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Raumsystem und Skype for Business Verbundpartner
 
In diesem Thema erfahren Sie, wie Sie Skype Raumsystem für Skype for Business Verbundpartner einrichten.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Raumsystem und Skype for Business Verbundpartner

Skype Raumsystem basiert auf dem Link "An Skype for Business Besprechung teilnehmen" in der Kalenderbesprechungsanfrage. Der Verknüpfungslink befindet sich in der Regel im Textkörper einer Besprechungsanfrage. Skype Room System hängt jedoch davon ab, ob dieser Link in den MAPI-Eigenschaften der Nachricht vorhanden ist. Wenn diese Besprechungsanfrage an Remoteorganisationen (Skype for Business Verbundpartner) gesendet wird, zeigt das Skype Raumsystem der Remoteorganisation standardmäßig nicht den Besprechungsbeitrittslink im Kalender an. Tatsächlich können alle Outlook Benutzer in der Remoteorganisation nicht mit einem Rechtsklick auf das Kalenderelement oder aus der Besprechungserinnerung an der Skype for Business Besprechung teilnehmen. Sie müssen die Besprechungseinladung öffnen und im Textkörper der Nachricht auf "An Skype for Business Besprechung teilnehmen" klicken. 
  
Der Grund für diese Einschränkung ist, dass Outlook und Microsoft Exchange keine spezielle Methode zum Verpacken von Informationen zum Senden von Nachrichten über das Internet verwenden. Diese Methode, die als Transport Neutral Encapsulation Format (TNEF) bezeichnet wird, ist standardmäßig für Nachrichten deaktiviert, die extern von einer Exchange Organisation gesendet werden. Damit ein Link zur Besprechungsteilnahme auf einem Remote-Skype Room System angezeigt wird, muss die sendende Organisation TNEF mithilfe des folgenden Befehls aktivieren:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Nachdem TNEF für die Remoteorganisation aktiviert wurde, werden nachrichten, die über das Internet an die Organisation gesendet werden, als Anlage im TNEF-Format gesendet. Wenn TNEF aktiviert ist und eine Skype for Business Besprechungsanfrage an den Skype for Business Verbundpartner gesendet wird, kann Skype Raumsystem die Besprechungsteilnahme Skype for Business rendern, und Remotebenutzer können teilnehmen Skype for Business Besprechungen. 
