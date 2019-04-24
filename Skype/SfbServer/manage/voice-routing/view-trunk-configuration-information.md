---
title: Anzeigen von Trunk-Konfigurationsinformationen in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: SIP-trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und das Gateway public switched Telephone Network, (PSTN), eine öffentliche IP-PBX (Branch Exchange) oder eine Session Border Controller (SBC) des Dienstanbieters.
ms.openlocfilehash: 6ba97fa4650b8d62be625256ff4d3b9a3bb7cc68
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32195493"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Anzeigen von Trunk-Konfigurationsinformationen in Skype für Business Server

SIP-trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und das Gateway public switched Telephone Network, (PSTN), eine öffentliche IP-PBX (Branch Exchange) oder eine Session Border Controller (SBC) des Dienstanbieters.

- Ob Medienumgehung für die Trunks aktiviert werden soll.
- Die Bedingungen, unter denen Pakete Real-Time Transport Control Protocol (RTCP) gesendet werden.
- Unabhängig davon, ob die Verschlüsselung secure Real-Time Transport Protocol (SRTP) für jeden Trunk erforderlich ist.

Wenn Sie Skype für Business Server installieren, wird eine globale Auflistung von SIP-trunkkonfigurationseinstellungen für Sie erstellt. Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).

**So zeigen Sie SIP-Trunk-Konfigurationsinformationen mithilfe von Skype Business Server-Systemsteuerung an**

1. Klicken Sie in der Skype Business Server-Systemsteuerung klicken Sie auf **VoIP-Routing**, und klicken Sie dann auf **Trunkkonfiguration**.
2. Klicken Sie auf der Registerkarte **Trunkkonfiguration** sehen Sie eine Liste mit allen Trunk Configuration Settings Sammlungen. für jede Auflistung sehen Sie Werte für die Eigenschaften **Name**, **Bereich**, **Status**und **die medienumgehung** sowie die Anzahl der **PSTN-Verwendungen**, **Aufrufen für Rufnummern**und **genannte Zahl Regeln** verknüpft ist mit der Auflistung. Um weitere Details zu einer Auflistung von trunkkonfigurationseinstellungen anzuzeigen, klicken Sie auf die Auflistung von Interesse, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**. Beachten Sie, dass Sie detaillierte Informationen nur für eine Auflistung von trunkkonfigurationseinstellungen zu einem Zeitpunkt anzeigen können.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von SIP-Trunk-Konfigurationsinformationen mithilfe von Windows PowerShell-cmdlets

SIP-Trunk-Konfigurationen, die Einstellungen mithilfe von Skype für Business Server-PowerShell und dem Cmdlet Get-CsTrunkConfiguration angezeigt werden können. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer Windows PowerShell-Remotesitzung ausgeführt werden. Ausführliche Informationen zur Verwendung von remote Windows PowerShell für Business Server eine Verbindung mit Skype finden Sie im Lync Server-Windows PowerShell-Blog-Artikel "Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell" unter http://go.microsoft.com/fwlink/p/?linkId=255876. ERSETZEN ODER DIESEN LINK ENTFERNEN.


**So zeigen Sie SIP-Trunk-Konfigurationsinformationen an**

Anzeigen von Informationen zu allen SIP-Trunk-Konfigurationseinstellungen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:

`Get-CsTrunkConfiguration`

Es werden etwa folgende Informationen zurückgegeben:

```
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
Weitere Informationen finden Sie im Hilfethema zum [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) -Cmdlet.



