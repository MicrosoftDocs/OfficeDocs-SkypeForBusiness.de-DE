---
title: "Aufrufen von Plänen bekannte Probleme"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Calling Plans
description: "Hier erfahren Sie, bekannte Probleme bei der aufrufenden Plan für Office 365 (aufrufen, PSTN) und was Sie über diese möglich ist. "
ms.openlocfilehash: 42b282bce7ba65dc4e053020970a02e71c98b5bd
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="calling-plans-known-issues"></a>Aufrufen von Plänen bekannte Probleme

Aufrufen von Plänen in Office 365 sind ein neues Feature in Skype für Business Online gefunden. Im folgenden sind aktuelle Probleme, die werden nachverfolgt und aktiv untersucht. Sie werden potenziell aufgelöst werden, wenn das Feature für Business Online in zukünftigen Builds in Office 365 und Skype aktualisiert wird.
  
## <a name="calling-plans-known-issues"></a>Aufrufen von Plänen bekannte Probleme

|**Bekanntes Problem**|**Kommentare**|
|:-----|:-----|
|Übergang von Tech Preview aktualisieren nicht Softwarelizenzen zur Produktion Lizenzen für aufrufen plant automatisch die Lizenz.  <br/> |Zunächst erwerben Sie Ihre neuen Lizenzen, damit sie Ihren Benutzern zugewiesen werden können. Entfernen der Lizenzvertrags Promotion (Tech Preview) von einem Benutzer, und weisen Sie **sofort** die neuen **Nationalen aufrufen planen** und/oder **in- und International planen Aufrufen von** Lizenzen für den Benutzer. <br/> Wenn Sie entfernen und Hinzufügen von Lizenzen für mehrere Benutzer, ist es sehr wichtig, dass Sie die Lizenzen aus alle Benutzer von Windows PowerShell entfernen und dann **sofort** zuweisen die Lizenzen für alle Benutzer auch mithilfe von Windows PowerShell. Dadurch wird sichergestellt, dass bei der Behandlung von großer Mengen an Benutzer Lizenz Zuordnungen wird nicht unterbrochen im Dienst. PowerShell-Skriptbeispiele finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Hinweis:** Bei Verwendung von lokalen PSTN-Anbindung für hybridbenutzer müssen Sie *nur* eine **Telefonsystem** Lizenz zuweisen. Sie sollten **nicht** auch Zuweisen einer VoIP planen aufrufen. Wenn Sie aufrufen in Office 365-Pläne für Benutzer, die in Office 365 sind aktivieren, müssen Sie jedoch weiterhin eine **Nationalen aufrufen planen** oder keine Lizenz **in- und International aufrufen planen** , für die Benutzer zuweisen. Finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Wenn Sie weitere Telefonnummern als dieser erhalten möchten müssen, wenden Sie [Unterstützung für Business-Produkte – Admin Hilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Verwandte Themen
[Transferring phone numbers common questions](transferring-phone-numbers-common-questions.md)

[Verschiedene Arten von Telefonnummern für den Aufruf von plant verwendet](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Telefonnummern für Ihre Organisation verwalten](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://go.microsoft.com/fwlink/?LinkID=692099)
