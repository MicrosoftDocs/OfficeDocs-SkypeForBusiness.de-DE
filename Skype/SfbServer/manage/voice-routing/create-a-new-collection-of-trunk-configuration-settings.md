---
title: Erstellen einer neuen Auflistung von Trunk-Konfigurationseinstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: SIP-trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und das Gateway public switched Telephone Network, (PSTN), eine öffentliche IP-PBX (Branch Exchange) oder eine Session Border Controller (SBC) des Dienstanbieters.
ms.openlocfilehash: 86a731c07f3c7289e5eabcd74bb3ccf37ec4df9d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890451"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Erstellen einer neuen Auflistung von Trunk-Konfigurationseinstellungen in Skype für Business Server

SIP-trunkkonfigurationseinstellungen definieren die Beziehung und Funktionen zwischen einem Vermittlungsserver und das Gateway public switched Telephone Network, (PSTN), eine öffentliche IP-PBX (Branch Exchange) oder eine Session Border Controller (SBC) des Dienstanbieters. Diese Einstellungen geben unter anderem Folgendes an:
- Ob Medienumgehung für die Trunks aktiviert werden soll.
- Die Bedingungen, unter denen Pakete Real-Time Transport Control Protocol (RTCP) gesendet werden.
- Unabhängig davon, ob die Verschlüsselung secure Real-Time Transport Protocol (SRTP) für jeden Trunk erforderlich ist.

Wenn Sie Skype für Business Server installieren, wird eine globale Auflistung von SIP-trunkkonfigurationseinstellungen für Sie erstellt. Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).

Beim Erstellen von SIP-Trunk Configuration Settings UsingSkype für Business Server-Systemsteuerung sind die folgenden Optionen zur Verfügung:

|Benutzeroberflächeneinstellung | PowerShell-Parameter | Beschreibung |
|--|--|--|
|Name|Identität|Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung von Trunkkonfigurationseinstellungen nicht ändern.|
|Beschreibung|Beschreibung|Bietet Administratoren eine Möglichkeit, zusätzliche Informationen zu den Einstellungen zu speichern (z. B. Zweck der Trunkkonfiguration).|
|Maximal unterstützte frühe Dialoge|MaxEarlyDialogs|Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.|
|Unterstützte Verschlüsselungsstufe|SRTPMode|Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest. Bei der Medienumgehung muss dieser Wert mit der Einstellung „EncryptionLevel“ in der Medienkonfiguration kompatibel sein. Medienkonfiguration wird mithilfe der Cmdlets [New-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration) und [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration) festgelegt.<br/>Gültige Werte sind:<br/><br/>**Erforderlich**: SRTP-Verschlüsselung muss verwendet werden.<br/>**Optional**: SRTP wird verwendet, wenn es vom Gateway unterstützt.<br/>**Nicht unterstützt**: SRTP-Verschlüsselung wird nicht unterstützt und daher nicht verwendet werden.<br/><br/>„SRTPMode“ wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird „SRTPMode“ intern auf „Nicht unterstützt“ festgelegt.|
|Support melden|Enable3pccRefer<br/>EnableReferSupport|Mit der Einstellung **Senden der Weiterleitung an Gateway aktivieren** unterstützt der Trunk den Empfang von Weiterleitungsanforderungen vom Vermittlungsserver.<br/>Mit der Einstellung **Weiterleitung mithilfe von Drittanbieteranrufsteuerung aktivieren** kann das 3pcc-Protokoll verwendet werden, damit weitergeleitete Anrufe den gehosteten Standort umgehen können. 3pcc ist auch unter dem Namen „Third Party Call Control“ bekannt und tritt auf, wenn ein Drittanbieter verwendet wird, um zwei Anrufer miteinander zu verbinden (z. B. wenn ein Anruf von Person A an Person B über eine Telefonzentrale durchgestellt wird).|
|Medienumgehung aktivieren|EnableBypass|Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn auch **Zentralisierte Medienverarbeitung** aktiviert ist.|
|Zentralisierte Medienverarbeitung|ConcentratedTopology|Gibt an, ob ein bekannter Medienendpunkt vorhanden ist. (Ein Beispiel für einen bekannten Medienendpunkt ist ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse hat wie der Signaldatenverkehrendpunkt.)|
|RTP-Verriegelung aktivieren|EnableRTPLatching|Gibt an, ob SIP-Trunks die RTP-Verriegelung unterstützen oder nicht. Die RTP-Verriegelung ist eine Technologie, die RTP-/RTCP-Verbindungen über NAT (Network Address Translator, Netzwerkadressenübersetzung) oder eine Firewall ermöglicht.|
|Weiterleitung der Anrufliste aktivieren|ForwardCallHistory|Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.|
|Weiterleitung von P-Asserted-Identity-Daten aktivieren|ForwardPAI|Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.|
|Failovertimer für Ausgangsrouting aktivieren|EnableFastFailoverTimer|Gibt an, ob ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet werden. Wenn keine weiteren Trunks verfügbar sind, wird der Anruf automatisch beendet. In einer Organisation mit langsamen Netzwerk- und Gatewayreaktionen könnte dies dazu führen, dass Anrufe unnötigerweise beendet werden.|
|Zugeordnete PSTN-Verwendungen|PSTNUsages|Dem Trunk zugewiesene Auflistung von PSTN-Verwendungen.|
|Übersetzte Nummer zum Testen|n/v|Eine Telefonnummer, die für Ad-hoc-Tests der Trunkkonfigurationseinstellungen verwendet werden kann.|
|Zugehörige Übersetzungsregeln|OutboundTranslationRulesList|Sammlung an Regeln für die Telefonnummernübersetzung für Anrufe, die per Ausgangsrouting verarbeitet werden (Anrufe, die an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weitergeleitet werden).|
|Übersetzungsregeln für die gewählte Nummer|OutboundCallingNumberTranslationRulesList|Dem Trunk zugewiesene Auflistung von ausgehenden Übersetzungsregeln für Telefonnummern.|
|Testtelefonnummer|n/v|Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.|
|Anrufende Nummer|n/v|Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.|
|Angerufene Nummer|-|Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.|
||||

> [!Note]
> Die Skype für Business Server CsTrunkConfiguration Cmdlets unterstützt zusätzliche Eigenschaften werden nicht in Skype Business Server-Systemsteuerung angezeigt. Weitere Informationen finden Sie im Hilfethema für das [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration) -Cmdlet. 

**Neuen Trunk-Konfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung erstellen**

1. Klicken Sie in der Skype Business Server-Systemsteuerung klicken Sie auf **VoIP-Routing**, und klicken Sie dann auf **Trunkkonfiguration**.
2. Klicken Sie auf der Registerkarte **Trunkkonfiguration** auf **Neu** und dann auf **Standorttrunk**, um die neuen Einstellungen für den Standortbereich zu erstellen, oder klicken Sie auf **Pooltrunk**, um die neuen Einstellungen für den Dienstbereich zu erstellen.
3. Wählen Sie im **Dialogfeld Standort auswählen** oder im Dialogfeld **Wählen Sie einen Dienst** (das Dialogfeld richtet sich danach, ob Sie Standortebene oder Service-bezogenen Einstellungen erstellen) den Speicherort für die neue Konfigurationseinstellungen, und klicken Sie dann auf OK ** **. Wenn das Dialogfeld leer ist, bedeutet dies, dass es ist keine Stelle, an die neuen Einstellungen erstellen; Wenn das Dialogfeld **Standort auswählen** auf leer ist, bedeutet, dass beispielsweise, dass alle Ihre Websites haben bereits eine Auflistung von Trunk Configuration Websites zugewiesen, und jede Website (und jeden Dienst) können nur eine solche Auflistung hosten. In diesem Fall können Sie entweder die bestehende Auflistung zu löschen und erstellen eine neue Auflistung oder einfach ändern die vorhandene Auflistung.
4. Nehmen Sie im Dialogfeld **Neue Trunkkonfiguration** die gewünschten Einstellungen vor und klicken Sie auf **OK**.
5. Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
6. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
7. Klicken Sie im Dialogfeld **Skype für die Business-Systemsteuerung** auf **OK**.
