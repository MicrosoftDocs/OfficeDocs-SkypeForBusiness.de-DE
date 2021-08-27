---
title: Skype for Business Server – Testen der SIP-Trunkkonfigurationseinstellungen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'SIP-Trunkkonfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PST-Gateway, einer Nebenstellenanlage oder einem SBC beim Dienstanbieter. '
ms.openlocfilehash: 1684a2a45de1dd6608ab5fea70fa3bf2e1652723
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617821"
---
# <a name="skype-for-business-server---test-sip-trunk-configuration-settings"></a>Skype for Business Server – Testen der SIP-Trunkkonfigurationseinstellungen

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:

- Ob die Medienumgebung für Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.
- Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Wenn Sie Skype for Business Server installieren, wird eine globale Sammlung von SIP-Trunkkonfigurationseinstellungen für Sie erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Administratoren können auch das Cmdlet ["Test-CsTrunkConfiguration"](/powershell/module/skype/Test-CsTrunkConfiguration) verwenden, um zu überprüfen, ob ein Trunk eine von einem Benutzer gewählte Nummer in eine Nummer konvertieren kann, die vom Gateway verarbeitet werden kann.

Trunkkonfigurationseinstellungen können nur mit Windows PowerShell und dem cmdlet Test-CsTrunkConfiguration getestet werden. Dieses Cmdlet kann entweder über die Skype for Business Server Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 

**So testen Sie SIP-Trunkkonfigurationseinstellungen**

Mit diesem Befehl wird überprüft, ob die Trunkkonfigurationseinstellungen für den Standort Redmond die gewählte Nummer 4255551212 ordnungsgemäß konvertieren können.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
