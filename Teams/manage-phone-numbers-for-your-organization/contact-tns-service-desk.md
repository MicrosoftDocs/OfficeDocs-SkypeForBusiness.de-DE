---
title: Wenden Sie sich an das Team "Telefonnummerndienste"
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.tnsservicedesk
- ms.teamsadmincenter.voice.contacttnssupport
- Calling Plans
ROBOTS: NOINDEX, NOFOLLOW
description: Wenn Sie Telefonnummern oder Portnummern (Übertragungsnummern) für Ihre Organisation erhalten, müssen Sie möglicherweise Hilfe und Support beim TNS Service Desk erhalten.
ms.openlocfilehash: b490552b9f6f06a70e017b13f120bbb777cb9131
ms.sourcegitcommit: 46b5dc0519d487e264b1386e5074085c2d090e9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67674406"
---
# <a name="telephone-number-services-tns---service-desk"></a>Telefonnummerndienste (TNS) – Service Desk

> [!NOTE]
> Seit dem 22. Juli 2021 wurde das vorherige E-Mail-System zur Kontaktaufnahme mit dem TNS Service Desk eingestellt.

Es gibt einen neuen Prozess für die Interaktion mit dem TNS-Servicedesk (Telephone Number Services) aus unserem neuen **[Telefonnummern-Servicecenter](https://pstnsd.powerappsportals.com)**. Sie können jetzt Tickets öffnen, Tickets anzeigen und die Kommunikation an einem zentralen Ort nachverfolgen, der in das Teams Admin Center integriert ist. Jeder dieser Bereiche wird in den folgenden Abschnitten ausführlich beschrieben.


- **[Erstellen Sie einen neuen Fall](#create-a-new-case)** – Senden Sie eine neue Anfrage oder eine allgemeine Anfrage.

- **[Meine vorhandenen Fälle anzeigen](#view-and-manage-existing-cases)** – Ihre vorhandenen Fälle nachverfolgen und überwachen.

- **[Anzeigen von Fällen in meinem Unternehmen](#view-and-manage-existing-cases)** – Nachverfolgen und Überwachen der vorhandenen Fälle Ihres Unternehmens. Wenn Ihre Kollegen aus Ihrem Unternehmen Fälle geöffnet haben, können Sie diese in dieser Ansicht nachschlagen.

- **[Geben Sie Feedback](#view-and-manage-existing-cases)** – Teilen Sie Uns Ihr Feedback mit.

## <a name="create-a-new-case"></a>Erstellen eines neuen Falls

> [!NOTE]
> Nur jemand aus demselben Mandanten darf einen Fall erstellen. Beispielsweise kann eine Person von @fabrikam.com keinen Fall im Namen von @contoso.com erstellen.

Führen Sie die folgenden Schritte aus, um einen neuen Fall zu erstellen:

1. Wählen Sie an einer der folgenden Stellen **Neuen Fall erstellen** aus:

   - Auf der Startseite des **Telefonnummern-Servicecenters** oben auf der Seite oder auf der unteren Kachel.

   - Auf der Seite **Meine vorhandenen Fälle**  anzeigen.

   - Auf der Seite **Meine Unternehmensfälle**  anzeigen.

2. Geben Sie Ihre Falldetails an, wie im [nächsten Abschnitt](#provide-case-details) ausführlich beschrieben.

3. Nachdem Sie alle Werte eingegeben haben, wählen Sie **"Absenden**" aus. Es wird ein neuer Bildschirm angezeigt, auf dem Sie Ihre Fallnummer sehen können.

### <a name="provide-case-details"></a>Angeben von Falldetails

Um die Falldetails zu verstehen, benötigt Microsoft die folgenden Informationen:

- [Fallkategorie](#case-category)
- [Land oder Region](#country-or-region)
- [Falltyp](#case-type)
- [Falltitel](#case-title)
- [Zusätzliche Kontakte für Benachrichtigungen](#additional-contacts-for-notifications)
- [Beschreibung](#description)
- [Zusätzliche unterstützende Dokumente](#additional-supporting-documents)

#### <a name="case-category"></a>Fallkategorie

Ein Fall kann eine von zwei Kategorien aufweisen:

- **Übermitteln einer neuen Anforderung**: Wählen Sie diese Option aus, wenn Sie eine neue Anforderung übermitteln möchten. Sie möchten z. B. eine Portanforderung übermitteln oder Telefonnummern von Microsoft erhalten.

- **Allgemeine** : Wählen Sie diese Option aus, wenn Sie Fragen haben, die Ihnen helfen, Ihre Anfrage zu bestimmen. Beispielsweise müssen Sie wissen, ob Sie Ihre Drahtlosnummern zu Microsoft portieren können, oder sie müssen wissen, ob Microsoft gebührenfreie Vanity-Nummern unterstützt.

#### <a name="country-or-region"></a>Land oder Region

Wählen Sie das Land/die Region aus, für das/die Sie diesen Fall übermitteln. Wenn Sie Anforderungen für mehrere Länder haben, müssen Sie einen Fall pro Land/Region öffnen.

#### <a name="case-type"></a>Falltyp

Der Falltyp kann eine der folgenden sein:

- **Benutzerdefinierter Anrufname (nur USA)** : Legen Sie einen benutzerdefinierten Anrufnamen für Ihre Microsoft-Telefonnummern fest. Dies gilt nur für USA Telefonnummern.

  - **Festzulegenden benutzerdefinierten Anrufnamen (nur 15 Zeichen)** : Der benutzerdefinierte Anrufname, den Sie festlegen möchten. Der Name darf maximal 15 Zeichen enthalten.

  - **Liste der Telefonnummern** : Die Liste der Telefonnummern, für die Sie einen benutzerdefinierten Anrufnamenwert festlegen möchten. CSV-Datei mit der Liste der Rufnummern hochladen.

- **Mandantenübergreifender Port**– Telefonnummern von einem Mandanten in einen anderen verschieben. Sie haben z. B. zwei verschiedene Mandanten in Microsoft und möchten Ihre Telefonnummern von einem Mandanten zum anderen verschieben.

  - **Domänenname des Quellmandanten** : Der Mandant, aus dem Sie Telefonnummern in einen anderen Mandanten verschieben möchten.

  - **eindeutiger Bezeichner des Quellmandanten** : Die Mandanten-ID für den Quellmandanten. Dieses Feld ist optional.

  - **Domänenname des Zielmandanten** : Der Mandant, in den Sie Telefonnummern verschieben möchten.

  - **eindeutiger Bezeichner des Zielmandanten** : Die Mandanten-ID für den Zielmandanten. Dieses Feld ist optional.

  - **angeforderte Datums-*** – Datum und Uhrzeit, an dem Ihre Nummern vom Quellmandanten in den Zielmandanten verschoben werden sollen. Siehe Datum und Uhrzeit.

  - **Liste der Telefonnummern** : Die Liste der Telefonnummern, die Sie vom Quellmandanten zum Zielmandanten verschieben möchten. CSV-Datei mit der Liste der Rufnummern hochladen.

- **Ändern des Inventurtyps**– Ändern des Typs der Telefonnummern. Beispielsweise möchten Sie Ihre Microsoft-Abonnentennummern in Dienstnummern ändern. Weitere Informationen zu den von Microsoft unterstützten Telefonnummern finden Sie unter [Arten von Telefonnummern](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Konvertieren in** – Wählen Sie diese Option aus, um Ihre Nummern in Benutzer- oder Dienstnummern zu konvertieren.

  - **bevorzugter Datetime-*** – Das Datum und die Uhrzeit, an dem der Bestandstyp Ihrer Nummern geändert werden soll. Weitere Informationen finden Sie unter Datum und Uhrzeit.

  - **Kontrollkästchen – Ich verstehe, dass meine Telefonnummern nicht zugewiesen werden müssen, um den Bestandstyp aktualisieren zu können** . Microsoft kann Keine Änderungsanforderungen für Telefonnummerntypen verarbeiten, es sei denn, die Telefonnummern in Ihrem Mandanten sind nicht zugewiesen. Wenn Sie diese Änderung für ein zukünftiges Datum anfordern, müssen Sie sicherstellen, dass die Nummern vor dem angeforderten Datum und der gewünschten Uhrzeit nicht zugewiesen sind.

  - **Liste der Telefonnummern** : Die Liste der Telefonnummern, deren Typ Sie ändern möchten. CSV-Datei mit der Liste der Rufnummern hochladen.

- **New TN Acquisition** – Erhalten neuer Telefonnummern von Microsoft.

  - **Nummerntyp**: Wählen Sie den Typ für Ihre Nummern aus. Weitere Informationen finden Sie unter [Arten von Telefonnummern](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Sie haben versucht, Telefonnummern aus dem Teams Admin Center-Portal abzurufen** – Haben Sie versucht, diese Telefonnummern über das Microsoft Teams Admin Center zu erwerben?

  - **Anzahl der erforderlichen Telefonnummern**: Die Anzahl der Telefonnummern, die Sie erhalten möchten.

  - **Bundesland/Kanton** : Das Bundesland/die Provinz in Ihrem Land/Ihrer Region, für das/die Sie Telefonnummern benötigen.

  - **City** – Die Stadt innerhalb des Bundeslands/Kantons, für das Sie Telefonnummern benötigen.

  - **Office-Adresse** – Dies gilt nur für bestimmte Länder. Dies ist die Websiteadresse Ihres Büros.

  - **Verzeichnisauflistung** – Dies gilt nur für bestimmte Länder/Regionen. Möchten Sie Ihre Unternehmensinformationen mit den Telefonnummern veröffentlichen?

- **Port in**– Portieren vorhandener Telefonnummern von Ihrem aktuellen Dienstanbieter zu Microsoft.

  - **Benennen Sie Ihren Portierungsauftrag** – Geben Sie einen leicht zu merkenden Namen für Ihre Portanforderung an.

  - **Angefordertes Portierungsdatum/-uhrzeit*** – Datum und Uhrzeit, an dem die Nummern zu Microsoft portiert werden sollen. Dies ist kein garantiertes Portierungsdatum, da der aktuelle Nummernbesitzer zuerst unsere Portanforderung genehmigen muss. Siehe Datum und Uhrzeit.

  - **Liste der Portierungsnummern** : Die Liste der Telefonnummern, die Sie zu Microsoft portieren möchten. CSV-Datei mit der Liste der Rufnummern hochladen.

  - **Autorisierungsschreiben (LETTER of Authorization LOA)** : Fügen Sie hier einen ausgefüllten unterschriebenen und gestempelten LOA an. Microsoft kann eine Portierungsanfrage nicht ohne LOA bearbeiten.

- **Adressupdate**– Aktualisieren der Notrufadresse. Beachten Sie, dass dieses Feld nur für ausgewählte Länder gilt.

  - **Standort-ID** : Die Standort-ID für Ihre Notfalladresse.

  - **Liste der Telefonnummern** : Die Liste der Telefonnummern, für die Sie die Notfalladresse ändern möchten (geben Sie ihre gewünschte Adresse in das Feld "Beschreibung" ein). CSV-Datei mit der Liste der Rufnummern hochladen.

**Datum und Uhrzeit.** Wenn Sie Land = Frankreich, Datum = 14.08.2021 und Uhrzeit = 10:00 Uhr auswählen, wird die Anforderung am 14.08.2021 um 10:00 Uhr ausgeführt. Französische Zeit.

#### <a name="case-title"></a>Falltitel

Geben Sie einen Titel ein, der Ihre Frage zusammenfasst.

#### <a name="additional-contacts-for-notifications"></a>Zusätzliche Kontakte für Benachrichtigungen

Geben Sie die Liste der Personen ein, die automatisierte Statusbenachrichtigungen von Microsoft erhalten.
Beispielsweise möchten Sie eine Portierung beantragen und möchten, dass zwei weitere Kollegen zusätzlich zu sich selbst automatisierte Statusbenachrichtigungen erhalten. Geben Sie die E-Mail-Adressen Ihrer Kollegen im Abschnitt **Benachrichtigungs-E-Mails** an. Diese Informationen sind optional.

#### <a name="description"></a>Beschreibung

Beschreiben Sie, was Sie erreichen möchten, und führen Sie Ihre Fragen für den Microsoft Telephone Number Services (TNS) Service Desk auf.

#### <a name="additional-supporting-documents"></a>Zusätzliche unterstützende Dokumente

Laden Sie alle zusätzlichen Dokumente für Ihren Fall hoch.

## <a name="view-and-manage-existing-cases"></a>Anzeigen und Verwalten vorhandener Fälle

Sie können Ihre Fälle anzeigen, indem Sie **Meine vorhandenen Fälle anzeigen** und die Fallnummer auswählen. Wenn Sie eine Fallnummer auswählen, werden Sie zu den Falldetails weitergeleitet. (Sie können auch Unternehmensfälle anzeigen, indem Sie **Unternehmensfälle anzeigen** auswählen.)  Sie können auch folgende Aktionen ausführen:

- **Filtern Sie Ihre Fälle**, indem Sie **Offene Fälle**,  **Alle Fälle** oder **Geschlossene Fälle** auswählen.

- **Kommunizieren Sie mit dem TNS Service Desk** über Ihren Fall, indem Sie einen vorhandenen Fall öffnen, nach unten scrollen und **"Kommentar hinzufügen"** auswählen. Ein neues Fenster wird angezeigt. Geben Sie Ihre Nachricht in das Kommentarfeld ein. Fügen Sie alle unterstützenden Dokumente an (sofern verfügbar), und wählen Sie dann **"Absenden**" aus.

  Antworten vom **TNS Service Desk** werden auf derselben Zeitachse angezeigt. Wenn in Ihrem Fall ein Update vorhanden ist, erhalten Sie eine automatisierte E-Mail-Benachrichtigung über das Update.

- **Abbrechen eines Falls**, indem Sie zu einem vorhandenen Fall navigieren, nach unten scrollen und **Fall abbrechen** auswählen. Wählen Sie in der Dropdownliste einen Grund für den Abbruch aus, und wählen Sie dann **Abbrechen** aus.

- **Lösen eines Falls** : Wenn Sie der Meinung sind, dass Ihre Anforderung abgeschlossen wurde, können Sie einen Fall auflösen, indem Sie zu einem vorhandenen Fall navigieren, nach unten scrollen und **Fall auflösen** auswählen. Wählen Sie **Schließen**; der Fall wird jetzt als **– gelöstes Problem** angezeigt.

## <a name="related-topics-and-additional-resources"></a>Verwandte Themen und zusätzliche Ressourcen

- Unterstützung im Zusammenhang mit der Einrichtung und Konfiguration von Nummern, Lizenzen, Gebühren oder Abrechnung finden Sie unter [Supportkontakt für Geschäftsprodukte – Administratorhilfe](/microsoft-365/admin/contact-support-for-business-products?tabs=online).

- Informationen darüber, was in Ihrem Land oder in Ihrer Region verfügbar ist, finden Sie unter [Verfügbarkeit nach Ländern und Regionen für Audiokonferenzen und Anrufpläne](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

- Informationen zu den entsprechenden Telefonnummerntypen für Ihre Organisation finden Sie unter ["Verschiedene Arten von Telefonnummern"](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

- Informationen zum Abrufen neuer Telefonnummern finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization.md).

- Informationen zu den Geschäftsbedingungen für Notrufe finden Sie unter [Geschäftsbedingungen für Notrufe](../emergency-calling-terms-and-conditions.md).
