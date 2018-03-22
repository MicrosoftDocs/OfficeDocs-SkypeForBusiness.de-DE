---
title: Make Phone System with Calling Plans service decisions - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Choose from calling plans and licensing, configure emergency locations and features like voicemail and caller ID, acquire or transfer phone numbers.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38e382992f3170f16718eac8d2c6f0902dbaff3b
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="make-my-service-decisions"></a>Make my service decisions

## <a name="calling-in-teams"></a>Anrufe in Microsoft Teams

With Microsoft Teams, your users can place and receive phone calls to or from the public switched telephone network (PSTN). Your users can use their own dedicated phone numbers for placing and receiving domestic and international phone calls from Teams client applications, with advanced features that include voicemail and emergency calling (enhanced 911).

> [!NOTE]
> The latest Teams roadmap for identifying Teams Audio Conferencing features in scope for your deployment can be found at <https://aka.ms/skype2teamsroadmap>.

## <a name="phone-system-in-teams"></a>Phone System in Teams

For Teams users to be able to place and receive PSTN calls, they need to be enabled for Phone System, a feature in Office 365.

To enable connectivity to the PSTN, your organization can use Microsoft as its telecommunications service provider. Eventually, you’ll also have the option to “bring your own” telecommunications service provider to enable connectivity to PSTN for Phone System.

> [!IMPORTANT]
> The ability to choose your own telecommunications service provider for Phone System will be available in the future. To learn more about the projected timeline, please review the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap).

## <a name="phone-system-with-calling-plans"></a>Telefonsystem mit Anrufplänen

To use Microsoft as your telecommunications service provider, you need to obtain Calling Plan licenses and assign them to your Phone System users.

There are two major types of calling plans:

-   Domestic calling plan

-   Domestic and international calling plan

Each type of calling plan allocates a certain number of call minutes per month to each user who has been assigned the license. When the call minutes allocation is exhausted, the user won’t be able to place outbound calls—except for emergency calls—until the next month’s billing cycle. If you want users to be able to continue to place outbound call even after they’ve exhausted their allocation of call minutes, or to let users who have a domestic calling plan place international calls, you can set up Communications Credits for your organization.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>Verfügbarkeit von Anrufplänen

Before you plan for the implementation of Calling Plans in Teams, verify that the Calling Plans service is available in your area by reviewing [Country and region availability for Audio Conferencing and Calling Plans](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

> [!IMPORTANT]
> Due to legal constraints, for Calling Plans to be available to multinational organizations, the contract for Office 365 subscriptions must be based in a country or region where the Calling Plans service is available, or where the Calling Plans service can be purchased.

After confirming that your organization can obtain the Calling Plans service, compile the list of user locations or offices where you’ll be implementing the Calling Plans service, based on the list of available countries and regions.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide which user locations or offices you’ll implement the Calling Plans service in.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Document the user locations or offices to be enabled for the Calling Plans service.</li></ul>|

> [!TIP]
> Below is an example of a Phone System with Calling Plans site enablement list.
>|Niederlassung   |Standort |Phone System service  |
>|---------|---------|---------|
>|One Epping Road|Australien|Legacy-PSTN-Dienst|
>|100 Cyberport Road|Hong Kong SAR (香港特別行政區)|Legacy-PSTN-Dienst|
>|One Marina Boulevard|Singapur|Legacy-PSTN-Dienst|
>|32 London Bridge Street|Vereinigtes Königreich|Telefonsystem mit Anrufplänen|
>|39 quai du Président Roosevelt|Frankreich|Telefonsystem mit Anrufplänen|

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Telefonnummern und Notfallstandorte

With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dialing (DID) phone number and a corresponding validated emergency address. Review [Manage cloud voice telephone numbers](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-phone-system#manage-cloud-voice-telephone-numbers) to plan the phone number acquisition for your Calling Plans implementation.

When you’re configuring phone numbers for Calling Plans, you must assign an emergency address to each telephone number before you assign the number to a user. Dieser Schritt ist für die Unterstützung von Notrufen erforderlich. The emergency address must be validated to ensure that it’s in the correct format to be used by emergency response services.

> [!IMPORTANT]
> Emergency Services calling operates differently in the Calling Plans service than in traditional telephone services. It’s important that you understand these differences and communicate them to all users. See [Emergency Calling Terms and Conditions](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions) for more details.

In addition to supplying a validated emergency address, you can define emergency locations and associate them with the validated emergency address to give a more exact location within an address. Ein Notfallstandort ist meist die Gebäudenummer, das Stockwerk, der Gebäudeflügel oder die Nummer des Zimmers, in dem sich der Benutzer befindet.

To learn more about emergency locations in relation to Calling Plans, review the following articles:

-   [Was sind Notfallstandorte, Notfalladressen und Anrufweiterleitung?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)

-   [Nutzungsbedingungen für Notrufe](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide the granularity of emergency location information to be collected for user locations or offices in scope for the Calling Plans implementation.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Document the detailed emergency address and emergency locations for each user location or office in scope for the Calling Plans implementation.</li></ul>|

> [!TIP]
> You can use the following template to document the details of phone numbers and emergency location details.
>|Benutzer |Emergency location and address |Phone number |
>|-----|-------------------------------|-------------|
>|Emily Braun |1034/32 London Bridge Street, London, SE1, Vereinigtes Königreich |+44 23 4567 8901 |
>|Lidia Holloway |1065/32 London Bridge Street, London, SE1, United Kingdom |+44 23 4567 89112 |
>|Louis Lahr |1023/32 London Bridge Street, London, SE1, Vereinigtes Königreich |+44 23 4567 8921 |
>|Marcel Beauchamp |07E15D/39 Quai du Président Roosevelt, 92130 Issy-les-Moulineaux, Frankreich | TBA |
>|Rachelle Cormier |07N15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |
>|Isabell Potvin |07F05E/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Voicemail

Phone System voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.

By default, Phone System voicemail works with Exchange Online; however it has a minimum supported Exchange on-premises version and deployment model to allow delivery of voicemail messages to user mailboxes in the on-premises Exchange deployment.

Voicemail für Telefonsysteme umfasst Voicemailtranskription. Diese Funktion ist standardmäßig für alle Benutzer in Ihrer Organisation aktiviert. Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization. If your organization decided to keep voicemail transcription enabled, you need to also consider whether voicemail transcription profanity masking need to be enabled. See [Setting voicemail policies in your organization](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) for more details.

>[!NOTE]
> Als Ausweichmechanismus kann Voicemail für Telefonsysteme Nachrichten über SMTP erneut senden. Das bedeutet, dass Benutzer mit einem Postfach in einem E-Mail-System eines Drittanbieters ihre Voicemailnachrichten erhalten. This mechanism doesn’t include guaranteed service uptime or other voicemail features, such as changing voicemail greeting.

For more information about voicemail in a Phone System implementation, see [Azure PBX voicemail support for Exchange Server](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#licensing-for-calling-plans).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide whether you’ll enable Phone System voicemail in your Calling Plans implementation.</li><li>If using Exchange on-premises and your existing deployment doesn’t meet your requirements to support Phone System voicemail, choose from the available options (upgrade and setup for Phone System voicemail support, migrate to Exchange Online, or leverage the fallback mechanism described earlier).</li><li>Decide whether you’ll enable or disable voicemail transcription and voicemail transcription profanity masking throughout the organization or for specific users.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>If applicable, document the Exchange decision points to support Phone System voicemail.</li><li>If you’ll enable/disable voicemail, voicemail transcription, and voicemail transcription profanity masking only for specific users, document that list of users.</li></ul>|

> [!TIP]
> Phone System voicemail details for the Phone System with Calling Plans implementation can be documented as the following.
>|Benutzer |Exchange mailbox |Enable voicemail? |Voicemail transcription |Voicemail transcription profanity masking |
>|------------------|------------------|-------------------|----------|----------|
>|Emily Braun      |Online      |Ja |Aktiviert |Aktiviert |
>|Lidia Holloway   |Online      |Ja |Aktiviert |Deaktiviert |
>|Louis Lahr       |Lokal |Ja |Aktiviert |Aktiviert |
>|Marcel Beauchamp |Lokal |Ja |Deaktiviert |n/v |
>|Rachelle Cormier |Online      |Ja |Deaktiviert |n/v |
>|Isabell Potvin   |Lokal |Ja |Deaktiviert |n/v |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>Anrufer-ID

Standardmäßig wird bei allen ausgehenden Anrufen die zugewiesene Telefonnummer als Anrufer-ID verwendet. Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte. In some cases, there are legitimate business requirements to mask the Caller ID to protect the identity of callers by using the office main line number—this is typically a service number serviced by the Auto Attendant configuration—as Caller ID, or to block Caller ID presentation altogether.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide whether Caller ID manipulation is required for your Calling Plans implementation.</li><li>If applicable, decide the types of Caller ID manipulation (mask with service number or anonymize) to be implemented.</li><li>If applicable, decide which users require Caller ID manipulation and the type of Caller ID manipulation to be assigned to each user.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer aus, um die Änderung von Anrufer-IDs und den Typ der Bearbeitung Zuweisen von Anrufer-ID zugewiesen werden.</li></ul>|

> [!TIP]
> The following is an example of Caller ID masking details documentation.
>|Benutzer  |Maskierung für ausgehende Anrufer-IDs aktivieren  |Art der Anrufer-ID-Maskierung  |Außerkraftsetzung durch Benutzer zulassen  | Maskierung für eingehende Anrufer-IDs aktivieren  |
>|---------|---------|---------|---------|---------|
>|Emily Braun|Nein|n/v|Ja|Nein|
>|Lidia Holloway|Ja|Servicenummer (OrgAA, +44 20 7946 0000)|Nein|Ja|
>|Louis Lahr|Nein|n/v|Ja|Nein|
>|Marcel Beauchamp|Ja|Servicenummer (OrgAA, TBA)|Nein|Ja|
>|Rachelle Cormier|Ja|Anonymisieren|Ja|Nein|
>|Isabell Potvin|Ja|Servicenummer (OrgAA, TBA)|Nein|Ja|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>Lizenzierung für Cloud-Sprachfunktionen

Audio-Konferenzen und Telefonsystem sind Funktionen in Office 365. Sie können separat als Add-on-Dienste für Kunden lizenziert werden, die über Office 365 E3 oder E1-Abonnementpläne verfügen; Sie sind bereits in der Office 365 E5-Abonnementplan enthalten.

Aufrufen von Plänen ist ein auszuführendes Add-on das Telefonsystem Feature in Office 365, müssen Sie ein Telefonsystem lizenziert verfügen plant aufrufen Verwendung aktiviert.

Unterstützung für zusätzliche Audiokonferenzen und Pläne aufrufen Anwendungsfälle (Internationale Konferenz Dial-Out-aufrufen nach Minute Zuweisungen aufrufen planen aufgebraucht sind externe und usw.), Sie können Communications haben für Ihre Organisation einrichten.

## <a name="licensing-for-calling-plans"></a>Lizenzierung für Anrufpläne

Wenn Ihre Organisation Microsoft verwenden möchte, wie Telekommunikation Internetdienstanbieter, müssen Sie planen aufrufen Add-ons zu Ihrer Benutzer geschäftlichen Anforderungen zu erhalten. Im Allgemeinen muss nicht allen Mitgliedern einer Organisation Ausland telefonieren, damit Sie die meisten Benutzer mit nationalen aufrufen planen Lizenzen bereitstellen können.

Es gibt zwei Arten von Lizenzen aufrufen planen:

-   Anrufplan für Inland

-   Anrufplan für Ausland und Inland

> [!NOTE]
> Was für einen bestimmten Benutzer als „Inland“ gilt, wird durch den zugewiesenen Office 365-Verwendungsstandort des Benutzers bestimmt.

Jeder Anrufplantyp umfasst ein zugewiesenes Minutenkontingent, das die Benutzer pro Monat für Inlands- oder Auslandsanrufe nutzen können. Die nationalen aufrufen planen Kosten, die kleiner im Vergleich zu den internationalen und nationalen aufrufen planen.

Die Flexibilität der abonnieren und Zuweisen von am besten geeigneten aufrufen planen Typ für einzelne Benutzer geschäftlichen Anforderungen kann Ihrer Organisation steuern, die Kosten für seine Implementierung plant aufrufen.

Alle Minutenkontingente der einzelnen Office 365-Mandanten werden in Pools für Länder bzw. Regionen und Anrufplantypen zusammengefasst. Wenn die Obergrenze des monatlichen Minutenkontingents für den Mandanten erreicht ist, wird der Anrufplandienst (mit Ausnahme von Notrufen) für den Rest des Monats ausgesetzt. Der Dienst aufrufen Pläne wird automatisch auf den ersten Tag des nächsten Monats fortgesetzt.

Sie können Communications haben für Ihre Organisationen durch Benutzer einrichten, ausgehende Anrufe tätigen, nach die Zuweisung von Minuten aufrufen, ohne warten, bis zum nächsten Monat Abrechnung Cycle erreicht ist. Darüber hinaus zugewiesen haben Communications bieten Benutzern die nationalen aufrufen planen die Möglichkeit, internationale Anrufe tätigen, die dann mithilfe eines Modells "Bezahlung pro Minute" berechnet werden.

Weitere Informationen zum Telefonsystem und Pläne aufrufen, überprüfen Sie in den folgenden Artikeln:

-   [Telefonsystem](https://products.office.com/skype-for-business/phone-system)

-   [Anrufpläne](https://products.office.com/skype-for-business/calling-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Wenn Ihre Organisation nicht über die erforderlichen Telefonsystem-Lizenz entscheiden, ob Sie die Lizenz Telefonsystem durch Ihre vorhandenen Office 365-Abonnements umsteigen oder durch Erwerb des Telefonsystem Add-on-Diensts erwerben werden.</li><li>Entscheiden Sie, welche Benutzer erfordern, dass eine Lizenz nationalen planen aufrufen und die in- und International aufrufen planen Lizenz erforderlich.</li><li>Entscheiden Sie, ob Sie Communications haben für die Implementierung des Plans aufrufen benötigen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Division, Abteilung, Office oder Benutzergruppen ordnen Sie einen Telefonsystem Lizenz mit nationalen aufrufen planen oder nationalen und internationalen aufrufen planen.</li></ul>|

> [!TIP]
> Im folgende Beispiel können Sie um die Lizenz-Zuordnung für Telefonsystem mit plant Aufrufen von Benutzern zu dokumentieren.
>|Benutzer |Niederlassung |Office 365-Lizenz |Plan aufrufen |
>|----|----|----|----|
>|Emily Braun |32 London Bridge Street |Office 365 E5 |Anrufplan für Ausland und Inland |
>|Lidia Holloway |32 London Bridge Street |Office 365 E5 |Plan für Inlandsanrufe |
>|Louis Lahr |32 London Bridge Street |Office 365 E5 |Plan für Inlandsanrufe |
>|Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3 Telefonsystem add-on |Plan für Inlandsanrufe |
>|Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |Anrufplan für Ausland und Inland |
>|Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, Phone System add-on |Plan für Inlandsanrufe |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>Guthaben für Kommunikationen

Verwenden von Communications haben, können die Benutzer aus einer Besprechung Audiokonferenzen um eine andere Person aus an einer beliebigen Stelle in der ganzen Welt (außerhalb der ursprünglichen Land des Besprechungsorganisators) hinzuzufügen anwählen. Sie können Communications haben für Ihre Organisation, um Benutzern zu ermöglichen einrichten, um ausgehende Anrufe tätigen, nachdem sie deren Zuordnung für den Aufruf Minuten, ohne dass Sie warten, bis der des nächsten Monats Abrechnung Cycle erreicht haben. Darüber hinaus übergeben Communications haben Benutzer die Möglichkeit für Auslandsgespräche, die dann mithilfe eines Modells "Bezahlung pro Minute" erhoben werden mit den nationalen aufrufen Plan zugewiesen.

Bei der Implementierung von Kommunikationsguthaben müssen Sie zunächst überlegen, wie hoch der anfängliche Betrag für das Guthaben sein soll. Wenn Ihre Organisation entscheidet, Auto-Ladeleuchte verwenden, müssen Sie den optimalen Umfang durch Messen der tatsächlichen Verwendung bestimmen. Überwachen Sie der Nutzung von Communications haben über einen Zeitraum, und passen Sie Ihre Ladeleuchte Betrag nach Bedarf.

Für die Implementierung des Plans aufrufen können Sie die Verwendung von Communications haben für jeden Benutzer einzeln, steuern, die welche wird sichergestellt, dass Sie diese Laufzeit Ausrichtung mit Ihrer geschäftlichen Anforderungen zugewiesen haben.

Weitere Informationen zum Communications haben, überprüfen Sie [Was sind Communications haben?](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Communications haben für die Implementierung des Audiokonferenzen oder plant aufrufen.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Document the division, department, office, or user groups you’ll enable Communications Credits for.</li><li>Dokumentieren Sie Ihre Kommunikation haben Plan für die Implementierung des Audiokonferenzen oder plant aufrufen.</li></ul>|

> [!TIP]
> Sie mithilfe des folgenden Beispiels, um die Liste der Communications haben Zuordnung für Benutzer plant aufrufen zu dokumentieren.
>|Benutzer |Niederlassung |Plan aufrufen |Guthaben für Kommunikationen |
>|----|----|----|----|
>|Emily Braun |32 London Bridge Street |Anrufplan für Ausland und Inland |Aktiviert |
>|Lidia Holloway |32 London Bridge Street |Plan für Inlandsanrufe |Deaktiviert |
>|Louis Lahr |32 London Bridge Street |Plan für Inlandsanrufe |Aktiviert |
>|Marcel Beauchamp |39 quai du Président Roosevelt |Plan für Inlandsanrufe |Deaktiviert |
>|Rachelle Cormier |39 quai du Président Roosevelt |Anrufplan für Ausland und Inland |Aktiviert |
>|Isabell Potvin |39 quai du Président Roosevelt |Plan für Inlandsanrufe |Deaktiviert |

<br>
> [!TIP]
> Your Communications Credits planning numbers can be documented as in the following example.
>|         |         |
>|---------|---------|
>|Anfangsbetrag|1.000 US-Dollar|
>|Betrag für die Auslösung der Auffüllung|400 US-Dollar|
>|Höhe des Betrags für die automatische Auffüllung|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Verwalten von Cloud-VoIP-Telefonnummern

Bei der Implementierung von Telefonsystem wider, da es Ihren eigenen Telekommunikation Dienstanbieter Anzahl Management Telefon als bleiben-ist.

Für Implementierungen Audiokonferenzen und Pläne aufrufen können Sie neue Telefonnummern zu erwerben oder Übertragen der vorhandene Telefonnummern (Port).

Benutzer können Zahlen Neuer Telefonanruf wie gewohnt sind – wie Vorwahlen für Ortsgespräche auslassen, Ländercode für Gespräche auslassen oder sogar mit Short Ziffer Wählvorgang beim Ausführen einer Dial-Out-Konferenz oder Aufrufen von anderen Benutzern in der Organisation – Sie können einen benutzerdefinierten Wählplan konfigurieren und Benutzern zuweisen.

## <a name="acquire-new-telephone-numbers"></a>Erwerben Sie neue Telefonnummern

Die zwei Arten von Telefonnummern in Microsoft Cloud VoIP-Lösungen sind:

-   Zahlen Abonnenten (Benutzer), die für Benutzer in Ihrer Organisation zugewiesen werden können.

-   Service, verfügbare Nummern als gebührenpflichtige oder gebührenfreie Service Zahlen, die höheren Kapazität für gleichzeitige Anrufe als Abonnenten Zahlen und Diensten wie etwa Audiokonferenzen, automatischen Telefonzentralen oder rufen Sie Warteschlangen zugewiesen werden können.

Weitere Informationen zu den Arten von Telefonnummern finden Sie unter [verschiedenen Arten von Telefonnummern für den Aufruf von plant verwendet](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

Die Gesamtzahl der Telefonnummern, die Sie herunterladen können, abhängig von den Typ der Telefonnummer und die Anzahl der Lizenzen, die Sie erworben und Ihren Benutzern zugewiesen haben.

Weitere Informationen über die Gesamtzahl der Telefonnummern, die Sie herunterladen können, finden Sie unter [wie viele Rufnummern erhalten Sie?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide the user locations or offices where new telephone numbers will be acquired from Microsoft.</li><li>Decide the type of telephone numbers to be acquired from Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Document the user locations or offices where new telephone numbers will be acquired from Microsoft.</li><li>Document the type of telephone numbers to be acquired from Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transfer existing telephone numbers

If your organization wants to transfer (or port) existing telephone numbers to Microsoft, you can do so by submitting a port order request to Microsoft.

Sie können alle Ihre vorhandenen Telefonnummern gleichzeitig (vollständige Port) übertragen und – in einigen Märkten – Sie können eine Teilmenge der vorhandenen Telefonnummern (teilweise Port) übertragen. Ein partieller Port kann in Fällen nützlich sein, auf dem Sie einfach Ihre Benutzer in Telefonsystem mit Aufrufen plant schrittweise verschieben möchten.

Eine einzelnen Port Reihenfolge kann nur die Telefonnummern an ein einzelnes Telefon übertragen. Wenn Sie einige Ihrer Telefonnummern als Abonnenten Zahlen und einige als Dienst Zahlen übertragen müssen, wird empfohlen, dass Sie zuerst die Weiterleitung an Microsoft abgeschlossen, und Sie dann die Konvertierung führen, sobald die Zahlen in der Kontrolle von Microsoft sind.

Als Alternative (wenn es sich um eine partielle Port unterstützt wird) können Sie mehrere Port-Anfragen, einen Port Anforderung zu einem Zeitpunkt übermitteln. Diese alternative Ansatz wird jedoch Ihrem Vertrag mit Ihren vorhandenen Telekommunikation Dienstanbieter verlängert.

Telefon Nummer Portieren ist ein komplexes Thema und erfordert gründliche Planung, Koordination und angemessen verwalten beteiligten erwartet. Finden Sie weitere Informationen finden Sie in den folgenden Artikeln:

-   [Übertragen von Telefonnummern zu Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Transferring phone numbers common questions](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide the user locations or offices where existing telephone numbers will be transferred to Microsoft.</li><li>Legen Sie die Art der Telefonnummern an Microsoft übertragen werden.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Document the user locations or offices where existing telephone numbers will be transferred to Microsoft.</li><li>Document the type of telephone numbers to be transferred to Microsoft.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Wählpläne

A Dial Plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing. The Audio Conferencing service leverages the same capabilities used by Phone System to translate dialed phone numbers in conference dial-out scenarios (for example, invite participants via PSTN and dial back, “call me” feature).

In das Telefonsystem Feature von Office 365 gibt es zwei Arten von Wählplänen:

-   **Service-Wählplan:** Dies ist die Standardeinstellung Wählplan, die auf Benutzer angewendet wird basierend auf deren Speicherort der Office 365-Verwendung und kann nicht geändert werden.

-   **Mandanten Wählplan:** Dies ist eine anpassbare Wählplan innerhalb eines Mandanten liegen weiter in zwei Typen unterteilt werden:

    -   **Mandanten globale Wählplan:** Die Wähleinstellungen, die für alle Benutzer in den Mandanten gilt.

    -   **Mandanten benutzerwähleinstellungen:** Die Wähleinstellungen, die nur auf bestimmte Benutzer gilt.

Die effektive Wähleinstellungen, die Benutzern zugewiesen ist eine Kombination aus dem Dienst Wählplan (basierend auf den Standort eines Benutzers Office 365 Verwendung) und Mandanten Wählplan (die ein Mandant globale Wählplan oder Mandanten benutzerwähleinstellungen sein können).

![Tabelle werden die drei Kombinationen Quality of Service und Mandanten Wählplänen.] (media/audio_conferencing_image8.png "Tabelle werden die drei Kombinationen Quality of Service und Mandanten Wählplänen.")

> [!IMPORTANT]
> There can be a maximum of 25 normalization rules in each tenant dial plan; therefore, it’s important to avoid duplicating normalization rules that are already available as part of the service dial plan.

For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide whether your organization requires customized dial plans (business requirements, adoption requirements, and so on).</li><li>If applicable, decide the scope of the tenant dial plan (tenant-global or tenant-user) to support your requirements for customized dial plans.</li><li>If applicable, decide the tenant dial plans that you’ll create to support user locations or offices in scope for the cloud voice implementation.</li><li>If applicable, decide which users require a customized dial plan and the tenant dial plan to be assigned for each user.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Document the customized dial plans and the associated normalization rules to be configured as part of cloud voice implementation.</li><li>Document the users to be assigned a customized dial plan and the tenant dial plan to be assigned for each user.</li></ul>|

> [!TIP]
> If it’s applicable to your project, you can use the following template to document the tenant dial plan configurations.
>|Name des Mandantenwählplans<br>_Beschreibung_  |Name der Normalisierungsregeln<br>_Beschreibung_  |Muster<br>Übersetzung<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_One Epping Road North Ryde, NSW, Wählplan für Australien_|**AU-NSW-NorthRyde-OER-Internal**<br>_Interne Nummer (x7000 - x7999) für One Epping Road-Niederlassung, North Ryde, NSW, Australien_|^(7\d{3})$<br>+6125550$1<br>Wahr|
>||**AU-NSW-Local**<br>_Normalisierung für lokale Nummern für NSW, Australien_|^([2-9]\d{7})$<br>+612$1<br>Falsch|
>||**AU-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Australien_|^(1[38]\d{4,8})\d*$<br>+61$1<br>Falsch|
>||**AU-Service**<br>_Normalisierung für Servicenummern für Australien_|^(000\|1[0125]\d{1,8})$<br>$1<br>Falsch|
>|**SG-Singapore-OMB**<br>_OMB Singapore, Wählplan für Singapur_|**SG-OMB-Internal**<br>_Internal number (x8000 â€“ x8999) for OMB office, Singapore_|^(8\d{3})$<br>+656888$1<br>Wahr|
>||**SG-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Singapur_|^(1?800\d{7})\d*$<br>+65$1<br>Falsch|
>||**SG-Service**<br>_Normalisierung für Servicenummern für Singapur_|^(1\d{3,4}\|9\d{2})$<br>$1<br>Falsch|
>|**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, Wählplan für Frankreich_|**FR-39qdPR-Internal**<br>_Internal number (x7000 â€“ x7999) for 39 quai du Président Roosevelt office, Issy-les-Moulineaux, France_|^(7\d{3})$<br>+3319999$1<br>Wahr|
>||**FR-TollFree**<br>_Normalisierung für gebührenfreie Nummern für Frankreich_|^0?(80\d{7})\d*$<br>+33$1<br>Falsch|
>||**FR-Service**<br>_Normalisierung für Servicenummern für Frankreich_|^(1\d{1,2}\|11[68]\d{3}\|10\d{2}\|3\d{3})$<br>$1<br>Falsch|

<br>
> [!TIP]
> Sie können die folgende Beispielvorlage nutzen, um Wählplanzuweisungen für Ihr Projekt zu dokumentieren:
>|Benutzer  |Niederlassung  |Typ des Wählplans  |Name des Wählplans  |
>|---------|---------|---------|---------|
>|Adele Vance|One Epping Road|Mandantenwählplan|AU-NSW-NorthRyde-OER|
>|Alex Wilber|One Epping Road|Mandantenwählplan|AU-NSW-NorthRyde-OER|
>|Ben Walters|One Epping Road|Mandantenwählplan|AU-NSW-NorthRyde-OER|
>|Christie Cline|One Marina Boulevard|Mandantenwählplan|SG-Singapore-OMB|
>|Debra Berger|One Marina Boulevard|Mandantenwählplan|SG-Singapore-OMB|
>|Lee Gu|One Marina Boulevard|Mandantenwählplan|SG-Singapore-OMB|
>|Emily Braun|32 London Bridge Street|Dienstwählplan|n/v|
>|Lidia Holloway|32 London Bridge Street|Dienstwählplan|n/v|
>|Louis Lahr|32 London Bridge Street|Dienstwählplan|n/v|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|Mandantenwählplan|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Document service decisions 

Use the information from the previous sections of this article to document your service decisions. In general, this documentation will contain the following main sections:

-   Aktivierungsliste für Standorte mit dem Telefonsystem mit Anrufplänen

-   Lizenzzuweisungen für Benutzer des Telefonsystems mit Anrufplänen

-   Zahlen für die Planung des Kommunikationsguthabens

-   Erwerb von Telefonnummern, Details zu Telefonnummern und Notfallstandorten

-   Details der Voicemailkonfiguration

-   Zuweisungen der Einstellungen für die Konferenzbrücke

-   Details der Konfiguration der Anrufer-ID-Maskierung

-   Mandantenwählpläne

-   Wählplanzuweisungen

<!--ENDOFSECTION-->