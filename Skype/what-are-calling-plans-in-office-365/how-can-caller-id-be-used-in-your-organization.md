---
title: "Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation"
ms.author: tonysmit
author: tonysmit
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
description: "Anrufer-ID kann für eingehende und ausgehende Anrufe für Telefonsystem Benutzer mithilfe einer Richtlinie mit der Bezeichnung CallingLineIdentity gesteuert werden."
---

# Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](5a0bd8ba-3334-46ee-becf-1025597737f6.md#MT_Footer).  
  
Anrufer-ID kann für eingehende und ausgehende Anrufe für Telefonsystem Benutzer mithilfe einer Richtlinie mit der Bezeichnung CallingLineIdentity gesteuert werden.
  
Die Anrufer-ID-Funktionalität ist für alle Benutzer von Telefonsystem unabhängig davon PSTN-Konnektivität verfügbar:
  
- Online-PSTN-Anbindung
    
- Lokale PSTN-Anbindung mit Skype for Business Cloud Connector Edition (erfordert Cloud Connector Edition 1.4.2 oder höher)
    
- Lokale PSTN-Anbindung mit Skype for Business Server (erfordert Skype for Business Server 2015 CU5 oder höher)
    
> [!NOTE]
> Diese Richtlinie ist in Skype for Business Server 2015 nicht verfügbar. 
  
## Ausgehende Anrufer-ID

Für die ausgehende PSTN-Anrufer-ID sind drei Optionen verfügbar:
  
- Die Telefonnummer für den Benutzer, der Standard zugewiesen.
    
- Eine Telefonnummer, die als  *Dienst*  klassifiziert ist und *kostenlosen weder eine gebührenpflichtige*  Nummer in Ihrem aufrufen Pläne in Office 365-Telefon Nummer Inventory. Es wird in der Regel eine Organisation automatische Telefonzentrale oder einen Anruf Warteschlange zugewiesen.
    
- Auf „Anonym" festgelegt
    
Die folgenden Arten von Telefonnummern können Sie jedoch nicht als ausgehende Anrufer-ID nicht zuweisen:
  
- Eine beliebige Telefonnummern zu erhalten, die als ein  *Benutzer*  in Ihrem Telefon aufrufen Pläne klassifiziert werden Zahl inventory
    
- Lokale Skype for Business Server-Telefonnummern
    
Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).
  
### Steuerung der ausgehenden Anrufer-ID durch Endbenutzer

Das Attribut EnableUserOverride kann einzelne oder mehrere Benutzer ihre Anrufer-ID-Einstellung auf **Anonym** ändern. Dies trifft nur zu, wenn eine CallingLineIdentity Richtlinie mit einem CallingIDSubstitute Parameter entweder LineURI oder Substitute konfiguriert ist. Der Standardwert für EnableUserOverride ist falsch.
  
Ihre Endbenutzer können ihre Anrufer-ID mithilfe der Registerkarte **Anrufen weiterleiten Einstellungen** in den Skype für Business-Desktopclient auf **Anonym** festgelegt.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Version** <br/> |**Unterstützt** <br/> |
|Klick-und-Los  <br/> |Aktueller Kanal, Veröffentlichung am 6. Dezember 2016 - Version 1611 (Build 7571.2072)  <br/> |Ja  <br/> |
|Klick-und-Los  <br/> |First Release für verzögerten Kanal, Veröffentlichung am 22. Februar 2017 - Version 1701 (Build 7766.2060)  <br/> |Ja  <br/> |
|Klick-und-Los  <br/> |Zurückgestellt Channel freigegeben auf 13 Juni 2017 - Version 1701 (7766.2092 erstellen)  <br/> |Ja  <br/> |
|MSI  <br/> |Skype for Business  <br/> |Nein  <br/> |
|Mac  <br/> |Skype for Business  <br/> |Nein  <br/> |
   
Die Endbenutzer können ihre Anrufer ID-Einstellung auch auf der Seite mit den Benutzereinstellungen unter [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling) festlegen.
  
## Eingehende Anrufer-ID

Das Attribut BlockIncomingCallerID ermöglicht die Anrufer-ID bei eingehenden PSTN anrufen blockieren. Sie können dieses Attribut festlegen, aber es ist nicht verfügbar für Ihre Endbenutzer auf der Benutzerseite. Und es steht zurzeit nur mit Online PSTN-Konnektivität.
  
Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  
## Siehe auch
<a name="MT_Footer"> </a>

#### Weitere Ressourcen

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)
  
[Audio-Konferenzen Grußformeln durchführen Periode](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

