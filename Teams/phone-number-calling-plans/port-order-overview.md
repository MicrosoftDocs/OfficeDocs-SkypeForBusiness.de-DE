---
title: Was ist ein Portierungsauftrag?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: Verschaffen Sie sich einen Überblick darüber, was Portierungsaufträge sind und wie Sie Telefonnummern von Ihrem Dienstanbieter zu Teams übertragen.
ms.collection:
- M365-voice
- m365initiative-voice
ms.openlocfilehash: c5c8b68cfd97c8a39f0b4866fb7670473a9ecef3
ms.sourcegitcommit: 46b5dc0519d487e264b1386e5074085c2d090e9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67674376"
---
# <a name="whats-a-port-order"></a>Was ist ein Portierungsauftrag?

Wenn Sie derzeit über einen Telefondienstanbieter oder Netzbetreiber verfügen und bereits über Telefonnummern für Ihre Benutzer oder Dienste verfügen, müssen Sie einen "*Portierungsauftrag*" erstellen, um diese Telefonnummern an Microsoft Teams zu übertragen. Wenn die Nummern portiert werden, können Sie diese Telefonnummern Ihren Benutzern und Diensten wie Audiokonferenzen (für Konferenzbrücken), automatischen Telefonzentralen und Anrufwarteschleifen zuweisen.
  
Nachdem Sie Ihre Telefonnummern zu Teams portiert haben, wird Microsoft Ihr Dienstanbieter, und Sie können Ihren Dienst mit Ihrem alten Dienstanbieter oder Netzbetreiber trennen.

Lesen Sie die Informationen in diesem Artikel, um sich mit der Nummernportierung vertraut zu machen. Danach sollten Sie bereit sein, einen Portierungsauftrag zu erstellen und Ihre Telefonnummern zu übertragen. Schritt-für-Schritt-Anleitungen finden Sie unter [Übertragen von Telefonnummern an Teams](transfer-phone-numbers-to-teams.md) .
  
## <a name="what-countries-or-regions-support-number-porting"></a>Welche Länder oder Regionen unterstützen die Portierung von Nummern?

Sie können Telefonnummern in allen unterstützten Ländern oder Regionen portieren oder übertragen, aber wie Sie einen Portierungsantrag einreichen, hängt vom Land oder der Region ab, aus dem die Telefonnummern stammen. Eine Liste der Länder und Regionen, die die Nummernportierung unterstützen, finden [Sie unter "Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)".  

Derzeit unterstützt [der Portierungs-Assistent](transfer-phone-numbers-to-teams.md) im Microsoft Teams Admin Center das Abrufen von Telefonnummern für Großbritannien, USA und Kanada. Um Telefonnummern für andere Länder und Regionen zu erhalten, können Sie [manuell einen Portierungsantrag einreichen](manually-submit-port-order.md).
  
## <a name="what-numbers-can-be-transferred"></a>Welche Nummern können übertragen werden?

 **Sie können übertragen**
  
Im Allgemeinen können Sie eine beliebige Telefonnummer übertragen, die von einem unterstützten Anbieter stammt, einschließlich:
  
- Festnetztelefonnummern.

- Mobiltelefonnummern, wie sie für Mobiltelefone und Tablets verwendet werden.

    > [!NOTE]
    > Die Übertragung von Mobiltelefonnummern ist nur in den USA und Puerto Rico verfügbar.
  
- Gebührenpflichtige Telefonnummern.

- Gebührenfreie Telefonnummern.

    > [!NOTE]
    > Universal International Freephone Number (UIFN) kann nicht an uns übertragen werden.
    > Die Portierungsverfügbarkeit für gebührenfreie Telefonnummern kann je nach Land und Region variieren. Weitere Informationen finden Sie in ihren landes- oder regionsspezifischen Dokumenten, um den verfügbaren Support für den Portierungsdienst zu erhalten. 
  
- Servicetelefonnummern, z. B. für Konferenzbrücken, automatische Telefonzentralen usw.

- Faxtelefonnummern können jedoch nicht zum Faxen verwendet werden. Sie müssen einem Benutzer zugewiesen werden.

- VoIP-Telefonnummern von einem Telefonanbieter wie Vonage oder RingCentral.

- Wenn Sie Hybridtelefonnummern portieren (Migrieren von Direct Routing oder Telefonieanbieter zu Anrufplänen), wenden Sie sich bitte an das [Telefonnummerndienste-Team](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md), stellen Sie sicher, dass Sie einen Hinweis angeben, dass es sich um Hybridtelefonnummern handelt.

**Sie können Folgendes nicht übertragen:**
  
> [!NOTE]
> Derzeit können Sie keine Telefonnummern oder Nummern übertragen, die nicht aus einem unterstützten Land oder einer unterstützten Region stammen, einschließlich Telefonnummern von einem VoIP-Telefonanbieter. Eine Liste der unterstützten Länder/Regionen finden Sie unter [Verfügbarkeit von Ländern und Regionen für Audiokonferenzen und Anrufpläne](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Telefonnummern, die für Datenverbindungen wie DSL-Leitungen oder Breitband-Internetverbindungen verwendet werden.

- Telefonnummern, die dem Faxen gewidmet sind.

    Wenn Sie über dedizierte Telefonnummern verfügen, die zum Faxen verwendet werden,  *können*  Sie diese Nummern an Teams übertragen, aber Ihre Faxdienste funktionieren nicht wie erwartet. Faxdienste sind für Teams-Kunden nicht verfügbar, auch wenn Sie über Lizenzen für das Telefonsystem, den Anrufplan für Inland oder den Internationalen Anrufplan verfügen.

    Wenn Sie die Telefonnummer zu Teams portieren, können Sie diese Telefonnummer einem Benutzer in Ihrer Organisation zuweisen, anstatt sie zum Faxen zu verwenden.

> [!NOTE]
> Zu diesem Zeitpunkt im Vereinigten Königreich unterstützen wir derzeit nicht die Übertragung nicht geografischer Nummern des Vereinigten Königreichs einschließlich gemeinsamer Kostennummern für die Ortsvorwahlen 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>Welche Informationen muss ich bereitstellen?

Sie benötigen alle Kontoinformationen für Ihren aktuellen Netzbetreiber. Die Informationen, die Sie im Portierauftrag eingeben, finden Sie hauptsächlich auf der neuesten Rechnung ihres aktuellen Dienstanbieters. Sie müssen auch wissen, wessen Name sich auf dem Konto befindet und welche Nummern Sie portieren möchten.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>Was sind vollständige Port- und Teilportübertragungen?

Wenn Sie Telefonnummern zu Microsoft Teams portieren, haben Sie die Möglichkeit, alle Ihre Nummern oder einige davon zu übertragen.
  
- **Vollständiger Port** Dies ist der Zeitpunkt, an dem Sie alle Ihre Nummern von Ihrem aktuellen Dienstanbieter zu Teams übertragen. Wenn Sie nach den Telefonnummern gefragt werden, die Sie übertragen möchten, müssen Sie die Abrechnungstelefonnummer (BTN) zusammen mit allen anderen Telefonnummern in Ihrem Konto *angeben* .

    Angenommen, Ihr BTN ist  *+1 425-555-1234*  und Sie möchten alle Ihre 25 Telefonnummern portieren (*+1 425-555-1235 bis 1259*). Wenn Sie die nachstehenden Anweisungen zum Übertragen Ihrer Nummern befolgen, geben Sie Folgendes ein: **+14255551234 - +14255551259**.

- **Teilport** Dies ist der Zeitpunkt, an dem Sie nur einige Ihrer Telefonnummern von Ihrem aktuellen Dienstanbieter zu Teams übertragen. Wenn Sie einige der Telefonnummern portieren möchten, die mit demselben BTN verbunden sind, *dürfen* Sie ** nicht ** die BTN zusammen mit allen anderen Telefonnummern in Ihrem Konto einschließen.

    Angenommen, Ihr BTN ist  *+1 425-555-1234*  und Sie möchten nur 5 Ihrer 25 Telefonnummern portieren (*+1 425-555-1235 bis 1259*). Wenn Sie die nachstehenden Anweisungen befolgen, um Ihre Nummern zu übertragen, geben Sie Folgendes ein: **+1 425 555 1235 - +1 425 555 1239**.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>Kann ich eine einzige Nummernportierungsanforderung für alle meine Nummern gleichzeitig übermitteln?
<a name="bkmk_type_1"> </a>

Für jeden Netzbetreiber und typ der portierten Nummer ist eine eindeutige Anforderung erforderlich.
  
Sie müssen z. B. eine eindeutige Nummernportierungsanforderung für jeden der folgenden Nummerntypen übermitteln:
  
- Lokale gebührenpflichtige Nummern, auch als Abonnentennummern oder geografische Nummern bezeichnet

- Gebührenfreie Nummern mit Vorwahlen wie: 800, 844, 855, 866, 877 und 888

- Mobilnummern

- Dienstnummern, die für Audiokonferenzen in Microsoft 365 oder Office 365 verwendet werden können.

Hier finden Sie weitere Informationen zum Übermitteln von Nummernportierungsanforderungen für jeden dieser Nummerntypen:
  
- **Telefonnummern** , die von verschiedenen Netzbetreibern bereitgestellt werden, erfordern eine eindeutige Portierungsanforderung für Nummern bei jedem Netzbetreiber.

- **Gebührenfreie Nummern** mit Vorwahlen wie: 800, 844, 855, 866, 877 und 888 können nicht in einer Nummernportierungsanforderung mit anderen Nummerntypen enthalten sein. Um diese gebührenfreien Nummern portieren zu können, müssen Sie [manuell einen Portierungsantrag übermitteln](manually-submit-port-order.md). Diese Nummern können nicht im Microsoft Teams Admin Center portiert werden. Weitere Informationen finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    Es ist wichtig, die richtige Schriftliche Vollmacht (Letter of Authorization, LOA) für das Land und die Art der Telefonnummern zu verwenden, die Sie portieren möchten. Sie können [die LOA, die Sie benötigen, hier herunterladen](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- **Mobiltelefonnummern** erfordern einen PIN-Code, um die Übertragung zu autorisieren. Daher benötigen sie eine separate Nummernportierungsanforderung.

- Portierungsanforderungen für **Dienstnummern** müssen selbst übermittelt werden. Sie können nicht mit anderen Arten von Zahlen übermittelt werden.

## <a name="how-long-does-it-take-to-port-numbers"></a>Wie lange dauert das Portieren von Nummern?
<a name="bkmk_type_1"> </a>

Nachdem Sie die Anforderung des Portierauftrags abgeschlossen haben, dauert die Verarbeitung zwischen 7 und 14 Tagen. Je nach Dienstanbieter kann dies jedoch bis zu 30 Tage dauern. Nachdem die Telefonnummern portiert wurden, erhalten Sie eine E-Mail von uns, um Sie darüber zu informieren, dass Sie losfahren können.
  
Um den Status Ihres Portierungsauftrags zu überprüfen, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **VoIP-Telefonnummern** > , und klicken Sie dann auf "**Bestellverlauf**". Jeder Portierauftragsstatus wird in der Spalte **"Status"** aufgeführt.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>Können Telefonnummern von Benutzern (Abonnenten) in Servicenummern konvertiert werden?
<a name="bkmk_type_1"> </a>

Ja, das können sie. Informationen hierzu finden Sie unter [Verwalten der Verwendung einer Telefonnummer](../manage-the-usage-of-a-phone-number.md).

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>Kann ich meine Nummern von Teams zu einem anderen Telefondienstanbieter oder Netzbetreiber portieren?

Um Ihre Nummern von Teams zu einem anderen Netzbetreiber zu portieren, müssen Sie eine Anforderung beim neuen Netzbetreiber übermitteln. Sie müssen auch eine Portierungs-PIN im Microsoft Teams Admin Center festlegen.

Um Ihre Portierungs-PIN zu definieren, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **VoIP-Telefonnummern** > , wählen Sie in der oberen rechten Ecke der Seite die Option **"Portierungs-PIN verwalten**" aus, und geben Sie dann eine 10-stellige PIN ein.

Wenn Ihr neuer Netzbetreiber uns mit der Portierungsanfrage kontaktiert, bitten wir ihn, die von Ihnen definierte PIN anzugeben.

Wenn Sie weitere Informationen zum Einrichten einer PIN benötigen, wenden Sie sich bitte an das [Team für Telefonnummerndienste](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md).

## <a name="common-mistakes-to-watch-out-for"></a>Häufige Fehler, auf die Sie achten müssen
<a name="bkmk_type_1"> </a>

Das Portieren von Nummern ist einfach. Ihre Bestellung kann jedoch fehlerhaft werden, wenn ein Problem mit dem Telefondienstanbieter vorliegt, die Bestellung unvollständig ist und Informationen fehlen oder Tippfehler vorhanden sind.
  
Hier sind die häufigsten Fehler, die Kunden beim Portieren von Nummern machen. Speichern Sie sich einen Anruf beim Kundensupport, und überprüfen Sie diese Fehler.
  
- Stellen Sie sicher, dass die von Ihnen bereitgestellten Kontoinformationen genau mit dem übereinstimmen, was Ihr Netzbetreiber aufzeichnet. Nicht übereinstimmende Informationen sind die häufigste Ursache für Fehler und verzögern Ihren Portierungsauftrag. Stellen Sie sicher, dass Folgendes zutrifft:

  - Der Name oder die Person, die berechtigt ist, Änderungen am Konto vorzunehmen, ist richtig.

  - Die Adresse ist richtig.

  - Kontonummer ist richtig.

  - BTN ist richtig.

- Stellen Sie sicher, dass keine erweiterten Anrufsteuerungsfeatures vorhanden sind, z. B. "Anrufsuche", "Unverwechselbarer Ring", die für diese Telefonnummern aktiviert sind.

- Stellen Sie sicher, dass Sie keine neuen Serviceaufträge oder Trennungen bei Ihrem aktuellen Dienstanbieter aufgegeben haben.

- Stellen Sie sicher, dass alle Nummern vom gleichen Netzbetreiber und demselben Konto stammen.

- Stellen Sie sicher, dass Ihr Dienst aktiv ist. Das Einfrieren des Kontos verhindert den Wechsel von Netzbetreibern auf dem Konto. Die Person, die berechtigt ist, Änderungen am Konto vorzunehmen, muss eine Bestellung an den aktuellen Netzbetreiber übermitteln, um das Einfrieren zu entfernen. Dieser Vorgang kann je nach Netzbetreiber ein bis drei Wochen dauern.

## <a name="related-topics"></a>Verwandte Themen

- [Wie ist der Status meiner Portierungsaufträge?](port-order-status.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Nutzungsbedingungen für Notrufe](../emergency-calling-terms-and-conditions.md)
- [Haftungsausschlussbezeichnung für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
