---
title: "Wie sollte ich die Telefonnummern eingeben?"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- ms.lync.lac.PortOrderNumbers
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
description: "Learn how to set up phone numbers when you port them to Skype for Business. "
---

# Wie sollte ich die Telefonnummern eingeben?

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](28aa24b4-8c81-4327-9752-989ea7540db2.md#MT_Footer).  
  
Beim Portieren Telefonnummern zu erhalten, müssen Sie diese im korrekten Format eingeben.
  
> [!NOTE]
> Jede Telefonnummer oder jeder Telefonnummernbereich muss in die jeweilige Zeile separat eingegeben werden. 
  
- Bei der Eingabe einzelner Telefonnummern:
    
  - Werden alle Sonderzeichen ignoriert (auch der Bindestrich „-"). Beispiel:
    
  - Für eine 10-stellige Zahl: **&amp;*(425*()(*&amp;4&amp;*())(*250649** wird korrigiert zu **+14255550649**.
    
  - Für eine 11-stellige Zahl: **1*()(*&amp;42&amp;*()(*&amp;55550649** wird korrigiert zu **+14255550649**.
    
  - Alle Tags werden ignoriert, wenn sie 10 oder 11 Ziffern umfassen. Beispiel: **<div> 4255551234</div>** wird zu **+14255551234**.
    
  - „-", Leerzeichen und Klammern werden ignoriert. Beispiel:
    
  - Für eine 10-stellige Zahl: **(425) 555-6776** wird korrigiert zu **+14255556776**.
    
  - Für eine 11-stellige Zahl: **1(425) 555-6776** wird korrigiert zu **+14255556776**.
    
  - Aller Buchstaben werden ignoriert, wenn es eine Telefonnummer 10 Ziffern oder 11 zweistellig ist und als Sonderzeichen behandelt werden. Zum Beispiel:
    
  - Für eine 10-stellige Zahl: **14jaosia2reoij05jof55506ajfoj49isdjf** wird korrigiert zu **+14255550649**.
    
  - Für eine 11-stellige Zahl: **1ade4jaoda2rfoij05ojof55506dsfoj49if** wird korrigiert zu **+14255550649**.
    
  - Jede Kombination von Sonderzeichen, selbst in anderen Sprachen, wird korrigiert. Beispiel: 
    
  - Für eine 10-stellige Zahl: **中文4中文2ajj5*（）（*（5()...551345** wird korrigiert zu **+14555551345**.
    
  - Für eine 11-stellige Zahl: **中文4中文2$a5*（）（*（5()...55(.1345** wird korrigiert zu **+14555551345**.
    
  - Wenn die Nummer ein, die weniger als 10 Ziffern oder mehr als 11 Stellen enthalten, werden sie für den Benutzer zur Behebung hervorgehoben:
    
  - ** 5551245** wird hervorgehoben und muss korrigiert werden.
    
  - **1234567891011** wird hervorgehoben und muss korrigiert werden.
    
  - Alle Zahlen, die weniger als 10 Ziffern oder mehr als 11 Stellen mit dieser Sonderzeichen, sind werden ohne, die automatisch korrigiert hervorgehoben.
    
  - Für 7 zweistellig Zahl ohne Sonderzeichen, die eingegeben werden: **123456abcdefg7** wird hervorgehoben werden und korrigiert werden müssen, aber die Buchstaben wird nicht ignoriert werden.
    
  - Für Zahl 7 zweistellig mit Sonderzeichen, die eingegeben werden: **12345!@#$%^ &amp; * () - @# $% ^ &amp; * (7)** werden hervorgehoben werden, um korrigiert werden. Die Sonderzeichen wird nicht ignoriert.
    
- Bei der Eingabe eines Telefonnummernbereichs.
    
  - Es sind nur zwei Telefonnummern zulässig. Die kleinere Nummer muss die erste Nummer im Bereich sein.
    
  - Alle Sonderzeichen (mit Ausnahme der Gedankenstrich "-") werden wie einzelne Zahlen behandelt. Beispielsweise **(425) 555 0 &amp; * (123-(1425) 5557899nm** werden korrigiert werden, um **+14255550123 - +13202040659**.
    
  - Die "-" wird zum Extrahieren nur der zwei Zahlen verwendet. Es nicht unterstützt, wenn Sie mehrere "-" im Bereich Zahl. Beispiel:, **(425) 555-0649-(425) 555-1115** eingegeben werden soll, als **(425) 5550649 - +(425) 5551115**.
    
 **Vollständige schrittweise Anweisungen finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).**
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  
## Siehe auch
<a name="MT_Footer"> </a>

#### Weitere Ressourcen

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)
  
[Audio-Konferenzen Grußformeln durchführen Periode](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

