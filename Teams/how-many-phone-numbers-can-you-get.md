---
title: Wie viele Telefonnummern können Sie bekommen?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Wenn Sie Telefonnummern für Ihre Organisation reservieren möchten, kann die Anzahl der reservierten Telefonnummern die Anzahl der zugewiesenen Lizenzen übersteigen. Dies richtet sich jedoch nach der Art der Telefonnummern und der Art der Lizenzen, die Sie gekauft haben und die Ihnen zugewiesen wurden. Sie können klicken Sie auf verschiedene Arten von Rufnummern für plant Aufrufen verwendet, um Informationen zu den verschiedenen Rufnummern finden Sie heraus, die in Skype für Business Online verwendet werden.
ms.openlocfilehash: fa2a33086d832cc7d35afa6da59f431ebae47b19
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "30352786"
---
# <a name="how-many-phone-numbers-can-you-get"></a>Wie viele Telefonnummern können Sie bekommen?

Wenn Sie Telefonnummern für Ihre Organisation reservieren möchten, kann die Anzahl der reservierten Telefonnummern die Anzahl der zugewiesenen Lizenzen übersteigen. Dies richtet sich jedoch nach der Art der Telefonnummern und der Art der Lizenzen, die Sie gekauft haben und die Ihnen zugewiesen wurden. Klicken Sie auf [verschiedene Arten von Rufnummern, die zum Aufrufen von plant](different-kinds-of-phone-numbers-used-for-calling-plans.md) , über die die verschiedenen Rufnummern finden Sie heraus, die in Skype für Business Online verwendet werden.
  
Sehen Sie die Anzahl der Rufnummern, die Sie auf der Seite **Telefonnummern** in das Skype für Business Administrationscenter erhalten können, oder Sie können das Cmdlet [Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/library/mt634605.aspx) ausführen.
  
> [!IMPORTANT]
> Die Beschränkungen unten beinhalten nicht die Telefonnummern, die Sie an Microsoft portiert oder übertragen haben. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>Wie viele Rufnummern erhalten Sie?

||||
|:-----|:-----|:-----|
|**Art der Telefonnummern** <br/> |**Wie reservieren Sie alle Telefonnummern?** <br/> |**Nachfolgend ein Beispiel** <br/> |
|Nummer des Benutzers (Abonnenten)  <br/> |Die Anzahl von Rufnummern ist gleich der Gesamtzahl der **Nationalen aufrufen planen** und/oder **in- und International aufrufen planen** Lizenzen multipliziert 1.1 + 10 weitere Telefonnummern. <br/> |Wenn ich 50 Benutzer in insgesamt mit entweder eine nationalen aufrufen planen und/oder nationalen und internationalen aufrufen planen, können Sie **65** Phone Number **(50 x 1.1 + 10)** erwerben. <br/> |
|Gebührenpflichtige Leistungsnummer  <br/> | Die Anzahl der Rufnummern ist gleich der Gesamtzahl der **Telefonsystem** und **Audiokonferenzen** Lizenzen und verwendet die folgenden: <br/>  Wenn Sie über **1-25 Lizenzen** verfügen, werden **5** Telefonnummern zugeteilt. <br/>  Wenn Sie über **26-49 Lizenzen** verfügen, werden **10** Telefonnummern zugeteilt. <br/>  Wenn es **50-99-Lizenzen sind** werden **20** Telefonnummern angegeben. <br/>  Wenn Sie über **100-149 Lizenzen** verfügen, werden **30** Telefonnummern zugeteilt. <br/>  Wenn Sie über **150-199 Lizenzen** verfügen, werden **40** Telefonnummern zugeteilt. <br/>  Wenn Sie über **200-499 Lizenzen** verfügen, werden **65** Telefonnummern zugeteilt. <br/>  Wenn Sie über **500-749 Lizenzen** verfügen, werden **90** Telefonnummern zugeteilt. <br/>  Wenn Sie über **750-999 Lizenzen** verfügen, werden **110** Telefonnummern zugeteilt. <br/>  Wenn Sie über **1.000-1.249 Lizenzen** verfügen, werden **125** Telefonnummern zugeteilt. <br/>  Wenn vorhanden **1.250 1,499 Lizenzen sind** werden Telefonnummern **135** angegeben. <br/>  Wenn Sie über **1.500-1.999 Lizenzen** verfügen, werden **160** Telefonnummern zugeteilt. <br/>  Wenn Sie über **2.000-2.999 Lizenzen** verfügen, werden **210** Telefonnummern zugeteilt. <br/>  Wenn Sie über **3.000-6.999 Lizenzen** verfügen, werden **420** Telefonnummern zugeteilt. <br/>  Wenn Sie über **7.000-9.999 Lizenzen** verfügen, werden **500** Telefonnummern zugeteilt. <br/>  Wenn Sie über **10.000-14.999 Lizenzen** verfügen, werden **600** Telefonnummern zugeteilt. <br/>  Wenn Sie über **15.000-19.999 Lizenzen** verfügen, werden **700** Telefonnummern zugeteilt. <br/>  Wenn Sie über **20.000-49.999 Lizenzen** verfügen, werden **1000** Telefonnummern zugeteilt. <br/>  Wenn Sie über **mehr als 50.000 Lizenzen** verfügen, werden **1.500** Telefonnummern zugeteilt. <br/> |Wenn Sie insgesamt **51** **Telefonsystem** und **Audiokonferenzen** Lizenzen haben, können Sie die Nummern von **20** gebührenpflichtige Service abrufen. <br/> |
|Gebührenfreie Leistungsnummer  <br/> | Die Anzahl der Rufnummern ist gleich der Gesamtzahl der **Telefonsystem** und **Audiokonferenzen** Lizenzen und verwendet die folgenden: <br/>  Wenn Sie über **1-25 Lizenzen** verfügen, werden **5** Telefonnummern zugeteilt. <br/>  Wenn Sie über **26-49 Lizenzen** verfügen, werden **10** Telefonnummern zugeteilt. <br/>  Wenn es **50-99-Lizenzen sind** werden **20** Telefonnummern angegeben. <br/>  Wenn Sie über **100-149 Lizenzen** verfügen, werden **30** Telefonnummern zugeteilt. <br/>  Wenn Sie über **150-199 Lizenzen** verfügen, werden **40** Telefonnummern zugeteilt. <br/>  Wenn Sie über **200-499 Lizenzen** verfügen, werden **65** Telefonnummern zugeteilt. <br/>  Wenn Sie über **500-749 Lizenzen** verfügen, werden **90** Telefonnummern zugeteilt. <br/>  Wenn Sie über **750-999 Lizenzen** verfügen, werden **110** Telefonnummern zugeteilt. <br/>  Wenn Sie über **1.000-1.249 Lizenzen** verfügen, werden **125** Telefonnummern zugeteilt. <br/>  Wenn vorhanden **1.250 1,499 Lizenzen sind** werden Telefonnummern **135** angegeben. <br/>  Wenn Sie über **1.500-1.999 Lizenzen** verfügen, werden **160** Telefonnummern zugeteilt. <br/>  Wenn Sie über **2.000-2.999 Lizenzen** verfügen, werden **210** Telefonnummern zugeteilt. <br/>  Wenn Sie über **3.000-6.999 Lizenzen** verfügen, werden **420** Telefonnummern zugeteilt. <br/>  Wenn Sie über **7.000-9.999 Lizenzen** verfügen, werden **500** Telefonnummern zugeteilt. <br/>  Wenn Sie über **10.000-14.999 Lizenzen** verfügen, werden **600** Telefonnummern zugeteilt. <br/>  Wenn Sie über **15.000-19.999 Lizenzen** verfügen, werden **700** Telefonnummern zugeteilt. <br/>  Wenn Sie über **20.000-49.999 Lizenzen** verfügen, werden **1000** Telefonnummern zugeteilt. <br/>  Wenn Sie über **mehr als 50.000 Lizenzen** verfügen, werden **1.500** Telefonnummern zugeteilt. <br/> |Wenn Sie insgesamt **1001** **Telefonsystem** und **Audiokonferenzen** Lizenzen haben, können Sie **125** Service gebührenfreie Nummern abrufen. <br/> <br/> **Wichtig:** [Abrechnung Communications haben](set-up-communications-credits-for-your-organization.md) ist erforderlich, um reservieren und gebührenfreien Telefonnummern verwenden.          |
   
> [!NOTE]
> Wenn Sie mehr als die angegebenen Telefonnummern benötigen, lesen Sie [Kontaktieren des Supports für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
  
## <a name="related-topics"></a>Verwandte Themen
[Allgemeine Fragen zum Übertragen von Telefonnummern](transferring-phone-numbers-common-questions.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 