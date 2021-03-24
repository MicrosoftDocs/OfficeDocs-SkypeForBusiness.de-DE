---
title: Testen von SIP-Trunkkonfigurationseinstellungen in Skype for Business Server
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
ms.openlocfilehash: 87f5b8aa07a7545f30f1d0e8b81b33197ea704c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103021"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Testen von SIP-Trunkkonfigurationseinstellungen in Skype for Business Server

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:

- Ob die Medienumgebung für Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.
- Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Wenn Sie Skype for Business Server installieren, wird eine globale Auflistung von KONFIGURATIONSeinstellungen für den SIP-Trunk für Sie erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Administratoren können auch das [Cmdlet Test-CsTrunkConfiguration](/powershell/module/skype/Test-CsTrunkConfiguration) verwenden, um zu überprüfen, ob ein Trunk eine Zahl, die von einem Benutzer gewählt wird, in eine Nummer konvertieren kann, die vom Gateway verarbeitet werden kann.

Trunkkonfigurationseinstellungen können nur mithilfe von Windows PowerShell und dem cmdlet Test-CsTrunkConfiguration getestet werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell. 

**So testen Sie die Konfigurationseinstellungen für SIP-Trunks**

Mit diesem Befehl wird überprüft, ob die Trunkkonfigurationseinstellungen für den Standort "Redmond" die gewählte Nummer 4255551212 korrekt konvertieren können.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```