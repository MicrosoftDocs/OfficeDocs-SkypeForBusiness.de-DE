---
title: Erstellen einer neuen Auflistung von Trunkkonfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine neue Sammlung von Trunkkonfigurationseinstellungen mithilfe der Skype for Business Server Systemsteuerung erstellen.'
ms.openlocfilehash: 74a1b9b88adcce3164cd8bebc761d9868e8b0f1f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594093"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Erstellen einer neuen Auflistung von Trunkkonfigurationseinstellungen in Skype for Business Server 

**Zusammenfassung:** Erfahren Sie, wie Sie mithilfe der Skype for Business Server Systemsteuerung eine neue Sammlung von Trunkkonfigurationseinstellungen erstellen.
  
SIP-Trunkkonfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch eXchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Mit diesen Einstellungen kann Folgendes angegeben werden:
  
- Ob die Medienumgebung für Trunks aktiviert werden soll.
    
- Die Bedingungen, unter denen RTCP-Pakete (Realtime Transport Control Protocol) gesendet werden.
    
- Gibt an, ob die SRTP-Verschlüsselung (Secure Realtime Transport Protocol) für jeden Trunk erforderlich ist.
    
Wenn Sie Skype for Business Server installieren, wird eine globale Sammlung von SIP-Trunkkonfigurationseinstellungen für Sie erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).
  
Beim Erstellen von SIP-Trunkkonfigurationseinstellungen mit Skype for Business Server Systemsteuerung stehen Ihnen die folgenden Optionen zur Verfügung.
  
|**UI-Einstellung**|**PowerShell-Parameter**|**Beschreibung**|
|:-----|:-----|:-----|
|Name  <br/> |Identität  <br/> |Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung an Trunkkonfigurationseinstellungen nicht ändern.  <br/> |
|Beschreibung  <br/> |Beschreibung  <br/> |Bietet Administratoren eine Möglichkeit, zusätzliche Informationen zu den Einstellungen zu speichern (z. B. Zweck der Trunkkonfiguration).  <br/> |
|Maximal unterstützte frühe Dialoge  <br/> |MaxEarlyDialogs  <br/> |Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.  <br/> |
|Unterstützte Verschlüsselungsstufe  <br/> |SRTPMode  <br/> | Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest. Bei der Medienumgehung muss dieser Wert mit der Einstellung "EncryptionLevel" in der Medienkonfiguration kompatibel sein. Die Medienkonfiguration wird mithilfe der Cmdlets ["New-CsMediaConfiguration"](/powershell/module/skype/new-csmediaconfiguration?view=skype-ps) und ["Set-CsMediaConfiguration"](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) festgelegt. <br/>  Gültige Werte sind: <br/>  Required: Die SRTP-Verschlüsselung muss verwendet werden. <br/>  Optional: SRTP wird verwendet, wenn es vom Gateway unterstützt wird. <br/>  Not Supported: Die SRTP-Verschlüsselung wird nicht unterstützt und daher auch nicht verwendet. <br/>  "SRTPMode" wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird "SRTPMode" intern auf "Not Supported" festgelegt.<br/> |
|Support melden  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |Mit der Einstellung **Refer-Anforderungen an das Gateway senden** unterstützt der Trunk den Empfang von Refer-Anforderungen vom Vermittlungsserver.  <br/> Mit der Einstellung **Refer-Anforderungen mit 3pcc senden** kann das 3pcc-Protokoll verwendet werden, damit weitergeleitete Anrufe den gehosteten Standort umgehen können. 3pcc ist auch unter dem Namen "Third Party Call Control" bekannt und tritt auf, wenn ein Drittanbieter verwendet wird, um zwei Anrufer miteinander zu verbinden (z. B. wenn ein Anruf von Person A an Person B über eine Telefonzentrale durchgestellt wird).<br/> |
|Medienumgehung aktivieren  <br/> |EnableBypass  <br/> |Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn auch **Zentrale Medienverarbeitung** aktiviert ist.<br/> |
|Zentrale Medienverarbeitung  <br/> |1000000000  <br/> |Gibt an, ob ein bekannter Medienendpunkt vorhanden ist. (Ein Beispiel für einen bekannten Medienendpunkt ist ein PSTN-Gateway, bei dem der Medienendpunkt die gleiche IP-Adresse hat wie der Signaldatenverkehr-Endpunkt.)  <br/> |
|RTP-Latching aktivieren  <br/> |EnableRTPLatching  <br/> |Gibt an, ob SIP-Trunks RTP-Latching unterstützen oder nicht. RTP-Latching ist eine Technologie, die RTP-/RTCP-Verbindungen über NAT (Network Address Translator, Netzwerkadressenübersetzung) oder eine Firewall ermöglicht.  <br/> |
|Weiterleiten der Anrufliste aktivieren  <br/> |ForwardCallHistory  <br/> |Gibt an, ob Informationen zum Anruferverlauf durch den Trunk weitergeleitet werden.  <br/> |
|Weiterleiten von P-Asserted-Identity-Daten aktivieren  <br/> |ForwardPAI  <br/> |Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.  <br/> |
|Timer für Ausgangsroutingfailover aktivieren  <br/> |EnableFastFailoverTimer  <br/> |Gibt an, ob ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet werden. Wenn keine weiteren Trunks verfügbar sind, wird der Anruf automatisch beendet. In einer Organisation mit langsamen Netzwerk- und Gateway-Reaktionen könnte dies dazu führen, dass Anrufe unnötigerweise beendet werden.  <br/> |
|Zugeordnete PSTN-Verwendungen  <br/> |PSTNUsages  <br/> |Eine Sammlung von dem Trunk zugewiesenen PSTN-Verwendungen.  <br/> |
|Übersetzte Nummer zum Testen  <br/> |Nicht zutreffend  <br/> |Eine Telefonnummer, die für Ad-hoc-Tests der Trunkkonfigurationseinstellungen verwendet werden kann.  <br/> |
|Zugehörige Übersetzungsregeln  <br/> |OutboundTranslationRulesList  <br/> |Sammlung an Regeln für die Telefonnummernübersetzung für Anrufe, die per Ausgangsrouting verarbeitet werden (Anrufe, die an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weitergeleitet werden).  <br/> |
|Übersetzungsregeln für angerufene Nummern  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |Sammlung an Regeln für die Nummernübersetzung für ausgehende Anrufe, die dem Trunk zugewiesen sind.  <br/> |
|Testtelefonnummer  <br/> |Nicht zutreffend  <br/> |Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.  <br/> |
|Anrufende Nummer  <br/> |Nicht zutreffend  <br/> |Gibt an, dass die zu testende Telefonnummer die Telefonnummer des Anrufers ist.  <br/> |
|Angerufene Nummer  <br/> |Nicht zutreffend  <br/> |Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.  <br/> |
   
> [!NOTE]
> Die Skype for Business Server CsTrunkConfiguration-Cmdlets unterstützen zusätzliche Eigenschaften, die nicht in Skype for Business Server Systemsteuerung angezeigt werden. Weitere Informationen finden Sie im Hilfethema zum Cmdlet ["New-CsTrunkConfiguration".](/powershell/module/skype/new-cstrunkconfiguration?view=skype-ps)
  
### <a name="to-create-new-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie neue Trunkkonfigurationseinstellungen mithilfe Skype for Business Server Systemsteuerung

1. Klicken Sie in Skype for Business Server Systemsteuerung auf **VoIP-Routing** und dann auf **Trunkkonfiguration.**
    
2. Klicken Sie auf der Registerkarte **Trunkkonfiguration** auf **Neu** und dann auf **Standorttrunk**, um die neuen Einstellungen auf Standortebene zu erstellen, oder klicken Sie auf **Pooltrunk**, um die neuen Einstellungen auf Dienstebene zu erstellen.
    
3. Wählen Sie im Dialogfeld **Standort auswählen** oder im Dialogfeld **Dienst auswählen** (das angezeigte Dialogfeld ist abhängig davon, ob Sie Einstellungen auf Standort- oder auf Dienstebene vornehmen) den Standort für die neuen Konfigurationseinstellungen aus, und klicken Sie auf **OK**. Wenn das Dialogfeld leer ist, können Sie keine neuen Einstellungen erstellen. Wenn beispielsweise das Dialogfeld **Standort auswählen** leer ist, bedeutet dies, dass allen Standorten bereits eine Sammlung von Trunkkonfigurationsstandorten zugewiesen wurde. An jedem Standort (und in jedem Dienst) kann jedoch nur eine solche Sammlung gehostet werden. In diesem Fall können Sie die bestehende Sammlung löschen und eine neue erstellen, oder Sie können die bestehende Sammlung bearbeiten.
    
4. Nehmen Sie im Dialogfeld **Neue Trunkkonfiguration** die gewünschten Einstellungen vor, und klicken Sie auf **OK**.
    
5. Die Eigenschaft **Zustand** für die Sammlung wird aktualisiert und lautet jetzt **Ohne Commit**. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit** und dann auf **Commit für alle**.
    
6. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
    
7. Klicken Sie im Dialogfeld **Skype for Business Server Systemsteuerung** auf **OK.**
