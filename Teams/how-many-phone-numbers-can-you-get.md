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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Wenn Sie Telefonnummern für Ihre Organisation reservieren möchten, kann die Anzahl der reservierten Telefonnummern die Anzahl der zugewiesenen Lizenzen übersteigen. Dies richtet sich jedoch nach der Art der Telefonnummern und der Art der Lizenzen, die Sie gekauft haben und die Ihnen zugewiesen wurden. Sie können auf verschiedene Arten von Telefonnummern klicken, die für Anrufpläne verwendet werden, um sich über die verschiedenen Telefonnummern zu informieren, die in Skype for Business Online verwendet werden.
ms.openlocfilehash: 1051eea164cdee1c9582bf0226c1bd54620f502a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299965"
---
# <a name="how-many-phone-numbers-can-you-get"></a>Wie viele Telefonnummern können Sie bekommen?

Wenn Sie Telefonnummern für Ihre Organisation reservieren möchten, kann die Anzahl der reservierten Telefonnummern die Anzahl der zugewiesenen Lizenzen übersteigen. Dies richtet sich jedoch nach der Art der Telefonnummern und der Art der Lizenzen, die Sie gekauft haben und die Ihnen zugewiesen wurden. Sie können auf [verschiedene Arten von Telefonnummern klicken, die für Anrufpläne verwendet](different-kinds-of-phone-numbers-used-for-calling-plans.md) werden, um sich über die verschiedenen Telefonnummern zu informieren, die in Skype for Business Online verwendet werden.
  
Sie können die Anzahl der Telefonnummern sehen, die Sie im Skype for Business Admin Center auf der Seite " **Telefonnummern** " abrufen können, oder Sie können das Cmdlet " [Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/library/mt634605.aspx) " ausführen.
  
> [!IMPORTANT]
> Die Beschränkungen unten beinhalten nicht die Telefonnummern, die Sie an Microsoft portiert oder übertragen haben. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>Wie viele Telefonnummern können Sie erhalten?

||||
|:-----|:-----|:-----|
|**Art der Telefonnummern** <br/> |**Wie reservieren Sie alle Telefonnummern?** <br/> |**Nachfolgend ein Beispiel** <br/> |
|Nummer des Benutzers (Abonnenten)  <br/> |Die Anzahl der Telefonnummern entspricht der Gesamtzahl der Tarife für **Inlandsanrufe** und/oder Lizenzen für **Inlands-und Auslandsanrufe** , multipliziert mit 1,1 + 10 zusätzlichen Telefonnummern. <br/> |Wenn ich 50-Nutzer mit einem Inlandsanruf Plan und/oder einem Inlands-und Auslands Anrufplan besitze, können Sie **65** -Telefonnummer **(50 x 1,1 + 10)** erwerben. <br/> |
|Gebührenpflichtige Leistungsnummer  <br/> | Die Anzahl der Telefonnummern entspricht der Gesamtzahl der Lizenzen für **Telefon System** - **** und Audiokonferenzen und verwendet die folgenden: <br/>  Wenn Sie über **1-25 Lizenzen** verfügen, werden **5** Telefonnummern zugeteilt. <br/>  Wenn Sie über **26-49 Lizenzen** verfügen, werden **10** Telefonnummern zugeteilt. <br/>  Wenn 50-99- **Lizenzen** vorhanden sind, werden **20** Telefonnummern angegeben. <br/>  Wenn Sie über **100-149 Lizenzen** verfügen, werden **30** Telefonnummern zugeteilt. <br/>  Wenn Sie über **150-199 Lizenzen** verfügen, werden **40** Telefonnummern zugeteilt. <br/>  Wenn Sie über **200-499 Lizenzen** verfügen, werden **65** Telefonnummern zugeteilt. <br/>  Wenn Sie über **500-749 Lizenzen** verfügen, werden **90** Telefonnummern zugeteilt. <br/>  Wenn Sie über **750-999 Lizenzen** verfügen, werden **110** Telefonnummern zugeteilt. <br/>  Wenn Sie über **1.000-1.249 Lizenzen** verfügen, werden **125** Telefonnummern zugeteilt. <br/>  Wenn es **1250-1499-Lizenzen** gibt, werden **135** -Telefonnummern angegeben. <br/>  Wenn Sie über **1.500-1.999 Lizenzen** verfügen, werden **160** Telefonnummern zugeteilt. <br/>  Wenn Sie über **2.000-2.999 Lizenzen** verfügen, werden **210** Telefonnummern zugeteilt. <br/>  Wenn Sie über **3.000-6.999 Lizenzen** verfügen, werden **420** Telefonnummern zugeteilt. <br/>  Wenn Sie über **7.000-9.999 Lizenzen** verfügen, werden **500** Telefonnummern zugeteilt. <br/>  Wenn Sie über **10.000-14.999 Lizenzen** verfügen, werden **600** Telefonnummern zugeteilt. <br/>  Wenn Sie über **15.000-19.999 Lizenzen** verfügen, werden **700** Telefonnummern zugeteilt. <br/>  Wenn Sie über **20.000-49.999 Lizenzen** verfügen, werden **1000** Telefonnummern zugeteilt. <br/>  Wenn Sie über **mehr als 50.000 Lizenzen** verfügen, werden **1.500** Telefonnummern zugeteilt. <br/> |Wenn Sie über eine Gesamtzahl von **51** - **Telefon System** -und Audiokonferenz Lizenzen verfügen, können Sie **20** gebührenpflichtige Dienstnummern erhalten. **** <br/> |
|Gebührenfreie Leistungsnummer  <br/> | Die Anzahl der Telefonnummern entspricht der Gesamtzahl der Lizenzen für **Telefon System** - **** und Audiokonferenzen und verwendet die folgenden: <br/>  Wenn Sie über **1-25 Lizenzen** verfügen, werden **5** Telefonnummern zugeteilt. <br/>  Wenn Sie über **26-49 Lizenzen** verfügen, werden **10** Telefonnummern zugeteilt. <br/>  Wenn 50-99- **Lizenzen** vorhanden sind, werden **20** Telefonnummern angegeben. <br/>  Wenn Sie über **100-149 Lizenzen** verfügen, werden **30** Telefonnummern zugeteilt. <br/>  Wenn Sie über **150-199 Lizenzen** verfügen, werden **40** Telefonnummern zugeteilt. <br/>  Wenn Sie über **200-499 Lizenzen** verfügen, werden **65** Telefonnummern zugeteilt. <br/>  Wenn Sie über **500-749 Lizenzen** verfügen, werden **90** Telefonnummern zugeteilt. <br/>  Wenn Sie über **750-999 Lizenzen** verfügen, werden **110** Telefonnummern zugeteilt. <br/>  Wenn Sie über **1.000-1.249 Lizenzen** verfügen, werden **125** Telefonnummern zugeteilt. <br/>  Wenn es **1250-1499-Lizenzen** gibt, werden **135** -Telefonnummern angegeben. <br/>  Wenn Sie über **1.500-1.999 Lizenzen** verfügen, werden **160** Telefonnummern zugeteilt. <br/>  Wenn Sie über **2.000-2.999 Lizenzen** verfügen, werden **210** Telefonnummern zugeteilt. <br/>  Wenn Sie über **3.000-6.999 Lizenzen** verfügen, werden **420** Telefonnummern zugeteilt. <br/>  Wenn Sie über **7.000-9.999 Lizenzen** verfügen, werden **500** Telefonnummern zugeteilt. <br/>  Wenn Sie über **10.000-14.999 Lizenzen** verfügen, werden **600** Telefonnummern zugeteilt. <br/>  Wenn Sie über **15.000-19.999 Lizenzen** verfügen, werden **700** Telefonnummern zugeteilt. <br/>  Wenn Sie über **20.000-49.999 Lizenzen** verfügen, werden **1000** Telefonnummern zugeteilt. <br/>  Wenn Sie über **mehr als 50.000 Lizenzen** verfügen, werden **1.500** Telefonnummern zugeteilt. <br/> |Wenn Sie über eine Gesamtzahl von **1001** - **Telefon System** -und **Audio-Konferenz** Lizenzen verfügen, können Sie **125** gebührenfreie Servicenummern erhalten. <br/> <br/> **Wichtig:** Für die [Abrechnung von Kommunikationsguthaben](set-up-communications-credits-for-your-organization.md) müssen gebührenfreie Telefonnummern reserviert und verwendet werden.          |
   
> [!NOTE]
> Wenn Sie mehr als die angegebenen Telefonnummern benötigen, lesen Sie [Kontaktieren des Supports für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
  
## <a name="related-topics"></a>Verwandte Themen
[Allgemeine Fragen zum Übertragen von Telefonnummern](transferring-phone-numbers-common-questions.md)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 