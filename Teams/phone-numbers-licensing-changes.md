---
title: Telefonnummern und Lizenzierungsänderungen
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
description: Erfahren Sie, wie sich Lizenzänderungen auf die Verwaltung von Telefonnummern auswirken können.
ms.openlocfilehash: 58821f950baf68474a637a8d76acaab9a088f31e
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005474"
---
# <a name="how-licensing-affects-phone-number-management"></a>Auswirkungen der Lizenzierung auf die Telefonnummernverwaltung

Das Entfernen und Zuweisen von Lizenzen zu Benutzern kann sich auf die Fähigkeit eines Benutzers auswirken, PSTN-Anrufe (Public Switched Telephone Network) in Microsoft Teams zu tätigen und zu empfangen. In diesem Artikel wird beschrieben, wie Sie Lizenzänderungen verwalten können, um sicherzustellen, dass die Fähigkeit Ihrer Benutzer, PSTN-Anrufe zu tätigen und zu empfangen, nicht beeinträchtigt wird.

Allgemeine Informationen zum Verwalten von Telefonnummern finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-landing-page.md). Allgemeine Informationen zur Lizenzierung von Teams-Add-Ons finden Sie unter [Microsoft Teams-Add-On-Lizenzen](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md).



## <a name="remove-a-license"></a>Entfernen einer Lizenz

Wenn Sie einen Benutzer mit einer zugewiesenen Telefonnummer haben und eine oder mehrere der erforderlichen Lizenzen entfernen, hebt das Entfernen der Lizenz auch die Zuweisung der Telefonnummer zum Benutzer auf. Ohne eine zugewiesene Telefonnummer ist die Fähigkeit des Benutzers, PSTN-Anrufe in Microsoft Teams zu tätigen und zu empfangen, beeinträchtigt.

Abhängig von der [PSTN-Konnektivitätsoption](pstn-connectivity.md) des Benutzers hat das Entfernen einer Lizenz die folgenden Auswirkungen auf die Telefonieparameter:

- **Das Entfernen einer Microsoft 365-Anrufplanlizenz von einem Benutzer mit einer Anrufplantelefonnummer** bewirkt Folgendes:
  - Kopieren eines beliebigen Werts in "OnPremLineUri" in "LineUri"
  - EnterpriseVoiceEnabled auf "False" festlegen
  - Festlegen des Status der Telefonnummernzuweisung auf "Nicht zugewiesen" in der Telefonnummerndatenbank


- **Das Entfernen einer Microsoft 365-Telefonsystemlizenz von einem Benutzer mit einer Telefonnummer des Telefonanbieters führt** zu Folgenden:
  - LineUri löschen
  - EnterpriseVoiceEnabled auf "False" festlegen
  - Festlegen des Zuordnungsstatus der Telefonnummer auf "Nicht zugewiesen" in der Telefonnummerndatenbank


- **Das Entfernen einer Microsoft 365-Telefonsystemlizenz von einem Benutzer mit einer Direct Routing-Telefonnummer** bewirkt Folgendes:
  - LineUri löschen
  - EnterpriseVoiceEnabled auf "False" festlegen
  - Entfernen der Telefonnummer aus der Telefonnummerndatenbank


## <a name="change-a-license"></a>Ändern einer Lizenz

Wenn Sie eine Lizenz für einen Benutzer ändern müssen, die eine der erforderlichen Lizenzen umfasst, sollten Sie sicherstellen, dass die Lizenzierungsänderungen gleichzeitig vorgenommen und gespeichert werden. Mit dieser Methode wird sichergestellt, dass der Benutzer seine zugewiesene Telefonnummer behält und weiterhin PSTN-Anrufe in Microsoft Teams tätigen und empfangen kann. 

Angenommen, Sie möchten einem Benutzer, der derzeit über eine Microsoft 365 E3-Lizenz verfügt, eine Microsoft 365 E5 Lizenz zuweisen. 

- Wenn Sie das Teams Admin Center verwenden, stellen Sie auf der Registerkarte **"Lizenzen und Apps** " in den Benutzerdetails sicher, dass die alte Lizenz entfernt und die neue Lizenz hinzugefügt wird, bevor Sie auf **"Änderungen speichern"** klicken. 

- Wenn Sie die PowerShell-Cmdlets [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) oder [Set-MgUserLicense](/powershell/module/microsoft.graph.users.actions/set-mguserlicense) verwenden, führen Sie das Cmdlet einmal aus, und verwenden Sie die Parameter "-AddLicenses" und "-RemoveLicenses".

(Wenn Sie die alte Lizenz entfernen und die Änderung speichern und dann die neue Lizenz hinzufügen und die Änderung speichern, wird die Telefonnummer nicht zugewiesen, und der Benutzer verliert möglicherweise die Möglichkeit, PSTN-Anrufe in Microsoft Teams zu tätigen und zu empfangen. Nachdem Sie die neue Lizenz zugewiesen haben, müssen Sie die Telefonnummer dem Benutzer erneut zuweisen.)










