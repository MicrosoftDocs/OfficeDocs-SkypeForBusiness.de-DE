---
title: Zuweisen von Business Voice-Telefonnummern zu Ihren Benutzern
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Erfahren Sie, wie sie Microsoft 365 Business Voice Telefonnummern Benutzern in Ihrer Organisation zuweisen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d380fe3b3f5524f756a85f7b51037a07cd8cfc45
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282572"
---
# <a name="step-5-assign-business-voice-phone-numbers-to-your-users"></a>Schritt 5: Zuweisen von Business Voice-Telefonnummern zu Ihren Benutzern

Bevor Benutzer mithilfe von Teams Telefonanrufe an normale Telefonleitungen oder von diesen empfangen können, müssen Sie ihnen Telefonnummern zuweisen. In Microsoft Teams-Clients wird die Telefonnummer, die Sie einem Benutzer zuweisen, auf der Wähltast wählt, wenn der Benutzer auf Anrufe **klickt.** Gehen Sie für jeden Benutzer, der eine Telefonnummer benötigt, wie folgt vor.

![Telefonnummer des Benutzers, die in Microsoft Teams angezeigt wird.](../media/teams-phone-number.png)

> [!NOTE]
> Wenn keine Telefonnummern zu sehen sind, warten Sie bitte. Es kann mehrere Stunden dauern, bis Ihre neuen Telefonnummern in Ihrem Teams.

1. Öffnen Sie Microsoft Teams Admin Center, und melden Sie sich mit einem Benutzer an, der ein globaler Administrator ist (dies ist normalerweise das Konto, mit dem Sie sich für die Microsoft 365).
1. Wechseln Sie im linken Navigationsbereich zu <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">   >  **Sprachanrufnummern Telefon .**</a>
1. Wählen Sie auf der Seite **Telefonnummern** eine nicht zugewiesene Nummer aus der Liste aus, und klicken Sie dann auf **Bearbeiten**.  
1. Suchen Sie im Bereich **Bearbeiten** unter **Zugewiesen an** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, und klicken Sie dann auf **Zuweisen**.
1. Unter **Notfallstandort** können Sie entweder den Notfallstandort [](set-up-emergency-locations.md) auswählen, den Sie im Schritt Notfallstandorte einrichten hinzugefügt haben, oder wenn Sie einen neuen Standort für eine andere Niederlassung oder ein Heimbüro erstellen müssen, klicken Sie auf Standort hinzufügen **.**
1. Entscheiden Sie, ob sie dem Benutzer eine Willkommens-E-Mail mit Telefonnummerninformationen senden möchten. Wenn Sie:
    - **Portieren Ihrer vorhandenen Telefonnummern** zu Business  Voice (Portieren von Telefonnummern) Deaktivieren Sie E-Mail-Benutzer **mit Telefonnummerninformationen.**
    - **Verwenden Sie die von** Business Voice ausgewählten neuen Telefonnummern, und wählen Sie **E-Mail-Benutzer mit Telefonnummerninformationen aus.** 
1. Klicken Sie auf **Speichern**.
1. Wiederholen Sie die vorstehenden Schritte für jeden Benutzer, dem Sie eine Telefonnummer zuweisen möchten.

> [!NOTE]
> Aufgrund der Latenz zwischen Microsoft 365 oder Office 365 und Teams kann die Aktivierung von Benutzern bis zu 24 Stunden dauern. Wenn die Telefonnummer nach 24 Stunden nicht ordnungsgemäß zugewiesen wurde, wenden Sie sich an den Support für Business-Produkte [– Administratorhilfe](/microsoft-365/admin/contact-support-for-business-products). Wir helfen Ihnen gerne weiter!

> [!div class="nextstepaction"]
> [Nächster Schritt: Einrichten einer automatischen Attendant](set-up-auto-attendant.md?tabs=general-info#steps)