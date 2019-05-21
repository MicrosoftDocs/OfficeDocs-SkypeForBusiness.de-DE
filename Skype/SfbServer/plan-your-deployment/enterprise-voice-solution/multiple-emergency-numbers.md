---
title: Planen mehrerer Notrufnummern in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: In diesem Thema erfahren Sie, wie Sie in Skype for Business Server mehrere Notfallnummern planen können.
ms.openlocfilehash: 43214e42e4fd998aef673ad8d0fbd57ec2d3b498
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276845"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planen mehrerer Notrufnummern in Skype for Business Server
 
In diesem Thema erfahren Sie, wie Sie in Skype for Business Server mehrere Notfallnummern planen können.
  
Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Mehrere Notfallnummern sind eine neue Funktion, die im kumulativen Update vom Juni 2016 eingeführt wurde. Während es in den Vereinigten Staaten eine einzige Notrufnummer gibt (911), sind in vielen Ländern mehrere Notrufnummern möglich. Das Vereinigte Königreich beispielsweise unterstützt sowohl 999, die für das Vereinigte Königreich spezifische Notrufnummer als auch 112, die Notrufnummer für die Europäische Union. 
  
Diese Funktion ist auch nützlich für Versorger im Gesundheitsweisen der Vereinigten Staaten, die Roamingunterstützung für mehrere Rufnummern für medizinische Notfälle benötigen.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Mehrere Notrufnummern und Standortrichtlinien

Sie konfigurieren Notrufe, indem Sie Positions Richtlinien erstellen, die definieren, wie Notrufe implementiert werden. Sie verwenden die ortungsrichtlinie, um festzulegen, welche Nummer ein Notruf ist, beispielsweise 911 in den USA; 999 und 112 in Großbritannien. Die ortungsrichtlinie bestimmt, ob ein Benutzer für Notrufe aktiviert ist, und wenn ja, was das Verhalten eines Notrufs ist. Sie können auch festlegen, ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.
  
Weitere Informationen zum Definieren und Ändern einer Standortrichtlinie finden Sie unter [Planen von Standortrichtlinien für Skype for Business Server](location-policies.md) und [Erstellen von Standortrichtlinien in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). In diesen Themen werden Konzepte für Standortrichtlinien beschrieben. Sie müssen jedoch die Anweisungen unter [Konfigurieren mehrerer Notrufnummern in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) befolgen, um mehrere Notfallnummern zu konfigurieren.
  
Berücksichtigen Sie beim Planen mehrerer Notrufnummern Folgendes:
  
- Mit dem kumulativen Update vom Juni 2016 können Sie bis zu fünf Notrufnummern für eine bestimmte Standortrichtlinie definieren. Mit dem kumulativen Update vom November 2016 steigt diese Zahl auf 100.
    
    > [!NOTE]
    > Wenn Sie noch nicht auf das kumulative Update vom November 2016 aktualisiert haben, lesen Sie [Updates für Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Für jede Notrufnummer können Sie NULL oder mehr Notfall-Wähl Masken angeben, die für eine bestimmte Standortrichtlinie eindeutig sind.
    
    Eine Wähl Maske ist eine Zahl, die Sie in den Wert des Notrufnummern Werts übersetzen möchten, wenn Sie gewählt wird. Nehmen Sie beispielsweise an, dass Sie in diesem Feld den Wert 212 eingeben und das Feld Notrufnummer den Wert 911 hat. Wenn ein Benutzer 212 anwählt, wird die Nummer in 911 übersetzt. Auf diese Weise können alternative Notrufnummern gewählt werden, und der Anruf kann immer noch in Notfällen erfolgen (Wenn beispielsweise jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Nummer des Landes oder der Region zu wählen, anstatt die Nummer des Land oder Region, in dem Sie sich gerade befinden). (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Landes zu wählen, und nicht die Notrufnummer des Landes oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Die Zeichenfolgenbeschränkung für eine Wähl Maske beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.
    
- Jede Standortrichtlinie gibt eine einzige PSTN-Verwendung an. Mit dieser wird die VoIP-Route für die Weiterleitung von Notrufen über die Clients bestimmt, die die jeweilige Richtlinie verwenden. Dabei kann für jede Notrufnummer eine eindeutige Route vorgesehen sein.
    
- Wenn in einer Standortrichtlinie die Parameter „EmergencyNumbers“ und „DialString“ definiert sind und der Client mehrere Notrufnummern unterstützt, hat die Notrufnummer Vorrang. Wenn der Client mehrere Notrufnummern nicht unterstützt, wird die Notrufwählzeichenfolge verwendet.
    
- Informationen zu den Skype for Business-und lync-Clients, die Unterstützung für den Empfang mehrerer Notrufnummern, Wähl Masken und PSTN-Nutzungen (Public Switched Telephone Network) erhalten, finden Sie unter [Client Support](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Mit dem Skype Control Panel für Unternehmen können Sie nicht mehrere Notrufnummern konfigurieren. Für diesen Vorgang müssen Sie die PowerShell verwenden. 
  
Berücksichtigen Sie vor dem Konfigurieren mehrerer Notrufnummern Folgendes:
  
- Wenn Sie mehrere Notfallnummern konfigurieren möchten, müssen Sie das Cmdlet New-CsEmergencyNumber verwenden, und Sie müssen Standortrichtlinien definieren, die mehr als eine Notrufnummer unterstützen, indem Sie den EmergencyNumbers-Parameter mit dem [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) und Cmdlets für [CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- 	Wenn Sie anhand des Cmdlets Set-CsLocationPolicy oder New-CsLocationPolicy vorhandene Nummern mit den Parametern EmergencyDialString und EmergencyDialMask definiert haben, haben die mit dem Parameter EmergencyNumbers angegebenen Werte Vorrang vor den alten Werten. Dies bedeutet, dass die Werte für die Parameter EmergencyDialString und EmergencyDialMask ignoriert werden.
    
- Wenn Sie vorhandene Nummern mit dem Cmdlet "CsLocationPolicy" oder "New-CsLocationPolicy" mit den Parametern EmergencyDialString und EmergencyDialMask definiert haben *und keine neuen Notrufnummern konfigurieren* , werden die vorhandenen Nummern weiterhin verwendet werden.
    
- Zur reibungslosen Verwendung der Funktion für mehrere Notrufnummern müssen die von Ihnen ausgeführten Clientversionen diese neue Funktion unterstützen. Ältere Clients verwenden weiterhin die vom Cmdlet Set-CsLocationPolicy oder New-CsLocationPolicy angegebenen Werte mit den Parametern EmergencyDialString und EmergencyDialMask. 
    
- Wenn die Benutzer eine Nummer wählen, die der Wählzeichenfolge entspricht, ist keine Wählmaske erforderlich. Wenn es sich zum Beispiel bei der vom Benutzer gewählten Nummer um 911 handelt, ist die Wählzeichenfolge 911, und es ist keine Wählmaske erforderlich. 
    
Weitere Informationen zum Konfigurieren mehrerer Notrufnummern finden Sie unter [Konfigurieren mehrerer Notrufnummern in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
Die folgende Tabelle zeigt Beispiele für Standortrichtlinien (da es sich um Beispiele handelt, sind nicht alle Attribute enthalten):
  

|**Name der Standortrichtlinie**|**Notrufe aktiviert**|**Notrufwählzeichenfolge**|**Wählmaske**|**Notrufnummern**|**PSTN-Verwendung**|**Standort erforderlich**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Vereinigte Staaten  <br/> |Ja  <br/> |911  
  <br/> | 112;999 <br/> ||USEmergency  <br/> |Ja  <br/> |
|US-Hospital  <br/> |Ja  <br/> |911  
  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Ja  <br/> |
|London  <br/> |Ja  <br/> |999  
  <br/> |144  <br/> |999-144  <br/> 112 – 911; 117; 118  <br/> |GBEmergency  <br/> |Nein  <br/> |
|India  <br/> |Ja  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Nein  <br/> |
   
 **Vereinigte Staaten** – es gibt keine Voraussetzungen für mehrere Notfallnummern. In den Vereinigten Staaten verwenden Sie die alte Notruf Zeichenfolge und die Wähl Masken Konfiguration.
  
 **US-Hospital** – es ist nicht erforderlich, "450" zu maskieren. Für Kunden, die noch nicht mehrere Notrufnummern unterstützen, können Sie die alte Notruf-und Wähl Masken-Konfiguration verwenden. Für Kunden, die mehrere Notfallnummern unterstützen, können Sie eine Notrufnummer für "911" und "450" definieren, anstatt 450 zu maskieren.
  
 **London** – für Kunden, die noch nicht mehrere Notfallnummern unterstützen, können Sie die alte Notruf Zeichenfolge und die Einstellungen für die Wähl Maske verwenden. Für Kunden, die mehrere Notrufnummern unterstützen, können Sie für beide "999" und "112" eine Notrufnummer definieren.
  
 **Indien** – alle bereitgestellten Clients unterstützen mehrere Notfallnummern. In Indien müssen Sie nur mehrere Notfallnummern konfigurieren.
  
## <a name="client-support"></a>Clientunterstützung
<a name="BKMK_Clients"> </a>

Die folgende Tabelle zeigt die Clientunterstützung für mehrere Notrufnummern. Microsoft testet die Unterstützung für weitere Clients und wird diese veröffentlichen. Überprüfen Sie diese Seite regelmäßig auf Aktualisierungen.

|**Windows**|**Version**|
|:-----|:-----|
|**Klick-und-Los** <br/> |CC (aktueller Kanal), veröffentlicht am 10. Mai, 2016-Version 1604 (Build 6868,2062)  <br/> |
||FRCC (First Release für aktuellen Kanal) veröffentlicht am 14. Juni 2016 - Version 1605 (Build 6965.2058)  <br/> |
||DC (Verzögerter Kanal) veröffentlicht am Dienstag, 11. Oktober 2016 - Version 1605 (Build 6965.2092)  <br/> |
|**MSI** <br/> |Update vom Juni 7 –[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac und IOS** <br/> |**Version** <br/> |
||Skype for Business-Mac-Client Version 16,9  <br/> Skype for Business IOS-Client Version 6,16  <br/> |
|**Android** <br/> |**Version** <br/> |
||Skype for Business-Android-Client Version 6,17  <br/> |
|**Lync Phone Edition** <br/> |**Version** <br/> |
|| Aastra 6721ip und Aastra 6725ip-Telefone-September 2016 Kumulatives Update (Build 7577,4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| HP 4110 und HP 4120-Telefone-September 2016 Kumulatives Update (Build 7577,4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Polycom CX500-, Polycom CX600-und Polycom-CX3000-Telefone-September 2016 Kumulatives Update (Build 7577,4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

