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
ms.openlocfilehash: c473c3fc19138ac91b44dff8552555418d36533f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826165"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Anzeigen von Trunkkonfigurationsinformationen in Skype for Business Server

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert.

- Ob die Medienumgebung für Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.
- Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Bei der Installation von Skype for Business Server wird eine globale Auflistung von Sip-Trunk-Konfigurationseinstellungen für Sie erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).

**So zeigen Sie Informationen zur Sip-Trunk-Konfiguration mithilfe der Skype for Business Server-Systemsteuerung an**

1. Klicken Sie in der Skype for Business Server-Systemsteuerung auf **"Sprachrouting"** und dann auf **"Trunkkonfiguration".**
2. Auf der **Registerkarte "Trunkkonfiguration"** wird eine Liste aller Auflistungen von Trunkkonfigurationseinstellungen angezeigt. Für jede Auflistung werden Werte für die Eigenschaften  **"Name",** **"Bereich",** **"Bundesland"** und "Medienumgehung" sowie die Anzahl der **pstN-Verwendungen,** Anrufnummerregeln und Regeln für die angerufene Nummer angezeigt, die der Auflistung zugeordnet sind.   Um weitere Details zu einer Auflistung von Trunkkonfigurationseinstellungen anzuzeigen, klicken Sie auf die sammlung von Interesse, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**. Beachten Sie, dass Sie detaillierte Informationen nur für eine Auflistung von Trunkkonfigurationseinstellungen gleichzeitig anzeigen können.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Sip-Trunk-Konfigurationsinformationen mithilfe Windows PowerShell Cmdlets

Sip-Trunk-Konfigurationseinstellungen können mithilfe von Skype for Business Server PowerShell und dem cmdlet Get-CsTrunkConfiguration angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung Windows PowerShell. Details zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Lync Server Windows PowerShell-Blogartikel "Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell" unter https://go.microsoft.com/fwlink/p/?linkId=255876 . ERSETZEN ODER ENTFERNEN SIE DIESEN LINK.


**So zeigen Sie Informationen zur Sip-Trunk-Konfiguration an**

Geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE, um Informationen zu allen Konfigurationseinstellungen für den SIP-Trunk anzeigen zu können:

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
Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Get-CsTrunkConfiguration".](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)



