---
title: Planen von mehreren Notrufnummern in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: In diesem Thema erfahren Sie, wie Sie mehrere Notrufnummern in Skype for Business Server planen.
ms.openlocfilehash: 10b6d02391fbf1ac7af1ae5233261c36fd2fd6ab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983020"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planen von mehreren Notrufnummern in Skype for Business Server
 
In diesem Thema erfahren Sie, wie Sie mehrere Notrufnummern in Skype for Business Server planen.
  
Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Mehrere Notrufnummern sind ein neues Feature, das im kumulativen Update vom Juni 2016 eingeführt wurde. Während die Vereinigten Staaten über eine einzige Notrufnummer verfügen, 911, unterstützen viele Länder mehrere Notrufnummern. Das Vereinigte Königreich beispielsweise unterstützt sowohl 999, die Notrufnummer für das Vereinigte Königreich als auch 112, die Notrufnummer für die Europäische Union. 
  
Dieses Feature ist auch für Anbieter von Gesundheitsdiensten in den Vereinigten Staaten nützlich, die Roaming-Unterstützung für mehrere Code blaue Notrufnummern benötigen.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Mehrere Notrufnummern und ortungsrichtlinien

Sie konfigurieren Notrufe durch Erstellen von ortungsrichtlinien, die definieren, wie Notrufe implementiert werden. Sie verwenden die ortungsrichtlinie, um festzulegen, welche Zahl einen Notruf darstellt (beispielsweise 911 in den USA). 999 und 112 im Vereinigten Königreich. Die ortungsrichtlinie legt fest, ob ein Benutzer für Notrufe aktiviert ist, und wenn ja, was das Verhalten eines Notrufs ist. Sie können auch festlegen, ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.
  
Weitere Informationen zum Definieren und Ändern einer ortungsrichtlinie finden Sie unter [Planen von Standortrichtlinien für Skype for Business Server](location-policies.md) und [Erstellen von ortungsrichtlinien in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). In diesen Themen werden Konzepte für Standortrichtlinien beschrieben. Sie müssen jedoch den Anweisungen unter [Configure Multiple Emergency Numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) folgen, um mehrere Notrufnummern zu konfigurieren.
  
Beachten Sie bei der Planung für mehrere Notrufnummern Folgendes:
  
- Mit dem kumulativen Update vom Juni 2016 können Sie bis zu fünf Notrufnummern für eine bestimmte Standortrichtlinie definieren. Mit dem kumulativen Update vom November 2016 steigt diese Zahl auf 100.
    
    > [!NOTE]
    > Wenn Sie noch nicht auf das kumulative Update vom November 2016 aktualisiert haben, lesen Sie [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Sie können für jede Notrufnummer NULL oder mehr Notruf Masken angeben, die für eine bestimmte Standortrichtlinie eindeutig sind.
    
    Bei einer Wähl Maske handelt es sich um eine Nummer, die Sie beim wählen in den Wert des Notrufnummern Werts übersetzen möchten. Angenommen, Sie geben den Wert 212 in dieses Feld ein, und das Feld Notrufnummer hat den Wert 911. Wenn ein Benutzer 212 wählt, wird die Nummer in 911 übersetzt. Auf diese Weise können alternative Notrufnummern gewählt werden und weiterhin Notrufdienste für Anrufe erhalten (beispielsweise, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Nummer des Landes oder der Region zu wählen, statt die Nummer für den Land oder Region, in dem Sie sich derzeit befinden). (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Lands zu wählen, und nicht die Notrufnummer des Lands oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Die Zeichenfolgen Begrenzung für eine Wähl Maske beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.
    
- Jede ortungsrichtlinie verfügt über eine einzige PSTN-Verwendung (Public Switched Telephone Network), die verwendet wird, um zu bestimmen, welche VoIP-Route zum Weiterleiten von Notrufen von Clients verwendet wird, die diese Richtlinie verwenden. Die Verwendung kann eine eindeutige Route pro Notrufnummer aufweisen.
    
- Wenn für eine ortungsrichtlinie sowohl die "emergencynumbers"-als auch die dialtype-Parameter definiert sind und der Client mehrere Notrufnummern unterstützt, hat die Notrufnummer Vorrang. Wenn der Client mehrere Notrufnummern nicht unterstützt, wird die Notruf-Wählzeichenfolge verwendet.
    
- Informationen dazu, welche Skype for Business-und lync-Clients unterstützen, die mehrere Notrufnummern, Wähl Masken und PSTN-Verwendungen (Public Switched Telephone Network) erhalten, finden Sie unter [Client Support](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Sie können nicht mehrere Notrufnummern mithilfe der Skype for Business-Systemsteuerung konfigurieren. Sie müssen PowerShell verwenden, um mehrere Notrufnummern zu konfigurieren. 
  
Beachten Sie Folgendes, bevor Sie mehrere Notrufnummern konfigurieren:
  
- Um mehrere Notrufnummern zu konfigurieren, müssen Sie das Cmdlet New-csemergencynumber "verwenden, und Sie müssen Standortrichtlinien definieren, die mehr als eine Notrufnummer unterstützen, indem Sie den Parameter" emergencynumbers "mit den Cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) und [setCsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) festlegen.
    
- Wenn Sie vorhandene Nummern mit dem Cmdlet "CsLocationPolicy" oder "New-CsLocationPolicy" mit den Parametern EmergencyDialString und EmergencyDialMask definiert haben, haben die Werte, die mit dem Parameter "emergencynumbers" angegeben werden, Vorrang vor den alten Werte. Das bedeutet, dass die Werte für die Parameter EmergencyDialString und EmergencyDialMask ignoriert werden.
    
- Wenn Sie vorhandene Nummern mit dem Cmdlet "CsLocationPolicy" oder "New-CsLocationPolicy" mit den Parametern EmergencyDialString und EmergencyDialMask definiert haben *und keine neuen Notrufnummern konfigurieren* , werden die vorhandenen Nummern weiterhin verwendet.
    
- Damit das Feature für mehrere Notrufnummern funktionsfähig ist, müssen die von Ihnen ausgeführten Clientversionen das neue Feature unterstützen können. Ältere Clients verwenden weiterhin die alten Werte, die von den Cmdlets "CsLocationPolicy" oder "New-CsLocationPolicy" mit den Parametern EmergencyDialString und EmergencyDialMask angegeben werden. 
    
- Wenn die Benutzer eine Nummer wählen, die mit der Wählzeichenfolge übereinstimmt, ist keine Wähl Maske erforderlich. Wenn beispielsweise die Nummer, die ein Benutzer wählt, 911 ist, lautet die Wählzeichenfolge 911, und es ist keine Maske erforderlich. 
    
Weitere Informationen zum Konfigurieren mehrerer Notrufnummern finden Sie unter [Configure Multiple Emergency Numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
In der folgenden Tabelle sind Beispiele für Standortrichtlinien aufgeführt (im Beispiel werden nicht alle Attribute angezeigt):
  

|**Name der Standortrichtlinie**|**E911 aktiviert**|**Notrufnummern Zeichenfolge**|**Wähl Maske**|**Notrufnummern**|**PSTN-Verwendung**|**Speicherort erforderlich**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|USA  <br/> |Ja  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |Ja  <br/> |
|US-Hospital  <br/> |Ja  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Ja  <br/> |
|London  <br/> |Ja  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112 – 911; 117; 118  <br/> |GBEmergency  <br/> |Nein  <br/> |
|India  <br/> |Ja  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Nein  <br/> |
   
 **USA** – es ist keine Anforderung für mehrere Notrufnummern erforderlich. In den Vereinigten Staaten verwenden Sie die alte notrufwählzeichenfolge und die Konfigurationen für Wähl Masken.
  
 **US-Hospital-** es ist eine Anforderung nicht zu maskieren "450". Für Clients, die noch nicht mehrere Notrufnummern unterstützen, können Sie die alte notrufwählzeichenfolge und Konfigurationen für Wähl Masken verwenden. Für Clients, die mehrere Notrufnummern unterstützen, können Sie eine Notrufnummer für "911" und "450" anstelle von "Masking 450" definieren.
  
 **London** – für Clients, die noch nicht mehrere Notrufnummern unterstützen, können Sie die alte notrufwählzeichenfolge und Konfigurationen für Wähl Masken verwenden. Für Clients, die mehrere Notrufnummern unterstützen, können Sie eine Notrufnummer für "999" und "112" mit Masken für jede definieren.
  
 **Indien** – alle bereitgestellten Clients unterstützen mehrere Notrufnummern. In Indien müssen Sie nur mehrere Notrufnummern konfigurieren.
  
## <a name="client-support"></a>Clientunterstützung
<a name="BKMK_Clients"> </a>

In der folgenden Tabelle ist die Clientunterstützung für mehrere Notrufnummern aufgeführt. Microsoft testet und veröffentlicht weiterhin die Unterstützung für zusätzliche Clients. Besuchen Sie diese Website regelmäßig.

|**Windows**|**Version**|
|:-----|:-----|
|**Klick-und-Los** <br/> |CC (aktueller Kanal) veröffentlicht am 10. Mai 2016-Version 1604 (Build 6868,2062)  <br/> |
||FRDC (First Release Current Channel) veröffentlicht am 14. Juni 2016-Version 1605 (Build 6965,2058)  <br/> |
||DC (verzögerter Kanal) veröffentlicht am 11. Oktober 2016-Version 1605 (Build 6965,2092)  <br/> |
|**MSI** <br/> |Update 7. Juni-[https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac und IOS** <br/> |**Version** <br/> |
||Skype for Business Mac-Client Version 16,9  <br/> Skype for Business IOS-Client Version 6,16  <br/> |
|**Android** <br/> |**Version** <br/> |
||Skype for Business Android-Client Version 6,17  <br/> |
|**Lync Phone Edition** <br/> |**Version** <br/> |
|| Aastra 6721ip und Aastra 6725ip Telefone-September 2016 Kumulatives Update (Build 7577,4512)-[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110 und HP 4120 Telefone-September 2016 Kumulatives Update (Build 7577,4512)-[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500, Polycom CX600 und Polycom CX3000-Telefone-September 2016 Kumulatives Update (Build 7577,4512)-[https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
   

