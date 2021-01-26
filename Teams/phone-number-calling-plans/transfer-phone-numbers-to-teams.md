---
title: Übertragen von Telefonnummern zu Microsoft Teams
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
description: Erfahren Sie, wie Sie mithilfe des Portierungsassistenten Ihre Telefonnummer von Ihrem aktuellen Dienstanbieter zu Microsoft Teams übertragen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52dd8a2a1dcbc14930695efd52141ce3b1842458
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812965"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Übertragen von Telefonnummern zu Microsoft Teams

[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Verwenden Sie den Portierungsassistenten im Microsoft Teams Admin Center, um Ihre Telefonnummern von Ihrem aktuellen Dienstanbieter zu Teams zu übertragen. Nachdem Sie Ihre Telefonnummern zu Teams portiert haben, wird Microsoft Ihr Dienstanbieter und stellt Ihnen diese Telefonnummern in Rechnung.

Bevor Sie beginnen, empfiehlt es sich, die Informationen unter ["Was ist ein Portierungsauftrag?" zu lesen.](port-order-overview.md) Wenn Sie über Servicenummern für Einwahlkonferenzbrücken, automatische Telefonisten oder andere Servicenummern, gebührenfreie Telefonnummern oder mehr als 999 Telefonnummern von [](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) Benutzern (Abonnenten) verfügen, die Sie an Teams übertragen müssen, lesen Sie "Verwalten von Telefonnummern für Ihre Organisation", um die richtigen Formulare herunterzuladen und an uns zu senden.

  > [!NOTE]
  > Wir verarbeiten Portierungsaufträge zur Übertragung von Telefonnummern nur an Werktagen in den USA und nicht an Feiertagen oder Wochenenden.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Erstellen eines Portierungsauftrags und Übertragen Ihrer Telefonnummern zu Teams

> [!NOTE]
> **Derzeit können Sie diesen Assistenten** verwenden, um Telefonnummern für Großbritannien, vereinigte Staaten und Kanada zu erhalten. Um Telefonnummern für andere Länder und Regionen zu erhalten, können Sie [einen Portierungsauftrag manuell übermitteln.](manually-submit-port-order.md) Um das Formular zu erhalten, das Sie manuell einen Portierungsauftrag übermitteln müssen, wählen Sie Ihr Land oder Ihre Region in der Dropdownliste unter "Telefonnummern für Ihre [Organisation verwalten" aus.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Voice**  >  **phone numbers".** Klicken **Sie auf "Nummern"** und dann auf **"Portieren",** um den Assistenten zum Portieren zu starten.
2. Überprüfen Sie die Informationen **auf** der Seite "Erste Schritte", und klicken Sie dann auf "Weiter", wenn Sie fertig **sind.**
3. Geben Sie **auf der Seite "Speicherort und** Zahlentyp auswählen" Folgendes an, und klicken Sie dann auf **"Weiter":**

    - **Land oder Region:** Das Land oder die Region, in dem bzw. in der Sie Nummern erhalten.
    - **Telefonnummerntyp:** Typ der Nummer, z. B. geografische oder gebührenfreie Telefonnummern.
    - **Nummern, denen zugewiesen** ist: Was die Nummern sind Beispielsweise Benutzer, Konferenz- oder Sprachfeatures.

4. Führen Sie **auf der Seite "Kontoinformationen hinzufügen"** die folgenden Schritte aus, und klicken Sie dann auf **"Weiter".**

    > [!IMPORTANT]
    > Die auf dieser Seite angezeigten Informationen sind vom Land oder der Region und dem Zahlentyp bestimmt. Für jedes Land und jede Region gelten unterschiedliche Vorschriften zu den Informationen, die für Portierungsnummern erforderlich sind. Das, was Sie auf dieser Seite sehen, kann sich von dem hier beschriebenen unterscheiden.

    - **Bestelldetails:** 
        - **Bestellname:** Name Ihrer Bestellung
        - **Benachrichtigungs-E-Mails:** E-Mail-Adressen zum Empfangen von Bestellbenachrichtigungen. Wenn Sie mehrere E-Mail-Adressen eingeben, trennen Sie diese durch ein Semikolon.
        - **Transferdatum:** Übertragungsdatum, das von Ihrem aktuellen Dienstanbieter ausgestellt wurde.
    - **Telefonnummerndetails**
        - **Porttyp:** Ganz gleich, ob Sie eine vollständige Portierung zum Übertragen aller Nummern oder eine teilweise Portierung zum Übertragen einiger Ihrer Nummern unternehmen.
    - **Person, die Details anfordert**  
        - Der Name Ihrer Organisation und die Kontaktdetails der Person, die die Übertragung anfordert.
    - **Details zum aktuellen Anbieter**
        - **Abrechnungstelefonnummer (Billing Telephone Number, BTN):** Ihr BTN im E.164-Format, für das ein +-Zeichen vor der Nummer erforderlich ist. Verwenden Sie beispielsweise für eine Telefonnummer aus Nordamerika das Format +1XXXYYYZZZZ.
        - Weitere Details, einschließlich des Namens Ihres aktuellen Dienstanbieters, Ihrer Kontonummer und Ihrer Dienstadresse.
            
5. Klicken Sie **auf** der Seite "Zahlen hinzufügen" auf "Datei auswählen", navigieren Sie zu der CSV-Datei, die die zu übertragende Telefonnummer enthält, und wählen Sie sie aus, und klicken Sie dann auf "Weiter".   

    > [!NOTE]
    > Die DATEI "CSV" darf nur eine Spalte mit der Überschrift "PhoneNumber" enthalten. Jede Telefonnummer muss in einer separaten Zeile stehen und kann nur Ziffern oder im E.164-Format sein.

6. Klicken Sie auf der  Seite **"Bestellung** abschließen" auf "Eine signierte Genehmigungsschreiben hochladen", um eine gescannte Kopie der signierten Genehmigungsschreiben hochzuladen.

    Wenn Sie den LOA noch nicht heruntergeladen und signiert haben, gehen Sie wie folgt vor:
    
    1. Klicken **Sie auf "Vorlage herunterladen",** um den LOA für Ihr Land oder Ihre Region herunterzuladen. 
    2. Drucken Sie den LOA.
    3. Lassen Sie den LOA von der Person unterzeichnen, die berechtigt ist, Änderungen am Konto vorzunehmen.
    4. Überprüfen Sie den signierten LOA, und klicken Sie dann auf **"Eine signierte Genehmigungsschreiben hochladen",** um ihn hochzuladen.

    > [!NOTE]
    > Nachdem Sie Ihren LOA hochgeladen haben, übermitteln Sie Ihre Bestellung. Nur das Hochladen des LOA reicht nicht aus. Sie müssen die Bestellung auch übermitteln, damit sie verarbeitet wird.

7. Überprüfen Sie die Bestelldetails, und klicken Sie dann auf **"Absenden".**


## <a name="what-happens-next"></a>Wie geht es weiter?

Wenn wir Ihren Portierungsantrag erhalten, erhalten Sie eine E-Mail, in der Ihre Anforderung überprüft wird. Ihre Anfrage wird täglich überprüft und aktualisiert, und Sie werden per E-Mail über ihren Status und Status benachrichtigt. Wenn Ihre Portierungsanforderung vom verlorenen Netzbetreiber abgelehnt wird, wenden Sie sich an den [PSTN Service Desk.](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)

Um den Status Ihres Portierungsauftrags zu sehen, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu > **Voice**  >  **Portierungsaufträge,** und klicken Sie dann auf "Bestellverlauf".  Der Status jedes Portierungsauftrags wird in der Spalte **"Status"** aufgeführt. Weitere Informationen finden Sie unter ["Wie ist der Status Ihrer Portierungsaufträge?".](port-order-status.md)

## <a name="related-topics"></a>Verwandte Themen

- [Was ist ein Portierungsauftrag?](port-order-overview.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Nutzungsbedingungen für Notrufe](../emergency-calling-terms-and-conditions.md)
- [Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
