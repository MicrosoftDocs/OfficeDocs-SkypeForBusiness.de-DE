---
title: Was ist ein Portierungsauftrag?
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: Verschaffen Sie sich einen Überblick darüber, was Portierungsaufträge sind und wie Telefonnummern von Ihrem Dienstanbieter an Teams übertragen werden.
ms.openlocfilehash: d7ca4769dcd1f320a7d0b8a8ed18fdba5b06abbd
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615051"
---
# <a name="whats-a-port-order"></a>Was ist ein Portierungsauftrag?

Wenn Sie derzeit über einen Telefondienstanbieter oder Netzbetreiber verfügen und bereits Telefonnummernfür Ihre Benutzer oder Dienste haben, müssen Sie einen Portierungsauftrag erstellen, um diese Telefonnummern an Microsoft Teams zu übertragen. Wenn die Nummern portiert werden, können Sie diese Telefonnummern Ihren Benutzern und Diensten zuweisen, z. B. Audiokonferenzen (für Konferenzbrücken), automatische Telefonkonferenzen und Anrufwarteschlangen.
  
Nachdem Sie Ihre Telefonnummern zu Teams portiert haben, wird Microsoft Ihr Dienstanbieter, und Sie können Ihren Dienst mit Ihrem alten Dienstanbieter oder Netzbetreiber trennen.

Lesen Sie die Informationen in diesem Artikel, um sich mit der Nummernportierung vertraut zu machen. Danach sollten Sie bereit sein, einen Portierungsauftrag zu erstellen und Ihre Telefonnummern zu übertragen. Schrittweise [Anleitungen finden Sie](transfer-phone-numbers-to-teams.md) unter Übertragen von Telefonnummern nach Teams.
  
## <a name="what-countries-or-regions-support-number-porting"></a>Welche Länder oder Regionen unterstützen die Nummernportierung?

Sie können Telefonnummern in allen unterstützten Ländern oder Regionen portieren oder übertragen, aber wie Sie eine Portierungsauftragsanfrage übermitteln, hängt vom Land oder der Region ab, aus dem die Telefonnummern stammen. Eine Liste der Länder und Regionen, die die Nummernportierung unterstützen, finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)  

Derzeit unterstützt [der Portierungs-Assistent](transfer-phone-numbers-to-teams.md) im Microsoft Teams Admin Center das Abrufen von Telefonnummern für Großbritannien, usa und Kanada. Um Telefonnummern für andere Länder und Regionen zu erhalten, können Sie [manuell einen Portierungsauftrag übermitteln.](manually-submit-port-order.md)
  
## <a name="what-numbers-can-be-transferred"></a>Welche Zahlen können übertragen werden?

 **Sie können**
  
Im Allgemeinen können Sie eine beliebige Telefonnummer übertragen, die von einem unterstützten Anbieter ist, einschließlich:
  
- Festnetztelefonnummern.

- Mobiltelefontelefonnummern, z. B. für Mobiltelefone und Tablets.

    > [!NOTE]
    > Das Übertragen von Mobiltelefonnummern ist nur in den USA und Puerto Rico verfügbar.
  
- Gebührenpflichtige Telefonnummern.

- Gebührenfreie Telefonnummern.

    > [!NOTE]
    > Universal International Freephone Number (UIFN) kann nicht an uns übertragen werden. 
  
- Servicetelefonnummern, z. B. für Konferenzbrücken, automatische Telefonkonferenzen usw.

- Faxtelefonnummern, aber sie können nicht zum Faxen verwendet werden. Sie müssen einem Benutzer zugewiesen werden.

- VoIP-Telefonnummern von einem Telefonanbieter wie Vonage oder RingCentral.

- Skype for Business-Hybridtelefonnummern. Wenn Sie diese Nummern übertragen möchten, senden Sie uns eine E-Mail an <ptn@microsoft.com> .

  **Sie können nicht übertragen:**
  
    > [!NOTE]
    > Derzeit können Sie keine Telefonnummern oder Nummern übertragen, die nicht aus einem unterstützten Land oder einer unterstützten Region kommen, einschließlich Telefonnummern von einem VoIP-Telefonanbieter. Eine Liste der unterstützten Länder/Regionen finden Sie unter Verfügbarkeit von Ländern und Regionen für [Audiokonferenzen und Anrufpläne.](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Telefonnummern, die für Datenverbindungen wie für DSL-Leitungen oder Breitbandinternetverbindungen verwendet werden.

- Telefonnummern, die dem Faxen gewidmet sind.

    Wenn Sie über dedizierte Telefonnummern verfügen, die  zum Faxen verwendet werden, können Sie diese Nummern an Teams übertragen, aber Ihre Faxdienste funktionieren nicht wie erwartet. Faxdienste sind für Teams-Kunden nicht verfügbar, auch wenn Sie über Lizenzen für Telefonsystem, Hausanrufplan oder Auslandsanrufplan verfügen.

    Wenn Sie die Telefonnummer zu Teams portieren, können Sie diese Telefonnummer einem Benutzer in Ihrer Organisation zuweisen, anstatt sie zum Faxen zu verwenden.

    > [!NOTE]
    > Derzeit unterstützen wir in Großbritannien nicht die Übertragung nicht geografischer Britischer Nummern, einschließlich geteilter Kostennummern für die Vorwahlen 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>Welche Informationen muss ich bereitstellen?

Sie benötigen alle Kontoinformationen für Ihren aktuellen Netzbetreiber. Die Informationen, die Sie in den Portierungsauftrag eingeben, finden Sie hauptsächlich auf der neuesten Rechnung ihres aktuellen Dienstanbieters. Sie müssen auch wissen, wessen Name sich auf dem Konto befindet und welche Nummern Sie portieren möchten.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>Was sind Übertragungen mit vollständigem Port und teilweiser Portierung?

Wenn Sie Telefonnummern zu Teams portieren, haben Sie die Möglichkeit, alle Ihre Telefonnummern oder einige davon zu übertragen.
  
- **Vollständige Portierung** Dabei übertragen Sie alle Ihre Nummern von Ihrem aktuellen Dienstanbieter an Teams. Wenn Sie nach den Telefonnummern gefragt werden,  die Sie übertragen möchten, müssen Sie die Abrechnungstelefonnummer (Billing Telephone Number, BTN) zusammen mit allen anderen Telefonnummern in Ihrem Konto enthalten.

    Angenommen, Ihr BTN ist  *+1 425-555-1234,*  und Sie möchten alle Ihre 25 Telefonnummern portieren (*+1 425-555-1235 bis 1259*). Wenn Sie die nachstehenden Anweisungen zum Übertragen Ihrer Zahlen befolgen, geben Sie ein: **+14255551234 - +14255551259**.

- **Teilportierung** Dabei übertragen Sie nur einige Ihrer Telefonnummern von Ihrem aktuellen Dienstanbieter zu Teams. Wenn Sie einige der Telefonnummern portieren möchten, die an denselben BTN gebunden sind, *dürfen* Sie ** den BTN nicht zusammen mit allen anderen Telefonnummern in Ihrem Konto enthalten.

    Angenommen, Ihr BTN ist  *+1 425-555-1234,*  und Sie möchten nur 5 Ihrer 25 Telefonnummern portieren (*+1 425-555-1235 bis 1259*). Wenn Sie die nachstehenden Anweisungen zum Übertragen Ihrer Zahlen befolgen, geben Sie ein: **+1 425 555 1235 - +1 425 555 1239.**
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>Kann ich gleichzeitig eine Portierungsanforderung für alle meine Nummern einreichen?
<a name="bkmk_type_1"> </a>

Für jeden Netzbetreiber und den Typ der portierten Nummer ist eine eindeutige Anforderung erforderlich.
  
Sie müssen z. B. eine eindeutige Nummerierungsanforderung für jeden der folgenden Nummerntypen übermitteln:
  
- Lokale Gebührennummern, auch als Abonnentennummern oder geografische Nummern bekannt

- Gebührenfreie Nummern mit Vorwahlnummern wie: 800, 844, 855, 866, 877 und 888

- Mobiltelefonnummern

- Servicenummern, die für Audiokonferenzen in Microsoft 365 oder Office 365 verwendet werden können.

Hier finden Sie weitere Informationen zum Übermitteln von Nummernportierungsanforderungen für jeden dieser Nummerntypen:
  
- **Telefonnummern,** die von verschiedenen Netzbetreibern bereitgestellt werden, erfordern eine eindeutige Portierungsanforderung für Nummern bei jedem Netzbetreiber.

- **Gebührenfreie** Nummern mit Vorwahlnummern wie 800, 844, 855, 866, 877 und 888 können nicht in eine Nummerierungsanforderung mit anderen Nummerntypen einbezogen werden. Zum Portieren dieser gebührenfreien Nummern müssen Sie [manuell einen Portierungsauftrag übermitteln.](manually-submit-port-order.md) Sie können diese Nummern nicht im Microsoft Teams Admin Center portieren. Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    Es ist wichtig, für das Land und die Art der Telefonnummern, die Sie portieren möchten, die richtige Berechtigungsschreiben (Letter of Authorization, LOA) zu verwenden. Sie können [die loA herunterladen, die Sie hier benötigen.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- **Für Mobiltelefonnummern** ist ein PIN-Code erforderlich, um die Übertragung zu autorisieren. Daher benötigen sie eine separate Nummerierungsanforderung.

- **Portierungsanforderungen** für Dienstnummer müssen von sich aus übermittelt werden. Sie können nicht mit anderen Zahlentypen übermittelt werden.

## <a name="how-long-does-it-take-to-port-numbers"></a>Wie lange dauert es, bis Portnummern portieren?
<a name="bkmk_type_1"> </a>

Nachdem Sie die Anfrage zum Portierungsauftrag abgeschlossen haben, dauert die Verarbeitung zwischen 7 und 14 Tagen. Je nach Dienstanbieter kann dies jedoch bis zu 30 Tage dauern. Nachdem die Telefonnummern portiert wurden, erhalten Sie von uns eine E-Mail, mit der Sie wissen lassen, dass Sie losgehen können.
  
Um den Status Ihres Portierungsauftrags zu überprüfen, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Voice**  >  **Phone-Nummern,** und klicken Sie dann auf **Bestellverlauf**. Der Status jedes Portierungsauftrags wird in der Spalte **Status** aufgeführt.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>Können Telefonnummern von Benutzern (Abonnenten) in Servicenummern konvertiert werden?
<a name="bkmk_type_1"> </a>

Ja, das können sie. Sie müssen nur eine Dienstanforderung übermitteln, die die GUID des Mandanten Ihrer Organisation und die Telefonnummern enthält, die Konvertiert werden soll. Informationen dazu finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>Kann ich meine Nummern von Teams zu einem anderen Telefondienstanbieter oder Netzbetreiber portieren?

Um Ihre Nummern von Teams zu einem anderen Netzbetreiber zu portieren, müssen Sie eine Anfrage beim neuen Netzbetreiber einreichen. Sie müssen auch eine Portierungs-PIN im Microsoft Teams Admin Center festlegen.

Um Ihre Portierungs-PIN zu definieren, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu Voice Phone-Nummern, wählen Sie in der oberen rechten Ecke der Seite Portierungs-PIN verwalten aus, und geben Sie dann eine  >  10-stellige PIN ein. 

Wenn Ihr neuer Netzbetreiber uns mit der Portierungsanfrage kontaktiert, bitten wir ihn, die von Ihnen definierte PIN zur Verfügung zu stellen.

## <a name="common-mistakes-to-watch-out-for"></a>Häufige Fehler, auf die Sie achten müssen
<a name="bkmk_type_1"> </a>

Das Portieren von Zahlen ist einfach. Ihre Bestellung kann jedoch durcheinander kommen, wenn ein Problem mit dem Telefondienstanbieter vorkommt, die Bestellung unvollständig ist und informationen fehlt oder Tippfehler vorhanden sind.
  
Dies sind die häufigsten Fehler, die Kunden beim Portieren von Nummern machen. Speichern Sie sich einen Anruf beim Kundensupport, und überprüfen Sie auf diese Fehler.
  
- Stellen Sie sicher, dass die von Ihnen erhaltenen Kontoinformationen genau dem entspricht, was Ihr Telefonanbieter aufgezeichnet hat. Nicht übereinstimmende Informationen sind die häufigste Ursache für Fehler und verzögern Den Portierungsauftrag. Stellen Sie sicher, dass Folgendes zutrifft:

  - Der Name oder die Person, die berechtigt ist, Änderungen am Konto vorzunehmen, ist richtig.

  - Die Adresse ist richtig.

  - Die Kontonummer ist richtig.

  - BTN ist richtig.

- Stellen Sie sicher, dass es keine erweiterten Anrufsteuerungsfunktionen gibt, z. B. Anrufsuche, Unterscheidungszeichenring, die für diese Telefonnummern aktiviert sind.

- Stellen Sie sicher, dass Sie keine neuen Serviceaufträge oder Verbindungen mit Ihrem aktuellen Dienstanbieter getrennt haben.

- Stellen Sie sicher, dass alle Nummern vom gleichen Netzbetreiber und demselben Konto kommen.

- Stellen Sie sicher, dass Ihr Dienst aktiv ist. Durch das Einfrieren des Kontos wird der Wechsel von Netzbetreibern für das Konto verhindert. Die Person, die berechtigt ist, Änderungen am Konto vorzunehmen, muss eine Bestellung an den aktuellen Netzbetreiber übermitteln, um das Fixieren zu entfernen. Dieser Vorgang kann je nach Netzbetreiber ein bis drei Wochen dauern.

## <a name="related-topics"></a>Verwandte Themen

- [Wie ist der Status meiner Portierungsaufträge?](port-order-status.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Nutzungsbedingungen für Notrufe](../emergency-calling-terms-and-conditions.md)
- [Haftungsausschlussetikett für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
