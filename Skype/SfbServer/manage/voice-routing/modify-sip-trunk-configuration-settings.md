---
title: Ändern der SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. '
ms.openlocfilehash: fec64de813a9e4b0686e257ccfed7cb9c034467c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274926"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Ändern der SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server

SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:

- Ob Medienumgehung für die Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.
- Ob die SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden trunk erforderlich ist.

Wenn Sie Skype for Business Server installieren, wird eine globale Sammlung von SIP-Trunk-Konfigurationseinstellungen für Sie erstellt. Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Eine dieser Sammlungen kann später entweder über die Skype for Business Server-Systemsteuerung oder Windows PowerShell geändert werden.

Wenn Sie die SIP-Trunk-Konfigurationseinstellungen mithilfe des Skype for Business Server-Control Panels ändern, stehen Ihnen die folgenden Optionen zur Verfügung:

|Benutzeroberflächeneinstellung |PowerShell-Parameter |Beschreibung |
|--|--|--|
|Name|Identität|Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung von Trunkkonfigurationseinstellungen nicht ändern.|
|Beschreibung|Beschreibung|Bietet Administratoren eine Möglichkeit, zusätzliche Informationen zu den Einstellungen zu speichern (z. B. Zweck der Trunkkonfiguration).|
|Maximal unterstützte frühe Dialoge|MaxEarlyDialogs|Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.|
|Unterstützte Verschlüsselungsstufe|SRTPMode|Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest. Bei der Medienumgehung muss dieser Wert mit der Einstellung „EncryptionLevel“ in der Medienkonfiguration kompatibel sein. Die Medienkonfiguration wird mithilfe der Cmdlets New-CsMediaConfiguration und CsMediaConfiguration gesetzt.<br/>Gültige Werte sind:<br/><br/>**Erforderlich**: SRTP-Verschlüsselung muss verwendet werden.<br/>**Optional**: srtp wird verwendet, wenn es vom Gateway unterstützt wird.<br/>**Nicht unterstützt**: die SRTP-Verschlüsselung wird nicht unterstützt und wird daher nicht verwendet.<br/><br/>„SRTPMode“ wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird „SRTPMode“ intern auf „Nicht unterstützt“ festgelegt.|
|Support melden|Enable3pccRefer<br/>EnableReferSupport|Mit der Einstellung **Senden der Weiterleitung an Gateway aktivieren** unterstützt der Trunk den Empfang von Weiterleitungsanforderungen vom Vermittlungsserver.<br/>Mit der Einstellung **Weiterleitung mithilfe von Drittanbieteranrufsteuerung aktivieren** kann das 3pcc-Protokoll verwendet werden, damit weitergeleitete Anrufe den gehosteten Standort umgehen können. 3pcc ist auch unter dem Namen „Third Party Call Control“ bekannt und tritt auf, wenn ein Drittanbieter verwendet wird, um zwei Anrufer miteinander zu verbinden (z. B. wenn ein Anruf von Person A an Person B über eine Telefonzentrale durchgestellt wird).|
|Medienumgehung aktivieren|EnableBypass|Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn auch **Zentralisierte Medienverarbeitung** aktiviert ist.|
|Zentralisierte Medienverarbeitung|ConcentratedTopology|Gibt an, ob ein bekannter Medienendpunkt vorhanden ist. (Ein Beispiel für einen bekannten Medienendpunkt ist ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse hat wie der Signaldatenverkehrendpunkt.)|
|RTP-Verriegelung aktivieren|EnableRTPLatching|Gibt an, ob SIP-Trunks die RTP-Verriegelung unterstützen oder nicht. Die RTP-Verriegelung ist eine Technologie, die RTP-/RTCP-Verbindungen über NAT (Network Address Translator, Netzwerkadressenübersetzung) oder eine Firewall ermöglicht.|
|Weiterleitung der Anrufliste aktivieren|ForwardCallHistory|Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.|
|Weiterleitung von P-Asserted-Identity-Daten aktivieren|ForwardPAI|Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.|
|Failovertimer für Ausgangsrouting aktivieren|EnableFastFailoverTimer|Gibt an, ob ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet werden. Wenn keine weiteren Trunks verfügbar sind, wird der Anruf automatisch beendet. In einer Organisation mit langsamen Netzwerk- und Gatewayreaktionen könnte dies dazu führen, dass Anrufe unnötigerweise beendet werden.|
|Zugeordnete PSTN-Verwendungen|PSTNUsages|Dem Trunk zugewiesene Auflistung von PSTN-Verwendungen.|
|Übersetzte Nummer zum Testen|Nicht zutreffend|Eine Telefonnummer, die für Ad-hoc-Tests der Trunkkonfigurationseinstellungen verwendet werden kann.|
|Zugehörige Übersetzungsregeln|OutboundTranslationRulesList|Sammlung an Regeln für die Telefonnummernübersetzung für Anrufe, die per Ausgangsrouting verarbeitet werden (Anrufe, die an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weitergeleitet werden).|
|Übersetzungsregeln für die gewählte Nummer|OutboundCallingNumberTranslationRulesList|Dem Trunk zugewiesene Auflistung von ausgehenden Übersetzungsregeln für Telefonnummern.|
|Testtelefonnummer|Nicht zutreffend|Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.|
|Anrufende Nummer|Nicht zutreffend|Gibt an, dass die zu testende Telefonnummer die Telefonnummer des Anrufers ist.|
|Angerufene Nummer|-|Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.|
|||

> [!Note]
> Die Skype for Business Server-CsTrunkConfiguration-Cmdlets unterstützen zusätzliche Eigenschaften, die nicht in der Skype for Business Server-Systemsteuerung angezeigt werden. Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTrunkConfiguration) ". 

**So ändern Sie die SIP-Trunk-Konfigurationseinstellungen mithilfe des Skype for Business Server-Control Panels**

1. Klicken Sie im Skype for Business Server-Control Panel auf **VoIP-Routing**und dann auf trunk- **Konfiguration**.
2. Doppelklicken Sie auf der Registerkarte **Trunkkonfiguration** auf die Trunkkonfigurationseinstellungen, die Sie ändern möchten. Beachten Sie, dass Sie immer nur eine Einstellung bearbeiten können. Wenn Sie die gleichen Änderungen an mehreren Sammlungen vornehmen möchten, verwenden Sie Windows PowerShell.
3. Nehmen Sie im Dialogfeld **trunk-Konfiguration bearbeiten** die entsprechende Auswahl vor, und klicken Sie dann auf **OK**.
4. Die Eigenschaft State für die Sammlung wird als Commit nicht ausgeführt angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit**, und klicken Sie dann auf **alle**übernehmen.
5. Klicken Sie im Dialogfeld nicht **festgeschriebene sprach Konfigurationseinstellungen**auf **OK**.
6. Klicken Sie im Dialogfeld **Skype for Business Server Control Panel** auf **OK**.
