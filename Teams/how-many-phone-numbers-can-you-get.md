---
title: Wie viele Telefonnummern können Sie bekommen?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.quantity
- seo-marvel-mar2020
description: Erfahren Sie, wie viele Telefonnummern Sie in einem Microsoft Teams basierend auf dem Typ der Nummer und der Anzahl Ihrer Lizenzen erhalten.
ms.openlocfilehash: 8ee72f7af039fae5fc5f0a9b4983cc7d7691b2ce
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598529"
---
# <a name="how-many-phone-numbers-can-you-get"></a>Wie viele Telefonnummern können Sie bekommen?

Wenn Sie Telefonnummern für Ihre Organisation reservieren möchten, kann die Anzahl der reservierten Telefonnummern die Anzahl der zugewiesenen Lizenzen übersteigen. Dies richtet sich jedoch nach der Art der Telefonnummern und der Art der Lizenzen, die Sie gekauft haben und die Ihnen zugewiesen wurden. Sie können auf [Verschiedene Arten von Telefonnummern](different-kinds-of-phone-numbers-used-for-calling-plans.md) klicken, die für Anrufpläne verwendet werden, um informationen zu den verschiedenen Telefonnummern zu erhalten, die in einer Microsoft Teams.
  
Die Anzahl der Telefonnummern, die Sie  erhalten können, finden Sie auf der Seite Telefonnummern erhalten im Microsoft Teams Admin Center, oder Sie können das [Cmdlet Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/Get-CsOnlineTelephoneNumberAvailableCount) ausführen.
  
> [!IMPORTANT]
> Die Beschränkungen unten beinhalten nicht die Telefonnummern, die Sie an Microsoft portiert oder übertragen haben. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>Wie viele Telefonnummern können Sie erhalten?

||||
|:-----|:-----|:-----|
|**Art der Telefonnummern** <br/> |**Wie reservieren Sie alle Telefonnummern?** <br/> |**Nachfolgend ein Beispiel** <br/> |
|Nummer des Benutzers (Abonnenten)  <br/> |Die Anzahl der Telefonnummern entspricht der  Gesamtzahl der Lizenzen  für einen Plan für Inlandanrufe und/oder einen Plan für Inlands- und Auslandsanrufe multipliziert mit 1,1 + 10 zusätzliche Telefonnummern. <br/> |Wenn ich insgesamt 50 Benutzer mit einem Plan für Inlandanrufe und/oder einem Plan für Inlands- und Auslandsanrufe habe, können Sie **65** Telefonnummern **(50 x 1,1 + 10) erwerben.** <br/> |
|Gebührenpflichtige Leistungsnummer  <br/> | Die Anzahl der Telefonnummern entspricht der  Gesamtanzahl der Lizenzen Telefonsystem **audio conferencing (Audiokonferenz)** und verwendet Folgendes: <br/>  Wenn Sie über **1-25 Lizenzen** verfügen, werden **5** Telefonnummern zugeteilt. <br/>  Wenn Sie über **26-49 Lizenzen** verfügen, werden **10** Telefonnummern zugeteilt. <br/>  Wenn Sie **über 50-99 Lizenzen verfügen,** **werden 20** Telefonnummern angegeben. <br/>  Wenn Sie über **100-149 Lizenzen** verfügen, werden **30** Telefonnummern zugeteilt. <br/>  Wenn Sie über **150-199 Lizenzen** verfügen, werden **40** Telefonnummern zugeteilt. <br/>  Wenn Sie über **200-499 Lizenzen** verfügen, werden **65** Telefonnummern zugeteilt. <br/>  Wenn Sie über **500-749 Lizenzen** verfügen, werden **90** Telefonnummern zugeteilt. <br/>  Wenn Sie über **750-999 Lizenzen** verfügen, werden **110** Telefonnummern zugeteilt. <br/>  Wenn Sie über **1.000-1.249 Lizenzen** verfügen, werden **125** Telefonnummern zugeteilt. <br/>  Wenn Sie **über 1.250-1.499** Lizenzen verfügen, werden **135** Telefonnummern angegeben. <br/>  Wenn Sie über **1.500-1.999 Lizenzen** verfügen, werden **160** Telefonnummern zugeteilt. <br/>  Wenn Sie über **2.000-2.999 Lizenzen** verfügen, werden **210** Telefonnummern zugeteilt. <br/>  Wenn Sie über **3.000-6.999 Lizenzen** verfügen, werden **420** Telefonnummern zugeteilt. <br/>  Wenn Sie über **7.000-9.999 Lizenzen** verfügen, werden **500** Telefonnummern zugeteilt. <br/>  Wenn Sie über **10.000-14.999 Lizenzen** verfügen, werden **600** Telefonnummern zugeteilt. <br/>  Wenn Sie über **15.000-19.999 Lizenzen** verfügen, werden **700** Telefonnummern zugeteilt. <br/>  Wenn Sie über **20.000-49.999 Lizenzen** verfügen, werden **1000** Telefonnummern zugeteilt. <br/>  Wenn Sie über **mehr als 50.000 Lizenzen** verfügen, werden **1.500** Telefonnummern zugeteilt. <br/> |Wenn Sie über insgesamt **51**  Lizenzen für Telefonsystem **und Audiokonferenzen** verfügen, erhalten Sie **20** gebührenpflichtige Servicenummern. <br/> |
|Gebührenfreie Leistungsnummer  <br/> | Die Anzahl der Telefonnummern entspricht der  Gesamtanzahl der Lizenzen Telefonsystem **audio conferencing (Audiokonferenz)** und verwendet Folgendes: <br/>  Wenn Sie über **1-25 Lizenzen** verfügen, werden **5** Telefonnummern zugeteilt. <br/>  Wenn Sie über **26-49 Lizenzen** verfügen, werden **10** Telefonnummern zugeteilt. <br/>  Wenn Sie **über 50-99 Lizenzen verfügen,** **werden 20** Telefonnummern angegeben. <br/>  Wenn Sie über **100-149 Lizenzen** verfügen, werden **30** Telefonnummern zugeteilt. <br/>  Wenn Sie über **150-199 Lizenzen** verfügen, werden **40** Telefonnummern zugeteilt. <br/>  Wenn Sie über **200-499 Lizenzen** verfügen, werden **65** Telefonnummern zugeteilt. <br/>  Wenn Sie über **500-749 Lizenzen** verfügen, werden **90** Telefonnummern zugeteilt. <br/>  Wenn Sie über **750-999 Lizenzen** verfügen, werden **110** Telefonnummern zugeteilt. <br/>  Wenn Sie über **1.000-1.249 Lizenzen** verfügen, werden **125** Telefonnummern zugeteilt. <br/>  Wenn Sie **über 1.250-1.499** Lizenzen verfügen, werden **135** Telefonnummern angegeben. <br/>  Wenn Sie über **1.500-1.999 Lizenzen** verfügen, werden **160** Telefonnummern zugeteilt. <br/>  Wenn Sie über **2.000-2.999 Lizenzen** verfügen, werden **210** Telefonnummern zugeteilt. <br/>  Wenn Sie über **3.000-6.999 Lizenzen** verfügen, werden **420** Telefonnummern zugeteilt. <br/>  Wenn Sie über **7.000-9.999 Lizenzen** verfügen, werden **500** Telefonnummern zugeteilt. <br/>  Wenn Sie über **10.000-14.999 Lizenzen** verfügen, werden **600** Telefonnummern zugeteilt. <br/>  Wenn Sie über **15.000-19.999 Lizenzen** verfügen, werden **700** Telefonnummern zugeteilt. <br/>  Wenn Sie über **20.000-49.999 Lizenzen** verfügen, werden **1000** Telefonnummern zugeteilt. <br/>  Wenn Sie über **mehr als 50.000 Lizenzen** verfügen, werden **1.500** Telefonnummern zugeteilt. <br/> |Wenn Sie über insgesamt **1001**  Lizenzen für Telefonsystem und **Audiokonferenzen** verfügen, erhalten Sie **125** gebührenfreie Servicenummern. <br/> <br/> **Wichtig: Die** [Abrechnung mit Guthaben für](set-up-communications-credits-for-your-organization.md) Kommunikationen ist erforderlich, um gebührenfreie Telefonnummern zu reservieren und zu verwenden.          |
   
> [!NOTE]
> Wenn Sie mehr als die angegebenen Telefonnummern benötigen, lesen Sie [Kontaktieren des Supports für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
  
## <a name="related-topics"></a>Verwandte Themen
[Übertragen von Telefonnummern – häufig gestellte Fragen](./phone-number-calling-plans/port-order-overview.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Haftungsausschlussbezeichnung für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
