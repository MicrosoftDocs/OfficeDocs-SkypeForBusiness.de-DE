---
title: Treffen von Entscheidungen für das Telefonsystem mit Anrufplänen – Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Wählen Sie aus Anrufplänen und Lizenzen, konfigurieren Sie Notfall Standorte und Funktionen wie Voicemail und Rufnummernanzeige, erwerben oder übertragen Sie Telefonnummern.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ddc618a4b68c8a620568eba5ae2ed52d17096b30
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232357"
---
# <a name="make-my-service-decisions"></a>Meine Dienst Entscheidungen treffen

Wenn Sie die technische Implementierung des Telefonsystems mit Anrufplänen planen möchten, müssen Sie eine Reihe von Dienst Entscheidungen vorzeitig treffen, um Ihre Organisation besser auf die Implementierung einer Lösung vorzubereiten, die ihre definierten geschäftlichen Anforderungen erfüllt.

## <a name="calling-in-teams"></a>Anrufe in Teams

Mit Microsoft Teams können Ihre Benutzer Telefonanrufe in das öffentlich geschaltete Telefonnetz (PSTN) tätigen und empfangen. Ihre Benutzer können Ihre eigenen dedizierten Telefonnummern für das tätigen und empfangen von Inlands-und Auslandsanrufen aus Teams-Clientanwendungen mit erweiterten Funktionen, die Voicemail enthalten, verwenden.

> [!NOTE]
> Die aktuelle Roadmap für Teams zur Identifizierung von Teams-Telefonsystemen mit Anruf Plan Funktionen im Bereich für Ihre Bereitstellung <https://aka.ms/O365Roadmap>finden Sie unter.

## <a name="phone-system-in-teams"></a>Telefon System in Teams

Damit Teams-Benutzer PSTN-Anrufe tätigen und empfangen können, müssen Sie für das Telefon System, ein Feature in Office 365, aktiviert sein.

Um die Verbindung mit dem PSTN zu ermöglichen, kann Ihre Organisation Microsoft als Telekommunikationsdienst Anbieter verwenden. Schließlich haben Sie auch die Möglichkeit, ihren eigenen Telekommunikationsdienstanbieter zu "bringen", um die Verbindung zu PSTN für das Telefon System zu ermöglichen.

> [!IMPORTANT]
> Die Möglichkeit zur Nutzung Ihres eigenen Telekommunikationsdienstanbieters für Telefonsysteme mit ihrer Teams-Bereitstellung ist auch mit direktem Telefonsystem-Routing verfügbar. Wenn Sie mehr über das direkte Routing erfahren möchten, lesen Sie die Anweisungen für das [direkte Routing](2-envision-make-my-service-decisions-direct-routing.md).

## <a name="phone-system-with-calling-plans"></a>Telefon System mit Anrufplänen

Wenn Sie Microsoft als Telekommunikationsdienst Anbieter verwenden möchten, müssen Sie die Lizenzen für den Anrufplan erhalten und Sie Ihren Telefon System Benutzern zuweisen.

Es gibt zwei Haupttypen von Anrufplänen:

-   Plan für Inlandsanrufe

-   Plan für Inlands-und Auslandsgespräche

Jede Art von Anrufplan ordnet jedem Benutzer, dem die Lizenz zugewiesen wurde, eine bestimmte Anzahl von Anruf Minuten pro Monat zu. Wenn die Zuweisung der Anruf Minuten aufgebraucht ist, kann der Benutzer bis zum Abrechnungszyklus des nächsten Monats keine ausgehenden Anrufe tätigen – mit Ausnahme von Notrufen. Wenn Sie möchten, dass Benutzer weiterhin ausgehende Anrufe tätigen können, auch wenn Sie die Zuweisung von Gesprächsminuten erschöpft haben oder wenn Benutzer mit einem Inlandsanruf Plan Auslandsgespräche führen, können Sie für Ihre Organisation Kommunikationsguthaben einrichten.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>Verfügbarkeit von Anrufplänen

Bevor Sie die Implementierung von Anrufplänen in Teams planen, stellen Sie sicher, dass der Anruf Plandienst in Ihrem Gebiet verfügbar ist, indem Sie die [Verfügbarkeit von Ländern und Regionen für Audiokonferenz-und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)überprüfen.

> [!IMPORTANT]
> Aufgrund rechtlicher Einschränkungen muss der Vertrag für Office 365-Abonnements in einem Land oder einer Region basieren, in dem der Anrufplan-Service verfügbar ist, oder der Service für Anrufpläne erworben.

> [!NOTE]
> Wenn in Ihrem Bereich keine Anrufpläne verfügbar sind, können Sie Ihre Benutzer mithilfe des direkten Routings für das [Telefon System](2-envision-make-my-service-decisions-direct-routing.md) für die Verwendung von Teams mit PSTN-Funktionen aktivieren.

Nachdem Sie bestätigt haben, dass Ihre Organisation den Anruf Plandienst abrufen kann, kompilieren Sie die Liste der Benutzer Standorte oder-Büros, in denen Sie den Anruf Plandienst durchführen werden, basierend auf der Liste der verfügbaren Länder und Regionen.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, für welche Benutzer Standorte oder Büros Sie den Anruf Plandienst in implementieren.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer Standorte oder Offices, die für den Anruf Plandienst aktiviert werden sollen.</li></ul>|

> [!TIP]
> Nachfolgend finden Sie ein Beispiel für ein Telefon System mit einer Liste der Anrufpläne für die Website Aktivierung.
> 
> | **Office**                     | **Standort**   | **Telefon System Dienst** |
> |--------------------------------|----------------|--------------------------|
> | One Epping Road                | Australien      | PSTN-Legacy Dienst |
> | 100 Cyberport Road             | Hong Kong SAR (香港特別行政區)  | Direktes Routing für Telefonsysteme |
> | One Marina Boulevard           | Singapur      | Direktes Routing für Telefonsysteme |
> | 32 London Bridge Street        | Vereinigtes Königreich | Telefon System mit Anrufplänen |
> | 39 quai du Président Roosevelt | Frankreich         | Telefon System mit Anrufplänen |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Telefonnummern und Notfallstandorte

Bei Anrufplänen in Office 365 muss jeder Benutzer in Ihrer Organisation über eine eindeutige direkte Durchwahl (DID)-Telefonnummer und eine entsprechende validierte Notfalladresse verfügen. Überprüfen Sie [Cloud-VoIP-Telefonnummern verwalten](2-envision-make-my-service-decisions-phone-system.md#manage-cloud-voice-telephone-numbers) , um die Rufnummern Erfassung für Ihre Anruf Plan Implementierung zu planen.

Wenn Sie Telefonnummern für Anrufpläne konfigurieren, müssen Sie jeder Telefonnummer eine Notfalladresse zuweisen, bevor Sie die Nummer einem Benutzer zuweisen. Dies ist erforderlich, um Notrufe zu unterstützen. Die Notfalladresse muss überprüft werden, um sicherzustellen, dass Sie das richtige Format hat, damit Sie von den Notrufdiensten verwendet werden kann.

> [!IMPORTANT]
> Notrufdienste Anrufe funktionieren anders im Calling-Plan-Service als in herkömmlichen Telefondiensten. Es ist wichtig, dass Sie diese Unterschiede verstehen und allen Benutzern mitteilen. Weitere Informationen finden Sie in den [allgemeinen Geschäftsbedingungen](emergency-calling-terms-and-conditions.md) für Notrufe.

Zusätzlich zur Bereitstellung einer validierten Notfalladresse können Sie Notfall Standorte definieren und diese mit der überprüften Notfalladresse verknüpfen, um eine genauere Position innerhalb einer Adresse anzugeben. Ein Notfallstandort ist meist die Gebäudenummer, das Stockwerk, der Gebäudeflügel oder die Nummer des Zimmers, in dem sich der Benutzer befindet.

Wenn Sie mehr über Notfall Standorte in Bezug auf Anrufpläne erfahren möchten, lesen Sie die folgenden Artikel:

-   [Was sind Notfallstandorte, Notfalladressen und Anrufweiterleitung?](what-are-emergency-locations-addresses-and-call-routing.md)

-   [Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie sich für die Granularität der Notfall Standortinformationen, die für Benutzer Standorte oder Büros im Bereich für die Implementierung des Anruf Plans erfasst werden sollen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die detaillierten Notfalladressen und Notfall Speicherorte für die einzelnen Benutzer Standorte oder Office im Bereich für die Implementierung von Anrufplänen.</li></ul>|

> [!TIP]
> Mit der folgenden Vorlage können Sie die Details von Telefonnummern und Notfall Standortdetails dokumentieren.
> 
> |User |Notfall Standort und-Adresse |Telefonnummer |
> |-----|-------------------------------|-------------|
> |Emily Braun |1034/32 London Bridge Street, London, SE1, Vereinigtes Königreich |+ 44 23 4567 8901 |
> |Lidia Holloway |1065/32 London Bridge Street, London, SE1, Vereinigtes Königreich |+ 44 23 4567 89112 |
> |Louis Lahr |1023/32 London Bridge Street, London, SE1, Vereinigtes Königreich |+ 44 23 4567 8921 |
> |Marcel Beauchamp |07E15D/39 Quai du President Roosevelt, 92130 Issy-les-Moulineaux, Frankreich | TBA |
> |Rachelle Cormier |07N15D/39 Quai du President Roosevelt, 92130 Issy-les-Moulineaux, Frankreich | TBA |
> |Isabell Potvin |07F05E/39 Quai du President Roosevelt, 92130 Issy-les-Moulineaux, Frankreich | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Voicemail

Cloud Voicemail, powered by Azure Voicemail Services, unterstützt Voicemail-Einzahlungen nur für Exchange-Postfächer und unterstützt keine e-Mail-Systeme von Drittanbietern.

Standardmäßig funktioniert Cloud Voicemail mit Exchange Online; Es verfügt jedoch über eine minimale unterstützte Exchange-lokale Version und ein Bereitstellungsmodell, um die Zustellung von Voicemail-Nachrichten an Benutzerpostfächer in der lokalen Exchange-Bereitstellung zu ermöglichen.

Cloud Voicemail umfasst Voicemail-Transkription, die standardmäßig für alle Benutzer in Ihrer Organisation aktiviert ist. Für Ihre geschäftlichen Anforderungen müssen Sie möglicherweise die Voicemail-Transkription für bestimmte Benutzer oder alle in der Organisation deaktivieren. Wenn Ihre Organisation entschieden hat, die Voicemail-Transkription zu aktivieren, müssen Sie auch berücksichtigen, ob die Maskierung von Voicemail-Transkriptions Obszönitäten aktiviert sein muss. Weitere Informationen finden Sie unter [Festlegen von Voicemail-Richtlinien in Ihrer Organisation](set-up-phone-system-voicemail.md) .

>[!NOTE]
> Ein Fallback-Mechanismus wurde implementiert, damit Cloud Voicemail Nachrichten mithilfe von SMTP erneut senden kann, was bedeutet, dass Benutzer, die über ein Postfach auf einem Drittanbieter-e-Mail-System verfügen, ihre Sprachnachrichten erhalten. Dieser Mechanismus umfasst keine garantierte Dienstverfügbarkeit oder andere Voicemail-Funktionen wie das Ändern der Voicemail-Ansage.

Weitere Informationen zu Voicemail in einer Telefonsystem Implementierung finden Sie unter [Telefonsystem mit Anrufplänen](calling-plan-landing-page.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie in Ihrer Anruf Plan Implementierung Cloud Voicemail aktivieren möchten.</li><li>Wenn Sie Exchange lokal verwenden und Ihre vorhandene Bereitstellung Ihre Anforderungen zur Unterstützung von Cloud-Voicemail nicht erfüllt, wählen Sie eine der verfügbaren Optionen aus (Upgrade und Setup für Cloud Voicemail-Unterstützung, zu Exchange Online migrieren oder das Fallback nutzen zuvor beschriebene Mechanismus).</li><li>Entscheiden Sie, ob Sie Voicemail-Transkriptions-und Voicemail-Transkriptions-Obszönitäten in der gesamten Organisation oder für bestimmte Benutzer aktivieren oder deaktivieren möchten.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie gegebenenfalls die Exchange-Entscheidungspunkte, um die Cloud-Voicemail zu unterstützen.</li><li>Wenn Sie Voicemail, Voicemail-Transkription und Voicemail-Transkription für anstößige Ausdrücke nur für bestimmte Benutzer aktivieren/deaktivieren möchten, dokumentieren Sie die Liste der Benutzer.</li></ul>|

> [!TIP]
> Cloud-Voicemail-Details für das Telefon System mit der Implementierung von Anrufplänen können wie folgt dokumentiert werden.
> 
> |User |Exchange-Postfach |Voicemail aktivieren? |Voicemail-Transkription |Voicemail-Transkriptions-Obszönität-Maskierung |
> |------------------|------------------|-------------------|----------|----------|
> |Emily Braun      |Online      |Ja |Aktiviert |Aktiviert |
> |Lidia Holloway   |Online      |Ja |Aktiviert |Deaktiviert |
> |Louis Lahr       |Lokal |Ja |Aktiviert |Aktiviert |
> |Marcel Beauchamp |Lokal |Ja |Deaktiviert |Nicht zutreffend |
> |Rachelle Cormier |Online      |Ja |Deaktiviert |Nicht zutreffend |
> |Isabell Potvin   |Lokal |Ja |Deaktiviert |Nicht zutreffend |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>Identität des Anrufs

Standardmäßig verwenden alle ausgehenden Anrufe die zugewiesene Telefonnummer als Anruf Identität (Rufnummernanzeige). Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte. In einigen Fällen gibt es legitime geschäftliche Anforderungen, um die Rufnummernanzeige zu maskieren, um die Identität von Anrufern mithilfe der Office-Haupt Leitungsnummer zu schützen – in der Regel handelt es sich um eine Servicenummer, die von der Konfiguration der automatischen Telefonzentrale gewartet wird – als Rufnummernanzeige oder zum Blockieren der Rufnummernanzeige. Präsentation insgesamt.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob die Anrufer-ID-Manipulation für Ihre Anruf Plan Implementierung erforderlich ist.</li><li>Falls zutreffend, entscheiden Sie, welche Arten von Anrufer-ID-Manipulation (Maske mit Service-Nummer oder Anonymisierung) implementiert werden sollen.</li><li>Falls zutreffend, entscheiden Sie, welche Benutzer die Manipulation der Rufnummernanzeige und die Art der Manipulation der Anrufer-ID für die einzelnen Benutzer festlegen müssen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer, denen die Rufnummernanzeige Manipulation zugewiesen werden soll, und die Art der zu zuweisenden Manipulation der Rufnummernanzeige.</li></ul>|

> [!TIP]
> Im folgenden finden Sie ein Beispiel für die Dokumentation zur Maskierung der Rufnummernanzeige.
> 
> |User  |Ausgehende Anrufer-ID-Maskierung aktivieren  |Typ der Rufnummernanzeige-Maskierung  |Benutzer Überschreibung zulassen  | Aktivieren der eingehenden Anrufer-ID-Maskierung  |
> |---------|---------|---------|---------|---------|
> |Emily Braun|Nein|n/v|Ja|Nein|
> |Lidia Holloway|Ja|Service-Nummer (orgaa, + 44 20 7946 0000)|Nein|Ja|
> |Louis Lahr|Nein|n/v|Ja|Nein|
> |Marcel Beauchamp|Ja|Service-Nummer (orgaa, TBA)|Nein|Ja|
> |Rachelle Cormier|Ja|Anonymisieren|Ja|Nein|
> |Isabell Potvin|Ja|Service-Nummer (orgaa, TBA)|Nein|Ja|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>Lizenzierung für Cloud-Sprachfunktionen

Audiokonferenz-und Telefon System sind Features in Office 365. Sie können separat als Add-on-Dienste für bestehende Kunden lizenziert werden, die über Office 365 E3-oder E1-Abonnement Pläne verfügen. Sie sind bereits im Rahmen des Office 365 E5-Abonnementplans enthalten.

Anrufpläne sind ein Add-on für das Telefonsystem Feature in Office 365, daher muss für die Verwendung von Anrufplänen eine Lizenz für das Telefonsystem aktiviert sein.

Zur Unterstützung von zusätzlichen Audiokonferenz-und Anrufplänen verwenden Sie Fälle (internationale Konferenz Auswahl, externe Anrufe nach dem Anruf Plan Minuten Zuweisungen sind erschöpft usw.), Sie können Kommunikationsguthaben für Ihre Organisation einrichten.

## <a name="licensing-for-calling-plans"></a>Lizenzierung für Anrufpläne

Wenn Ihre Organisation beabsichtigt, Microsoft als Telekommunikationsdienst Anbieter zu verwenden, müssen Sie die Add-ons für den Anrufplan abrufen, die den geschäftlichen Anforderungen Ihrer Benutzer entsprechen. Im Allgemeinen müssen nicht alle in einer Organisation Auslandsanrufe tätigen, sodass Sie die meisten Benutzer mit Lizenzen für den Inlandsanruf Plan bereitstellen können.

Es gibt zwei Arten von Lizenzen für den Anruf Plan:

-   Anrufplan für Inland

-   Anrufplan für Ausland und Inland

> [!NOTE]
> Was als "Domestic" für einen bestimmten Benutzer gilt, hängt vom zugewiesenen Office 365-Verwendungsstandort des Benutzers ab.

Jede Art des Anruf Plans bietet eine Zuteilung von Gesprächsminuten, die Benutzer pro Monat nutzen können, um Inlandsanrufe oder Auslandsgespräche zu führen. Der Plan für Inlandsanrufe kostet im Vergleich zum Auslands-und Inlandstarif einen niedrigeren Preis.

Die Flexibilität beim abonnieren und Zuweisen des am besten geeigneten Anruf Plan Typs für die geschäftlichen Anforderungen einzelner Benutzer hilft Ihrer Organisation, die Kosten für die Implementierung der Anrufpläne zu kontrollieren.

Für jeden Office 365-Mandanten werden die kombinierte Anzahl von Anruf Minuten nach Land oder Region und pro Anruf Plantyp gebündelt. Wenn die monatliche Gesprächsminuten Obergrenze für den Mandanten erreicht ist, wird der Anrufplan-Service (mit Ausnahme von Notrufen) für den Rest des Monats angehalten. Der Service für Anrufpläne wird am ersten Tag des nächsten Kalendermonats automatisch fortgesetzt.

Sie können Kommunikationsguthaben für ihre Organisationen einrichten, damit Benutzer ausgehende Anrufe tätigen können, nachdem die Zuweisung von Gesprächsminuten aufgebraucht ist, ohne bis zum Abrechnungszyklus des nächsten Monats warten zu müssen. Darüber hinaus bieten Kommunikationsguthaben Benutzern, die dem Inlandsanruf Plan zugewiesen sind, die Möglichkeit, Auslandsgespräche zu führen, die dann mit einem "Pay-per-Minute"-Modell berechnet werden.

Wenn Sie mehr über Telefon System-und Anrufpläne erfahren möchten, lesen Sie die folgenden Artikel:

-   [Telefonsystem](https://products.office.com/en-us/skype-for-business/phone-system)

-   [Anrufpläne](https://products.office.com/en-us/skype-for-business/calling-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Wenn Ihre Organisation nicht über die erforderliche Lizenz für das Telefonsystem verfügt, entscheiden Sie, ob Sie die Telefonsystem Lizenz erwerben möchten, indem Sie Ihre vorhandenen Office 365-Abonnements verstärken oder den Add-on-Dienst für das Telefonsystem erwerben.</li><li>Entscheiden Sie, welche Benutzer eine Lizenz für einen Inlandstarif benötigen und welche eine Lizenz für den nationalen und internationalen Tarif erfordern.</li><li>Entscheiden Sie, ob Sie Kommunikationsguthaben für Ihre Anruf Plan Implementierung benötigen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Abteilung, die Abteilung, die Office-oder die Benutzergruppen, denen Sie eine Telefon System Lizenz mit einem Inlandsanruf Plan oder einem Inlands-und Auslandstarif zuweisen.</li></ul>|

> [!TIP]
> Im folgenden Beispiel können Sie die Lizenzzuweisung für Telefonsysteme mit Anruf Plan Benutzern dokumentieren.
> 
> |Benutzer |Niederlassung |Office 365-Lizenz |Anrufplan |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Office 365 E5 |Anrufplan für Ausland und Inland |
> |Lidia Holloway |32 London Bridge Street |Office 365 E5 |Anrufplan für Inland |
> |Louis Lahr |32 London Bridge Street |Office 365 E5 |Anrufplan für Inland |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, Telefon System-Add-on |Anrufplan für Inland |
> |Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |Anrufplan für Ausland und Inland |
> |Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, Telefon System-Add-on |Anrufplan für Inland |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>Guthaben für Kommunikationen

Mithilfe von Kommunikationsguthaben können sich die Benutzer aus einer Audiokonferenz-Besprechung heraus wählen, um eine andere Person aus der ganzen Welt hinzuzufügen (außerhalb des Ursprungslandes des Besprechungsorganisators). Sie können Kommunikationsguthaben für Ihre Organisation einrichten, damit Benutzer ausgehende Anrufe tätigen können, nachdem Sie die Zuweisung von Gesprächsminuten aufgebraucht haben, ohne bis zum Abrechnungszyklus des nächsten Monats warten zu müssen. Darüber hinaus bieten Kommunikationsguthaben Benutzern, die dem Inlandsanruf Plan zugewiesen sind, die Möglichkeit, Auslandsanrufe zu tätigen, die dann mit einem "Pay-per-Minute"-Modell berechnet werden.

Bei der Implementierung von Kommunikationsguthaben müssen Sie zunächst überlegen, wie hoch der anfängliche Betrag für das Guthaben sein soll. Wenn Ihre Organisation die Verwendung der automatischen Aufladefunktion auswählt, ermitteln Sie den optimalen Betrag, indem Sie die tatsächliche Nutzung messen. Überwachen Sie die Nutzung ihrer Kommunikationsguthaben über einen Zeitraum, und passen Sie den aufladbaren Betrag nach Bedarf an.

Für Ihre Implementierung von Anrufplänen können Sie die Verwendung von Kommunikationsguthaben für einzelne Benutzer steuern, wodurch Sie sicherstellen können, dass Sie diese Guthaben in Übereinstimmung mit Ihren geschäftlichen Anforderungen zugewiesen haben.

Wenn Sie mehr über Kommunikationsguthaben erfahren möchten, lesen Sie [Was sind Kommunikationsguthaben?](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie Kommunikationsguthaben für Ihre Audiokonferenz-oder Anruf Plan Implementierung benötigen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Abteilung, Abteilung, Office oder Benutzergruppen, für die Sie Kommunikationsguthaben aktivieren möchten.</li><li>Dokumentieren Sie Ihren Plan für Kommunikations Kredite für Ihre Audiokonferenz-oder Anruf Plan Implementierung.</li></ul>|

> [!TIP]
> Verwenden Sie das folgende Beispiel, um die Zuordnungsliste für Kommunikations Kredite für Benutzer von Anrufplänen zu dokumentieren.
> 
> |Benutzer |Niederlassung |Anrufplan |Guthaben für Kommunikationen |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Anrufplan für Ausland und Inland |Aktiviert |
> |Lidia Holloway |32 London Bridge Street |Anrufplan für Inland |Deaktiviert |
> |Louis Lahr |32 London Bridge Street |Anrufplan für Inland |Aktiviert |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Anrufplan für Inland |Deaktiviert |
> |Rachelle Cormier |39 quai du Président Roosevelt |Anrufplan für Ausland und Inland |Aktiviert |
> |Isabell Potvin |39 quai du Président Roosevelt |Anrufplan für Inland |Deaktiviert |

<br>

> [!TIP]
> Ihre Kommunikations Kredite Planungs Nummern können wie im folgenden Beispiel dokumentiert werden.
>
> |         |         |
> |---------|---------|
> |Anfangsbetrag|1.000 US-Dollar|
> |Betrag für die Auslösung der Auffüllung|400 US-Dollar|
> |Höhe des Betrags für die automatische Auffüllung|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Verwalten von Cloud-VoIP-Telefonnummern

Wenn Sie das Telefon System durch die Einführung Ihres eigenen Telekommunikationsdienstanbieters implementieren, bleibt das Telefonnummern Management unverändert.

Für Audiokonferenz-und Anrufpläne Implementierungen können Sie auswählen, ob Sie neue Telefonnummern erwerben oder vorhandene Telefonnummern übertragen (portieren) möchten.

Damit Benutzer Telefonnummern so wählen können, wie Sie es gewohnt sind, beispielsweise das Auslassen von Ortsnetzen für Ortsgespräche, das Auslassen von Landesvorwahl für Inlandsanrufe oder das Verwenden von Kurzwahlnummern beim Durchführen einer Konferenz Auswahl oder dem Anrufen anderer Benutzer in der Organisation – Sie können einen benutzerdefinierten Wählplan konfigurieren und ihn Benutzern zuweisen.

## <a name="acquire-new-telephone-numbers"></a>Neue Telefonnummern erwerben

Die beiden Arten von Telefonnummern in Microsoft Cloud-VoIP-Lösungen sind:

-   Abonnenten Nummern (Benutzer), die Benutzern in Ihrer Organisation zugewiesen werden können.

-   Dienstnummern, die als gebührenpflichtige und gebührenfreie Servicenummern zur Verfügung stehen, die eine höhere gleichzeitige Anrufkapazität als Teilnehmer Nummern aufweisen und Diensten wie Audiokonferenzen, automatischen Telefonzentralen oder Anrufwarteschlangen zugewiesen werden können.

Weitere Informationen zu den Arten von Telefonnummern finden Sie unter [verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md).

Die Gesamtanzahl der Telefonnummern, die Sie erhalten können, hängt von der Art der Telefonnummer und der Anzahl der Lizenzen ab, die Sie Ihren Benutzern gekauft und zugewiesen haben.

Weitere Informationen zur Gesamtanzahl der Telefonnummern, die Sie erhalten können, finden Sie unter [wie viele Telefonnummern können Sie erhalten?](how-many-phone-numbers-can-you-get.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, welche Benutzer Standorte oder Büros neue Telefonnummern von Microsoft erwerben sollen.</li><li>Entscheiden Sie, welche Telefonnummern von Microsoft erworben werden sollen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer Standorte oder Niederlassungen, in denen neue Telefonnummern von Microsoft erworben werden.</li><li>Dokumentieren Sie die Art der Telefonnummern, die von Microsoft erworben werden sollen.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Übertragen vorhandener Telefonnummern

Wenn Ihre Organisation vorhandene Telefonnummern an Microsoft übertragen (oder portieren) möchte, können Sie dies tun, indem Sie eine Portierungs Auftragsanforderung an Microsoft übermitteln.

Sie können alle Ihre vorhandenen Telefonnummern gleichzeitig übertragen (Vollständiger Port) und – in einigen Märkten – eine Teilmenge ihrer vorhandenen Telefonnummern (teilweiser Port) übertragen. Ein partieller Port kann in Fällen nützlich sein, in denen Sie Ihre Benutzer nach und nach mit Anrufplänen auf das Telefon System verschieben möchten.

Eine einzelne Portierungs Reihenfolge kann die Telefonnummern nur an einen einzigen Telefonnummerntyp übertragen. Wenn Sie einige ihrer Telefonnummern als Teilnehmer Nummern und einige als Servicenummern übertragen müssen, empfehlen wir, dass Sie zuerst die Übertragung an Microsoft durchführen und dann die Konvertierung durchführen, sobald die Nummern in der Microsoft-Steuerung sind.

Als Alternative (wenn partieller Port unterstützt wird) können Sie mehrere Portanforderungen, jeweils eine Port Anforderung, senden. Dieser Alternative Ansatz verlängert jedoch ihren Vertrag mit Ihrem bestehenden Telekommunikationsdienstanbieter.

Das Portieren von Telefonnummern ist ein komplexes Thema und erfordert eine gründliche Planung, Koordination und angemessene Verwaltung der Erwartungen ihrer Stakeholder. Weitere Informationen finden Sie in den folgenden Artikeln:

-   [Übertragen von Telefonnummern an Office 365](transfer-phone-numbers-to-office-365.md)

-   [Übertragen von Telefonnummern – häufig gestellte Fragen](transferring-phone-numbers-common-questions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie sich für die Benutzer Standorte oder Offices, in denen vorhandene Telefonnummern an Microsoft übertragen werden.</li><li>Entscheiden Sie, welche Telefonnummern an Microsoft übertragen werden sollen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer Standorte oder Niederlassungen, an denen vorhandene Telefonnummern an Microsoft übertragen werden.</li><li>Dokumentieren Sie die Art der Telefonnummern, die an Microsoft übertragen werden sollen.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Wählpläne

Ein Wählplan in der Telefon System Funktion von Office 365 ist eine Reihe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise E. 164-Format) für die Anruf Autorisierung und das Anrufrouting übersetzen. Der Audiokonferenzdienst nutzt dieselben Funktionen, die vom Telefon System verwendet werden, um gewählte Telefonnummern in Szenarien für die Konferenz Auswahl zu übersetzen (zum Beispiel: einladen von Teilnehmern über PSTN und zurück wählen, "Anruf"-Funktion).

In der Telefon System Funktion von Office 365 gibt es zwei Arten von Wählplänen:

-   **Dienst Wähl Plan:** Dies ist der Standard-Wählplan, der auf Benutzer basierend auf dem Standort der Office 365-Nutzung angewendet wird und nicht geändert werden kann.

-   **Mandanten Wähl Plan:** Hierbei handelt es sich um einen anpassbaren Wählplan innerhalb eines Mandanten, der in zwei Arten unterteilt ist:

    -   **Mandanten – globaler Wählplan:** Die Wähleinstellungen, die für alle Benutzer im Mandanten gelten.

    -   **Mandanten-Benutzerwähleinstellungen:** Die Wähleinstellungen, die nur für bestimmte Benutzer gelten.

Der effektive Wählplan, der Benutzern zugewiesen ist, ist die Kombination aus dem Dienst Wählplan (basierend auf dem Office 365-Verwendungsstandort eines Benutzers) und dem Mandanten Wählplan (Dies kann entweder ein Mandanten globaler Wählplan oder ein Mandanten Wähl Plan sein).

![Tabelle zeigt drei Kombinationen von Wählplänen für Dienst-und Mandanten.] (media/audio_conferencing_image8.png "Tabelle zeigt drei Kombinationen von Wählplänen für Dienst-und Mandanten.")

> [!IMPORTANT]
> In jedem Mandanten-Wählplan können maximal 25 Normalisierungsregeln vorhanden sein. Daher ist es wichtig, zu vermeiden, dass Normalisierungsregeln dupliziert werden, die bereits im Rahmen des Dienst Wählplans verfügbar sind.

Weitere Informationen zu Wählplänen finden Sie unter [Was sind Wählpläne?](what-are-dial-plans.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Ihre Organisation angepasste Wählpläne erfordert (Geschäftsanforderungen, Adoptions Anforderungen usw.).</li><li>Falls zutreffend, entscheiden Sie den Bereich des Mandanten-Wählplans (Mandant – Global oder Mandanten-Benutzer), um Ihre Anforderungen für angepasste Wählpläne zu unterstützen.</li><li>Falls zutreffend, entscheiden Sie die Mandanten Wählpläne, die Sie erstellen, um die Benutzer Standorte oder Offices im Bereich für die Cloud-VoIP-Implementierung zu unterstützen.</li><li>Falls zutreffend, entscheiden Sie, für welche Benutzer ein benutzerdefinierter Wählplan erforderlich ist und welcher Mandanten-Wählplan für jeden Benutzer zugewiesen werden soll.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die angepassten Wählpläne und die zugehörigen Normalisierungsregeln, die als Teil der Cloud-VoIP-Implementierung konfiguriert werden sollen.</li><li>Dokumentieren Sie die Benutzer, denen ein benutzerdefinierter Wählplan zugewiesen werden soll, und den Mandanten Wähl Plan, der für jeden Benutzer zugewiesen werden soll.</li></ul>|

> [!TIP]
> Wenn Sie für Ihr Projekt gültig ist, können Sie die folgenden Vorlagen verwenden, um die Konfigurationen des Mandanten Wähl Plans zu dokumentieren.
> 
> |Name des Mandantenwählplans<br>_Beschreibung_  |Name der Normalisierungsregeln<br>_Beschreibung_  |Muster<br>Übersetzung<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_One Epping Road North Ryde, NSW, Wählplan für Australien_|**AU-NSW-NorthRyde-OER-Internal**<br>_Interne Nummer (x7000 - x7999) für One Epping Road-Niederlassung, North Ryde, NSW, Australien_|^ (7 \ d{3}) $<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalisierung für lokale Nummern für NSW, Australien_|^ ([2-9] \d{7}) $<br>+612$1<br>Falsch|
> ||**AU-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Australien_|^ (1 [38] \d{4,8}) \d * $<br>+61$1<br>Falsch|
> ||**AU-Service**<br>_Normalisierung für Servicenummern für Australien_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>Falsch|
> |**SG-Singapore-OMB**<br>_OMB Singapore, Wählplan für Singapur_|**SG-OMB-Internal**<br>_Interne Nummer (x8000 â € "x8999) für OMB Office, Singapur_|^ (8 \ d{3}) $<br>+656888$1<br>Wahr|
> ||**SG-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Singapur_|^ (1? 800 \ d{7}) \d * $<br>+65$1<br>Falsch|
> ||**SG-Service**<br>_Normalisierung für Servicenummern für Singapur_|^ (1 \ d{3,4}\|9 \ d{2}) $<br>$1<br>Falsch|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, Wählplan für Frankreich_|**FR-39qdPR-Internal**<br>_Interne Nummer (x7000 â € "x7999) für 39 Quai du President Roosevelt Office, Issy-les-Moulineaux, Frankreich_|^ (7 \ d{3}) $<br>+3319999$1<br>Wahr|
> ||**FR-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Frankreich_|^ 0? (80 \ d{7}) \d * $<br>+33$1<br>Falsch|
> ||**FR-Service**<br>_Normalisierung für Servicenummern für Frankreich_|^ (1 \ d{1,2}\|11 [68] \d{3}\|10 \ d{2}\|3 \ d{3}) $<br>$1<br>Falsch|

<br>

> [!TIP]
> Sie können die folgende Beispielvorlage nutzen, um Wählplanzuweisungen für Ihr Projekt zu dokumentieren:
>
> |Benutzer  |Niederlassung  |Typ des Wählplans  |Name des Wählplans  |
> |---------|---------|---------|---------|
> |Adele Vance|One Epping Road|Mandantenwählplan|AU-NSW-NorthRyde-OER|
> |Alex Wilber|One Epping Road|Mandantenwählplan|AU-NSW-NorthRyde-OER|
> |Ben Walters|One Epping Road|Mandantenwählplan|AU-NSW-NorthRyde-OER|
> |Christie Cline|One Marina Boulevard|Mandantenwählplan|SG-Singapore-OMB|
> |Debra Berger|One Marina Boulevard|Mandantenwählplan|SG-Singapore-OMB|
> |Lee Gu|One Marina Boulevard|Mandantenwählplan|SG-Singapore-OMB|
> |Emily Braun|32 London Bridge Street|Dienstwählplan|n/v|
> |Lidia Holloway|32 London Bridge Street|Dienstwählplan|n/v|
> |Louis Lahr|32 London Bridge Street|Dienstwählplan|n/v|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Dokumentdienst Entscheidungen 

Verwenden Sie die Informationen aus den vorherigen Abschnitten dieses Artikels, um Ihre Dienst Entscheidungen zu dokumentieren. Diese Dokumentation enthält im Allgemeinen die folgenden Hauptabschnitte:

-   Telefon System mit Anruf Plan Website-Aktivierungs Liste

-   Lizenzzuweisung für Telefon System mit Anruf Plan Benutzern

-   Zahlen für die Planung des Kommunikationsguthabens

-   Telefonnummern Erfassung, Telefonnummern und Notfall Standortdetails

-   Voicemail-Konfigurationsdetails

-   Konfigurationsdetails der Rufnummernanzeige

-   Mandantenwählpläne

-   Wählplanzuweisungen

<!--ENDOFSECTION-->