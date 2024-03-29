---
title: Kauf von Telefonen für Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 91f2d947-45fc-4fab-bd8b-2e313531c477
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 'Erfahren Sie, welche Telefone Skype for Business Polycom, HP und Mitel sowie die erforderlichen Lizenzen verwenden. '
ms.openlocfilehash: 4b4a5e48a531a694b006126221ddc7fcba40e1c3
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013149"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Kauf von Telefonen für Skype for Business Online

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

Skype for Business Online qualifiziert und unterstützt Festnetztelefone für Benutzer, die lieber auf herkömmliche Weise als über die Skype for Business-App telefonieren möchten. In diesem Thema werden die Telefone und Firmwareversionen behandelt, die für die Verwendung in Skype for Business Online unterstützt werden. Außerdem finden Sie weitere Informationen, die Sie beim Einrichten von Telefonen in Ihrer Organisation unterstützen sollen.

> [!NOTE]
> Skype For Business wird langsam durch Microsoft Teams als primäre Kommunikationsmethode in Microsoft 365 und Office 365.  Weitere Informationen finden Sie unter Eine neue Vision für [intelligente Kommunikation in Office 365](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/) Für weitere Informationen.
>
>Die neuesten Updates und aktuellsten Informationen zu unterstützten Geräten finden Sie auf den Microsoft Teams [für intelligente Kommunikation.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)
  
## <a name="supported-phones"></a>Unterstützte Telefone
  
Microsoft arbeitet eng mit Polycom, Yealink und AudioCodes zusammen, um über das Partner IP Telefon Program (PIP) für die Telefonsystem eine Vielzahl von Geräten zu entwickeln und zu zertifizieren.
  
Wenn Sie neue Telefone für Skype for Business bestellen, ist es wichtig, Telefone mit der *richtigen Produkt-ID zu kaufen.* Durch diese Produkt-IDs ist sichergestellt, dass Sie Telefone erhalten, in denen die qualifizierte Version von Skype for Business Online bereits installiert ist.
  
|Telefonpartner  |Skype for Business-spezifische Produkt-ID  |
|:-----|:-----|
|Polycom   |Produkt-ID -019   |
|Yealink   |SIP-TXXG Skype for Business Edition   |
|AudioCodes   |UCXXXHDEG (SfB)   |
   
Weitere Informationen zu Polycom-Telefonen finden Sie unter [Polydokumentationsbibliothek.](https://documents.polycom.com/category/voice)
  
Weitere Informationen zu Yealink-Telefonen finden Sie unter Skype for Business [IP-Telefone.](http://www.yealink.com/products_list_10.html#filter2)
  
Weitere Details zu AudioCodes-Telefonen finden Sie unter [IP-Telefone für Skype for Business](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> Lync Telefon Edition wird von Skype for Business Online, jedoch nicht von Lync Microsoft Teams. Mainstream-Support für die LPE-Plattform endete bis zum 10. April 2014 und wurde bis zum 11. April 2023 erweitert, um den Produktsupportlebenszyklus von Lync Server 2013 zu nutzen. Details [zum Lebenszyklus von](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) LPE finden Sie unter Microsoft Product Lifecycle. LPE CAP-Modelle werden von der Online-Skype for Business unterstützt.
>
> Später in diesem Jahr Office 365 version von TLS, die älter als 1.2 ist, nicht mehr unterstützt. Da das zugrunde liegende Betriebssystem von LPE TLS 1.2 nicht unterstützt, wird LPE nicht mehr für die Verbindung zu Office 365 unterstützt. Weitere Informationen finden Sie unter Vorbereiten der obligatorischen Verwendung [von TLS 1.2 in Office 365.](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="supported-firmware"></a>Unterstützte Firmware

Dies ist die Mindestsoftwareversion, die für unterstützte Telefone erforderlich ist, um mit Telefonsystem:
  

|Telefontyp |Mindestfirmwareversion |Veröffentlichungsdatum |
|:-----|:-----|:-----|
|Optimiert (Lync Phone Edition)   |4.0.7577.4463   |Mai 2015   |
|Zertifizierte Polycom VVX-Serie   |5.4.0A   |Dezember 2015   |
|Yealink   |X.8.1.52   |Februar 2017   |
|AudioCodes   |3.0.0.459.1   |Dezember 2016   |

Weitere Informationen zu aktuellen zertifizierten Firmwareversionen finden Sie unter Skype for Business [IP-Telefone.](../../../SfbPartnerCertification/certification/devices-ip-phones.md)

> [!NOTE]
> Telefone mit Lync Phone Edition (LPE), die Sie für die lokale Bereitstellung eingerichtet haben, müssen auf die Mindestversion oder höher der notwendigen Firmware aktualisiert werden, bevor die entsprechenden Benutzer zu Skype for Business Online transferiert werden. Wenn Sie Ihre Benutzer von lokal auf Skype for Business Online transferieren, bevor Sie die Firmware auf den Telefonen aktualisieren, können diese Telefone nicht mit Skype for Business Online verbunden werden. 
  
## <a name="required-licenses"></a>Erforderliche Lizenzen

Für Skype for Business Online benötigen Sie neben den Benutzerlizenzen keine weiteren Microsoft-Lizenzen. Weitere Informationen zu den erforderlichen Benutzerlizenzen finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
Für Open SIP-Firmware und Skype for Business-zertifizierte Firmware können unterschiedliche Lizenzierungsmodelle der Hersteller gelten. Wenn Sie ein zertifiziertes Modell mit Open SIP-Firmware einem anderen Zweck zuführen, müssen Sie die Firmware-Lizenzanforderungen des Herstellers überprüfen.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype for Business Online-Featuresatz für verbundene Telefone

Eine vollständige Aufstellung der Gerätefeatures und -funktionen finden Sie in den Benutzerhandbüchern der Hersteller.
  

|Feature  |Polycom 3PIP  |Yealink 3PIP |AudioCodes 3PIP |LPE |
|:-----|:-----|:-----|:-----|:-----|
|Anmelden mit Benutzeranmeldeinformationen   |Ja  |Ja   |Ja   |Nein   |
|Anmelden über PC (Kopplung), nur Windows   |Ja   |Ja   |Ja   |Ja   |
|Anmelden über Webanmeldung  <br/>  <br/> **Hinweis:** Überprüfen Sie die Unterstützungsmatrix im Bereitstellungshandbuch.  |Ja   |Ja   |Ja   |Nein   |
|Teilnehmen an einer Besprechung mit Einfachklick   |Ja   |Ja   |Ja   |Ja   |
|Wählen durch Klicken (Kopplung)   |Ja   |Ja   |Ja   |Ja > |
|Besprechungssteuerelemente   |Ja   |Ja   |Ja   |Ja   |
|Visuelle Mailbox   |Ja   |Ja   |Ja   |Ja   |
|Telefonsperre   |Ja   |Ja   |Ja   |Ja   |
|Geräteupdate   |Ja   |Ja   |Ja   |Ja   |
|In-Band-Bereitstellung   |Ja   |Ja   |Ja   |Ja   |
|QoE   |Ja   |Ja   |Ja   |Nein  |
|Protokoll-Upload  <br/> <br/> **Hinweis:** Derzeit werden alle Protokolle nur in das Microsoft Support-Team hochgeladen. Kundenzugriff auf Telefonprotokolle ist noch nicht verfügbar.           |Ja   |Ja   |Ja   |Ja   |
|Moderne Authentifizierung   |Ja   |Ja   |Ja   |Nein   |
|Mehrere Notrufnummern   |Ja   |Nein   |Nein   |Ja   |
|Integration von Exchange-Kalendern*   |Ja   |Ja   |Ja   |Ja  <br/> <br/> **Hinweis:** Erfordert PC-Tethering           |
|Integration von Anwesenheitsfunktionen   |Ja   |Ja   |Ja   |Ja   |
|Unternehmensverzeichnis   |Ja   |Ja   |Ja   |Ja   |
|Delegierung   |Ja   |Ja   |Ja   |Nein   |
|Integration von Kontaktbildern   |Nein   |Ja  |Nein   |Ja   |


     
> [!NOTE]
> CX 600 oder andere Aries-Telefone unterstützen keine mehrstufige Authentifizierung (Multifactor Authentication, MFA). Wenn Sie MFA erzwingen, können sich diese Geräte nicht anmelden. Diese Geräte dürfen nur die Organisations-ID für die Authentifizierung verwenden.
 
## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?
Schrittweise Anweisungen finden Sie unter [Bereitstellen von Telefonen für Skype for Business Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Verwandte Themen
[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Das Telefonsystem bietet Ihnen Folgendes](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
