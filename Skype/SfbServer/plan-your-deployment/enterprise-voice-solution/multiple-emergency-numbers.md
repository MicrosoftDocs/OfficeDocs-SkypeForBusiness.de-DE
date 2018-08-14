---
title: Planen von mehreren Notfall Zahlen in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Lesen Sie in diesem Thema erfahren, wie mehrere Notfall Zahlen in Skype für Business Server planen.
ms.openlocfilehash: 48b71f5f4810378ec05ae769de4ec57b9a840a79
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979783"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planen von mehreren Notfall Zahlen in Skype für Business Server
 
Lesen Sie in diesem Thema erfahren, wie mehrere Notfall Zahlen in Skype für Business Server planen.
  
Skype für Business Server unterstützt jetzt die Konfiguration von mehreren Notfall Zahlen für einen Client an. Mehrere Notfall Nummern ist ein neues Feature in der Juni 2016 kumulative Update. Während es in den Vereinigten Staaten eine einzige Notrufnummer gibt (911), sind in vielen Ländern mehrere Notrufnummern möglich. Im Vereinigten Königreich, unterstützt beispielsweise 999, die speziell für die Vereinigtes Königreich Notrufnummer und 112, die Notrufnummer für die Europäische Union. 
  
Diese Funktion ist auch nützlich für Versorger im Gesundheitsweisen der Vereinigten Staaten, die Roamingunterstützung für mehrere Rufnummern für medizinische Notfälle benötigen.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Mehrere Notrufnummern und Standortrichtlinien

Sie konfigurieren Notfall aufrufen, indem Sie erstellen Speicherort Ihrer Richtlinien, die definieren, wie notrufdienste implementiert werden. Verwenden Sie die Standortrichtlinie um zu definieren, welche Anzahl, bildet einen Notruf – beispielsweise 911 in den USA; 999 und im Vereinigten Königreich 112. Die Standortrichtlinie bestimmt, ob ein Benutzer für notrufdienste aktiviert ist, und wenn dies der Fall ist was das Verhalten des ein Notruf ist. Sie können auch definieren, ob die Sicherheit im Unternehmen automatisch benachrichtigt werden soll, und wie der Anruf weitergeleitet werden sollen.
  
Weitere Informationen zum Definieren und Ändern einer ortungsrichtlinie finden Sie unter [Standortrichtlinien für Skype für Business Server planen](location-policies.md) und [Erstellen von Standortrichtlinien in Skype für Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). Die folgenden Themen beschreiben die Konzepte zur Standortrichtlinien; Folgen Sie jedoch die Anweisungen in [mehrere Notfall Zahlen in Skype für Unternehmen konfigurieren](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) mehrere Notfall Nummern konfigurieren.
  
Berücksichtigen Sie beim Planen mehrerer Notrufnummern Folgendes:
  
- Mit der Juni 2016 kumulative Update können bis zu 5 Notfall Zahlen für eine bestimmte ortungsrichtlinie zu definieren. Mit der 2016 November Kumulatives Update diese Nummer auf 100 erhöht.
    
    > [!NOTE]
    > Wenn Sie noch nicht auf die November 2016 aktualisiert haben kumulative Update finden Sie unter [Updates für Skype für Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Für jede Notrufnummer können Sie NULL oder mehr Notrufnummer Masken, angeben, die für einen bestimmten Standortrichtlinie eindeutig sind.
    
    Eine Zugriffsnummer Maske ist eine Zahl, die bei der aus sie gewählt wird in den Wert der Zahlenwert Notrufnummer übersetzt werden soll. Nehmen wir beispielsweise an, geben Sie einen Wert von 212 in dieses Feld und Feld Notrufnummer 911 Wert hat. Wenn ein Benutzer 212 wählt, wird die Anzahl 911 übersetzt werden. Dies ermöglicht eine alternative Notfall Nummern in gewählt werden und immer noch den Anruf erreichen der notrufdienste (z. B., wenn eine Person aus einem Land oder einer Region mit einem anderen Notrufnummer versucht, einwählen, Land oder Region Nummern und nicht die Anzahl für's der Land oder Region, die sie gerade werden). (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Landes zu wählen, und nicht die Notrufnummer des Landes oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Die Zeichenfolge für eine Zugriffsnummer Maske beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.
    
- Jede Standortrichtlinie gibt eine einzige PSTN-Verwendung an. Mit dieser wird die VoIP-Route für die Weiterleitung von Notrufen über die Clients bestimmt, die die jeweilige Richtlinie verwenden. Dabei kann für jede Notrufnummer eine eindeutige Route vorgesehen sein.
    
- Wenn in einer Standortrichtlinie die Parameter „EmergencyNumbers“ und „DialString“ definiert sind und der Client mehrere Notrufnummern unterstützt, hat die Notrufnummer Vorrang. Wenn der Client mehrere Notrufnummern nicht unterstützt, wird die Notrufwählzeichenfolge verwendet.
    
- Informationen über welche Skype für Unternehmen und Lync Clients unterstützt mehrere Notfall Nummern empfangen, Wähleinstellungen Masken und public switched Telephone Network, (PSTN) Verwendungen finden Sie unter [Client unterstützen](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Sie können nicht mehrere Notfall Nummern konfigurieren, mithilfe der Skype für die Business-Systemsteuerung. Für diesen Vorgang müssen Sie die PowerShell verwenden. 
  
Berücksichtigen Sie vor dem Konfigurieren mehrerer Notrufnummern Folgendes:
  
- Um mehrere Notfall Nummern zu konfigurieren, müssen Sie das Cmdlet "New-CsEmergencyNumber" verwenden, und definieren Sie ortungsrichtlinien, die mehr als eine Notrufnummer durch den EmergencyNumbers-Parameter angeben, mit dem [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) unterstützen und [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) -Cmdlets.
    
- 	Wenn Sie anhand des Cmdlets Set-CsLocationPolicy oder New-CsLocationPolicy vorhandene Nummern mit den Parametern EmergencyDialString und EmergencyDialMask definiert haben, haben die mit dem Parameter EmergencyNumbers angegebenen Werte Vorrang vor den alten Werten. Dies bedeutet, dass die Werte für die Parameter EmergencyDialString und EmergencyDialMask ignoriert werden.
    
- Wenn Sie Nummern mit dem Set-CsLocationPolicy oder New-CsLocationPolicy-Cmdlet mit den Parametern EmergencyDialString und EmergencyDialMask, *und Sie nicht neue Notfall Nummern konfigurieren* , definiert haben, werden mit Nummern fortgesetzt verwendet werden.
    
- Zur reibungslosen Verwendung der Funktion für mehrere Notrufnummern müssen die von Ihnen ausgeführten Clientversionen diese neue Funktion unterstützen. Ältere Clients verwenden weiterhin die vom Cmdlet Set-CsLocationPolicy oder New-CsLocationPolicy angegebenen Werte mit den Parametern EmergencyDialString und EmergencyDialMask. 
    
- Wenn die Benutzer eine Nummer wählen, die der Wählzeichenfolge entspricht, ist keine Wählmaske erforderlich. Wenn es sich zum Beispiel bei der vom Benutzer gewählten Nummer um 911 handelt, ist die Wählzeichenfolge 911, und es ist keine Wählmaske erforderlich. 
    
Weitere Informationen zur Konfiguration mehrerer Notfall Zahlen finden Sie unter [Configure Zahlen von mehreren Emergency in Skype für Unternehmen](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
Die folgende Tabelle zeigt Beispiele für Standortrichtlinien (da es sich um Beispiele handelt, sind nicht alle Attribute enthalten):
  

|**Name der Standortrichtlinie**|**Notrufe aktiviert**|**Notrufwählzeichenfolge**|**Wählmaske**|**Notruf Zahlen**|**PSTN-Verwendung**|**Standort erforderlich**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Vereinigte Staaten  <br/> |Ja  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |Ja  <br/> |
|US-Hospital  <br/> |Ja  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Ja  <br/> |
|London  <br/> |Ja  <br/> |999  <br/> |144  <br/> |999 144  <br/> 112 911 117; 118  <br/> |GBEmergency  <br/> |Nein  <br/> |
|India  <br/> |Ja  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Nein  <br/> |
   
 **Vereinigte Staaten** – besteht keine Notwendigkeit für mehrere Notfall Zahlen. In den Vereinigten Staaten verwenden Sie die alten Emergency Dial Zeichenfolge und Einwahl Maske Konfigurationen.
  
 **US-Krankenhaus** – es ist eine Voraussetzung nicht für "450" maskieren. Für Clients, die noch nicht über mehrere Notfall Nummern unterstützen, können Sie die alten Notfall DFÜ-Zeichenfolge und Einwahl Maske Konfigurationen. Für Clients, die mehrere Notfall Nummern zu unterstützen, können Sie eine Notrufnummer für "911" und "450" anstelle von 450 Maskierung definieren.
  
 **London** – für Clients, die noch nicht über mehrere Notfall Nummern unterstützen, können Sie die alten Notfall DFÜ-Zeichenfolge und Einwahl Maske Konfigurationen verwenden. Für Clients, die mehrere Notfall Nummern zu unterstützen, können Sie eine Notrufnummer für "999" und "112" mit Masken für jede definieren.
  
 **Indien** – alle bereitgestellten Clients bieten Unterstützung für mehrere Notfall Nummern. In Indien müssen Sie nur mehrere Notfall Nummern zu konfigurieren.
  
## <a name="client-support"></a>Clientunterstützung
<a name="BKMK_Clients"> </a>

Die folgende Tabelle zeigt die Clientunterstützung für mehrere Notrufnummern. Microsoft testet die Unterstützung für weitere Clients und wird diese veröffentlichen. Überprüfen Sie diese Seite regelmäßig auf Aktualisierungen.

|**Windows**|**Version**|
|:-----|:-----|
|**Klick-und-Los** <br/> |CC (aktuelle Channel) veröffentlicht auf 10 Mai 2016 - Version 1604 (Build 6868.2062)  <br/> |
||FRCC (First Release für aktuellen Kanal) veröffentlicht am 14. Juni 2016 - Version 1605 (Build 6965.2058)  <br/> |
||DC (Verzögerter Kanal) veröffentlicht am Dienstag, 11. Oktober 2016 - Version 1605 (Build 6965.2092)  <br/> |
|**MSI** <br/> |Update für Juni 7-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac und iOS** <br/> |**Version** <br/> |
||Skype für Business Mac Clientversion 16,9  <br/> Skype für Business iOS Clientversion 6.16  <br/> |
|**Android** <br/> |**Version** <br/> |
||Skype für Android Business Clientversion 6.17  <br/> |
|**Lync Phone Edition** <br/> |**Version** <br/> |
|| Aastra 6721ip und Aastra 6725ip Telefone - aktualisieren September 2016 kumulative (Build 7577.4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| HP 4110 und HP 4120 Telefone - September 2016 Kumulatives Update (Build 7577.4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Polycom CX500, Polycom CX600 und Polycom CX3000 Telefone - September 2016 Kumulatives Update (Build 7577.4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

