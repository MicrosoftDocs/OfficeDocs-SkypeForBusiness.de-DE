---
title: Ändern von SIP-Trunk-Konfigurationseinstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
description: 'Zusammenfassung: Erfahren Sie, wie SIP-Trunk-Konfigurationseinstellungen mithilfe der Skype für Business Server-Systemsteuerung ändern.'
ms.openlocfilehash: 04a381d0e3bd935eeef860bdfb6866b232812189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892314"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Ändern von SIP-Trunk-Konfigurationseinstellungen in Skype für Business Server
 
**Zusammenfassung:** Erfahren Sie, wie SIP-Trunk-Konfigurationseinstellungen mithilfe der Skype für Business Server-Systemsteuerung ändern.
  
SIP-Trunk-Konfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network, Festnetz), einer IP-Nebenstellenanlage (Public Branch Exchange, PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:
  
- Ob Medienumgehung für die Trunks aktiviert werden soll
    
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.
    
- Ob SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden Trunk erforderlich ist.
    
Wenn Sie Skype für Business Server installieren, wird eine globale Auflistung von SIP-trunkkonfigurationseinstellungen für Sie erstellt. Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Eine der folgenden Auflistungen können später mit entweder Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell geändert werden.
  
Beim Ändern von SIP-Trunk-Konfigurationseinstellungen mithilfe der Skype für Business Server-Systemsteuerung sind die folgenden Optionen zur Verfügung.
  
|**UI-Einstellung**|**PowerShell-Parameter**|**Beschreibung**|
|:-----|:-----|:-----|
|Name  <br/> |Identität  <br/> |Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung von Trunkkonfigurationseinstellungen nicht ändern.  <br/> |
|Beschreibung  <br/> |Beschreibung  <br/> |Bietet Administratoren eine Möglichkeit, zusätzliche Informationen zu den Einstellungen zu speichern (z. B. Zweck der Trunkkonfiguration).  <br/> |
|Maximal unterstützte frühe Dialoge  <br/> |MaxEarlyDialogs  <br/> |Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.  <br/> |
|Unterstützte Verschlüsselungsstufe  <br/> |SRTPMode  <br/> | Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest. Bei der Medienumgehung muss dieser Wert mit der Einstellung „EncryptionLevel“ in der Medienkonfiguration kompatibel sein. Medienkonfiguration wird mithilfe der Cmdlets [New-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmediaconfiguration?view=skype-ps) und [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) festgelegt. <br/>  Zulässige Werte: <br/>  Erforderlich: Die SRTP-Verschlüsselung muss verwendet werden. <br/>  Optional: SRTP wird verwendet, wenn es vom Gateway unterstützt wird. <br/>  Nicht unterstützt: Die SRTP-Verschlüsselung wird nicht unterstützt und daher auch nicht verwendet. <br/>  „SRTPMode“ wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird „SRTPMode“ intern auf „Nicht unterstützt“ festgelegt.<br/> |
|Support melden  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |Mit der Einstellung **Senden der Weiterleitung an Gateway aktivieren** unterstützt der Trunk den Empfang von Weiterleitungsanforderungen vom Vermittlungsserver.  <br/> Mit der Einstellung **Weiterleitung mithilfe von Drittanbieteranrufsteuerung aktivieren** kann das 3pcc-Protokoll verwendet werden, damit weitergeleitete Anrufe den gehosteten Standort umgehen können. 3pcc ist auch unter dem Namen „Third Party Call Control“ bekannt und tritt auf, wenn ein Drittanbieter verwendet wird, um zwei Anrufer miteinander zu verbinden (z. B. wenn ein Anruf von Person A an Person B über eine Telefonzentrale durchgestellt wird).<br/> |
|Medienumgehung aktivieren  <br/> |EnableBypass  <br/> |Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn auch **Zentralisierte Medienverarbeitung** aktiviert ist.<br/> |
|Zentralisierte Medienverarbeitung  <br/> |ConcentratedTopology  <br/> |Gibt an, ob ein bekannter Medienendpunkt vorhanden ist. (Ein Beispiel für einen bekannten Medienendpunkt ist ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse hat wie der Signaldatenverkehrendpunkt.)  <br/> |
|RTP-Verriegelung aktivieren  <br/> |EnableRTPLatching  <br/> |Gibt an, ob SIP-Trunks die RTP-Verriegelung unterstützen oder nicht. Die RTP-Verriegelung ist eine Technologie, die RTP-/RTCP-Verbindungen über NAT (Network Address Translator, Netzwerkadressenübersetzung) oder eine Firewall ermöglicht.  <br/> |
|Weiterleitung der Anrufliste aktivieren  <br/> |ForwardCallHistory  <br/> |Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.  <br/> |
|Weiterleitung von P-Asserted-Identity-Daten aktivieren  <br/> |ForwardPAI  <br/> |Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.  <br/> |
|Failovertimer für Ausgangsrouting aktivieren  <br/> |EnableFastFailoverTimer  <br/> |Gibt an, ob ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet werden. Wenn keine weiteren Trunks verfügbar sind, wird der Anruf automatisch beendet. In einer Organisation mit langsamen Netzwerk- und Gatewayreaktionen könnte dies dazu führen, dass Anrufe unnötigerweise beendet werden.  <br/> |
|Zugeordnete PSTN-Verwendungen  <br/> |PSTNUsages  <br/> |Dem Trunk zugewiesene Auflistung von PSTN-Verwendungen.  <br/> |
|Übersetzte Nummer zum Testen  <br/> |Nicht zutreffend  <br/> |Eine Telefonnummer, die für Ad-hoc-Tests der Trunkkonfigurationseinstellungen verwendet werden kann.  <br/> |
|Zugehörige Übersetzungsregeln  <br/> |OutboundTranslationRulesList  <br/> |Sammlung an Regeln für die Telefonnummernübersetzung für Anrufe, die per Ausgangsrouting verarbeitet werden (Anrufe, die an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weitergeleitet werden).  <br/> |
|Übersetzungsregeln für die gewählte Nummer  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |Dem Trunk zugewiesene Auflistung von ausgehenden Übersetzungsregeln für Telefonnummern.  <br/> |
|Testtelefonnummer  <br/> |Nicht zutreffend  <br/> |Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.  <br/> |
|Anrufende Nummer  <br/> |Nicht zutreffend  <br/> |Gibt an, dass die zu testende Telefonnummer die Telefonnummer des Anrufers ist.  <br/> |
|Angerufene Nummer  <br/> |-  <br/> |Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.  <br/> |
   
> [!NOTE]
> Die Lync Server-CsTrunkConfiguration-Cmdlets unterstützt zusätzliche Eigenschaften, die in Lync Server-Systemsteuerung nicht angezeigt. Weitere Informationen finden Sie im Hilfethema zum [Set-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cstrunkconfiguration?view=skype-ps) -Cmdlet.
  
### <a name="to-modify-sip-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So ändern Sie die SIP-Trunk-Konfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung

1. Klicken Sie in Skype Business Server-Systemsteuerung auf **VoIP-Routing**, und klicken Sie dann auf **Trunkkonfiguration**.
    
2. Doppelklicken Sie auf der Registerkarte **Trunkkonfiguration** auf die Trunkkonfigurationseinstellungen, die Sie ändern möchten. Beachten Sie, dass Sie immer nur eine Einstellung bearbeiten können. Wenn Sie die gleichen Änderungen an mehreren Sammlungen vornehmen möchten, verwenden Sie Windows PowerShell.
    
3. Nehmen Sie im Dialogfeld **Trunkkonfiguration bearbeiten** die gewünschten Einstellungen vor und klicken Sie auf **OK**.
    
4. Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
    
5. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
    
6. Klicken Sie im Dialogfeld **Skype Business Server-Systemsteuerung** auf **OK**.
    

