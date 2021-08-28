---
title: Anzeigen von Trunkkonfigurationsinformationen in Skype for Business Server
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
description: Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert.
ms.openlocfilehash: 204f6f17387499719cf3b4bbe33638a849a4e363
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614065"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Anzeigen von Trunkkonfigurationsinformationen in Skype for Business Server

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert.

- Ob die Medienumgebung für Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.
- Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Wenn Sie Skype for Business Server installieren, wird eine globale Auflistung von SIP-Trunkkonfigurationseinstellungen für Sie erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).

**So zeigen Sie SIP-Trunkkonfigurationsinformationen mithilfe Skype for Business Server Systemsteuerung an**

1. Klicken Sie in der systemsteuerung Skype for Business Server auf **VoIP-Routing** und dann auf **Trunkkonfiguration.**
2. Auf der Registerkarte **"Trunkkonfiguration"** wird eine Liste aller Sammlungen der Trunkkonfigurationseinstellungen angezeigt. Für jede Auflistung werden Werte für die Eigenschaften **Name,** **Bereich,** **Status** und **Medienumgehung** zusammen mit der Anzahl der **PSTN-Verwendungen,** **Anrufnummernregeln** und Der Auflistung zugeordneten Regeln für **angerufene Nummern** angezeigt. Um weitere Details zu einer Sammlung von Trunkkonfigurationseinstellungen anzuzeigen, klicken Sie auf die sammlung von Interesse, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen.** Beachten Sie, dass Sie detaillierte Informationen jeweils nur für eine Sammlung von Trunkkonfigurationseinstellungen anzeigen können.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von SIP-Trunkkonfigurationsinformationen mithilfe Windows PowerShell Cmdlets

SIP-Trunkkonfigurationseinstellungen können mit Skype for Business Server PowerShell und dem Cmdlet Get-CsTrunkConfiguration angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel "Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell" unter "Lync Server https://go.microsoft.com/fwlink/p/?linkId=255876 Windows PowerShell". ERSETZEN ODER ENTFERNEN SIE DIESEN LINK.


**So zeigen Sie SIP-Trunkkonfigurationsinformationen an**

Geben Sie zum Anzeigen von Informationen zu allen SIP-Trunkkonfigurationseinstellungen den folgenden Befehl in die Skype for Business Server Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:

```powershell
Get-CsTrunkConfiguration
```

Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:

```console
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Get-CsTrunkConfiguration".](/powershell/module/skype/Get-CsTrunkConfiguration)