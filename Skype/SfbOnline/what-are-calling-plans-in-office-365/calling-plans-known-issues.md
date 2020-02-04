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
description: 'Lernen Sie bekannte Probleme mit dem Anrufplan für Office 365 (PSTN-Anrufe) kennen, und was Sie dagegen tun können. '
ms.openlocfilehash: 3441969133c8f67b63b620aff25545b89085858f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692310"
---
# <a name="calling-plans-known-issues"></a>Bekannte Probleme von Anrufplänen

Anrufpläne in Office 365 sind ein neues Feature, das in Skype for Business Online zu finden ist. Im folgenden finden Sie aktuelle Probleme, die nachverfolgt und aktiv untersucht werden. Sie werden möglicherweise aufgelöst, wenn das Feature in zukünftigen Builds in Office 365 und Skype for Business Online aktualisiert wird.
  
## <a name="calling-plans-known-issues"></a>Bekannte Probleme von Anrufplänen

|**Bekanntes Problem**|**Anmerkungen**|
|:-----|:-----|
|Durch den Übergang von technischen Preview-Lizenzen zu Produktionslizenzen für Anrufpläne wird die Lizenz nicht automatisch aktualisiert.  <br/> |Erwerben Sie zunächst Ihre neuen Lizenzen, damit diese für die Zuweisung zu Ihren Nutzern bereitstehen. Entfernen Sie die Promo-Lizenz (Tech Preview) von einem Benutzer, und weisen Sie dem Benutzer **sofort** den neuen Tarif für **Inlandsanrufe** und/oder Lizenzen für **Inlands-und Auslandsgespräche** zu. <br/> Falls Sie Lizenzen für mehrere Benutzer entfernen und hinzufügen, ist es äußerst wichtig, dass Sie zunächst mithilfe von Windows PowerShell die Lizenzen aller Benutzer entfernen und dann **UNMITTELBAR** danach ebenfalls mit Windows PowerShell die Lizenzen für alle Benutzer zuweisen. Auf diese Weise wird sichergestellt, dass bei der Behandlung großer Mengen von Benutzerlizenz Zuweisungen keine Unterbrechungen beim Service auftreten. Beispiele für PowerShell-Skripts finden Sie unter [Zuweisen von Skype for Business-und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Hinweis:** Wenn Sie lokale PSTN-Konnektivität für Hybrid Benutzer verwenden, müssen Sie *nur* eine **Telefon System** Lizenz zuweisen. Sie sollten auch **keinen** sprach Tarif zuweisen. Wenn Sie jedoch Anrufpläne in Office 365 für Benutzer in Office 365 aktivieren, müssen Sie diesen Benutzern weiterhin einen **Plan für Inlandsanrufe** oder eine Lizenz für **Inlands-und Auslandsanrufe** zuweisen. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Wenn Sie weitere Telefonnummern erhalten möchten, wenden Sie sich bitte [an den Support für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) .         |
   
## <a name="related-topics"></a>Verwandte Themen
[Übertragen von Telefonnummern – häufig gestellte Fragen](/microsoftteams/transferring-phone-numbers-common-questions)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 