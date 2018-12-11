---
title: Testen von SIP-trunkkonfigurationseinstellungen in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP-trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und das Gateway public switched Telephone Network, (PSTN), eine öffentliche IP-PBX (Branch Exchange) oder eine Session Border Controller (SBC) des Dienstanbieters. '
ms.openlocfilehash: d49b76c10505a009e6eed64d60632b52b08f3866
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222702"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Testen von SIP-trunkkonfigurationseinstellungen in Skype für Business Server

SIP-trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und das Gateway public switched Telephone Network, (PSTN), eine öffentliche IP-PBX (Branch Exchange) oder eine Session Border Controller (SBC) des Dienstanbieters. Diese Einstellungen geben unter anderem Folgendes an:

- Ob Medienumgehung für die Trunks aktiviert werden soll.
- Die Bedingungen, unter denen Pakete Real-Time Transport Control Protocol (RTCP) gesendet werden.
- Unabhängig davon, ob die Verschlüsselung secure Real-Time Transport Protocol (SRTP) für jeden Trunk erforderlich ist.

Wenn Sie Skype für Business Server installieren, wird eine globale Auflistung von SIP-trunkkonfigurationseinstellungen für Sie erstellt. Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Administratoren können auch das [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) -Cmdlet verwenden, um sicherzustellen, dass eine Zahl, wie von einem Benutzer eine Nummer gewählt wird, die vom Gateway behandelt werden können ein Trunk konvertiert werden kann.

Trunk-Konfigurationseinstellungen können nur mit Windows PowerShell und dem Test-CsTrunkConfiguration-Cmdlet. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 

**Testen von Konfigurationseinstellungen für SIP-Trunks**

Mit dem folgenden Befehl wird überprüft, ob mit den Trunk-Konfigurationseinstellungen für den Standort Redmond die gewählte Rufnummer 4255551212 ordnungsgemäß konvertiert werden kann.

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```