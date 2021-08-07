---
title: Bekannte Probleme von Anrufplänen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Hier erfahren Sie, welche bekannten Probleme mit dem Anrufplan für PstN-Anrufe auftreten und was Sie tun können.
ms.openlocfilehash: 239a0c83a12ae7d5d7b0be2fcbf81bf8825dd85d8a0dcb7a880bc53ad8b8e477
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306108"
---
# <a name="calling-plans-known-issues"></a>Bekannte Probleme von Anrufplänen

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Anrufpläne sind ein neues Feature in Skype for Business Online. Im Folgenden werden die aktuellen Probleme nachverfolgt und aktiv untersucht. Sie werden potenziell aufgelöst, wenn das Feature in zukünftigen Builds aktualisiert wird.
  
## <a name="calling-plans-known-issues"></a>Bekannte Probleme von Anrufplänen

|**Bekanntes Problem**|**Anmerkungen**|
|:-----|:-----|
|Beim Übergang von Lizenzen aus der technischen Vorschau zu Produktionslizenzen für Anrufpläne wird die Lizenz nicht automatisch aktualisiert.  <br/> |Erwerben Sie zunächst Ihre neuen Lizenzen, damit diese für die Zuweisung zu Ihren Nutzern bereitstehen. Entfernen Sie die Promo-Lizenz (technische Vorschau) von einem  Benutzer, und  weisen Sie dem Benutzer DANN **SOFORT** die neuen Lizenzen für einen Anrufplan für Inland und/oder Inlands- und Auslandsrufe zu. <br/> Falls Sie Lizenzen für mehrere Benutzer entfernen und hinzufügen, ist es äußerst wichtig, dass Sie zunächst mithilfe von Windows PowerShell die Lizenzen aller Benutzer entfernen und dann **UNMITTELBAR** danach ebenfalls mit Windows PowerShell die Lizenzen für alle Benutzer zuweisen. Dadurch wird sichergestellt, dass es bei der Behandlung großer Mengen von Benutzerlizenzzuweisungen zu keiner Dienstunterbrechung kommt. PowerShell-Beispielskripts finden Sie unter [Zuweisen Skype for Business und Microsoft Teams Lizenzen.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)  <br/> **Hinweis:** Wenn Sie lokale PSTN-Anbindung für Hybridbenutzer verwenden, *müssen* Sie nur eine Lizenz Telefonsystem **zuweisen.** Weisen Sie **NICHT** auch noch einen Sprachanrufplan zu. Wenn Sie jedoch Anrufpläne in Microsoft 365 oder Office 365 für Benutzer in Microsoft 365 oder Office 365 aktivieren, müssen Sie diesen  Benutzern weiterhin  einen Plan für Inlandsrufe oder eine Lizenz für einen Anrufplan für Inland und Ausland zuweisen. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Wenn Sie mehr als diese Telefonnummern benötigen, wenden Sie sich bitte an den [Support für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Verwandte Themen
[Übertragen von Telefonnummern – häufig gestellte Fragen](/microsoftteams/transferring-phone-numbers-common-questions)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
