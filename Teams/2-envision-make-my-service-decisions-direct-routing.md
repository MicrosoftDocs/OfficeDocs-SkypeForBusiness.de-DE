---
title: Treffen von Entscheidungen für das Telefonsystem mit direktem Routing – Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Informieren Sie sich über direktes Routing, Lizenzierung und die Entscheidungen, die getroffen werden müssen.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa92fcf7c30ecd8dfcecb84c3463f70ba13ee7ef
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240807"
---
# <a name="make-my-service-decisions"></a>Meine Dienst Entscheidungen treffen

Zur Planung der technischen Implementierung des direkten Routings von Telefonsystemen ("Direct Routing") müssen Sie eine Reihe von Dienst Entscheidungen vorzeitig treffen, um Ihre Organisation besser auf die Implementierung einer Lösung vorzubereiten, die die von Ihnen definierten geschäftlichen Anforderungen erfüllt.

## <a name="calling-in-teams"></a>Anrufe in Teams

Mit Microsoft Teams können Ihre Benutzer Telefonanrufe in das öffentlich geschaltete Telefonnetz (PSTN) tätigen und empfangen. Ihre Benutzer können Ihre eigenen dedizierten Telefonnummern für das tätigen und empfangen von Inlands-und Auslandsgesprächen (einschließlich Voicemail) über die Clientanwendung für Teams verwenden.

## <a name="direct-routing"></a>Direktes Routing

Damit Teams-Benutzer PSTN-Anrufe tätigen und empfangen können, müssen Sie für das Telefon System, ein Feature in Office 365, aktiviert sein.

Um die Verbindung mit dem PSTN zu aktivieren, können Sie mithilfe des direkten Routings Personen in Ihrer Organisation die Möglichkeit geben, Telefonanrufe außerhalb der Organisation über das PSTN zu tätigen und zu empfangen.

Beim direkten Routing wird die PSTN-Konnektivität von einem Drittanbieter unterstützt, sodass Sie weiterhin Ihre vorhandenen PSTN-Stämme verwenden können, die von Ihrem PSTN-Dienstanbieter bereitgestellt werden. Dies ermöglicht die Bereitstellung in Ländern, in denen Telefonsysteme mit Anrufplänen ("Anrufpläne") nicht verfügbar sind, oder in Bereitstellungen, bei denen ein vorhandener PSTN-Dienstanbieter Vertrag gewartet werden muss oder die Interoperabilität mit bestimmten lokalen Systemen erfolgt. Erforderlich.

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>Verfügbarkeit des direkten Routings

Direct Routing ist in jedem Land verfügbar, in dem Office 365 verfügbar ist. Eine Liste dieser Länder finden Sie unter [internationale Verfügbarkeit](https://products.office.com/business/international-availability) .

Nachdem Sie bestätigt haben, dass Ihre Organisation das Telefonsystem Feature erhalten kann, kompilieren Sie die Liste der Benutzer Standorte oder Büros, in denen Sie das Telefonsystem implementieren werden, basierend auf der Liste der verfügbaren Länder und Regionen. Identifizieren Sie auch die Benutzer, für die Sie Anrufpläne oder direktes Routing für jeden Standort aktivieren möchten.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Ermitteln Sie die Benutzer Standorte oder Offices, in denen Sie das Telefon System implementieren.<li>Ermitteln Sie die Benutzer, für die Sie Anrufpläne oder das direkte Routing für jeden Standort aktivieren möchten.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer Standorte oder Offices, die für das Telefon System aktiviert werden sollen.<li>Dokumentieren Sie die Liste der Benutzer, für die Sie Anrufpläne oder das direkte Routing für jeden Standort aktivieren möchten.</ul>|

> [!TIP]
> Nachfolgend finden Sie ein Beispiel für eine direkte Routing Site Enablement-Liste.
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

Für das Telefon System müssen alle Benutzer in Ihrer Organisation über eine eindeutige direkte Durchwahl (DID) Telefonnummer verfügen. Bei der direkten Weiterleitung werden die Telefonnummern und die Notfalldienste von Ihrem PSTN-Dienstanbieter bereitgestellt.

> [!NOTE]
> Beim direkten Routing können Ihre Benutzer weiterhin ihre eigenen Telefonnummern verwenden, die vom PSTN-Dienstanbieter bereitgestellt werden.
> 
> [!TIP]
> Mit der folgenden Vorlage können Sie die Details zu den Telefonnummern dokumentieren.
> 
> |User |Telefonnummer |
> |-----|-------------|
> |Emily Braun | + 44 23 4567 8901 |
> |Lidia Holloway | + 44 23 4567 89112 |
> |Louis Lahr | + 44 23 4567 8921 |
> |Marcel Beauchamp | TBA |
> |Rachelle Cormier | TBA |
> |Isabell Potvin | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Voicemail

Cloud Voicemail, powered by Azure Voicemail Services, unterstützt Voicemail-Einzahlungen nur für Exchange-Postfächer und unterstützt keine e-Mail-Systeme von Drittanbietern.

Cloud Voicemail umfasst Voicemail-Transkription, die standardmäßig für alle Benutzer in Ihrer Organisation aktiviert ist. Für Ihre geschäftlichen Anforderungen müssen Sie möglicherweise die Voicemail-Transkription für bestimmte Benutzer oder alle in der Organisation deaktivieren. Wenn Ihre Organisation entschieden hat, die Voicemail-Transkription zu aktivieren, müssen Sie auch berücksichtigen, ob die Maskierung von Voicemail-Transkriptions Obszönitäten aktiviert sein muss. Weitere Informationen finden Sie unter [Festlegen von Voicemail-Richtlinien in Ihrer Organisation](set-up-phone-system-voicemail.md) .

Weitere Informationen zu Voicemail in einer Telefon System Implementierung finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie Cloud Voicemail in ihrer direkten Routing Implementierung aktivieren möchten.<li>Entscheiden Sie, ob Sie Voicemail-Transkriptions-und Voicemail-Transkriptions-Obszönitäten in der gesamten Organisation oder für bestimmte Benutzer aktivieren oder deaktivieren möchten.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie gegebenenfalls die Entscheidungspunkte, um die Cloud-Voicemail zu unterstützen.<li>Wenn Sie Voicemail, Voicemail-Transkription und Voicemail-Transkription für anstößige Ausdrücke nur für bestimmte Benutzer aktivieren oder deaktivieren möchten, dokumentieren Sie die Liste der Benutzer.</ul>|

> [!TIP]
> Details zur Cloud-Voicemail für die Implementierung von Anrufplänen können wie in der folgenden Tabelle dokumentiert werden.
> 
> | **Benutzer**         | **Exchange-Postfach** | **Voicemail aktivieren?** | **Voicemail-Transkription** | **Voicemail-Transkriptions-Obszönität-Maskierung** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | Online               | Ja                   | Aktiviert                     | Aktiviert                                       |
> | Lidia Holloway   | Online               | Ja                   | Aktiviert                     | Deaktiviert                                      |
> | Louis Lahr       | Lokal          | Ja                   | Aktiviert                     | Aktiviert                                       |
> | Marcel Beauchamp | Lokal          | Ja                   | Deaktiviert                    | Nicht zutreffend                                           |
> | Rachelle Cormier | Online               | Ja                   | Deaktiviert                    | Nicht zutreffend                                           |
> | Isabell Potvin   | Lokal          | Ja                   | Deaktiviert                    | Nicht zutreffend                                           |
> 
> [!NOTE]
> Damit Sie Teams und Voicemail verwenden können, müssen Ihre Benutzer über Exchange-Postfächer verfügen. Weitere Informationen finden Sie unter [Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md) .

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>Lizenzierung für direktes Routing

Wenn Ihre Organisation beabsichtigen soll, Direktes Routing zu verwenden, müssen Sie die erforderlichen Lizenzen anfordern. Benutzern des direkten Routings muss in Office 365 die folgenden Lizenzen zugewiesen sein:

-   Microsoft Phone-System

-   Microsoft Teams

-   Audiokonferenzen

Für das Hinzufügen von externen Teilnehmern zu geplanten Besprechungen ist eine Audiokonferenz-Lizenz erforderlich, indem Sie entweder zu Ihnen wählen oder die Einwahlnummer angeben. Wenn ein externer Teilnehmer angewählt wird, platziert der Audiokonferenzdienst den Anruf über Online-Anruffunktionen. Audiokonferenz-Lizenzen sind optional und nur für Benutzer erforderlich, die Team Konferenzen organisieren, die Audiokonferenzen umfassen.


> [!NOTE]
> Wenn Sie gebührenfreie Konferenz Brücken-Telefonnummern bereitstellen und Konferenzanrufe an internationale Telefonnummern unterstützen möchten, sollten Sie [Kommunikationsguthaben](what-are-communications-credits.md) für Ihre Organisation einrichten.

Audiokonferenz-und Telefonsysteme können separat als Add-on-Dienste für bestehende Kunden lizenziert werden, die über Office 365 E3-oder E1-Abonnement Pläne verfügen. Sie sind bereits im Rahmen des Office 365 E5-Abonnementplans enthalten.

> [!TIP]
> Sie können auch die direkte Weiterleitung für die Benutzer verwenden, die für die Anrufpläne aktiviert sind, wenn Sie Ihre Anrufe an PBX-Anlagen von Drittanbietern weiterleiten. Weitere Informationen finden Sie unter [Lizenzierung und andere voraus](direct-routing-plan.md#licensing-and-other-requirements)setzungen für die direkte Weiterleitung.


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Wenn Ihre Organisation nicht über die erforderliche Lizenz für das Telefonsystem verfügt, entscheiden Sie, ob Sie die Telefonsystem Lizenz erwerben möchten, indem Sie Ihre vorhandenen Office 365-Abonnements verstärken oder den Add-on-Dienst für das Telefonsystem erwerben.<li>Entscheiden Sie, ob Sie Kommunikationsguthaben für Ihre direkte Routing Implementierung benötigen.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Abteilung, Abteilung, Office oder Benutzergruppen, denen Sie eine Telefon System Lizenz zuweisen.<li>Wenn Audiokonferenzen mit gebührenfreien Nummern im Umfang sind, dokumentieren Sie die Abteilung, Abteilung, Office oder Benutzergruppen, damit Sie Kommunikationsguthaben aktivieren können.</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Office 365-Überlegungen

Jeder Benutzer, der für die direkte Weiterleitung aktiviert werden soll, muss in Office 365 zu finden sein. Für hybridbereitstellungen mit lokalem Skype for Business-Server oder lync Server müssen Sie Benutzer in Skype for Business Online verschieben, bevor Sie Sie für die direkte Weiterleitung mit Teams konfigurieren.

Alle Benutzer, die im Bereich der direkten Routing Implementierungen sind, müssen für Teams aktiviert sein.

Ihr Office 365-Mandant muss mit einer oder mehreren Domänen aktiviert sein, da die \*standardmäßige onmicrosoft.com-Domäne nicht für die direkte Weiterleitung verwendet werden kann. Weitere Informationen zu Domänen und Office 365-Mandanten finden Sie unter [häufig gestellte Fragen zu Domains](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Benutzer zu Skype for Business Online migriert werden müssen, um die direkte Weiterleitung zu unterstützen.<li>Identifizieren Sie die Benutzer, die für Teams aktiviert werden müssen.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Liste der Benutzer, die zu Skype for Business Online wechseln und für Teams aktiviert werden müssen.</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>SBC-Überlegungen

Sie müssen zertifizierte und unterstützte Session Border Controller (SBCS) verwenden, die mit dem Direct Routing-Dienst gekoppelt werden müssen, um die PSTN-Konnektivität für Ihre Benutzer bereitzustellen. Eine Liste der zertifizierten SBCS finden Sie unter [unterstützte Session Border Controllers](direct-routing-plan.md#supported-session-border-controllers-sbcs).

Je nach Umgebung, Anzahl der Speicherorte und Anforderungen an das VoIP-Routing müssen Sie möglicherweise mehrere SBCS bereitstellen, um die Benutzerbasis zu unterstützen.

### <a name="sbc-domain-names"></a>SBC-Domänennamen

Jeder SBC, den Sie mit Direct Routing koppeln, muss einen eindeutigen DNS-Namen haben. Die SBC-DNS-Namen müssen aus einem der im Office 365-Mandanten registrierten Domänennamen sein. Wenn Ihrem Mandanten mehrere Domänennamen zugewiesen wurden, können Sie bei der Planung der DNS-Namen Ihrer SBCS einen dieser Domänennamen verwenden.

> [!IMPORTANT]
> Die Verwendung von *. onmicrosoft.com für den SBC-DNS-Namen ist nicht zulässig.

### <a name="certificates"></a>Zertifikate

Für jeden SBC, der mit Direct Routing bereitgestellt wird, muss ein Zertifikat aus einer Liste unterstützter Zertifizierungsstellen abgerufen werden. Das Zertifikat muss den SBC-DNS-Namen in den Feldern Betreff, Subject Alternate Name oder Common Name aufweisen.

> [!NOTE]
> Die Verwendung von Platzhalterzertifikaten mit SBCS wird ebenfalls unterstützt.

Weitere Informationen und eine Liste der unterstützten Zertifizierungsstellen finden Sie unter [Public Trusted Certificate für den SBC](direct-routing-plan.md#public-trusted-certificate-for-the-sbc).


### <a name="sbc-ip-addresses-and-ports"></a>SBC-IP-Adressen und-Ports

Jeder SBC muss mithilfe einer öffentlichen IP-Adresse konfiguriert werden, auf die von Office 365-Rechenzentren aus zugegriffen werden kann. Sie können auch Netzwerkadressübersetzung (Network Address Translation, NAT) konfigurieren, um Ihre SBCS in Office 365-Rechenzentren zu veröffentlichen.

SBCS erfordern bidirektionale Konnektivität für die Kommunikation mit den Cloud-Diensten für Signalisierungen und Medien. Das signalisieren wird von der Komponente *SIP Proxy*verarbeitet, und die Medien werden von den *Medien Prozessoren*verarbeitet.

Sie müssen für jeden SBC für SIP-Signalisierungs-und medienspezifische Portnummern definieren und ihre Firewalls so konfigurieren, dass bidirektionaler Datenverkehr zu diesen Ports und den zugehörigen IP-Adressen zugelassen wird.

Weitere Informationen finden Sie unter [SIP-Signalisierungen: FQDNs und Firewall-Ports](direct-routing-plan.md#sip-signaling-fqdns-and-firewall-ports) und [Mediendatenverkehr: Port Bereiche](direct-routing-plan.md#media-traffic-port-ranges).


> [!NOTE]
> Es wird dringend empfohlen, für jeden SBC basierend auf dem SBC-Modell eine maximale Anzahl von gleichzeitigen Sitzungen festzulegen. Dieser Grenzwert löst dann eine Benachrichtigung aus, wenn der SBC an seiner Kapazität oder in seiner Nähe ausgeführt wird.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, an welchen Speicherorten Sie SBCS bereitstellen möchten.<li>Entscheiden Sie sich für jeden SBC, den Sie bereitstellen möchten, um einen DNS-Namen.<li>Entscheiden Sie auf der Grundlage der SBC-Domänennamen Entscheidung, ob Sie ein Platzhalterzertifikat zur Unterstützung aller SBCS in Ihrer Bereitstellung oder eines dedizierten Zertifikats pro SBC verwenden möchten.<li>Entscheiden Sie, von welcher öffentlichen Zertifizierungsstelle Sie die Zertifikate für Ihre SBCS erhalten möchten.<li>Definieren Sie für jeden bereitzustellenden SBC ein öffentliches IP-Adresse/Port-Paar, und entscheiden Sie, ob Sie die öffentlichen IP-Adressen dem SBCS zuweisen oder NAT verwenden möchten.<li>Ermitteln Sie die maximale Anzahl von gleichzeitigen Sitzungen, die jeder SBC unterstützt oder verarbeiten kann.<li>Entscheiden Sie, welche SBCS mithilfe der medienumgehung konfiguriert werden.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die einzelnen Entscheidungen, die für die SBCS getroffen werden, mithilfe der folgenden Beispieltabelle.</ul>|


> [!TIP]
> Verwenden Sie die folgende Vorlage, um die SBC-Details für Ihre direkte Routing Bereitstellung zu dokumentieren.
> 
> | **SBC-DNS-Name (FQDN)** | **SBC-Marke und-Modell** | **Zertifikat** | **Standort**  | **IP-Adresse** | **SIP-Signalisierungs-Port** | **NAT?** | **Maximale Anzahl von gleichzeitigen Sitzungen** | **Medienumgehung aktiviert?** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC-Europe.contoso.com | TBD | \*. contoso.com | Amsterdam | TBD | TBD | Ja | TBD | Nein |
> | SBC-Asia.contoso.com | TBD | \*. contoso.com | Hong Kong SAR (香港特別行政區) | TBD | TBD | Nein | TBD | Ja |
> | SBC-Africa.contoso.com | TBD | \*. contoso.com | Johannesburg | TBD | TBD | Ja | TBD | Ja |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>VoIP-Routing

Sie müssen Microsoft Phone System so konfigurieren, dass die Anrufe an den jeweiligen SBCS für die direkte Weiterleitung weitergeleitet werden. Sie können VoIP-Routen basierend auf folgenden Einstellungen konfigurieren:

-   Als Zahlenmuster bezeichnet.

-   So genannte Zahlenmuster + der Benutzer, der den Anruf annimmt.


Das Anrufrouting besteht aus den folgenden Elementen:

-   VoIP-Routing Richtlinie – Container für PSTN-Nutzungen; kann einem Benutzer oder mehreren Benutzern zugewiesen werden

-   PSTN-Nutzungen – Container für sprach Routen und PSTN-Nutzungen; kann in verschiedenen VoIP-Routing Richtlinien freigegeben werden

-   VoIP-Routen – Nummernmuster und Satz von Online-PSTN-Gateways für Anrufe, bei denen die Rufnummer mit dem Muster übereinstimmt

-   Online-PSTN-Gateway – Zeiger auf SBC, speichert auch die Konfiguration, die angewendet wird, wenn ein Anruf über den SBC erfolgt, wie z. b. Weiterleiten von P-Asserted-Identity (Pai) oder bevorzugten Codecs; kann zu VoIP-Routen hinzugefügt werden

Sie können Ihre VoIP-Routen mit direktem Routing so konfigurieren, dass Sie mit Anrufplänen koexistieren. Mit dieser Konfiguration können Anrufpläne einige der Anrufe an den jeweiligen SBCS mithilfe von Direct Routing weiterleiten.

> [!TIP]
> SBCS kann als *aktiv* und als *Backup*festgelegt werden. Das bedeutet, wenn der SBC, der als aktiv für dieses Zahlenmuster konfiguriert ist – oder Zahlenmuster + bestimmter Benutzer – nicht verfügbar ist, werden die Anrufe an eine Sicherungs-SBC weitergeleitet.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie sich für die VoIP-Routing Richtlinien, die PSTN-Nutzung und die VoIP-Routen, die Sie erstellen, um die Benutzer Standorte oder-Büros im Bereich für die direkte Routingimplementierung zu unterstützen.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie VoIP-Routing Richtlinien, PSTN-Nutzungen und VoIP-Routen für Ihre Organisation.<li>Dokumentieren Sie die Benutzer, die für jede von Ihnen definierte VoIP-Routing Richtlinie zugewiesen werden sollen.</ul>|

> [!TIP]
> Verwenden Sie die folgende Vorlage, um die VoIP-Richtlinien für Ihre direkte Routing Bereitstellung zu dokumentieren.
> 
> | **PSTN-Verwendung** | **VoIP-Route** | **Nummernmuster** | **Priorität** | **Sbchttps** | **Beschreibung** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | Nur USA | "Redmond 1" | \^\\+ 1 (425\|206) (\\d{7})\$ | 1 | sbc1.contoso.com sbc2.contoso.com | Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX |
> | Nur USA | "Redmond 2" | \^\\+ 1 (425\|206) (\\d{7})\$ | 2 | sbc3.contoso.com sbc4.contoso.com | Sicherungs Route für genannte Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX |
> | Nur USA | "Andere + 1" | \^\\+ 1 (\\d{10})\$ | 3 | sbc5.contoso.com sbc6.contoso.com | Route für angerufene Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX) |
> | International | International | \\d + | 4 | sbc2.contoso.com sbc5.contoso.com | Route für beliebige Zahlenmuster |
> 
> [!IMPORTANT]
> Die PSTN-Nutzungen in VoIP-Routing Richtlinien werden in der angegebenen Reihenfolge angewendet, und wenn bei der ersten Verwendung eine Übereinstimmung gefunden wird, werden andere Verwendungen nie ausgewertet.

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>Anruf-und Interop-Richtlinien

Das direkte Routing wird nur von Microsoft Teams unterstützt. Sie müssen die erforderlichen Richtlinien konfigurieren, um sicherzustellen, dass eingehende Anrufe in Teams empfangen werden, um PSTN-Anrufe über direkte Weiterleitung zu tätigen oder zu empfangen.

> [!NOTE]
> Benutzer, die für die direkte Weiterleitung aktiviert sind, können mit Skype for Business keine direkten Routing Anrufe tätigen oder empfangen und müssen daher den Team-Client bereitstellen.

Sie können Ihre Benutzer so konfigurieren, dass Teams als bevorzugter Client für Anrufe mit einer der beiden folgenden Methoden festzulegen:

-   Konfigurieren des Benutzers für den Modus "nur für Teams"

-   Konfigurieren Sie Teams als bevorzugten Anruf Client, indem Sie TeamsCallingPolicy und TeamsInteropPolicy zuweisen.

Weitere Informationen finden Sie unter [Einrichten von Microsoft Teams als bevorzugter Anruf Client für Benutzer](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkte|<ul><li>Entscheiden Sie, welchen Ansatz Sie verwenden werden, um Teams als bevorzugten Client für Anrufe festzulegen.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächste Schritte|<ul><li>Dokumentieren Sie die Benutzer, die mit Interop-und Anruf Richtlinien konfiguriert werden sollen.</ul>|

> [!IMPORTANT]
> Wenn ein Benutzer für den Modus "nur für Teams" konfiguriert ist, kann sich dieser Benutzer nicht mehr bei Skype for Business anmelden.

Damit Ihre Benutzer die Registerkarte "Anrufe" im Team-Client sehen können, müssen Sie private Anrufe auf organisatorischer Ebene für den Mandanten aktivieren. Weitere Informationen zum Aktivieren privater Anrufe finden Sie unter [Aktivieren von Anrufen für Microsoft Teams](direct-routing-configure.md) .


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Dokumentdienst Entscheidungen

Verwenden Sie die Informationen aus den vorherigen Abschnitten dieses Artikels, um Ihre Dienst Entscheidungen zu dokumentieren. Diese Dokumentation enthält im Allgemeinen die folgenden Hauptabschnitte:

-   Telefon System mit Anruf Plan Website-Aktivierungs Liste

-   Voicemail-Konfigurationsdetails

-   Lizenzzuweisung für Benutzer des direkten Routings von Telefonsystemen

-   SBC-Konfigurationsdetails

-   VoIP-Routing Richtlinie und Routing Details

-   Details zu Interop-und Anruf Richtlinien

<!--ENDOFSECTION-->
