---
title: Reservieren von Telefonnummern für Ihre Benutzer
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 'Hier erfahren Sie, wie Sie vorhandene Nummern für Teams neu abrufen, portieren oder übertragen und wie Sie die Änderungen für Ihre Benutzer anzeigen können. '
ms.openlocfilehash: f2028a4d7b49560ff426d83241da8f1f7c3243d3
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030461"
---
# <a name="getting-phone-numbers-for-your-users"></a>Reservieren von Telefonnummern für Ihre Benutzer

Bevor Sie Benutzer in Ihrer Organisation für das Tätigen und Erhalten von Telefonanrufen einrichten können, müssen Sie Telefonnummern für sie abrufen.
  
Es gibt drei Möglichkeiten zum Abrufen von Benutzernummern:

- **Verwenden Sie das Microsoft Teams Admin Center.** In einigen Ländern und Regionen können Sie über das Microsoft Teams Admin Center Zahlen für Ihre Benutzer abrufen. Weitere Informationen finden Sie unter [Abrufen neuer Telefonnummern für Ihre Benutzer](#get-new-phone-numbers-for-your-users).

- **Portieren von bestehenden Nummern.** Sie können vorhandene Nummern von Ihrem aktuellen Dienstanbieter oder Telefonnetzbetreiber portieren oder übertragen. Über [Übertragen von Telefonnummern zu Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) oder [Rufnummern für Ihre Organisation verwalten](/microsoftteams/manage-phone-numbers-for-your-organization) erhalten Sie weitere hilfreiche Informationen.  
  
- **Verwenden eines Anforderungsformulars für neue Telefonnummern.** Manchmal (je nach Land oder Region) können Sie Ihre neuen Telefonnummern nicht über das Microsoft Teams Admin Center abrufen, oder Sie benötigen bestimmte Telefonnummern oder Ortsvorwahl. Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization).
  
> [!NOTE]
> Wenn Sie Hilfe beim Einrichten von Telefonnummern für Ihre Organisation benötigen, wenden Sie sich bitte an [wenden Sie sich an den Support-Kontakt für Business-Produkte – Administratorhilfe ( https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online .
  
## <a name="get-new-phone-numbers-for-your-users"></a>Erhalten von neuen Telefonnummern für Ihre Benutzer

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

Sie müssen ein Team Dienstadministrator sein, um diese Änderungen vornehmen zu können. Informationen zum Abrufen von Administratorrollen und-Berechtigungen finden Sie unter [Verwenden von Teams-Administratorrollen zum Verwalten von Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) .

1. Wechseln Sie zum Microsoft Teams Admin Center.
2. Wechseln Sie in der linken Navigationsleiste zu **VoIP** -  >  **Telefonnummern** , und klicken Sie dann auf **Hinzufügen**.
3. Geben Sie einen Namen für den Auftrag ein, und fügen Sie eine Beschreibung hinzu.
4. Gehen Sie auf der Seite Ort und Menge wie folgt vor:
    1. Wählen Sie unter **Land oder Region** ein Land oder eine Region aus.
    2. Wählen Sie unter **Number Type** den Eintrag **User (Subscriber)** aus.
    3. Wählen Sie unter **Standort** einen Speicherort aus. Wenn Sie einen neuen Speicherort erstellen müssen, klicken Sie auf **Ort hinzufügen**.
    4. Wählen Sie unter **Vorwahl** eine Ortsvorwahl aus.
    5. Geben **Sie unter Anzahl** die Anzahl der gewünschten Zahlen für Ihre Organisation ein, und klicken Sie dann auf **weiter** , um Ihre Nummern auszuwählen.
5. Wählen Sie die gewünschten Nummern aus. Sie haben 10 Minuten Zeit, um ihre Telefonnummern auszuwählen und Ihre Bestellung aufzugeben. Wenn Sie mehr als 10 Minuten benötigen, werden die Telefonnummern in den Nummern Pool zurückgegeben.
6. Wenn Sie bereit sind, Ihre Bestellung aufzugeben, klicken Sie auf **Bestellung aufgeben**.

    > [!IMPORTANT]
    > Die Anzahl der Rufnummern für Benutzer (Abonnenten) ist gleich der Gesamtzahl der Lizenzen im **nationalen Anrufplan** und/oder dem **nationalen und internationalen Anrufplan** , die Sie zugeordnet haben, multipliziert mit 1,1, plus 10 weitere Telefonnummern. Wenn Sie z.B. 50 Benutzer insgesamt in einem nationalen Anrufplan und/oder nationalen und internationalen Anrufplan haben, können Sie beispielsweise **65** Telefonnummern **(50 x 1,1 + 10)** erwerben. Weitere Informationen finden [Sie unter wie viele Telefonnummern können Sie erhalten?](/microsoftteams/how-many-phone-numbers-can-you-get). Wenn Sie weitere Telefonnummern erhalten möchten, wenden Sie sich an den [Support-Kontakt für Business-Produkte – Administratorhilfe](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online).
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Portieren oder übertragen Sie vorhandene Telefonnummern von Ihrem Dienstanbieter oder Netzbetreiber
  
- Wenn Sie 999 oder weniger Telefonnummern für Ihre Benutzer benötigen, verwenden Sie den Porting-Assistenten im Microsoft Teams Admin Center. Führen Sie die Schritte unter [übertragen von Telefonnummern in Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)aus. Wenn Ihr Land oder Ihre Region im Portierungs-Assistenten nicht aufgeführt ist, können Sie [einen Portierungs Auftrag manuell übermitteln](phone-number-calling-plans/manually-submit-port-order.md) oder lesen Sie [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization) , um den richtigen Letter of Authorization (LoA) herunterzuladen.

- Wenn Sie mehr als 999 Telefonnummern portieren müssen, können Sie [einen Portierungs Auftrag manuell übermitteln](phone-number-calling-plans/manually-submit-port-order.md) oder lesen Sie [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization) , um den richtigen Letter of Authorization (LoA) herunterzuladen, und senden Sie ihn dann an [den PSTN-Service-Desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) , um alle Ihre Nummern übertragen zu lassen.

## <a name="view-the-phone-numbers-for-your-organization"></a>Anzeigen der Telefonnummern für Ihre Organisation

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

Wechseln Sie in der linken Navigationsleiste des Admin Centers zu **VoIP** -  >  **Telefonnummern** , um die Nummern für Ihre Organisation anzuzeigen, einschließlich Standort, Nummerntyp und Statusinformationen.
  
## <a name="assign-phone-numbers-to-users"></a>Zuweisen von Telefonnummern an Benutzer

Nachdem Sie Ihre Telefonnummern erhalten haben, müssen Sie jedem Benutzer eine Nummer zuweisen. Weitere Informationen finden Sie unter [zuweisen, ändern oder Entfernen einer Telefonnummer für einen Benutzer](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) .

> [!NOTE]
> Wenn Sie weitere Telefonnummern erhalten möchten, wenden Sie sich an den [Support-Kontakt für Business-Produkte – Administratorhilfe](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online).

## <a name="related-topics"></a>Verwandte Themen

[Übertragen von Telefonnummern – häufig gestellte Fragen](/microsoftteams/transferring-phone-numbers-common-questions)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)

[Disclaimer-Label für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
