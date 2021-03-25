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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 'Erfahren Sie, welche Telefone mit Skype for Business von Polycom, HP und Mitel sowie den erforderlichen Lizenzen verwendet werden. '
ms.openlocfilehash: 03f9a6d5cf3ac496c4828825e68f068ec98a14ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106441"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Kauf von Telefonen für Skype for Business Online

Skype for Business Online qualifiziert und unterstützt Festnetztelefone für Benutzer, die lieber auf herkömmliche Weise als über die Skype for Business-App telefonieren möchten. In diesem Thema werden die Telefone und Firmwareversionen behandelt, die für die Verwendung in Skype for Business Online unterstützt werden. Außerdem finden Sie weitere Informationen, die Sie beim Einrichten von Telefonen in Ihrer Organisation unterstützen sollen.

> [!NOTE]
> Skype For Business wird langsam durch Microsoft Teams als primäre Kommunikationsmethode in Microsoft 365 und Office 365 ersetzt.  Weitere Informationen finden Sie unter Eine neue Vision für intelligente Kommunikation [in Office 365.](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/)
>
>Informationen zu den neuesten Updates und den aktuellsten Informationen auf unterstützten Geräten finden Sie unter [Microsoft Teams-Geräte für intelligente Kommunikation.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)
  
## <a name="supported-phones"></a>Unterstützte Telefone
  
Microsoft arbeitet eng mit Polycom, Yealink und AudioCodes zusammen, um eine Vielzahl von Geräten über das Partner IP Phone Program (PIP) für das Telefonsystem zu entwickeln und zu zertifizieren.
  
Bei der Bestellung neuer Telefone für Skype for Business ist es wichtig, Telefone mit der richtigen *Produkt-ID zu kaufen.* Durch diese Produkt-IDs ist sichergestellt, dass Sie Telefone erhalten, in denen die qualifizierte Version von Skype for Business Online bereits installiert ist.
  
|||
|:-----|:-----|
|**Telefonpartner** <br/> |**Skype for Business-spezifische Produkt-ID** <br/> |
|Polycom  <br/> |Produkt-ID -019  <br/> |
|Yealink  <br/> |SIP-TXXG Skype for Business Edition  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Weitere Informationen zu Polycom-Telefonen finden Sie unter [Polydokumentationsbibliothek](https://documents.polycom.com/category/voice).
  
Weitere Informationen zu Yealink-Telefonen finden Sie unter [Skype for Business-IP-Telefone.](http://www.yealink.com/products_list_10.html#filter2)
  
Weitere Details zu AudioCodes-Telefonen finden Sie unter [IP-Telefone für Skype for Business](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> Lync Phone Edition wird von Skype for Business Online, aber nicht von Microsoft Teams unterstützt. Der Mainstreamsupport für die LPE-Plattform endete bis zum 10.04.2014, mit verlängerter Unterstützung bis zum 11.04.2023, um sich an den Produktsupportlebenszyklus von Lync Server 2013 auszurichten. Details [zum LPE-Lebenszyklus](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) finden Sie unter Microsoft Product Lifecycle. LPE-CAP-Modelle werden von Skype for Business Online nicht unterstützt.
>
> Später in diesem Jahr unterstützt Office 365 keine Version von TLS, die älter als 1.2 ist. Da das zugrunde liegende Betriebssystem von LPE TLS 1.2 nicht unterstützt, wird LPE nicht mehr unterstützt, um eine Verbindung mit Office 365 herzustellen. Weitere Informationen finden Sie unter Vorbereiten der obligatorischen Verwendung [von TLS 1.2 in Office 365.](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="supported-firmware"></a>Unterstützte Firmware

Dies ist die mindeste Softwareversion, die für unterstützte Telefone für die Arbeit mit dem Telefonsystem erforderlich ist:
  
||||
|:-----|:-----|:-----|
|**Telefontyp** <br/> |**Mindestfirmwareversion** <br/> |**Veröffentlichungsdatum** <br/> |
|Optimiert (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Mai 2015  <br/> |
|Zertifizierte Polycom VVX-Serie  <br/> |5.4.0A  <br/> |Dezember 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Februar 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Dezember 2016  <br/> |

Weitere Informationen zu aktuellen zertifizierten Firmwareversionen finden Sie unter [Skype for Business IP Phones](../../../SfbPartnerCertification/certification/devices-ip-phones.md).

> [!NOTE]
> Telefone mit Lync Phone Edition (LPE), die Sie für die lokale Bereitstellung eingerichtet haben, müssen auf die Mindestversion oder höher der notwendigen Firmware aktualisiert werden, bevor die entsprechenden Benutzer zu Skype for Business Online transferiert werden. Wenn Sie Ihre Benutzer von lokal auf Skype for Business Online transferieren, bevor Sie die Firmware auf den Telefonen aktualisieren, können diese Telefone nicht mit Skype for Business Online verbunden werden. 
  
## <a name="required-licenses"></a>Erforderliche Lizenzen

Für Skype for Business Online benötigen Sie neben den Benutzerlizenzen keine weiteren Microsoft-Lizenzen. Weitere Informationen zu den erforderlichen Benutzerlizenzen finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
Für Open SIP-Firmware und Skype for Business-zertifizierte Firmware können unterschiedliche Lizenzierungsmodelle der Hersteller gelten. Wenn Sie ein zertifiziertes Modell mit Open SIP-Firmware einem anderen Zweck zuführen, müssen Sie die Firmware-Lizenzanforderungen des Herstellers überprüfen.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Featuresatz für verbundene Skype for Business Online-Telefone

Eine vollständige Aufstellung der Gerätefeatures und -funktionen finden Sie in den Benutzerhandbüchern der Hersteller.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Funktion** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**AudioCodes 3PIP** <br/> |**LPE** <br/> |
|Anmelden mit Benutzeranmeldeinformationen  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|Anmelden über PC (Kopplung), nur Windows  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Anmelden über Webanmeldung  <br/>  <br/> **Hinweis:** Überprüfen Sie die Unterstützungsmatrix im Bereitstellungshandbuch.           |Ja  <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|Teilnehmen an einer Besprechung mit Einfachklick  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Wählen durch Klicken (Kopplung)  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Besprechungssteuerelemente  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Visuelle Mailbox  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Telefonsperre  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Geräteupdate  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|In-Band-Bereitstellung  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|QoE  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|Protokoll-Upload  <br/> <br/> **Hinweis:** Derzeit werden alle Protokolle nur in das #A0 hochgeladen. Kundenzugriff auf Telefonprotokolle ist noch nicht verfügbar.           |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Moderne Authentifizierung  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|Mehrere Notrufnummern  <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |Ja  <br/> |
|Integration von Exchange-Kalendern*  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> <br/> **Hinweis:** Erfordert PC-Tethering           |
|Integration von Anwesenheitsfunktionen  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Unternehmensverzeichnis  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Delegierung  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|Integration von Kontaktbildern  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |Ja  <br/> |
||||||

     
> [!NOTE]
> CX 600 oder andere Widdertelefone unterstützen keine mehrstufige Authentifizierung (MFA). Wenn Sie MFA erzwingen, können sich diese Geräte nicht anmelden. Diese Geräte dürfen nur die Organisations-ID für die Authentifizierung verwenden.
 
## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?
Schrittweise Anweisungen finden Sie unter [Bereitstellen von Telefonen für Skype for Business Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Verwandte Themen
[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Das Telefonsystem bietet Ihnen Folgendes](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
