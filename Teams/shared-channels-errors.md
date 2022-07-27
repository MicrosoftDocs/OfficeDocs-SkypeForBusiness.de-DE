---
title: Fehler bei freigegebenen Kanälen in Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jasonlewis
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Fehler in freigegebenen Kanälen in Microsoft Teams beheben.
ms.openlocfilehash: ecd05f1593817ed03d6e516e8915cd15694b6315
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024162"
---
# <a name="shared-channels-errors-in-microsoft-teams"></a>Fehler bei freigegebenen Kanälen in Microsoft Teams

Wenn Ihren Benutzern Fehlermeldungen angezeigt werden, wenn sie versuchen, Personen von außerhalb Ihrer Organisation zu freigegebenen Kanälen hinzuzufügen, überprüfen Sie die Einstellungen in diesem Artikel. 

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel-for-more-info-talk-to-your-admin"></a>Aufgrund der Administratorrichtlinie können Sie dem Kanal keine externen Personen hinzufügen. Weitere Informationen erhalten Sie von Ihrem Administrator.

Teams verwendet Microsoft 365-Gruppen für die Teammitgliedschaft. Die Microsoft 365-Gruppen Gasteinstellungen müssen aktiviert sein, damit Personen außerhalb der Organisation einem freigegebenen Kanal hinzugefügt werden können. Wenn für Ihre Benutzer dieser Fehler angezeigt wird, überprüfen Sie die Microsoft 365-Gruppen Einstellungen für Personen außerhalb der Organisation.

So legen Sie Microsoft 365-Gruppen Einstellungen für Personen außerhalb der Organisation fest
1. Erweitern Sie im Microsoft 365 Admin Center im linken Navigationsbereich "**Einstellungen"**.
1. Klicken Sie auf **"Organisationseinstellungen"**.
1. Klicken Sie in der Liste auf **Microsoft 365-Gruppen**.
1. Stellen Sie sicher, dass die Kontrollkästchen "Zulassen, dass **Gruppenbesitzer Personen außerhalb Ihrer Organisation zu Microsoft 365-Gruppen als Gäste hinzufügen**" und "**Gastgruppenmitglieder zugriff auf Gruppeninhalte** zulassen" aktiviert sind.
1. Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **"Änderungen speichern"**.

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel"></a>Aufgrund der Administratorrichtlinie können Sie dem Kanal keine externen Personen hinzufügen.

Teams-Kanalrichtlinien bestimmen, wie Benutzer mit freigegebenen Kanälen interagieren können. Wenn Benutzern diese Fehlermeldung angezeigt wird, überprüfen Sie die Kanalrichtlinie für diesen Benutzer.

So legen Sie die Richtlinie zum Einladen von Personen außerhalb der Organisation zu freigegebenen Kanälen fest
1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu Teams > Teams-Richtlinien.
1. Wählen Sie die Richtlinie aus, der Ihr Benutzer zugewiesen ist.
1. Stellen Sie sicher, dass " **Externe Benutzer zu freigegebenen Kanälen einladen** " **aktiviert** ist.
1. Wenn Sie Änderungen vorgenommen haben, wählen Sie **"Übernehmen" aus**.

Weitere Informationen zu Teams-Kanalrichtlinien finden [Sie unter Verwalten von Kanalrichtlinien in Microsoft Teams](teams-policies.md).

## <a name="you-cant-share-this-channel-with-people-from-this-org"></a>Sie können diesen Kanal nicht für Personen aus dieser Organisation freigeben.

Wenn für Ihre Benutzer dieser Fehler angezeigt wird, werden sie durch die mandantenübergreifenden Azure Active Directory-Zugriffseinstellungen daran gehindert, den Kanal für Personen in der anderen Organisation freizugeben. Dies kann auf die eingehenden Einstellungen in Ihrer Organisation oder die ausgehenden Einstellungen in der anderen Organisation zurückzuführen sein.

So überprüfen Sie die eingehenden Einstellungen für Ihre Organisation
1. Wählen Sie in [Azure Active Directory](https://aad.portal.azure.com) **"Externe Identitäten**" und dann " **Mandantenübergreifende Zugriffseinstellungen"** aus.
1. Wählen Sie den Link für den eingehenden Zugriff für die Organisation aus, die Sie überprüfen möchten.
1. Wählen Sie auf der Registerkarte **"B2B Direct Connect** " die Option **"Einstellungen anpassen"** aus.
1. Stellen Sie auf der Registerkarte **"Externe Benutzer und Gruppen** " sicher, dass **"Zugriff zulassen** " und " **Alle externen Benutzer und Gruppen** " ausgewählt sind. Wenn Sie " **Externe Benutzer und Gruppen auswählen**" ausgewählt haben, stellen Sie sicher, dass der eingeladene Benutzer Mitglied der ausgewählten Gruppen ist.
1. Wenn Sie Änderungen vorgenommen haben, wählen Sie " **Speichern"** aus, und schließen Sie das Blatt **"Einstellungen für den eingehenden Zugriff"** .

Wenn der Fehler weiterhin angezeigt wird, wenden Sie sich an die Organisation, mit der sie zusammenarbeiten. Die ausgehenden Einstellungen dieser Organisation verbieten möglicherweise die Freigabe für Ihre Organisation. Informationen zum Einrichten freigegebener Kanäle zwischen Organisationen finden Sie unter [Zusammenarbeit mit externen Teilnehmern in einem freigegebenen Kanal](/microsoft-365/solutions/collaborate-teams-direct-connect).

## <a name="we-couldnt-find-any-matches-make-sure-the-email-address-is-correct-or-talk-to-your-admin"></a>Wir konnten keine Übereinstimmungen finden. Stellen Sie sicher, dass die E-Mail-Adresse korrekt ist, oder wenden Sie sich an Ihren Administrator.

Wenn für Ihre Benutzer dieser Fehler angezeigt wird, kann Microsoft 365 die angegebene E-Mail-Adresse in der externen Organisation nicht finden. Sie müssen die Adresse mit der externen Organisation bestätigen.

