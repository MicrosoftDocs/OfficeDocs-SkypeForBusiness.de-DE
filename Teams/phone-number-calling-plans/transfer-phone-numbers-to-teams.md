---
title: Übertragen von Telefonnummern an Microsoft Teams
author: cichur
ms.author: v-cichur
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
- m365initiative-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Mithilfe des Portierungs-Assistenten Ihre Telefonnummer von Ihrem aktuellen Dienstanbieter zu Microsoft Teams übertragen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dfc3141eea8d16a86c0f37221e597feac3bb957e
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421280"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Übertragen von Telefonnummern an Microsoft Teams

Verwenden Sie den Portierungs-Assistenten im Microsoft Teams Admin Center, um Ihre Telefonnummern von Ihrem aktuellen Dienstanbieter an Teams zu übertragen. Nachdem Sie Ihre Telefonnummern zu Teams portiert haben, wird Microsoft Ihr Dienstanbieter und stellt Ihnen diese Telefonnummern in Rechnung.

Bevor Sie beginnen, empfiehlt es sich, die Informationen unter [Was ist ein Portierungsauftrag? zu überprüfen.](port-order-overview.md) Wenn Sie Über Servicenummern für Einwahlkonferenzbrücken, automatische Telefonkonferenzen oder andere Servicenummern, gebührenfreie Telefonnummern oder mehr als 999 Telefonnummern von [](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) Benutzern (Abonnenten) haben, die Sie an Teams übertragen müssen, lesen Sie Verwalten von Telefonnummern für Ihre Organisation, um die richtigen Formulare herunterzuladen und an uns zu senden.

  > [!NOTE]
  > Wir verarbeiten Portierungsaufträge für die Übertragung von Telefonnummern nur an Werktagen in den USA und nicht an Feiertagen oder Wochenenden.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Erstellen eines Portierungsauftrags und Übertragen Ihrer Telefonnummern an Teams

> [!NOTE]
> **Derzeit können Sie diesen Assistenten verwenden, um Telefonnummern für Großbritannien, die Vereinigten Staaten** und Kanada zu erhalten. Um Telefonnummern für andere Länder und Regionen zu erhalten, können Sie [manuell einen Portierungsauftrag übermitteln.](manually-submit-port-order.md) Um das Formular zu erhalten, das Sie zum manuellen Übermitteln eines Portierungsauftrags benötigen, wählen Sie ihr Land oder Ihre Region in der Dropdownliste unter Verwalten von Telefonnummern [für Ihre Organisation aus.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Voice**  >  **phone numbers**. Klicken **Sie auf Zahlen** und dann auf **Portieren,** um den Portierungs-Assistenten zu starten.
2. Überprüfen Sie die Informationen auf **der** Seite Erste Schritte, und klicken Sie dann, wenn Sie fertig sind, auf **Weiter**.
3. Geben Sie auf der Seite Ort **und Zahlentyp** auswählen Folgendes an, und klicken Sie dann auf **Weiter:**

    - **Land oder Region:** Land oder Region, in dem Sie Zahlen erhalten.
    - **Telefonnummerntyp:** Typ der Nummer, z. B. geografische oder gebührenfreie Telefonnummern.
    - **Zugewiesene Zahlen:** Was den Zahlen zugewiesen sind. Beispielsweise Benutzer, Konferenz- oder Sprachfeatures.

4. Führen Sie **auf der Seite Kontoinformationen** hinzufügen die folgenden Schritte aus, und klicken Sie dann auf **Weiter**.

    > [!IMPORTANT]
    > Die auf dieser Seite angezeigten Informationen werden durch das Land oder die Region und den Zahlentyp bestimmt. Für jedes Land und jede Region gelten unterschiedliche Vorschriften für die Informationen, die zum Portieren von Nummern erforderlich sind. Was auf dieser Seite angezeigt wird, kann sich von den hier beschriebenen Unterscheiden unterscheiden.

    - **Bestelldetails:** 
        - **Bestellname**: Name Ihrer Bestellung
        - **Benachrichtigungs-E-Mails:** E-Mail-Adressen zum Empfangen von Bestellbenachrichtigungen. Wenn Sie mehrere E-Mail-Adressen eingeben, trennen Sie jede durch ein Semikolon.
        - **Übertragungsdatum:** Transferdatum, das von Ihrem aktuellen Dienstanbieter ausgestellt wurde.
    - **Telefonnummerndetails**
        - **Porttyp:** Ganz gleich, ob Sie eine vollständige Portierung zum Übertragen aller Zahlen oder einen teilportieren, um einige Ihrer Nummern zu übertragen.
    - **Person, die Details anfordert**  
        - Name Ihrer Organisation und Kontaktdetails der Person, die die Übertragung anfordert.
    - **Details des aktuellen Anbieters**
        - **Abrechnungstelefonnummer (BTN):** Ihr BTN im E.164-Format, für das ein +-Zeichen erforderlich ist, um die Nummer vorab zu verwenden. Verwenden Sie z. B. für eine Nordamerikanummer das Format +1XXXYYYYZZZZ.
        - Weitere Details wie der Name Ihres aktuellen Dienstanbieters, Ihre Kontonummer und Ihre Dienstadresse.
            
5. Klicken Sie **auf** der Seite Zahlen hinzufügen auf Datei **auswählen,** navigieren Sie zu der CSV-Datei, die die Telefonnummern enthält, die Sie übertragen möchten, und klicken Sie dann auf **Weiter**.  

    > [!NOTE]
    > Die CSV-Datei darf nur eine Spalte mit der Kopfzeile "PhoneNumber" enthalten. Jede Telefonnummer muss sich in einer separaten Zeile und darf nur Ziffern oder im E.164-Format sein.

6. Klicken Sie **auf der Seite** Bestellung abschließen auf **Signiertes** Autorisierungsschreiben hochladen, um eine gescannte Kopie des signierten Autorisierungsschreibens (Letter of Authorization, LOA) hochzuladen.

    Wenn Sie die LOA noch nicht heruntergeladen und signiert haben, gehen Sie wie folgt vor:
    
    1. Klicken **Sie auf Vorlage herunterladen,** um die LOA für Ihr Land oder Ihre Region herunterzuladen. 
    2. Drucken Sie die LOA.
    3. Lassen Sie die LOA von der Person, die berechtigt ist, Änderungen am Konto vorzunehmen, signiert werden.
    4. Überprüfen Sie das signierte LOA, und klicken Sie dann auf **Signiertes** Autorisierungsschreiben hochladen, um es hochzuladen.

    > [!NOTE]
    > Nachdem Sie Ihre LOA hochgeladen haben, übermitteln Sie Ihre Bestellung. Nur das Hochladen des LOA reicht nicht aus. Sie müssen auch die Bestellung für die Verarbeitung übermitteln.

7. Überprüfen Sie ihre Bestelldetails, und klicken Sie dann auf **Absenden**.


## <a name="what-happens-next"></a>Wie geht es weiter?

Wenn wir Ihren Portierungsauftrag erhalten, erhalten Sie eine E-Mail, in der Ihre Anfrage überprüft wird. Ihre Anfrage wird täglich überprüft und aktualisiert, und Sie werden in E-Mail über den Status und den Status der Anfrage benachrichtigt. Wenn Ihre Portierungsanfrage vom verlierende Netzbetreiber abgelehnt wird, wenden Sie sich an den [PSTN-Servicedesk.](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)

Um den Status Ihres Portierungsauftrags anzeigen zu können, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu > **Voice** Port orders , und klicken Sie dann auf  >   **Bestellverlauf**. Der Status jedes Portierungsauftrags wird in der Spalte **Status** aufgeführt. Weitere Informationen finden Sie unter [Wie ist der Status Ihrer Portierungsaufträge?](port-order-status.md)

## <a name="related-topics"></a>Verwandte Themen

- [Was ist ein Portierungsauftrag?](port-order-overview.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Nutzungsbedingungen für Notrufe](../emergency-calling-terms-and-conditions.md)
- [Haftungsausschlussetikett für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
