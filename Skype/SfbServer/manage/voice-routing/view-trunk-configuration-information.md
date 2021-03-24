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
localization_priority: Normal
description: Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert.
ms.openlocfilehash: 03b2ea63df8135edfdb3d63d9010aaace9266fd1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102991"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Anzeigen von Trunkkonfigurationsinformationen in Skype for Business Server

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert.

- Ob die Medienumgebung für Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.
- Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Wenn Sie Skype for Business Server installieren, wird eine globale Auflistung von KONFIGURATIONSeinstellungen für den SIP-Trunk für Sie erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).

**So zeigen Sie SIP-Trunkkonfigurationsinformationen mithilfe der Skype for Business Server-Systemsteuerung an**

1. Klicken Sie in der Skype for Business Server-Systemsteuerung auf **Voicerouting,** und klicken Sie dann auf **Trunkkonfiguration**.
2. Auf der **Registerkarte Trunkkonfiguration** wird eine Liste aller Auflistungen der Trunkkonfigurationseinstellungen angezeigt. Für jede Auflistung werden Werte für die Eigenschaften  **Name,** **Scope,** **State** und Media **bypass** angezeigt, zusammen mit der Anzahl der **PSTN-Verwendungen,** Anrufnummerregeln und Der Auflistung zugeordneten Regeln für Die Nummer aufgerufen.  Um weitere Details zu einer Auflistung von Trunkkonfigurationseinstellungen anzuzeigen, klicken Sie auf die Sammlung von Interesse, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**. Beachten Sie, dass Sie detaillierte Informationen nur für eine Auflistung von Trunkkonfigurationseinstellungen gleichzeitig anzeigen können.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von SIP-Trunkkonfigurationsinformationen mithilfe Windows PowerShell Cmdlets

Die Konfigurationseinstellungen für den SIP-Trunk können mithilfe von Skype for Business Server PowerShell und dem Get-CsTrunkConfiguration angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung ausgeführt Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Lync Server Windows PowerShell-Blogartikel "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter https://go.microsoft.com/fwlink/p/?linkId=255876 . ERSETZEN ODER ENTFERNEN SIE DIESEN LINK.


**So zeigen Sie Konfigurationsinformationen für SIP-Trunks an**

Geben Sie den folgenden Befehl in die Skype for Business Server-Verwaltungsshell ein, um Informationen zu allen Konfigurationseinstellungen für den SIP-Trunk eins zu sehen, und drücken Sie dann die EINGABETASTE:

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
Weitere Informationen finden Sie im Hilfethema für das [Cmdlet Get-CsTrunkConfiguration.](/powershell/module/skype/Get-CsTrunkConfiguration)