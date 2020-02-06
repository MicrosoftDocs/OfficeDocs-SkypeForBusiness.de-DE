---
title: Erstellen einer neuen Sammlung von trunk-Konfigurationseinstellungen in Skype for Business Server
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
ms.openlocfilehash: 6db4978151bf9b649375adb7a2200710a1a503c3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817005"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Erstellen einer neuen Sammlung von trunk-Konfigurationseinstellungen in Skype for Business Server

SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:
- Ob Medienumgehung für die Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.
- Ob die SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden trunk erforderlich ist.

Wenn Sie Skype for Business Server installieren, wird eine globale Sammlung von SIP-Trunk-Konfigurationseinstellungen für Sie erstellt. Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).

Beim Erstellen von SIP-Trunk-Konfigurationseinstellungen nutzen für Business Server Control Panel stehen Ihnen die folgenden Optionen zur Verfügung:

|Benutzeroberflächeneinstellung | PowerShell-Parameter | Beschreibung |
|--|--|--|
|Name|Identität|Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung von Trunkkonfigurationseinstellungen nicht ändern.|
|Beschreibung|Beschreibung|Bietet Administratoren eine Möglichkeit, zusätzliche Informationen zu den Einstellungen zu speichern (z. B. Zweck der Trunkkonfiguration).|
|Maximal unterstützte frühe Dialoge|MaxEarlyDialogs|Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.|
|Unterstützte Verschlüsselungsstufe|SRTPMode|Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest. Bei der Medienumgehung muss dieser Wert mit der Einstellung „EncryptionLevel“ in der Medienkonfiguration kompatibel sein. Die Medienkonfiguration wird mithilfe der Cmdlets [New-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration) und [CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration) gesetzt.<br/>Gültige Werte sind:<br/><br/>**Erforderlich**: SRTP-Verschlüsselung muss verwendet werden.<br/>**Optional**: srtp wird verwendet, wenn es vom Gateway unterstützt wird.<br/>**Nicht unterstützt**: die SRTP-Verschlüsselung wird nicht unterstützt und wird daher nicht verwendet.<br/><br/>„SRTPMode“ wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird „SRTPMode“ intern auf „Nicht unterstützt“ festgelegt.|
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
|Anrufende Nummer|Nicht zutreffend|Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.|
|Angerufene Nummer|-|Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.|
||||

> [!Note]
> Die Skype for Business Server CsTrunkConfiguration-Cmdlets unterstützen zusätzliche Eigenschaften, die nicht in der Skype for Business Server-Systemsteuerung angezeigt werden. Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration) . 

**So erstellen Sie neue trunk-Konfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung**

1. Klicken Sie im Skype for Business Server-Control Panel auf **VoIP-Routing**und dann auf trunk- **Konfiguration**.
2. Klicken Sie auf der Registerkarte **Trunkkonfiguration** auf **Neu** und dann auf **Standorttrunk**, um die neuen Einstellungen für den Standortbereich zu erstellen, oder klicken Sie auf **Pooltrunk**, um die neuen Einstellungen für den Dienstbereich zu erstellen.
3. Wählen Sie im Dialogfeld **Website auswählen** oder **Dienst auswählen** (das angezeigte Dialogfeld hängt davon ab, ob Sie Website Bereich oder Dienstbereichs Einstellungen erstellen) den Speicherort für die neuen Konfigurationseinstellungen aus, und klicken Sie dann auf **OK**. Wenn das Dialogfeld leer ist, bedeutet dies, dass kein Ort zum Erstellen der neuen Einstellungen vorhanden ist. Wenn beispielsweise das Dialogfeld **Website auswählen** leer ist, bedeutet dies, dass allen Websites bereits eine Sammlung von trunk-Konfigurations Websites zugewiesen wurde und jede Website (und jeder Dienst) nur eine dieser Sammlungen hosten kann. In diesem Fall können Sie entweder die vorhandene Sammlung löschen und eine neue Sammlung erstellen oder einfach die vorhandene Sammlung ändern.
4. Nehmen Sie im Dialogfeld **Neue Trunkkonfiguration** die gewünschten Einstellungen vor und klicken Sie auf **OK**.
5. Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
6. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
7. Klicken Sie im Dialogfeld **Skype Control Panel für Unternehmen** auf **OK**.
