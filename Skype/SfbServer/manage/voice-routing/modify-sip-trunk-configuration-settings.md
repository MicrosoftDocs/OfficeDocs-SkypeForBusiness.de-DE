---
title: Ändern von SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server
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
description: 'Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. '
ms.openlocfilehash: 5d87c9be3cbc609713f9ee8184cfe750ba5180b2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036243"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Ändern von SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:

- Ob die Medienumgebung für Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.
- Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Wenn Sie Skype for Business Server installieren, wird eine globale Sammlung von SIP-trunkkonfigurationseinstellungen für Sie erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Eine dieser Auflistungen kann später entweder über die Skype for Business Server-Systemsteuerung oder Windows PowerShell geändert werden.

Beim Ändern von SIP-Trunk-Konfigurationseinstellungen mithilfe der Skype for Business Server Server-Systemsteuerung stehen Ihnen die folgenden Optionen zur Verfügung:

|UI-Einstellung |PowerShell-Parameter |Beschreibung |
|--|--|--|
|Name|Identität|Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung an Trunkkonfigurationseinstellungen nicht ändern.|
|Beschreibung|Beschreibung|Bietet Administratoren eine Möglichkeit, zusätzliche Informationen zu den Einstellungen zu speichern (z. B. Zweck der Trunkkonfiguration).|
|Maximal unterstützte frühe Dialoge|MaxEarlyDialogs|Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.|
|Unterstützte Verschlüsselungsstufe|"Srtpmode"|Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest. Bei der Medienumgehung muss dieser Wert mit der Einstellung "EncryptionLevel" in der Medienkonfiguration kompatibel sein. Die Medienkonfiguration wird mithilfe der Cmdlets New-CsMediaConfiguration und setCsMediaConfiguration festgelegt.<br/>Gültige Werte sind:<br/><br/>**Erforderlich**: SRTP-Verschlüsselung muss verwendet werden.<br/>**Optional**: srtp wird verwendet, wenn es vom Gateway unterstützt wird.<br/>**Nicht unterstützt**: die SRTP-Verschlüsselung wird nicht unterstützt und wird daher nicht verwendet.<br/><br/>"SRTPMode" wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird "SRTPMode" intern auf "Not Supported" festgelegt.|
|Support melden|Enable3pccRefer<br/>"Enablerefersupport"|Mit der Einstellung **Refer-Anforderungen an das Gateway senden** unterstützt der Trunk den Empfang von Refer-Anforderungen vom Vermittlungsserver.<br/>Mit der Einstellung **Refer-Anforderungen mit 3pcc senden** kann das 3pcc-Protokoll verwendet werden, damit weitergeleitete Anrufe den gehosteten Standort umgehen können. 3pcc ist auch unter dem Namen "Third Party Call Control" bekannt und tritt auf, wenn ein Drittanbieter verwendet wird, um zwei Anrufer miteinander zu verbinden (z. B. wenn ein Anruf von Person A an Person B über eine Telefonzentrale durchgestellt wird).|
|Medienumgehung aktivieren|EnableBypass|Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn auch **Zentrale Medienverarbeitung** aktiviert ist.|
|Zentrale Medienverarbeitung|"Concentratedtopology"|Gibt an, ob ein bekannter Medienendpunkt vorhanden ist. (Ein Beispiel für einen bekannten Medienendpunkt ist ein PSTN-Gateway, bei dem der Medienendpunkt die gleiche IP-Adresse hat wie der Signaldatenverkehr-Endpunkt.)|
|RTP-Latching aktivieren|EnableRTPLatching|Gibt an, ob SIP-Trunks RTP-Latching unterstützen oder nicht. RTP-Latching ist eine Technologie, die RTP-/RTCP-Verbindungen über NAT (Network Address Translator, Netzwerkadressenübersetzung) oder eine Firewall ermöglicht.|
|Weiterleiten der Anrufliste aktivieren|ForwardCallHistory|Gibt an, ob Informationen zum Anruferverlauf durch den Trunk weitergeleitet werden.|
|Weiterleiten von P-Asserted-Identity-Daten aktivieren|ForwardPAI|Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.|
|Timer für Ausgangsroutingfailover aktivieren|EnableFastFailoverTimer|Gibt an, ob ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet werden. Wenn keine weiteren Trunks verfügbar sind, wird der Anruf automatisch beendet. In einer Organisation mit langsamen Netzwerk- und Gateway-Reaktionen könnte dies dazu führen, dass Anrufe unnötigerweise beendet werden.|
|Zugeordnete PSTN-Verwendungen|PSTNUsages|Eine Sammlung von dem Trunk zugewiesenen PSTN-Verwendungen.|
|Übersetzte Nummer zum Testen|Nicht zutreffend|Eine Telefonnummer, die für Ad-hoc-Tests der Trunkkonfigurationseinstellungen verwendet werden kann.|
|Zugehörige Übersetzungsregeln|OutboundTranslationRulesList|Sammlung an Regeln für die Telefonnummernübersetzung für Anrufe, die per Ausgangsrouting verarbeitet werden (Anrufe, die an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weitergeleitet werden).|
|Übersetzungsregeln für angerufene Nummern|OutboundCallingNumberTranslationRulesList|Sammlung an Regeln für die Nummernübersetzung für ausgehende Anrufe, die dem Trunk zugewiesen sind.|
|Testtelefonnummer|Nicht zutreffend|Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.|
|Anrufende Nummer|Nicht zutreffend|Gibt an, dass die zu testende Telefonnummer die Telefonnummer des Anrufers ist.|
|Angerufene Nummer|Nicht zutreffend|Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.|
|||

> [!Note]
> Die Skype for Business Server CsTrunkConfiguration-Cmdlets unterstützen zusätzliche Eigenschaften, die nicht in der Skype for Business Server-Systemsteuerung angezeigt werden. Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration) ". 

**So ändern Sie die SIP-Trunk-Konfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung**

1. Klicken Sie in der Skype for Business Server-Systemsteuerung auf **VoIP-Routing**, und klicken Sie dann auf **trunk Konfiguration**.
2. Doppelklicken Sie auf der Registerkarte **Trunkkonfiguration** auf die Trunkkonfigurationseinstellungen, die Sie ändern möchten. Beachten Sie, dass Sie immer nur eine Einstellung bearbeiten können. Wenn Sie die gleichen Änderungen an mehreren Sammlungen vornehmen möchten, verwenden Sie Windows PowerShell.
3. Nehmen Sie im Dialogfeld **trunk Konfiguration bearbeiten** die entsprechenden Optionen vor, und klicken Sie dann auf **OK**.
4. Die Eigenschaft State für die Auflistung wird in Commit nicht ausgeführt aktualisiert. Um die Änderungen zu übernehmen und die Auflistung zu löschen, klicken Sie auf **Commit**, und klicken Sie dann auf **Commit für alle**.
5. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellung für nicht zugesicherte Einstellungen**auf **OK**.
6. Klicken Sie im Dialogfeld **Skype for Business Server-System** Steuerung auf **OK**.
