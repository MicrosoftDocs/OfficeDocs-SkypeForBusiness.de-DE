---
title: Testen der Konfigurationseinstellungen für den SIP-Trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. '
ms.openlocfilehash: 1489fe1e45223bac6b62ed23a09212a569ea7838
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826185"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Testen der Konfigurationseinstellungen für den SIP-Trunk in Skype for Business Server

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:

- Ob die Medienumgebung für Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.
- Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Bei der Installation von Skype for Business Server wird eine globale Auflistung von Sip-Trunk-Konfigurationseinstellungen erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Administratoren können auch das Cmdlet ["Test-CsTrunkConfiguration"](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) verwenden, um zu überprüfen, ob ein Trunk eine von einem Benutzer gewählte Nummer in eine Nummer konvertieren kann, die vom Gateway verarbeitet werden kann.

Trunkkonfigurationseinstellungen können nur mithilfe von Windows PowerShell und dem Test-CsTrunkConfiguration getestet werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell. 

**So testen Sie die Konfigurationseinstellungen für den SIP-Trunk**

Mit diesem Befehl wird überprüft, ob die Trunkkonfigurationseinstellungen für den Standort "Redmond" die gewählte Nummer 4255551212 ordnungsgemäß konvertieren können.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
