---
title: Zuweisen Teams Telefonsystem Telefonnummern zu Ihren Benutzern
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Erfahren Sie, wie sie Microsoft Teams Telefonsystem Telefonnummern Benutzern in Ihrer Organisation zuweisen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ac68e38975eaece18554a1aa04f18734da2c851
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053014"
---
# <a name="step-5-assign-teams-phone-system-phone-numbers-to-your-users"></a>Schritt 5: Zuweisen Teams Telefonsystem Telefonnummern zu Ihren Benutzern

Bevor Benutzer mithilfe von Teams Telefonanrufe an normale Telefonleitungen oder von diesen empfangen können, müssen Sie ihnen Telefonnummern zuweisen. In Microsoft Teams-Clients wird die Telefonnummer, die Sie einem Benutzer zuweisen, auf der Wähltast wählt, wenn der Benutzer auf Anrufe **klickt**. Gehen Sie für jeden Benutzer, der eine Telefonnummer benötigt, wie folgt vor:

> [!NOTE]
> Wenn keine Telefonnummern zu sehen sind, warten Sie bitte. Es kann mehrere Stunden dauern, bis Ihre neuen Telefonnummern in der neuen Version verfügbar Teams.

1. Öffnen Sie Microsoft Teams Admin Center, und melden Sie sich mit einem Benutzer an, der ein globaler Administrator ist. Dies ist normalerweise das Konto, mit dem Sie sich für ihr Konto Microsoft 365.
1. Wechseln Sie im linken Navigationsbereich zu <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Sprachanruf** >  Telefon Nummern</a>.
1. Wählen Sie auf der Seite **Telefonnummern** eine nicht zugewiesene Nummer aus der Liste aus, und klicken Sie dann auf **Bearbeiten**.  
1. Suchen Sie im Bereich **Bearbeiten** unter **Zugewiesen an** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, und klicken Sie dann auf **Zuweisen**.
1. Unter **Notfallstandort** können Sie entweder den Notfallstandort auswählen, den Sie im Schritt [](set-up-emergency-locations.md) Notfallstandorte einrichten hinzugefügt haben, oder wenn Sie einen neuen Standort für eine andere Niederlassung oder ein Heimbüro erstellen müssen, klicken Sie auf Standort **hinzufügen.**
1. Entscheiden Sie, ob sie dem Benutzer eine Willkommens-E-Mail mit Telefonnummerninformationen senden möchten. Wenn Sie:
    - **Bringen Sie vorhandene Telefonnummern Telefonsystem** (portieren von Telefonnummern *genannt),* deaktivieren Sie E-Mail-Benutzer mit **Telefonnummerninformationen**.
    - **Verwenden Sie die von Ihnen ausgewählten** neuen Telefonsystem wählen *Sie* E-Mail-Benutzer **mit Telefonnummerninformationen aus**.
1. Klicken Sie auf **Speichern**.
1. Wiederholen Sie die vorstehenden Schritte für jeden Benutzer, dem Sie eine Telefonnummer zuweisen möchten.

> [!NOTE]
> Nach dem Zuweisen eines Microsoft-Anrufplans zu einem Benutzer kann es bis zu 24 Stunden dauern, bis ihm die Wähltast in seinem Teams angezeigt wird. Wenn die Wählta nicht in 24 Stunden angezeigt wird, überprüfen Sie die [Konfiguration der Wählta nicht](/microsoftteams/dial-pad-configuration). Bei Bedarf können Sie auch den [Support kontaktieren](/microsoft-365/admin/contact-support-for-business-products).

> [!div class="nextstepaction"]
> [Nächster Schritt: Einrichten einer automatischen Attendant](set-up-auto-attendant.md?tabs=general-info#steps)
