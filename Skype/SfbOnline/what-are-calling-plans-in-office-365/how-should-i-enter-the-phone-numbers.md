---
title: Wie sollte ich die angezeigten Rufnummern eingeben?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: "Erfahren Sie, wie Telefonnummern einrichten, wenn Sie diese zu Skype für Unternehmen port. "
ms.openlocfilehash: a7364c5ebf72730179c6848dc79172f4f971ff6a
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a>Wie sollte ich die angezeigten Rufnummern eingeben?

Wenn Sie Rufnummern portieren, müssen Sie diese im richtigen Format eingeben. 
  
> [!NOTE]
> Jede Telefonnummer oder der Bereich der Telefonnummer muss separat in jeder Zeile eingegeben werden. 
  
- Wenn Sie einzelne Rufnummern eingeben:
    
  - Alle Sonderzeichen ignoriert (einschließlich Strich "-"). Beispiel:
    
  - Für eine Zahl 10: ** &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649** wird auf **+14255550649**korrigiert werden.
    
  - Für eine Nummer 11: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** wird auf **+14255550649**korrigiert werden.
    
  - Alle Tags werden ignoriert, wenn 10 oder 11 Ziffern vorhanden sind. Beispielsweise ** \<Div > 4255551234\</div >** **+ 14255551234**werden.
    
  - "-", Leerzeichen und Klammern werden ignoriert. Beispiel:
    
  - Für eine Zahl 10: **(425) 555-6776** wird zu **+14255556776**korrigiert werden.
    
  - Für eine Nummer 11: **1(425) 555-6776** wird auf **+14255556776**korrigiert werden.
    
  - Alle Buchstaben werden als Sonderzeichen behandelt und eine Telefonnummer Ziffern 10 oder 11 Ziffer wird ignoriert, wenn werden. Beispiel:
    
  - Für eine Zahl 10: **14jaosia2reoij05jof55506ajfoj49isdjf** wird zu **+14255550649**korrigiert werden.
    
  - Für eine Nummer 11: **1ade4jaoda2rfoij05ojof55506dsfoj49if** wird zu **+14255550649**korrigiert werden.
    
  - Eine beliebige Kombination von Sonderzeichen, auch in anderen Sprachen werden korrigiert. Beispiel: 
    
  - Für eine Zahl 10:**中文4中文2ajj5\*() (\*(5()... 551345** wird auf **+14555551345**korrigiert werden.
    
  - Für eine Nummer 11:**中文4中文2$ a5\*() (\*(5()... 55 (.1345** wird auf **+14555551345**korrigiert werden.
    
  - Wenn alle Zahlen weniger als 10 Ziffern oder mehr als 11 Ziffern enthalten, werden sie für den Benutzer an den richtigen hervorgehoben:
    
  - \*\*5551245\* \* wird hervorgehoben und behoben werden müssen.
    
  - **1234567891011** wird hervorgehoben und korrigiert werden müssen.
    
  - Ohne wird automatisch korrigiert werden alle Zahlen, die weniger als 10 Ziffern oder mehr als 11 Stellen mit keine Sonderzeichen sind hervorgehoben.
    
  - Für eine 7 Ziffer Zahl ohne Sonderzeichen, die eingegeben wird: **123456abcdefg7** wird hervorgehoben und behoben werden, müssen jedoch die Buchstaben werden nicht ignoriert werden.
    
  - Für 7 Ziffer Zahl mit Sonderzeichen, die eingegeben werden: **12345!@#$%^&amp;\*() – @# $% ^&amp;\*(7)** wird hervorgehoben werden, um korrigiert werden. Sonderzeichen werden nicht ignoriert.
    
- Wenn Sie einen Bereich von Rufnummern eingeben.
    
  - Nur zwei Telefonnummern sind zulässig. Die kleinere Anzahl muss die erste Zahl im Bereich.
    
  - Alle Sonderzeichen (mit Ausnahme der Strich "-") sind wie einzelne Zahlen behandelt. Beispielsweise **(425) 555 0&amp;\*(123-(1425) 5557899nm** wird zum behoben **+ 14255550123 - +13202040659**.
    
  - Die "-" wird zur Trennung nur zweier Zahlen verwendet. Es wird nicht unterstützt, um mehrere einschließen "-" in den Nummernbereich. Beispielsweise sollte **(425) 555-0649-(425) 555-1115** eingegeben werden, als **(425) 5550649 - (425) 5551115**.
    
 **Eine vollständige schrittweise Anleitung finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).**

 > [!NOTE]
> Wenn Sie mehr als die angegebenen Telefonnummern benötigen, lesen Sie [Kontaktieren des Supports für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

  
## <a name="related-topics"></a>Verwandte Themen
[Allgemeine Fragen zum Übertragen von Telefonnummern](transferring-phone-numbers-common-questions.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://go.microsoft.com/fwlink/?LinkID=692099)

## <a name="feedback"></a>Feedback?
Geben Sie Feedback zu Produkten oder uns Ihre Meinung kennen, finden Sie unter [Skype für Business Feedback](https://www.skypefeedback.com).