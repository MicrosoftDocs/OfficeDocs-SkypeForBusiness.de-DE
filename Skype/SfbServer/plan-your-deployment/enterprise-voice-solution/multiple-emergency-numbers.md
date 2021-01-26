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
ms.openlocfilehash: eb5fbc55bc7f2e783fbfa98c7bc7fb6db67ff748
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813865"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planen mehrerer Notrufnummern in Skype for Business Server
 
In diesem Thema erfahren Sie, wie Sie mehrere Notrufnummern in Skype for Business Server planen.
  
Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Mehrere Notrufnummern sind eine neue Funktion, die im kumulativen Update vom Juni 2016 eingeführt wurde. Während die Vereinigten Staaten über eine einzelne Notrufnummer (911) verfügt, unterstützen viele Länder mehrere Notrufnummern. Das Vereinigte Königreich unterstützt beispielsweise sowohl 999, die für das Vereinigte Königreich spezifische Notrufnummer als auch 112, die Notrufnummer für die Europäische Union. 
  
Dieses Feature ist auch für Anbieter von Gesundheitsdiensten in den VEREINIGTEn Staaten nützlich, die Roamingunterstützung für mehrere blaue Notrufnummern mit Code haben möchten.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Mehrere Notrufnummern und Standortrichtlinien

Sie konfigurieren Notrufe, indem Sie Standortrichtlinien erstellen, die definieren, wie Notrufe implementiert werden. Sie verwenden die Standortrichtlinie, um zu definieren, welche Nummer einen Notruf bildet, z. B. 911 in den USA; 999 und 112 im Vereinigten Königreich. Die Standortrichtlinie bestimmt, ob ein Benutzer für Notrufe aktiviert ist und ob das Verhalten eines Notrufs ist. Sie können auch definieren, ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf geroutet werden soll.
  
Weitere Informationen zum Definieren und Ändern einer Standortrichtlinie finden Sie unter "Planen von Standortrichtlinien für [Skype for Business Server"](location-policies.md) und "Erstellen von [Standortrichtlinien in Skype for Business Server".](../../deploy/deploy-enterprise-voice/create-location-policies.md) In diesen Themen werden Konzepte zu Standortrichtlinien beschrieben. Sie müssen jedoch die Anweisungen unter "Konfigurieren mehrerer Notrufnummern [in Skype for Business"](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) befolgen, um mehrere Notrufnummern zu konfigurieren.
  
Beachten Sie bei der Planung mehrerer Notrufnummern Folgendes:
  
- Mit dem kumulativen Update vom Juni 2016 können Sie bis zu 5 Notrufnummern für eine bestimmte Standortrichtlinie definieren. Mit dem kumulativen Update vom November 2016 erhöht sich diese Zahl auf 100.
    
    > [!NOTE]
    > Wenn Sie noch nicht auf das kumulative Update vom November 2016 aktualisiert haben, finden Sie weitere Informationen unter [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Für jede Notrufnummer können Sie null oder mehr Notrufwählmasken angeben, die für eine bestimmte Standortrichtlinie eindeutig sind.
    
    Eine Wählmaske ist eine Nummer, die Sie beim Wählen in den Wert der Notrufnummer übersetzen möchten. Angenommen, Sie geben in dieses Feld den Wert 212 ein, und das Feld für notrufnummer hat den Wert 911. Wenn ein Benutzer 212 wählt, wird die Nummer in 911 übersetzt. Auf diese Weise können alternative Notrufnummern gewählt werden, und der Anruf wird weiterhin an die Notrufdienste angerufen (z. B. wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Nummer dieses Landes oder dieser Region anstelle der Nummer für das Land oder die Region zu wählen, in dem sie sich gerade befindet). (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Lands zu wählen, und nicht die Notrufnummer des Lands oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Die Zeichenfolgenbeschränkung für eine Wählmaske beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.
    
- Jede Standortrichtlinie verfügt über eine einzelne PSTN-Nutzung, die verwendet wird, um zu bestimmen, welche Sprachroute zum Routen von Notrufen von Clients verwendet wird, die diese Richtlinie verwenden. Die Verwendung kann eine eindeutige Route pro Notrufnummer haben.
    
- Wenn für eine Standortrichtlinie sowohl die Parameter "EmergencyNumbers" als auch "DialString" definiert sind und der Client mehrere Notrufnummern unterstützt, hat die Notrufnummer Vorrang. Wenn der Client nicht mehrere Notrufnummern unterstützt, wird die Notrufwählzeichenfolge verwendet.
    
- Informationen dazu, welche Skype for Business- und Lync-Clients den Empfang mehrerer Notrufnummern, Wählmasken und Verwendungen im Telefonnetz (Public Switched Telephone Network, PSTN) unterstützen, finden Sie unter [Clientsupport.](multiple-emergency-numbers.md#BKMK_Clients)
    
> [!NOTE]
> Sie können nicht mehrere Notrufnummern mithilfe der Skype for Business-Systemsteuerung konfigurieren. Sie müssen PowerShell verwenden, um mehrere Notrufnummern zu konfigurieren. 
  
Beachten Sie folgendes, bevor Sie mehrere Notrufnummern konfigurieren:
  
- Zum Konfigurieren mehrerer Notrufnummern müssen Sie das Cmdlet New-CsEmergencyNumber verwenden und Standortrichtlinien definieren, die mehrere Notrufnummern unterstützen, indem Sie den Parameter "EmergencyNumbers" mit den Cmdlets ["New-CsLocationPolicy"](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) und ["Set-CsLocationPolicy"](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) angeben.
    
- Wenn Sie vorhandene Nummern mit dem Cmdlet Set-CsLocationPolicy oder New-CsLocationPolicy mit den Parametern EmergencyDialString und EmergencyDialMask definiert haben, haben die mit dem Parameter "EmergencyNumbers" angegebenen Werte Vorrang vor den alten Werten. Das heißt, die Werte für die Parameter "EmergencyDialString" und "EmergencyDialMask" werden ignoriert.
    
- Wenn Sie vorhandene Nummern mit dem Cmdlet Set-CsLocationPolicy oder New-CsLocationPolicy mit den Parametern EmergencyDialString und EmergencyDialMask definiert haben und keine neuen Notrufnummern  *konfigurieren,*  werden die vorhandenen Nummern weiterhin verwendet.
    
- Damit die Funktion für mehrere Notrufnummern funktioniert, müssen die clientversionen, die Sie ausführen, in der Lage sein, das neue Feature zu unterstützen. Ältere Clients verwenden weiterhin die alten Werte, die von den cmdlets Set-CsLocationPolicy oder New-CsLocationPolicy emergencyDialString und EmergencyDialMask angegeben werden. 
    
- Wenn die Benutzer eine Nummer wählen, die der Wählzeichenfolge entspricht, ist keine Wählmaske erforderlich. Wenn beispielsweise die Nummer, die ein Benutzer wählt, 911 ist, ist die Wählzeichenfolge 911, und es ist keine Maske erforderlich. 
    
Weitere Informationen zum Konfigurieren mehrerer Notrufnummern finden Sie unter ["Konfigurieren mehrerer Notrufnummern in Skype for Business".](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)
  
In der folgenden Tabelle sind Beispielspeicherortrichtlinien aufgeführt (im Beispiel werden nicht alle Attribute gezeigt):
  

|**Name der Standortrichtlinie**|**E911 aktiviert**|**Notrufwählzeichenfolge**|**Wählmaske**|**Notrufnummern**|**PSTN-Verwendung**|**Erforderlicher Standort**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Vereinigte Staaten  <br/> |Ja  <br/> |911  <br/> | 112;999 <br/> ||USEmergency  <br/> |Ja  <br/> |
|US-Hospital  <br/> |Ja  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Ja  <br/> |
|London  <br/> |Ja  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911;117;118  <br/> |GBEmergency  <br/> |Nein  <br/> |
|Indien  <br/> |Ja  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Nein  <br/> |
   
 **Vereinigte Staaten** – Es ist nicht erforderlich, mehrere Notrufnummern zu verwenden. In den USA verwenden Sie die alten Konfigurationen für Notrufwählzeichenfolgen und Wählmasken.
  
 **US-Krankenhaus** – Es ist erforderlich, "450" nicht zu maskieren. Für Clients, die noch nicht mehrere Notrufnummern unterstützen, können Sie die alten Konfigurationen für Notrufwählzeichenfolge und Wählmaske verwenden. Für Clients, die mehrere Notrufnummern unterstützen, können Sie eine Notrufnummer für "911" und "450" definieren, anstatt 450 zu maskieren.
  
 **London** – Für Clients, die noch nicht mehrere Notrufnummern unterstützen, können Sie die alten Konfigurationen für Notrufwählzeichenfolge und Wählmaske verwenden. Für Clients, die mehrere Notrufnummern unterstützen, können Sie eine Notrufnummer für "999" und "112" mit Masken definieren.
  
 **Indien** – Alle bereitgestellten Clients unterstützen mehrere Notrufnummern. In Indien müssen Sie nur mehrere Notrufnummern konfigurieren.
  
## <a name="client-support"></a>Clientunterstützung
<a name="BKMK_Clients"> </a>

In der folgenden Tabelle ist die Clientunterstützung für mehrere Notrufnummern aufgeführt. Microsoft wird die Unterstützung für weitere Clients weiterhin testen und veröffentlichen. Besuchen Sie diese Website regelmäßig.

|**Windows**|**Version**|
|:-----|:-----|
|**Klick-und-Los** <br/> |CC (aktueller Kanal) veröffentlicht am 10. Mai 2016 - Version 1604 (Build 6868.2062)  <br/> |
||FRDC (First Release Current Channel) veröffentlicht am 14. Juni 2016 - Version 1605 (Build 6965.2058)  <br/> |
||DC (Verzögerter Kanal) veröffentlicht am 11. Oktober 2016 - Version 1605 (Build 6965.2092)  <br/> |
|**MSI** <br/> |Update vom 7. Juni – [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac und iOS** <br/> |**Version** <br/> |
||Skype for Business Mac Client, Version 16.9  <br/> Skype for Business iOS Client Version 6.16  <br/> |
|**Android** <br/> |**Version** <br/> |
||Skype for Business Android Client Version 6.17  <br/> |
|**Lync Phone Edition** <br/> |**Version** <br/> |
|| Aastra 6721ip- und Aastra 6725ip-Telefone – kumulatives Update vom September 2016 (Build 7577.4512) -[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110- und HP 4120-Telefone – kumulatives Update vom September 2016 (Build 7577.4512) –[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500-, Polycom CX600- und Polycom CX3000-Telefone – kumulatives Update vom September 2016 (Build 7577.4512) - [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
   

