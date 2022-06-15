---
title: Übertragen von Telefonnummern an Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie mit dem Portierungs-Assistenten Ihre Telefonnummer von Ihrem aktuellen Dienstanbieter zu Microsoft Teams übertragen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5b139d332026ffe0ec8338cbe54f6a5309e6e2df
ms.sourcegitcommit: 39fc58109da6b4628ffb658f2c6b94099e0ab604
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2022
ms.locfileid: "66103252"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Übertragen von Telefonnummern an Microsoft Teams

Verwenden Sie den Portierungs-Assistenten im Microsoft Teams Admin Center, um Ihre Telefonnummern von Ihrem aktuellen Dienstanbieter an Teams zu übertragen. Nachdem Sie Ihre Telefonnummern zu Teams portiert haben, wird Microsoft Ihr Dienstanbieter und berechnet Ihnen diese Telefonnummern.

Bevor Sie beginnen, empfehlen wir Ihnen, die Informationen in "[Was ist ein Portauftrag?"](port-order-overview.md) zu überprüfen. Wenn Sie über Servicenummern für Einwahlkonferenzbrücken, automatische Telefonzentralen oder andere Servicenummern, gebührenfreie Telefonnummern oder über mehr als 999 Benutzertelefonnummern (Abonnenten) verfügen, die Sie an Teams übertragen müssen, lesen Sie "[Telefonnummern für Ihre Organisation verwalten](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)", um die richtigen Formulare herunterzuladen und an uns zu senden.

  > [!NOTE]
  > Portierungsaufträge für die Übertragung von Telefonnummern verarbeiten wir nur an USA Werktagen und nicht an Feiertagen oder Wochenenden.
  > Die Portierungsverfügbarkeit für gebührenfreie Telefonnummern kann je nach Land und Region variieren. Weitere Informationen finden Sie in ihren landes- oder regionsspezifischen Dokumenten, um den verfügbaren Support für den Portierungsdienst zu erhalten.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Erstellen Sie einen Portierungsauftrag, und übertragen Sie Ihre Telefonnummern an Teams

> [!NOTE]
> **Derzeit können Sie diesen Assistenten verwenden, um Telefonnummern für Das Vereinigte Königreich, USA und Kanada abzurufen**. Um Telefonnummern für andere Länder und Regionen zu erhalten, können Sie [manuell einen Portierungsantrag einreichen](manually-submit-port-order.md). Um das Formular zu erhalten, das Sie manuell übermitteln müssen, wählen Sie Ihr Land oder Ihre Region in der Dropdownliste unter ["Telefonnummern für Ihre Organisation verwalten"](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) aus.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Voice** >  **Telefon Nummern**. Klicken Sie auf **"Zahlen**" und dann auf " **Port** ", um den Portierungs-Assistenten zu starten.
2. Überprüfen Sie die Informationen auf der **Erste Schritte** Seite, und klicken Sie dann, wenn Sie fertig sind, auf **"Weiter**".
3. Geben Sie auf der Seite **"Speicherort und Zahlentyp auswählen** " Folgendes an, und klicken Sie dann auf **"Weiter**":

    - **Land oder Region**: Land oder Region, in dem Sie Nummern erhalten.
    - **Telefon Nummerntyp**: Typ der Nummer, z. B. geografische oder gebührenfreie Nummern.
    - **Zugewiesene Nummern**: Was die Nummern zugewiesen sind. Beispielsweise Benutzer oder Konferenz- oder Sprachfeatures.

4. Führen Sie auf der Seite **"Kontoinformationen hinzufügen** " Folgendes aus, und klicken Sie dann auf **"Weiter**".

    > [!IMPORTANT]
    > Die auf dieser Seite angezeigten Informationen werden durch das Land oder die Region und den Nummerntyp bestimmt. Jedes Land und jede Region haben unterschiedliche Vorschriften zu den Informationen, die zum Portieren von Nummern erforderlich sind. Was Sie auf dieser Seite sehen, kann sich von den hier beschriebenen Unterscheiden unterscheiden.

    - **Bestelldetails**: 
        - **Bestellname**: Name Ihrer Bestellung
        - **Benachrichtigungs-E-Mails**: E-Mail-Adressen zum Empfangen von Auftragsbenachrichtigungen. Wenn Sie mehrere E-Mail-Adressen eingeben, trennen Sie jede durch ein Semikolon.
        - **Übertragungsdatum**: Von Ihrem aktuellen Dienstanbieter ausgestelltes Übertragungsdatum.
    - **Telefon Zahlendetails**
        - **Porttyp**: Ganz gleich, ob Sie einen vollständigen Port zum Übertragen aller Nummern oder einen teilweisen Port zum Übertragen einiger Ihrer Nummern ausführen.
    - **Person, die Details anfordert**  
        - Name und Kontaktdaten Ihrer Organisation der Person, die die Übertragung anfordert.
    - **Details des aktuellen Anbieters**
        - **Abrechnungstelefonnummer (BTN)**: Ihr BTN im E.164-Format, für das ein +-Zeichen erforderlich ist, um die Nummer voranzugeben. Verwenden Sie z. B. für eine Nordamerika Zahl das Format +1XXXYYYZZZZ.
        - Weitere Details, einschließlich des Namens Ihres aktuellen Dienstanbieters, Ihrer Kontonummer und Ihrer Dienstadresse.
            
5. Klicken Sie auf der Seite " **Zahlen hinzufügen** " auf **"Datei auswählen**", navigieren Sie zu der CSV-Datei, die die Telefonnummern enthält, die Sie übertragen möchten, und klicken Sie dann auf **"Weiter**".  

    > [!NOTE]
    > Die CSV-Datei darf nur eine Spalte mit der Kopfzeile "PhoneNumber" aufweisen. Jede Telefonnummer muss sich in einer separaten Zeile befinden und kann nur Ziffern oder im E.164-Format sein.

6. Klicken Sie auf der Seite "**Bestellung abschließen**" auf **Hochladen einem signierten Vollmachtsschreiben**, um eine gescannte Kopie des signierten Schriftliche Vollmachtsschreibens (Letter of Authorization, LOA) hochzuladen.

    Wenn Sie die LOA noch nicht heruntergeladen und signiert haben, gehen Sie folgendermaßen vor:
    
    1. Klicken Sie auf **"Vorlage herunterladen** ", um die LOA für Ihr Land oder Ihre Region herunterzuladen. 
    2. Drucken Sie die LOA.
    3. Lassen Sie die LOA von der Person unterschreiben, die berechtigt ist, Änderungen am Konto vorzunehmen.
    4. Scannen Sie die signierte LOA, und klicken Sie dann auf **Hochladen ein signiertes Autorisierungsschreiben**, um es hochzuladen.

    > [!NOTE]
    > Nachdem Sie Ihre LOA hochgeladen haben, übermitteln Sie Ihre Bestellung. Das Hochladen der LOA reicht nicht aus. Sie müssen auch die Bestellung übermitteln, damit sie verarbeitet wird.

7. Überprüfen Sie Ihre Bestelldetails, und klicken Sie dann auf **"Absenden**".


## <a name="what-happens-next"></a>Wie geht es weiter?

Wenn wir Ihren Portierauftrag erhalten, erhalten Sie eine E-Mail, die Ihre Anfrage überprüft. Ihre Anforderung wird täglich überprüft und aktualisiert, und Sie werden per E-Mail über den Fortschritt und Status informiert. Wenn Ihre Portanforderung vom verlierenden Netzbetreiber abgelehnt wird, wenden Sie sich an den [TNS-Service Desk](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md).

Um den Status Ihres Portierungsauftrags anzuzeigen, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu >**VoIP-Portierungsaufträge** > , und klicken Sie dann auf "**Bestellverlauf**". Jeder Portierauftragsstatus wird in der Spalte **"Status"** aufgeführt. Weitere Informationen finden Sie unter [Wie lautet der Status Ihrer Portierungsaufträge?](port-order-status.md)


## <a name="reporting-telephone-number-issues"></a>Telefonnummernprobleme melden?
Wenn Sie ein Problem mit den portierten Nummern innerhalb der ersten 24-48 Stunden nach Abschluss des Ports feststellen, wenden Sie sich an den [TNS-Service Desk](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md). Wenden Sie sich für alle Probleme, die über 48 Stunden hinausgehen, an das Microsoft-Support-Team.

## <a name="related-topics"></a>Verwandte Themen

- [Was ist ein Portierungsauftrag?](port-order-overview.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Nutzungsbedingungen für Notrufe](../emergency-calling-terms-and-conditions.md)
- [Haftungsausschlussbezeichnung für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
