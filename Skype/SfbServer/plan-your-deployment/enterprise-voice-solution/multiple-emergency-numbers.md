---
title: Planen mehrerer Notrufnummern in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 47ac1a93a39a95710bf1581aace0ec12a39caec6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101601"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planen mehrerer Notrufnummern in Skype for Business Server
 
In diesem Thema erfahren Sie, wie Sie mehrere Notrufnummern in Skype for Business Server planen.
  
Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Mehrere Notrufnummern sind ein neues Feature, das im kumulativen Update vom Juni 2016 eingeführt wurde. Während die VEREINIGTEn Staaten über eine einzige Notrufnummer (911) verfügt, unterstützen viele Länder mehrere Notrufnummern. Das Vereinigte Königreich unterstützt beispielsweise sowohl 999, die für Großbritannien spezifische Notrufnummer als auch 112, die Notrufnummer für die Europäische Union. 
  
Dieses Feature ist auch für Gesundheitsanbieter in den VEREINIGTEn Staaten nützlich, die Roamingunterstützung für mehrere codeblaue Notrufnummern wünschen.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Mehrere Notrufnummern und Standortrichtlinien

Sie konfigurieren Notrufe, indem Sie Standortrichtlinien erstellen, die definieren, wie Notrufe implementiert werden. Sie verwenden die Standortrichtlinie, um zu definieren, welche Nummer einen Notruf bildet, z. B. 911 in den USA; 999 und 112 im Vereinigten Königreich. Die Standortrichtlinie bestimmt, ob ein Benutzer für Notrufe aktiviert ist und ob das Verhalten eines Notrufs ist. Sie können auch definieren, ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf geroutet werden soll.
  
Weitere Informationen zum Definieren und Ändern einer Standortrichtlinie finden Sie unter [Plan location policies for Skype for Business Server](location-policies.md) und Create location policies in Skype for Business [Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). In diesen Themen werden Konzepte zu Standortrichtlinien beschrieben. Sie müssen jedoch die Anweisungen unter Konfigurieren mehrerer Notrufnummern [in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) befolgen, um mehrere Notrufnummern zu konfigurieren.
  
Beachten Sie bei der Planung mehrerer Notrufnummern Folgendes:
  
- Mit dem kumulativen Update vom Juni 2016 können Sie bis zu 5 Notrufnummern für eine bestimmte Standortrichtlinie definieren. Mit dem kumulativen Update vom November 2016 wird diese Zahl auf 100 erhöht.
    
    > [!NOTE]
    > Wenn Sie noch kein Upgrade auf das kumulative Update vom November 2016 durchgeführt haben, lesen Sie [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Für jede Notfallnummer können Sie null oder mehr Notrufmasken angeben, die für eine bestimmte Standortrichtlinie eindeutig sind.
    
    Eine Wählmaske ist eine Zahl, die Sie beim Wählen in den Wert des Notrufnummerwerts übersetzen möchten. Angenommen, Sie geben in dieses Feld den Wert 212 ein, und das Feld Notrufnummer hat den Wert 911. Wenn ein Benutzer 212 wählt, wird die Nummer in 911 übersetzt. Auf diese Weise können alternative Notrufnummern gewählt werden und die Notrufdienste erreichen (z. B. wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Nummer dieses Landes oder dieser Region anstelle der Nummer für das Land oder die Region zu wählen, in dem sie sich derzeit befinden). (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Lands zu wählen, und nicht die Notrufnummer des Lands oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Der Zeichenfolgengrenzwert für eine Wählmaske beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.
    
- Jede Standortrichtlinie verfügt über ein einzelnes Festnetz (Public Switched Telephone Network, PSTN), das verwendet wird, um zu bestimmen, welche Sprachroute zum Routen von Notrufen von Clients mithilfe dieser Richtlinie verwendet wird. Die Verwendung kann eine eindeutige Route pro Notfallnummer haben.
    
- Wenn für eine Standortrichtlinie sowohl die Parameter EmergencyNumbers als auch DialString definiert sind und der Client mehrere Notrufnummern unterstützt, hat die Notrufnummer Vorrang. Wenn der Client nicht mehrere Notrufnummern unterstützt, wird die Wählzeichenfolge für Notrufe verwendet.
    
- Informationen dazu, welche Skype for Business- und Lync-Clients den Empfang mehrerer Notrufnummern, Wählmasken und PstN(Public Switched Telephone Network) unterstützen, finden Sie unter [Clientsupport](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Sie können nicht mehrere Notrufnummern mithilfe der Skype for Business-Systemsteuerung konfigurieren. Sie müssen PowerShell verwenden, um mehrere Notrufnummern zu konfigurieren. 
  
Beachten Sie folgendes, bevor Sie mehrere Notrufnummern konfigurieren:
  
- Zum Konfigurieren mehrerer Notrufnummern müssen Sie das cmdlet New-CsEmergencyNumber verwenden und Standortrichtlinien definieren, die mehrere Notrufnummern unterstützen, indem Sie den Parameter EmergencyNumbers mit den [Cmdlets New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) und [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) angeben.
    
- Wenn Sie vorhandene Zahlen mit dem cmdlet Set-CsLocationPolicy oder New-CsLocationPolicy mit den Parametern EmergencyDialString und EmergencyDialMask definiert haben, haben die mit dem Parameter EmergencyNumbers angegebenen Werte Vorrang vor den alten Werten. Das heißt, die Werte für die Parameter EmergencyDialString und EmergencyDialMask werden ignoriert.
    
- Wenn Sie vorhandene Nummern mit dem cmdlet Set-CsLocationPolicy oder New-CsLocationPolicy mit den Parametern EmergencyDialString und EmergencyDialMask definiert haben und keine neuen Notrufnummern  *konfigurieren,*  werden die vorhandenen Nummern weiterhin verwendet.
    
- Damit das Feature für mehrere Notrufnummern funktioniert, müssen die ausgeführten Clientversionen das neue Feature unterstützen können. Ältere Clients verwenden weiterhin die alten Werte, die von den cmdlets Set-CsLocationPolicy oder New-CsLocationPolicy mit den Parametern EmergencyDialString und EmergencyDialMask angegeben werden. 
    
- Wenn die Benutzer eine Nummer wählen, die der Wählzeichenfolge entspricht, ist keine Wählmaske erforderlich. Wenn beispielsweise die Nummer, die ein Benutzer wählt, 911 ist, ist die Wählzeichenfolge 911, und es ist keine Maske erforderlich. 
    
Weitere Informationen zum Konfigurieren mehrerer Notrufnummern finden Sie unter [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
In der folgenden Tabelle sind Beispielspeicherortrichtlinien aufgeführt (im Beispiel werden nicht alle Attribute angezeigt):
  

|**Name der Standortrichtlinie**|**E911 aktiviert**|**Zeichenfolge für Notrufwähler**|**Wählmaske**|**Notrufnummern**|**PSTN-Verwendung**|**Erforderlicher Standort**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Vereinigte Staaten  <br/> |Ja  <br/> |911  <br/> | 112;999 <br/> ||USEmergency  <br/> |Ja  <br/> |
|US-Hospital  <br/> |Ja  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Ja  <br/> |
|London  <br/> |Ja  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911;117;118  <br/> |GBEmergency  <br/> |Nein  <br/> |
|Indien  <br/> |Ja  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Nein  <br/> |
   
 **VEREINIGTE STAATEN** – Es ist keine Anforderung für mehrere Notrufnummern erforderlich. In den USA verwenden Sie die alten Konfigurationen für Die Wählzeichenfolge und die Wählmaske.
  
 **US-Hospital** – Es ist erforderlich, "450" nicht zu maskieren. Für Clients, die noch nicht mehrere Notrufnummern unterstützen, können Sie die alten Konfigurationen für Die Wählzeichenfolge und die Wählmaske verwenden. Für Clients, die mehrere Notrufnummern unterstützen, können Sie eine Notrufnummer für "911" und "450" definieren, anstatt 450 zu maskieren.
  
 **London** – Für Clients, die noch nicht mehrere Notrufnummern unterstützen, können Sie die alten Konfigurationen für Wählzeichenfolge und Wählmaske verwenden. Für Clients, die mehrere Notrufnummern unterstützen, können Sie eine Notrufnummer für "999" und "112" mit Jeweils masken definieren.
  
 **Indien** – Alle bereitgestellten Clients unterstützen mehrere Notrufnummern. In Indien müssen Sie nur mehrere Notrufnummern konfigurieren.
  
## <a name="client-support"></a>Clientunterstützung
<a name="BKMK_Clients"> </a>

In der folgenden Tabelle ist die Clientunterstützung für mehrere Notrufnummern aufgeführt. Microsoft wird weiterhin die Unterstützung für zusätzliche Clients testen und veröffentlichen. Besuchen Sie diese Website regelmäßig.

|**Windows**|**Version**|
|:-----|:-----|
|**Klick-und-Los** <br/> |CC (Aktueller Kanal) veröffentlicht am 10. Mai 2016 - Version 1604 (Build 6868.2062)  <br/> |
||FRDC (First Release Current Channel) veröffentlicht am 14. Juni 2016 - Version 1605 (Build 6965.2058)  <br/> |
||DC (Verzögerter Kanal) veröffentlicht am 11. Oktober 2016 - Version 1605 (Build 6965.2092)  <br/> |
|**MSI** <br/> |Update vom 7. Juni – [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac und iOS** <br/> |**Version** <br/> |
||Skype for Business Mac Client Version 16.9  <br/> Skype for Business iOS-Clientversion 6.16  <br/> |
|**Android** <br/> |**Version** <br/> |
||Skype for Business Android Client Version 6.17  <br/> |
|**Lync Phone Edition** <br/> |**Version** <br/> |
|| Aastra 6721ip- und Aastra 6725ip-Telefone – kumulatives Update vom September 2016 (Build 7577.4512) -[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110- und HP 4120-Telefone – kumulatives Update vom September 2016 (Build 7577.4512) -[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500-, Polycom CX600- und Polycom CX3000-Telefone – kumulatives Update vom September 2016 (Build 7577.4512) - [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
