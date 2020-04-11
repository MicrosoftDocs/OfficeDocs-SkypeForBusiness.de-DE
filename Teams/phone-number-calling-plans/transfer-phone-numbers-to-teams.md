---
title: Übertragen von Telefonnummern an Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie mit dem Portierungs-Assistenten Ihre Telefonnummer von Ihrem aktuellen Dienstanbieter an Microsoft Teams übertragen können.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a13e08a569c34f8182997bb438e997d8caee2ae7
ms.sourcegitcommit: 2d44f1a673316daf0aca3149571b24a63ca72772
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2020
ms.locfileid: "43227529"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Übertragen von Telefonnummern an Microsoft Teams

[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Verwenden Sie den Porting-Assistenten im Microsoft Teams Admin Center, um ihre Telefonnummern von Ihrem aktuellen Dienstanbieter in Teams zu übertragen. Nachdem Sie Ihre Telefonnummern in Teams portiert haben, wird Microsoft Ihr Dienstanbieter und berechnet Ihnen diese Telefonnummern.

Bevor Sie beginnen, empfehlen wir Ihnen, die Informationen in [einem Port Auftrag](port-order-overview.md) zu überprüfen. Wenn Sie über Servicenummern für Einwahlkonferenz Brücken, automatische Telefonzentralen oder andere Dienstnummern, gebührenfreie Telefonnummern oder über mehr als 999-Benutzer (Teilnehmer)-Telefonnummern verfügen, die Sie an Teams übertragen müssen, lesen Sie [Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , um die richtigen Formulare herunterzuladen und an uns zu senden.

  > [!NOTE]
  > Wir verarbeiten Port Bestellungen für die Übertragung von Telefonnummern nur an Werktagen in den USA und nicht an Feiertagen oder an Wochenenden.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Erstellen eines Portierungs Auftrags und übertragen von Telefonnummern in Teams

> [!NOTE]
> **Derzeit können Sie mit diesem Assistententelefon Nummern für das Vereinigte Königreich, die Vereinigten Staaten und Kanada abrufen**. Wenn Sie Telefonnummern für andere Länder und Regionen erhalten möchten, können Sie [einen Portierungs Auftrag manuell übermitteln](manually-submit-port-order.md). Wenn Sie das Formular abrufen möchten, das Sie manuell übermitteln müssen, wählen Sie in der Dropdownliste unter [Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)Ihr Land oder Ihre Region aus.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > -**Telefonnummern**. Klicken Sie auf **Zahlen**, und klicken Sie dann auf **Port** , um den Porting-Assistenten zu starten.
2. Überprüfen Sie die Informationen auf der Seite " **Erste Schritte** ", und klicken Sie dann auf **weiter**, wenn Sie fertig sind.
3. Geben Sie auf der Seite **Speicherort und Zahlentyp auswählen** Folgendes an, und klicken Sie dann auf **weiter**:

    - **Land oder Region**: Land oder Region, in dem Sie Zahlen erhalten.
    - **Art der Telefonnummer**: Art der Nummer, beispielsweise geografische oder gebührenfreie Nummern.
    - **Nummern zugewiesen an**: Was die Nummern zugewiesen sind. Beispielsweise Benutzer oder Konferenz-oder Sprachfunktionen.

4. Führen Sie auf der Seite **Kontoinformationen hinzufügen** die folgenden Schritte aus, und klicken Sie dann auf **weiter**.

    > [!IMPORTANT]
    > Die auf dieser Seite angezeigten Informationen werden durch das Land oder die Region und den Nummerntyp bestimmt. Für jedes Land und jede Region gelten unterschiedliche Regelungen für die Informationen, die für die Portierung von Nummern erforderlich sind. Was auf dieser Seite angezeigt wird, kann sich von den hier beschriebenen unterscheiden.

    - **Bestelldetails**: 
        - **Bestell Name**: Name Ihrer Bestellung
        - **Benachrichtigungs**-e-Mails: e-Mail-Adressen zum Empfangen von Bestellbenachrichtigungen. Wenn Sie mehrere e-Mail-Adressen eingeben, trennen Sie die einzelnen Adressen durch ein Semikolon.
        - **Übertragenes Datum**: vom aktuellen Dienstanbieter ausgegebenes Übertragungsdatum.
    - **Telefonnummern Details**
        - **Porttyp**: ganz gleich, ob Sie eine vollständige Portierung durchführen, um alle Ihre Nummern zu übertragen, oder einen Teil-Port, um einige ihrer Nummern zu übertragen.
    - **Person, die Details anfordert**  
        - Name Ihrer Organisation und Kontaktdaten der Person, die die Übertragung beantragt.
    - **Informationen des aktuellen Anbieters**
        - **Abrechnungs Telefonnummer (BTN)**: Ihr BTN im E. 164-Format, für das ein +-Zeichen erforderlich ist, um die Nummer voranzustellen. Verwenden Sie beispielsweise für eine Nordamerika-Nummer das Format + 1XXXYYYZZZZ.
        - Weitere Informationen, einschließlich des Namens Ihres aktuellen Dienstanbieters, Ihrer Kontonummer und ihrer Dienstadresse.
            
5. Klicken Sie auf der Seite **Zahlen hinzufügen** auf **Datei auswählen**, navigieren Sie zu der CSV-Datei, die die zu übertragenden Telefonnummern enthält, und wählen Sie Sie aus, und klicken Sie dann auf **weiter**.  

    > [!NOTE]
    > Die CSV-Datei darf nur eine Spalte mit einem Header mit dem Namen "Faxnummer" aufweisen. Jede Telefonnummer muss sich in einer separaten Zeile befinden und kann nur Ziffern oder im E. 164-Format sein.

6. Klicken Sie auf der Seite " **Bestellung abschließen** " auf " **signierten Brief der Autorisierung hochladen** ", um eine gescannte Kopie des signierten Autorisierungs Schreibens (Letter of Authorization, Loa) hochzuladen.

    Wenn Sie den Loa noch nicht heruntergeladen und signiert haben, gehen Sie folgendermaßen vor:
    
    1. Klicken Sie auf **Vorlage herunterladen** , um die Loa für Ihr Land oder Ihre Region herunterzuladen. 
    2. Drucken Sie den Loa.
    3. Lassen Sie den Loa von der Person signieren, die berechtigt ist, Änderungen am Konto vorzunehmen.
    4. Überprüfen Sie den signierten Loa, und klicken Sie dann auf **einen signierten Brief der Autorisierung hochladen** , um ihn hochzuladen.

    > [!NOTE]
    > Nachdem Sie Ihre Loa hochgeladen haben, senden Sie Ihre Bestellung. Nur das Hochladen des Loa reicht nicht aus. Darüber hinaus müssen Sie den Auftrag für die Verarbeitung einreichen.

7. Überprüfen Sie Ihre Bestelldetails, und klicken Sie dann auf **Absenden**.


## <a name="what-happens-next"></a>Wie geht es weiter?

Wenn wir Ihren Portierungs Auftrag erhalten, erhalten Sie eine e-Mail, die Ihre Anfrage überprüft. Ihre Anfrage wird täglich überprüft und aktualisiert, und Sie werden über Ihren Status und Status per e-Mail benachrichtigt. Wenden Sie sich an den [PSTN-Service-Desk](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md), wenn Ihre Port Anfrage vom Verlierer-Netzbetreiber abgelehnt wurde.

Wenn Sie den Status Ihrer Portierungs Reihenfolge anzeigen möchten, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu > **VoIP** > -**Port Bestellungen**, und klicken Sie dann auf **Bestellverlauf**. Jeder Port Auftragsstatus wird in der Spalte **Status** aufgelistet. Weitere Informationen finden Sie unter [Was ist der Status Ihrer Portierungs Aufträge?](port-order-status.md)

## <a name="related-topics"></a>Verwandte Themen

- [Was ist ein Portierungsauftrag?](port-order-overview.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Nutzungsbedingungen für Notrufe](../emergency-calling-terms-and-conditions.md)
- [Disclaimer-Label für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
