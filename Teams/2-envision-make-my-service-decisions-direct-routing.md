---
title: Treffe Phone System direkten Routing Service - Microsoft-Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 07/09/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Erfahren Sie mehr über die direkte Routing, Lizenzierung, und die Entscheidungen, die getroffen werden müssen.
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82063cc595694c2bf60c3f6af6ab550f647c05cd
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015325"
---
# <a name="make-my-service-decisions"></a>Meine Service treffe

Wenn Sie die technische Implementierung der Phone System direkten Routing ("Direktes Routing") planen, müssen Sie eine Reihe von vorausschauendes Service Entscheidungen besser Vorbereiten Ihrer Organisation zum Implementieren einer Lösung, die die geschäftlichen Anforderungen erfüllt, die Sie definiert haben.

## <a name="calling-in-teams"></a>Anrufe in Microsoft Teams

Mit Microsoft-Teams können Ihre Benutzer tätigen und Entgegennehmen von Anrufen zu oder aus dem öffentlichen Telefonfestnetz (PSTN). Die Benutzer können ihre eigenen dedizierten Telefonnummern nutzen für das tätigen und annehmen von nationalen und internationalen Telefonanrufe (einschließlich Voicemail) von der Clientanwendung Teams.

## <a name="direct-routing"></a>Direktes Routing

Teams benötigen können PSTN-Anrufe tätigen und empfangen diese Benutzer, für ein Feature in Office 365 Telefonsystem aktiviert werden soll.

Um die Konnektivität mit dem PSTN zu aktivieren, können direkten Routing Sie Personen in Ihrer Organisation die Möglichkeit zum tätigen und Entgegennehmen von Anrufen außerhalb der Organisation über das Telefonfestnetz.

Mit direktem Routing wird von einem Drittanbieter-Anbieter, erhalten die Möglichkeit, um den Vorgang fortzusetzen, verwenden Ihre vorhandenen PSTN-Trunks vom PSTN-Dienstanbieter bereitgestellt PSTN-Anbindung erleichtert. Auf diese Weise können für die Bereitstellung in Länder, in dem Telefonsystem mit Aufrufen plant ("aufrufen plant") nicht verfügbar sind, oder bei der Bereitstellung, bei denen eine vorhandene PSTN-Anbieter Servicevertrag verwaltet werden muss oder Interoperabilität mit bestimmten lokalen Systemen Erforderlich.

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>Verfügbarkeit von direkten Routing

Direktes Routing steht in einem Land, in dem Office 365 verfügbar ist. Eine Liste dieser Länder finden Sie unter [internationale Verfügbarkeit](https://products.office.com/business/international-availability) .

Kompilieren Sie nach Bestätigung, dass Ihre Organisation das Telefonsystem Feature abrufen kann die Liste der Standorte oder Büros, in dem Sie Telefonsystem, basierend auf der Liste der verfügbaren Ländern und Regionen implementieren können. Identifizieren Sie die Benutzer, die Sie zum Aktivieren von Aufrufen plant oder einer direkten Routing für jeden Standort haben Sie auch.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Identifizieren Sie die Standorte oder Büros, in denen Sie Telefonsystem implementieren können.<li>Identifizieren Sie die Benutzer, die Sie zum Aktivieren von Aufrufen plant oder einer direkten Routing für jeden Standort haben Sie beabsichtigen.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Standorte oder Büros für Telefonsystem aktiviert werden soll.<li>Dokumentieren Sie die Liste der Benutzer, die Sie zum Aktivieren von Aufrufen plant oder einer direkten Routing für jeden Standort haben Sie</ul>|

> [!TIP]
> Es folgt ein Beispiel für eine direkte Routing-Aktivierung Websiteliste.
> | **Office**                     | **Standort**   | **Phone-Dienst** |
> |--------------------------------|----------------|--------------------------|
> | One Epping Road                | Australien      | Legacy-PSTN-Dienst |
> | 100 Cyberport Road             | Hong Kong SAR (香港特別行政區)  | Telefon System direkten Routing |
> | One Marina Boulevard           | Singapur      | Telefon System direkten Routing |
> | 32 London Bridge Street        | Vereinigtes Königreich | Telefonsystem mit Anrufplänen |
> | 39 quai du Président Roosevelt | Frankreich         | Telefonsystem mit Anrufplänen |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Telefonnummern und Notfallstandorte

Telefonsystem bewirkt, dass alle Benutzer in Ihrer Organisation eine eindeutige direkte nach innen (DID) Telefonnummer gewählt haben. Mit direktem Routing werden die Telefonnummern und die Notdienste vom PSTN-Dienstanbieter bereitgestellt.

> [!NOTE]
> Mit direktem Routing können die Benutzer auch weiterhin mithilfe ihrer eigenen Telefonnummern, von dem PSTN-Dienstanbieter bereitgestellt.

> [!TIP]
> Die folgende Vorlage können Sie um das Telefon Zahlen Details zu dokumentieren.
>|Benutzer |Telefonnummer |
>|-----|-------------|
>|Emily Braun | + 44 23 4567 8901 |
>|Lidia Holloway | + 44 23 4567 89112 |
>|Louis Lahr | + 44 23 4567 8921 |
>|Marcel Beauchamp | TBA |
>|Rachelle Cormier | TBA |
>|Isabell Potvin | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Voicemail

Telefon System Voicemail, unterstützt von Azure Voicemail-Dienste unterstützt Voicemail bandbreitenbeschränkungen zu nur Exchange-Postfächern und Drittanbieter-e-Mail-Systemen nicht unterstützt.

Voicemail für Telefonsysteme umfasst Voicemailtranskription. Diese Funktion ist standardmäßig für alle Benutzer in Ihrer Organisation aktiviert. Ihre geschäftsanforderungen erfordern möglicherweise, Voicemail Lautschrift für bestimmte Benutzer oder alle Benutzer in der gesamten Organisation zu deaktivieren. Wenn Ihre Organisation aktiviert Voicemail Lautschrift behalten, müssen Sie auch bedenken, ob Voicemail Lautschrift Gotteslästerung Maskierung muss aktiviert sein. Einzelheiten finden Sie unter [Festlegen von Voicemail Richtlinien in Ihrer Organisation](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) .

Weitere Informationen zu Voicemail in einer Implementierung Telefonsystem finden Sie unter [Einrichten von Voicemail Telefonsystem](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie Telefonsystem Voicemail Ihrer Implementierung direkten Routing aktivieren.<li>Entscheiden Sie, ob Sie aktivieren oder Lautschrift Voicemail und Voicemail Lautschrift Gotteslästerung Maskierung in der gesamten Organisation oder für bestimmte Benutzer deaktivieren benötigen.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie gegebenenfalls die Entscheidungspunkte zur Unterstützung der Telefonsystem Voicemail.<li>Wenn Sie aktivieren oder Deaktivieren von Voicemail, dokumentieren Sie Lautschrift Voicemail und Voicemail Lautschrift Gotteslästerung Maskierung nur für bestimmte Benutzer dieser Liste von Benutzern.</ul>|

> [!TIP]
> Telefon System Voicemail Details für die Implementierung plant aufrufen können wie in der folgenden Tabelle dokumentiert werden.
> | **User**         | **Exchange-Postfach** | **Aktivieren Sie Voicemail?** | **Voicemail Lautschrift** | **Voicemail Lautschrift Gotteslästerung-Maskierung** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | Online               | Ja                   | Aktiviert                     | Aktiviert                                       |
> | Lidia Holloway   | Online               | Ja                   | Aktiviert                     | Deaktiviert                                      |
> | Louis Lahr       | Lokal          | Ja                   | Aktiviert                     | Aktiviert                                       |
> | Marcel Beauchamp | Lokal          | Ja                   | Deaktiviert                    | n/v                                           |
> | Rachelle Cormier | Online               | Ja                   | Deaktiviert                    | n/v                                           |
> | Isabell Potvin   | Lokal          | Ja                   | Deaktiviert                    | n/v                                           |

> [!NOTE]
> Teams und Voicemail, müssen Ihre Benutzer Exchange-Postfächer vorhanden sein. Einzelheiten finden Sie unter [wie Exchange- und Microsoft-Produktteams interagieren](https://docs.microsoft.com/microsoftteams/exchange-teams-interact) .

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>Lizenzierung für direkte Routing

Wenn Ihre Organisation direkten Routing verwenden, müssen Sie die erforderliche Lizenzen zu erhalten. Benutzer von direkten Routing müssen die folgenden Lizenzen im Office 365 zugewiesen:



-   Microsoft Telefonsystem

-   Microsoft Teams

-   Audiokonferenz

Audio Conferencing-Lizenz ist erforderlich für das Hinzufügen von externer Teilnehmern auf geplante Besprechungen von Ihnen Telefonverbindung oder durch die Einwahlnummer bereitstellen. Wenn Sie ein externer Teilnehmer zu gewählt wird, leitet der Audio-Konferenzdienst das Gespräch mithilfe der aufrufende Onlinefunktionen. Audio Conferencing-Lizenz ist optional und nur für Benutzer erforderlich, Konferenzen, die Audiokonferenz enthalten Teams, die organisieren sein wird.


> [!NOTE]
> Anzugebende gebührenfreie Konferenz Bridge Telefonnummern und zur Unterstützung von Konferenzen Anwahl auf internationale Telefonnummern, sollten Sie für Ihre Organisation [Communications haben](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) einrichten.

Audio-Konferenzen und Telefonsystem können separat als Add-on-Dienste für Kunden lizenziert werden, die über Office 365 E3 oder E1-Abonnementpläne verfügen; Sie sind bereits in der Office 365 E5-Abonnementplan enthalten.

> [!TIP]
> Sie können auch direkten Routing für die Benutzer verwenden, die für den Aufruf von plant aktiviert werden, wenn ihre Aufrufe von Drittanbieter-PBX-Anlagen routing. Weitere Informationen finden Sie unter [Lizenzierung und anderen Anforderungen von direkten Routing](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Wenn Ihre Organisation nicht über die erforderlichen Telefonsystem-Lizenz entscheiden, ob Sie die Lizenz Telefonsystem durch Ihre vorhandenen Office 365-Abonnements umsteigen oder durch Erwerb des Telefonsystem Add-on-Diensts erwerben werden.<li>Entscheiden Sie, ob Sie Communications haben für die Implementierung des direkten Routing benötigen.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Division, Abteilung, Office oder Benutzer Gruppen, die Sie eine Telefonsystem Lizenz zuweisen können.<li>Wenn Audiokonferenzen mit gebührenfreie Nummern im Gültigkeitsbereich befindet, dokumentieren Sie die Division, Abteilung, Office oder Benutzer Gruppen, die Sie Communications haben aktivieren können.</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Überlegungen zu Office 365

Jeder Benutzer, der für die direkte Weiterleitung aktiviert wird, muss in Office 365 verwaltet werden. Für hybridbereitstellungen mit lokalen Skype für Business Server oder Lync Server müssen Sie Benutzer in Skype für Business Online verschieben, bevor Sie diese zur Verwendung des direkten Routings mit Teams konfigurieren.

Alle Benutzer, die im Bereich der direkten Routing Implementierungen sind müssen für Teams aktiviert sein.

Office 365-Mandanten muss mit einer oder mehreren Domänen, aktiviert werden, da der Standardwert \*. Domäne "onmicrosoft.com" kann nicht mit direktem Routing verwendet werden. Weitere Informationen zu Domänen und Office 365-Mandanten finden Sie unter [Häufig gestellte Fragen zu Domänen](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob alle Benutzer zu Skype für Business Online zur Unterstützung von direkten Routing migriert werden müssen.<li>Identifizieren der Benutzer, die für Teams aktiviert werden müssen.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Liste der Benutzer, wechseln Sie zu Skype für Business Online und für Teams aktiviert werden müssen.</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>SBC-Aspekte

Sie müssen zertifizierte und unterstützte Session Border Controller (SBCs) verwenden, die mit dem Dienst direkten Routing PSTN-Anbindung für die Benutzer bereitstellen kombiniert werden müssen. Eine Liste mit zertifizierten SBCs finden Sie unter [Unterstützte Session Border Controller](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs).

Je nach Ihrer Umgebung, die Anzahl der Standorte und VoIP-Routinganforderungen müssen Sie möglicherweise mehrere SBCs zur Unterstützung der Benutzerbasis bereitstellen.

### <a name="sbc-domain-names"></a>SBC-Domänennamen

Jede SBC, die Sie mit direktem Routing Kopplung benötigen einen eindeutigen DNS-Namen. Die SBC-DNS-Namen müssen von einem der Domänennamen in Office 365-Mandanten registriert sein. Wenn es sich bei Ihrem Mandanten mehrere Domänennamen zugewiesen wurde, können Sie jeden dieser Domänennamen bei der Planung für Ihre SBCs DNS-Namen verwenden.

> [!IMPORTANT]
> Die Verwendung von *. onmicrosoft.com für die SBC-DNS-Namen ist nicht zulässig.

### <a name="certificates"></a>Zertifikate

Jede SBC mit direktem Routing bereitgestellt erfordert ein Zertifikat aus einer Liste der unterstützten Zertifizierungsstellen abgerufen. Das Zertifikat muss den SBC-DNS-Namen der Betreff, Alternativer Antragstellername oder Feldern Name enthalten.

> [!NOTE]
> Die Verwendung von Platzhalterzertifikate mit SBCs wird ebenfalls unterstützt.

Weitere Informationen und eine Liste der unterstützten Zertifizierungsstellen finden Sie unter [Öffentliche vertrauenswürdiges Zertifikat für den SBC](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc).


### <a name="sbc-ip-addresses-and-ports"></a>SBC-IP-Adressen und ports

Jede SBC muss mithilfe einer Office 365 Rechenzentren über öffentlichen IP-Adresse konfiguriert werden. Sie können auch die Netzwerkadressübersetzung (NAT) zum Veröffentlichen Ihrer SBCs in Office 365 Rechenzentren konfigurieren.

SBCs erfordern bidirektionale Konnektivität mit der Clouddienste für Signale und Medien kommunizieren. Von der *SIP-Proxy*-Komponente verarbeitet Signale und Medien erfolgt mithilfe des *Media-Prozessoren*.

Sie müssen bestimmte Portnummern für jede SBC für SIP-Signale und Medien definieren und Konfigurieren Ihrer Firewalls um bidirektionale Datenverkehr an diesen Ports und ihre zugeordneten IP-Adressen zu ermöglichen.

Weitere Informationen finden Sie unter [SIP-Signale: FQDNs und Firewallports](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports) und [Mediendatenverkehr: Port Bereiche](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges).


> [!NOTE]
> Es wird dringend empfohlen, einen Grenzwert für die maximale Anzahl gleichzeitiger Sitzungen für jede SBC, basierend auf dem SBC-Modell festlegen. Diese Grenze würde dann eine Benachrichtigung ausgelöst wird, wenn der SBC zur oder in der Nähe seine Kapazität ausgeführt wird.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, wo Sie sich befinden Sie SBCs bereitstellen können.<li>Entscheiden Sie einen DNS-Namen für jede SBC, wenn Sie planen, bereitstellen.<li>Basierend auf der Entscheidung SBC Domain Name, entscheiden Sie, ob Sie ein Platzhalterzertifikat zur Unterstützung aller SBCs in Ihrer Bereitstellung oder ein dedizierter Zertifikat pro SBC verwenden möchten.<li>Entscheiden Sie, welche öffentlichen Zertifizierungsstelle Sie die Zertifikate für Ihre SBCs aus erhalten werden.<li>Definieren Sie ein Paar der öffentlichen IP-Adresse/externer Port für jeden SBC, die Sie bereitstellen, und entscheiden, ob Sie die SBCs die öffentlichen IP-Adressen zuweisen oder NAT verwenden<li>Identifizieren Sie die maximale Anzahl von gleichzeitigen Sitzungen, die jede SBC unterstützt oder behandeln Sie können.<li>Entscheiden Sie, welche SBCs mithilfe der Medienumgehung konfiguriert werden.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie jede Entscheidung für die SBCs mithilfe der folgenden Beispieltabelle gemacht wird.</ul>|


> [!TIP]
> Verwenden Sie die folgende Vorlage, um die SBC-Details für die Bereitstellung direkter Routing zu dokumentieren.
> | **SBC-DNS-Name (FQDN)** | **SBC Hersteller und Modell** | **Zertifikat** | **Standort**  | **IP-Adresse** | **SIP-Signalisierung port** | **NAT?** | **Maximale gleichzeitige Sitzungen** | **Die medienumgehung aktiviert?** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC-"Europe.contoso.com" | TBD | \*. contoso.com | Amsterdam | TBD | TBD | Ja | TBD | Nein |
> | SBC-Asia.contoso.com | TBD | \*. contoso.com | Hong Kong SAR (香港特別行政區) | TBD | TBD | Nein | TBD | Ja |
> | SBC-Africa.contoso.com | TBD | \*. contoso.com | Johannesburg | TBD | TBD | Ja | TBD | Ja |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>VoIP-routing

Sie müssen Microsoft Telefonsystem zum Weiterleiten der Anrufe für den bestimmten SBCs für die direkte Weiterleitung konfigurieren. Sie können basierende auf VoIP-Routen konfigurieren:

-   Nummernmuster aufgerufen.

-   Wird aufgerufen, Nummernmuster + der Benutzer, der den Anruf tätigt.


Anrufrouting aus den folgenden Elementen besteht:

-   VoIP Routing-Richtlinie – Container für PSTN-Verwendungen; kann an einen Benutzer oder mehreren Benutzern zugewiesen werden

-   PSTN-Verwendungen – Container für VoIP-Routen und PSTN-Verwendungen; können in unterschiedlichen VoIP-Routing-Richtlinien gemeinsam genutzt werden

-   VoIP-Routen-Muster und einen Satz von Online PSTN-Gateways für Anrufe verwendet, bei denen das Muster entspricht der Rufnummer

-   Online PSTN-Gateway - Zeiger SBC, speichert auch die Konfiguration, die angewendet wird, wenn ein Anruf über den SBC, wie P-Asserted-Identity (PAI) nach vorne oder bevorzugte Codecs getätigt wird. VoIP-Routen können hinzugefügt werden

Sie können VoIP-Routen mit direktem Routing Koexistenz mit Aufrufen plant konfigurieren. Diese Konfiguration ermöglicht aufrufen plant, einige der Aufrufe der bestimmten SBCs durch direktes Routing weiterleiten.

> [!TIP]
> SBCs können als *aktiv* und *backup*festgelegt werden. Das bedeutet, dass der SBC, der für diese als aktiv konfiguriert ist, wenn die Anzahl Muster – oder-Nummer Muster + bestimmten Benutzer – ist nicht verfügbar, die Anrufe werden an eine Sicherung SBC weitergeleitet werden.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie die VoIP-routing-Richtlinien, PSTN-Verwendungen und VoIP-Routen, die Sie erstellen, Unterstützung von Benutzerspeicherorten oder Büros im Bereich für die direkte Routing-Implementierung.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie VoIP-Routingrichtlinien zurückgegeben, PSTN-Verwendungen und VoIP-Routen für Ihre Organisation.<li>Dokumentieren Sie die Benutzer für jede VoIP-routing-Richtlinie zugewiesen werden soll, die Sie definieren.</ul>|

> [!TIP]
> Verwenden Sie die folgende Vorlage, um die VoIP-Richtlinien für die Bereitstellung direkter Routing zu dokumentieren.
> | **PSTN-Verwendung** | **VoIP-route** | **Nummernmuster** | **Priorität** | **SBC** | **Beschreibung** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | UNS nur | "" Redmond "1" | \^\\+ 1 (425\|206) (\\d{7})\$ | 1 | sbc1.contoso.com sbc2.contoso.com | Aktive Route für gewählte Nummern +1 425 XXX XX XX oder +1 206 XXX XX XX |
> | UNS nur | "" Redmond "2" | \^\\+ 1 (425\|206) (\\d{7})\$ | 2 | SBC3.contoso.com sbc4.contoso.com | Backup Route für die gewählte Nummern +1 425 XXX XX XX oder +1 206 XXX XX XX |
> | UNS nur | "Andere + 1" | \^\\+ 1 (\\d{10})\$ | 3 | sbc5.contoso.com sbc6.contoso.com | Weiterleiten von zur gewählte Nummern + 1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX) |
> | International | International | \\+ d | 4 | sbc2.contoso.com sbc5.contoso.com | Route für alle Nummernmuster |

> [!IMPORTANT]
> Die PSTN-Verwendungen in VoIP-Routing-Richtlinien in der Reihenfolge angewendet, und wenn in der ersten Verwendung eine Übereinstimmung gefunden wird, werden nie andere Verwendungen ausgewertet.

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>Anruf- und Interop-Richtlinien

Direktes Routing wird nur mit Microsoft-Teams, unterstützt. Zum tätigen oder Entgegennehmen von Anrufen über direkte Weiterleitung PSTN, müssen Sie zum Konfigurieren der erforderlichen Richtlinien, um sicherzustellen, dass eingehende Anrufe in Teams empfangen werden.

> [!NOTE]
> Benutzer, die für den direkten Routing getätigt oder entgegengenommen kann nicht aktiviert werden direkte Weiterleiten von Anrufen mithilfe von Skype für Unternehmen und aus diesem Grund muss den Client Teams bereitgestellt.

Sie können die Benutzer zum Festlegen von Teams als bevorzugter Client für Anrufe anhand einer der beiden folgenden Methoden konfigurieren:

-   Konfigurieren des Benutzers nur Teams-Modus

-   Konfigurieren von Teams als bevorzugter Client aufrufende durch die TeamsCallingPolicy und die TeamsInteropPolicy zuweisen.

Weitere Informationen finden Sie unter [Microsoft-Teams festgelegt, als der bevorzugte Client für die Benutzer aufrufen](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Bestimmen der Methode, die Sie zum Festlegen des Teams als bevorzugter Client für Anrufe verwenden.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer mit Interop und Aufrufen von Richtlinien konfiguriert werden.</ul>|

> [!IMPORTANT]
> Wenn ein Benutzer für Teams-only-Modus konfiguriert ist, kann dieser Benutzer nicht mehr Skype für Unternehmen anmelden.

Um Ihre Benutzer finden Sie in der Registerkarte Anrufe im Client Teams vorhanden sind, müssen Sie aktivieren private auf Organisationsebene für den Mandanten aufrufen. Weitere Informationen zum Aktivieren von privaten Anrufe von finden Sie unter [Aktivieren für Microsoft-Teams aufrufen](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams) .


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Dokument Service Entscheidungen

Verwenden Sie die Informationen aus den vorherigen Abschnitten dieses Artikels, um Ihre Entscheidungen Service zu dokumentieren. Im Allgemeinen enthält diese Dokumentation die folgenden Hauptabschnitte:

-   Aktivierungsliste für Standorte mit dem Telefonsystem mit Anrufplänen

-   Details der Voicemailkonfiguration

-   Lizenz-Zuordnung für Benutzer Phone System direkten Routing

-   SBC-Konfigurationsdetails

-   VoIP-routing-Richtlinie und das routing von details

-   Details zu Interop und ein Aufruf von Richtlinien

<!--ENDOFSECTION-->
