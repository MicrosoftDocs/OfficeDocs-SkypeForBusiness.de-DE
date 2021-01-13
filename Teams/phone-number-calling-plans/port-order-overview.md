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
description: Verschaffen Sie sich einen Überblick über Portierungsaufträge und wie Sie Telefonnummern von Ihrem Dienstanbieter zu Teams übertragen.
ms.openlocfilehash: 4f1f8ca843db8c2b27eaa467b0014befe6f2b519
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802505"
---
# <a name="whats-a-port-order"></a>Was ist ein Portierungsauftrag?

Wenn Sie derzeit über einen Telefondienstanbieter oder Netzbetreiber verfügen und bereits Telefonnummernfür Ihre Benutzer oder Dienste haben, müssen Sie einen "Portierungsauftrag" erstellen, um diese Telefonnummern an Microsoft Teams zu übertragen. Wenn die Nummern portiert werden, können Sie diese Telefonnummern Ihren Benutzern und Diensten wie Audiokonferenzen (für Konferenzbrücken), automatischen Telefonkonferenzen und Anrufwarteschleifen zuweisen.
  
Nachdem Sie Ihre Telefonnummern zu Teams portiert haben, wird Microsoft Ihr Dienstanbieter, und Sie können Ihren Dienst mit Ihrem alten Dienstanbieter oder Netzbetreiber trennen.

Lesen Sie die Informationen in diesem Artikel, um sich mit der Nummernportierung vertraut zu machen. Anschließend sollten Sie bereit sein, einen Portierungsauftrag zu erstellen und Ihre Telefonnummern zu übertragen. Eine [schrittweise Anleitung finden Sie unter](transfer-phone-numbers-to-teams.md) "Telefonnummern an Teams übertragen".
  
## <a name="what-countries-or-regions-support-number-porting"></a>In welchen Ländern oder Regionen wird die Nummernportierung unterstützt?

Sie können Telefonnummern in allen unterstützten Ländern oder Regionen portieren oder übertragen, aber wie Sie einen Portierungsantrag übermitteln, hängt vom Land oder der Region ab, aus dem bzw. der die Telefonnummern stammen. Eine Liste der Länder und Regionen, die nummernportieren unterstützen, finden Sie unter ["Verwalten von Telefonnummern für Ihre Organisation".](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)  

Derzeit unterstützt [der Portierungsassistent](transfer-phone-numbers-to-teams.md) im Microsoft Teams Admin Center das Abrufen von Telefonnummern für Großbritannien, usa und Kanada. Um Telefonnummern für andere Länder und Regionen zu erhalten, können Sie [einen Portierungsauftrag manuell übermitteln.](manually-submit-port-order.md)
  
## <a name="what-numbers-can-be-transferred"></a>Welche Nummern können übertragen werden?

 **Sie können**
  
Im Allgemeinen können Sie jede beliebige Telefonnummer übertragen, die von einem unterstützten Anbieter ist, einschließlich:
  
- Telefonnummern für Festnetztelefone.

- Telefonnummern für Mobilgeräte, z. B. für Mobiltelefone und Tablets.

    > [!NOTE]
    > Das Übertragen von Mobiltelefonnummern ist nur in den USA und Puerto Rico verfügbar.
  
- Gebührenpflichtige Telefonnummern.

- Gebührenfreie Telefonnummern.

    > [!NOTE]
    > Universal International Freephone Number (UIFN) kann nicht an uns übertragen werden. 
  
- Servicetelefonnummern wie die, die für Konferenzbrücken, automatische Telefonkonferenzen usw. verwendet werden

- Faxtelefonnummern, die jedoch nicht zum Faxen verwendet werden können. Sie müssen einem Benutzer zugewiesen werden.

- VoIP-Telefonnummern von einem Telefonanbieter wie Vonage oder RingCentral.

- Skype for Business-Hybridtelefonnummern. Wenn Sie diese Nummern übertragen möchten, senden Sie uns eine E-Mail an <ptn@microsoft.com> .

  **Sie können nicht übertragen:**
  
    > [!NOTE]
    > Derzeit können Sie keine Telefonnummern oder Nummern übertragen, die nicht aus einem unterstützten Land oder einer unterstützten Region kommen, einschließlich Telefonnummern von einem VoIP-Telefonanbieter. Eine Liste der unterstützten Länder/Regionen finden Sie unter "Verfügbarkeit von Ländern und Regionen" für [Audiokonferenzen und Anrufpläne.](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Telefonnummern, die für Datenverbindungen verwendet werden, z. B. für DSL-Linien oder Internet-Breitbandverbindungen.

- Telefonnummern, die für Faxnachrichten verwendet werden.

    Wenn Sie über dedizierte Telefonnummern verfügen, die  zum Faxen verwendet werden, können Sie diese Nummern an Teams übertragen, aber Ihre Faxdienste funktionieren nicht wie erwartet. Faxdienste sind für Teams-Kunden nicht verfügbar, auch wenn Sie über Lizenzen für Telefonsystem, Anrufplan für Inland oder Plan für Auslandsanrufe verfügen.

    Wenn Sie die Telefonnummer zu Teams portieren, können Sie diese Telefonnummer einem Benutzer in Ihrer Organisation zuweisen, statt sie für Faxnachrichten zu verwenden.

    > [!NOTE]
    > Derzeit wird im Vereinigten Königreich die Übertragung nicht geografischer Nummern (einschließlich der gemeinsamen Kostennummern für die Vorwahlnummern 0843, 0844, 0845, 0870, 0871, 0872) für Großbritannien derzeit nicht unterstützt.
  
## <a name="what-information-do-i-need-to-provide"></a>Welche Informationen muss ich bereitstellen?

Sie benötigen alle Kontoinformationen für Ihren aktuellen Netzbetreiber. Die Informationen, die Sie im Portierungsauftrag eingeben, sind meistens auf der letzten Rechnung Ihres aktuellen Dienstanbieters zu finden. Außerdem müssen Sie wissen, unter welchem Namen das Konto verwendet wird und welche Nummern Sie portieren möchten.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>Was sind Übertragungen mit vollständigem Portierung und teilweiser Portierung?

Wenn Sie Telefonnummern zu Teams portieren, haben Sie die Möglichkeit, alle Ihre Telefonnummern oder einige davon zu übertragen.
  
- **Vollständige Portierung** Dabei übertragen Sie alle Telefonnummern von Ihrem aktuellen Dienstanbieter zu Teams. Wenn Sie nach den Telefonnummern gefragt werden,  die Sie übertragen möchten, müssen Sie die Abrechnungstelefonnummer (Billing Telephone Number, BTN) zusammen mit allen anderen Telefonnummern in Ihrem Konto verwenden.

    Angenommen, Ihr BTN ist *+1 425-555-1234* und Sie möchten alle Ihre 25 Telefonnummern portieren *(+1 425-555-1235 bis 1259).* Wenn Sie die nachstehenden Anweisungen zum Übertragen Ihrer Nummern befolgen, geben Sie ein: **+14255551234 - +14255551259.**

- **Teilweise Portierung** Dabei übertragen Sie nur einige Ihrer Telefonnummern von Ihrem aktuellen Dienstanbieter zu Teams. Wenn Sie einige der mit demselben BTN verknüpften Telefonnummern portieren möchten, **** dürfen Sie ** den BTN nicht zusammen mit allen anderen Telefonnummern in Ihrem Konto enthalten.

    Angenommen, Ihr BTN ist *+1 425-555-1234* und Sie möchten nur 5 Ihrer 25 Telefonnummern portieren *(+1 425-555-1235 bis 1259).* Wenn Sie die nachstehenden Anweisungen zum Übertragen Ihrer Nummern befolgen, geben Sie ein: **+1 425 555 1235 - +1 425 555 1239.**
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>Kann ich eine einzelne Nummernportierungsanforderung für alle meine Nummern gleichzeitig übermitteln?
<a name="bkmk_type_1"> </a>

Für jeden zu portierten Netzbetreiber und Nummerntyp ist eine eindeutige Anforderung erforderlich.
  
Sie müssen z. B. eine eindeutige Portierungsanforderung für Nummern für jeden der folgenden Nummerntypen übermitteln:
  
- Gebührenpflichtige lokale Nummern, auch als Abonnentennummern oder geografische Nummern bekannt

- Gebührenfreie Nummern mit Vorwahlnummern wie 800, 844, 855, 866, 877 und 888

- Mobiltelefonnummern

- Servicenummern, die für Audiokonferenzen in Microsoft 365 oder Office 365 verwendet werden können.

Hier finden Sie weitere Informationen zum Übermitteln von Nummernportierungsanforderungen für jeden dieser Nummerntypen:
  
- **Telefonnummern,** die von verschiedenen Netzbetreibern bereitgestellt werden, erfordern eine eindeutige Portierungsanforderung für Nummern bei jedem Netzbetreiber.

- **Gebührenfreie** Nummern mit Vorwahlnummern wie 800, 844, 855, 866, 877 und 888 können in einer Nummernportierungsanforderung mit anderen Nummerntypen nicht enthalten sein. Zum Portieren dieser gebührenfreien Nummern müssen Sie [manuell einen Portierungsauftrag übermitteln.](manually-submit-port-order.md) Sie können diese Nummern nicht im Microsoft Teams Admin Center portieren. Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    Es ist wichtig, für das Land und die Art der Telefonnummern, die Sie portieren möchten, das richtige Genehmigungsschreiben (Letter of Authorization; LOA) zu verwenden. Sie können [den hier benötigten LOA herunterladen.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- **Mobiltelefonnummern benötigen** einen PIN-Code, um die Übertragung zu autorisieren. Daher benötigen sie eine separate Anforderung für die Nummernportierung.

- **Portierungsanforderungen** für Servicenummer müssen von sich aus übermittelt werden. Sie können nicht mit anderen Arten von Zahlen übermittelt werden.

## <a name="how-long-does-it-take-to-port-numbers"></a>Wie lange dauert die Portierung von Nummern?
<a name="bkmk_type_1"> </a>

Nachdem Sie die Anforderung für den Portierungsauftrag abgeschlossen haben, dauert die Verarbeitung zwischen 7 und 14 Tagen. Je nach Dienstanbieter kann dies jedoch bis zu 30 Tage dauern. Nachdem die Telefonnummern portiert wurden, erhalten Sie eine E-Mail von uns, mit der Sie darauf klicken können.
  
Um den Status Ihres Portierungsauftrags zu überprüfen, wechseln Sie in der linken Navigationsleiste des Microsoft Teams **Admin** Centers zu den Voice Phone-Nummern, und klicken Sie dann auf  >   **"Bestellverlauf".** Der Status jedes Portierungsauftrags wird in der Spalte **"Status"** aufgeführt.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>Können Telefonnummern von Benutzern (Abonnenten) in Servicenummern umgewandelt werden?
<a name="bkmk_type_1"> </a>

Ja, das können sie. Sie müssen nur eine Serviceanfrage übermitteln, die die Mandanten-GUID Ihrer Organisation und die Telefonnummern enthält, die Konvertiert werden möchten. Informationen dazu finden Sie unter ["Verwalten von Telefonnummern für Ihre Organisation".](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>Kann ich meine Telefonnummern von Teams zu einem anderen Telefondienstanbieter oder Netzbetreiber portieren?

Um Ihre Nummern von Teams zu einem anderen Netzbetreiber zu portieren, müssen Sie eine Anfrage an den neuen Netzbetreiber übermitteln. Außerdem müssen Sie im Microsoft Teams Admin Center eine Portierungs-PIN festlegen.

Um Ihre Portierungs-PIN zu definieren, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu den **Voice** Phone-Nummern, wählen Sie in der oberen rechten Ecke der Seite "Portierungs-PIN verwalten" aus, und geben Sie dann eine  >  10-stellige PIN ein. 

Wenn sich Ihr neuer Netzbetreiber mit der Portierungsanforderung an uns kontaktiert, bitten wir ihn, die von Ihnen definierte PIN einsenden.

## <a name="common-mistakes-to-watch-out-for"></a>Häufige Fehler, auf die Sie achten müssen
<a name="bkmk_type_1"> </a>

Das Portieren von Nummern ist einfach. Ihre Bestellung kann jedoch beschädigt werden, wenn ein Problem mit dem Telefondienstanbieter vor liegt, die Bestellung unvollständig ist und Informationen fehlen oder Tippfehler vorhanden sind.
  
Hier sind die häufigsten Fehler, die Kunden beim Portieren von Nummern machen. Rufen Sie den Kundensupport an, und überprüfen Sie diese Fehler noch mal.
  
- Stellen Sie sicher, dass die von Ihnen erhaltenen Kontoinformationen genau mit den Angaben Ihres Netzbetreibers in Übereinstimmung sind. Nicht übereinstimmende Informationen sind die häufigste Ursache für Fehler und Verzögerungen beim Portierungsauftrag. Vergewissern Sie sich, dass Folgendes zutrifft:

  - Der Name oder die Person, die zum Ändern des Kontos berechtigt ist, ist korrekt.

  - Die Adresse ist richtig.

  - Die Kontonummer ist richtig.

  - BTN ist richtig.

- Stellen Sie sicher, dass für diese Telefonnummern keine erweiterten Anrufsteuerungsfunktionen wie Sammelanrufe oder unterschiedliches Klingeln aktiviert sind.

- Stellen Sie sicher, dass Sie bei Ihrem aktuellen Dienstanbieter keine neuen Serviceaufträge oder Trennungen mehr gestellt haben.

- Stellen Sie sicher, dass alle Nummern von demselben Netzbetreiber und demselben Konto kommen.

- Stellen Sie sicher, dass der Dienst aktiv ist. Das Einfrieren des Kontos verhindert die Änderung von Netzbetreibern für das Konto. Die Person, die zum Ändern des Kontos berechtigt ist, muss eine Bestellung an den aktuellen Netzbetreiber übermitteln, um das Einfrieren zu entfernen. Dieser Vorgang kann je nach Netzbetreiber ein bis drei Wochen dauern.

## <a name="related-topics"></a>Verwandte Themen

- [Wie ist der Status meiner Portierungsaufträge?](port-order-status.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Nutzungsbedingungen für Notrufe](../emergency-calling-terms-and-conditions.md)
- [Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)