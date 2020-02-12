---
title: Anzeigen von trunk-Konfigurationsinformationen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter.
ms.openlocfilehash: 40820729727ec02e5494e69c773d7fbd3d7b1154
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888484"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Anzeigen von trunk-Konfigurationsinformationen in Skype for Business Server

SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter.

- Ob Medienumgehung für die Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.
- Ob die SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden trunk erforderlich ist.

Wenn Sie Skype for Business Server installieren, wird eine globale Sammlung von SIP-Trunk-Konfigurationseinstellungen für Sie erstellt. Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).

**So zeigen Sie SIP-Trunk-Konfigurationsinformationen mithilfe der Skype for Business Server-Systemsteuerung an**

1. Klicken Sie im Skype for Business Server-Control Panel auf **VoIP-Routing**und dann auf trunk- **Konfiguration**.
2. Auf dem Reiter " **trunk Configuration** " sehen Sie eine Liste aller ihrer trunk Configuration Settings-Sammlungen. für jede Sammlung werden Werte für die Eigenschaften **Name**, **Scope**, **State**und **Media Bypass** sowie die Anzahl der **PSTN-Nutzungen**, **Regeln**für die Rufnummernanzeige und **benannte Nummern Regeln** für die Sammlung angezeigt. Wenn Sie weitere Details zu einer Sammlung von trunk-Konfigurationseinstellungen anzeigen möchten, klicken Sie auf die Sammlung von Interesse, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**. Beachten Sie, dass Sie detaillierte Informationen nur für eine Sammlung von trunk-Konfigurationseinstellungen gleichzeitig anzeigen können.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von SIP-Trunk-Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets

Die SIP-Trunk-Konfigurationseinstellungen können mithilfe von Skype for Business Server PowerShell und dem Cmdlet Get-CsTrunkConfiguration angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Windows PowerShell-Remotesitzung ausgeführt werden. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von https://go.microsoft.com/fwlink/p/?linkId=255876Remote-PowerShell" unter. diesen Link ersetzen oder entfernen.


**So zeigen Sie die SIP-Trunk-Konfigurationsinformationen an**

Wenn Sie Informationen zu allen Ihren SIP-Trunk-Konfigurationseinstellungen anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:

```powershell
Get-CsTrunkConfiguration
```

Es werden etwa folgende Informationen zurückgegeben:

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
Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .



