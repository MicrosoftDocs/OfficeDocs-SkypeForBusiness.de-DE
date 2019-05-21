---
title: Wie sollte ich die Telefonnummern eingeben?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Hier erfahren Sie, wie Sie Telefonnummern einrichten, wenn Sie Sie in Skype for Business portieren. '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280530"
---
# <a name="how-should-i-enter-the-phone-numbers"></a>Wie sollte ich die Telefonnummern eingeben?

Wenn Sie Telefonnummern portieren, müssen Sie diese im richtigen Format eingeben. 
  
> [!NOTE]
> Jede Telefonnummer oder jeder Rufnummernbereich muss für jede Zeile separat eingegeben werden. 
  
- Wenn Sie einzelne Telefonnummern eingeben:
    
  - Alle Sonderzeichen werden ignoriert (einschließlich Bindestrich "-"). Beispiel:
    
  - Für eine 10-stellige Zahl: ** &amp; \*(\*425 ()\*&amp;(&amp;\*4 ())\*(250649** wird auf **+ 14255550649**korrigiert.
    
  - Für eine 11-stellige Zahl **:\*1 ()\*&amp;(&amp;\*42 ()\*&amp;(55550649** wird auf **+ 14255550649**korrigiert.
    
  - Alle Tags werden ignoriert, wenn 10 oder 11 Ziffern vorhanden sind. Beispielsweise ist ** \<div> 4255551234\</div>** **+ 14255551234**.
    
  - "-", Leerzeichen und Klammern werden ignoriert. Beispiel:
    
  - Für eine 10-stellige Zahl: **(425) 555-6776** wird auf **+ 14255556776**korrigiert.
    
  - Für eine 11-stellige Zahl: **1 (425) 555-6776** wird auf **+ 14255556776**korrigiert.
    
  - Alle Buchstaben werden als Sonderzeichen behandelt und ignoriert, wenn eine 10-stellige oder eine 11-stellige Telefonnummer vorhanden ist. Beispiel:
    
  - Für eine 10-stellige Zahl: **14jaosia2reoij05jof55506ajfoj49isdjf** wird auf **+ 14255550649**korrigiert.
    
  - Für eine 11-stellige Zahl: **1ade4jaoda2rfoij05ojof55506dsfoj49if** wird auf **+ 14255550649**korrigiert.
    
  - Eine Kombination von Sonderzeichen, auch in anderen Sprachen, wird korrigiert. Beispiel: 
    
  - Für eine 10-stellige Zahl:**中文 4\*中文2ajj5 ()\*((5 ()... 551345** wird auf **+ 14555551345**korrigiert.
    
  - Für eine 11-stellige Zahl:**中文 4 中文 2 $\*A5 ()\*((5 ()... 55 (1345** wird auf **+ 14555551345**korrigiert.
    
  - Wenn zahlen weniger als 10 Ziffern oder mehr als 11 Ziffern enthalten, werden diese hervorgehoben, damit der Benutzer Sie korrigieren kann:
    
  - \*\*5551245\* \* wird hervorgehoben und muss korrigiert werden.
    
  - **1234567891011** wird hervorgehoben und muss korrigiert werden.
    
  - Zahlen, die weniger als 10 Ziffern oder mehr als 11 Ziffern mit Sonderzeichen enthalten, werden hervorgehoben, ohne dass Sie automatisch korrigiert werden.
    
  - Für eine siebenstellige Zahl ohne eingegebene Sonderzeichen: **123456abcdefg7** wird hervorgehoben und muss korrigiert werden, aber die Buchstaben werden nicht ignoriert.
    
  - Bei einer siebenstelligen Zahl mit Sonderzeichen, die eingegeben werden **: 12345! @ # $%&amp;\*^ ()--@ # $%&amp;\*^ () 7** wird hervorgehoben, um korrigiert zu werden. Die Sonderzeichen werden nicht ignoriert.
    
- Wenn Sie einen Bereich von Telefonnummern eingeben.
    
  - Nur zwei Telefonnummern sind zulässig. Die kleinere Zahl muss die erste Zahl im Bereich sein.
    
  - Alle Sonderzeichen (mit Ausnahme des Bindestrichs "-") werden wie einzelne Zahlen behandelt. Beispielsweise wird **(425) 555 0&amp;\*(123-(1425) 5557899nm** auf **+ 14255550123-+ 13202040659**korrigiert.
    
  - Das "-" wird verwendet, um nur die beiden Zahlen voneinander zu trennen. Es wird nicht unterstützt, mehrere "-" im Zahlenbereich einzubeziehen. Beispielsweise sollte **(425) 555-0649-(425) 555-1115** als **(425) 5550649-(425) 5551115**eingegeben werden.
    
  **Eine vollständige Schritt-für-Schritt-Anleitung finden Sie unter [übertragen von Telefonnummern zu Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**

  > [!NOTE]
  > Wenn Sie mehr als die angegebenen Telefonnummern benötigen, lesen Sie [Kontaktieren des Supports für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

  
## <a name="related-topics"></a>Verwandte Themen
[Allgemeine Fragen zum Übertragen von Telefonnummern](/microsoftteams/transferring-phone-numbers-common-questions)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 