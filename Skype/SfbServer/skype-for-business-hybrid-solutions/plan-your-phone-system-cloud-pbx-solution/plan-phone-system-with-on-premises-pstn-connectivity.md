---
title: Planen eines Telefonsystems mit lokaler Festnetzanbindung in Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Erfahren Sie mehr über die Planungsüberlegungen für Telefonsystem (Cloud PBX) mit lokaler PSTN-Anbindung.
ms.openlocfilehash: efaba8aae1175db526d9607e2eb8c7e382dbaf1f95ec948a0c34758a055d5c1e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339871"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planen eines Telefonsystems mit lokaler Festnetzanbindung in Skype for Business Server

> [!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, danach ist der Dienst nicht mehr verfügbar.  Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.

Erfahren Sie mehr über die Planungsüberlegungen für Telefonsystem (Cloud PBX) mit lokaler PSTN-Anbindung.

Dieser Inhalt ist relevant, wenn Sie bereits Skype for Business Server oder lync Server 2013 lokal bereitgestellt haben. Weitere Szenarien finden Sie unter [Microsoft-Telefonielösungen.](/microsoftteams/cloud-voice-landing-page)

 Telefonsystem mit lokaler FESTNETZ-Anbindung können Sie Telefonsystem (Cloud PBX)-Funktionen für Ihre Benutzer nutzen. Dies kann bei den folgenden Szenarien hilfreich sein:

- Einige Ihrer Skype for Business Benutzer werden lokal verwaltet, andere in Skype for Business Online. Sie können jetzt Telefonsystem Funktionen und Features für Ihre Benutzer aktivieren, die in Skype for Business Online verwaltet werden, aber weiterhin die lokale PSTN-Konnektivität verwenden.

- Sie verfügen über eine lokale Bereitstellung, und Sie möchten einige oder alle Ihre Benutzer in Skype for Business Online verschieben, aber weiterhin die lokale PSTN-Konnektivität verwenden.

    > [!IMPORTANT]
    > Um Benutzer erfolgreich für Telefonsystem mit lokaler PSTN-Konnektivität zu aktivieren, muss sich ihre SIP-Adresse in Ihrer eigenen Domäne befinden. Die Verwendung der Standarddomäne für Microsoft 365 oder Office 365 onmicrosoft.com wird nicht unterstützt. 

Weitere Informationen zu Telefonsystem, einschließlich Lizenzierung und Plänen, finden Sie unter [PSTN-Anrufpläne für Skype for Business.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)

## <a name="feature-comparison"></a>Featurevergleich

Cloud PBX mit lokaler PSTN-Konnektivität bietet nicht den gleichen Featuresatz wie eine vollständig lokale Enterprise-VoIP Lösung. Wenn Sie entscheiden möchten, ob Cloud PBX mit lokaler PSTN-Konnektivität den richtigen Featuresatz für Ihre Organisation bereitstellt, lesen [Sie Folgendes, was Sie mit Cloud PBX erhalten.](/microsoftteams/here-s-what-you-get-with-phone-system?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2ftoc.json)

## <a name="benefits-and-planning-considerations"></a>Vorteile und Planungsüberlegungen

> [!CAUTION]
> Lync Telefon Edition-Geräte MÜSSEN vor dem Wechsel zu Skype for Business Online auf die mindestens erforderliche Firmware in Ihrer lokalen Umgebung aktualisiert werden.
Wenn Sie Ihre Benutzer vor dem Aktualisieren der Firmware von der lokalen in die Onlineumgebung verschieben, können Benutzer keine Verbindung mit ihren Telefonen herstellen. Um dieses Problem zu beheben, müssen Benutzer zurück in die lokale Umgebung verschoben werden, damit ihre Telefone auf die mindeste Firmware aktualisiert werden. VERSUCHEN SIE NICHT, AUF DIE MINDESTFIRMWARE ZU AKTUALISIEREN ODER DAS TELEFON ENDGÜLTIG ZURÜCKZUSETZEN, BEVOR SIE DEN BENUTZER ZURÜCK ZU IHRER LOKALEN UMGEBUNG VERSCHIEBEN.
Wenn ein hard reset durchgeführt wird, während das Gerät nicht mindestens Firmware ist, verwendet es standardmäßig die PIN-Authentifizierung, die in Skype for Business Online nicht unterstützt wird. Weitere Informationen finden Sie unter ["Abrufen von Telefonen für Skype for Business Online".](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)

Durch die Bereitstellung von Telefonsystem mit lokaler PSTN-Anbindung können Sie Ihre Benutzer über Skype for Business Online in Ihrem eigenen Tempo in die Cloud verschieben und gleichzeitig ihre lokale FESTNETZ-Anbindung beibehalten. Wenn Sie über eine Nebenstellenanlage verfügen, verwenden Sie diese weiterhin, um PSTN-Konnektivität für die Benutzer bereitzustellen, die Sie in die Cloud verschieben. Sobald ein Benutzer zu Skype for Business Online und Telefonsystem verschoben wird, funktioniert sein älteres PbX-Telefon nicht mehr, aber seine Telefonnummer wird an einen der Skype for Business Clients für PCs oder Smartphones sowie Skype for Business kompatible Schreibtischtelefone weitergeleitet. Nach der Portieren können Telefonsystem Benutzer und Ältere PbX-Benutzer sich gegenseitig normal anrufen sowie PSTN-Anrufe über ihre normale Telefonnummer tätigen/empfangen.

Möglicherweise verfügen Sie über ein benutzerdefiniertes Feature oder ein Haupt-Add-On für Ihre ältere Nebenstellenanlage, z. B. ein Callcenter. Wenn das benutzerdefinierte Feature derzeit nicht auf Telefonsystem verfügbar ist, sollten Sie die Benutzer, für die diese benutzerdefinierte Funktion lokal erforderlich ist, mit der älteren Nebenstellenanlage belassen und nur die Benutzer portieren, die nicht auf das benutzerdefinierte Feature zugreifen müssen, um Telefonsystem mit lokaler PSTN-Konnektivität zu verwenden.

Eine Liste der älteren Nebenstellenanlagen, die direkt mit Skype for Business Server 2015 zusammenarbeiten, finden Sie unter ["Infrastructure Qualified for Microsoft Lync".](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) Wenn Ihre Nebenstellenanlage nicht in dieser Liste aufgeführt ist, können Sie einen Session Border Controller verwenden, um Ihre Nebenstellenanlage mit Telefonsystem in Skype for Business Online zu verbinden.

### <a name="network-considerations-for-quality-and-performance"></a>Überlegungen zu Qualität und Leistung im Netzwerk

Bei der Bereitstellung eines in der Cloud gehosteten Diensts wie Telefonsystem mit lokaler PSTN-Konnektivität müssen Sie Folgendes berücksichtigen. In einer rein lokalen Skype for Business Server 2015 Enterprise-VoIP Bereitstellung befinden sich alle Infrastruktur und Clients im eigenen Netzwerk des Unternehmens. Die Qualität und Leistung dieses Netzwerks, das für qualitativ hochwertige Audio- und Videodaten entscheidend ist, unterliegen der direkten Kontrolle der Unternehmensmitarbeiter. Bei Telefonsystem mit lokaler PSTN-Anbindung sind drei Netzwerke beteiligt, von denen zwei der Kunde verantwortlich ist, aber nur eines, über das die Mitarbeiter des Unternehmens direkte Kontrolle haben:

- **Globales Medienübermittlungsnetzwerk von Microsoft** Das globale Cloudnetzwerk und die Infrastruktur von Microsoft. Telefonsystem Server und Datenverkehr durchqueren dieses Netzwerk.

- **Enterprise/Cloud PSTN Interconnect** Dies ist das Netzwerk, das Ihr Unternehmen mit der Cloud verbindet. Dies ist nicht notwendigerweise identisch mit Ihrer generischen Internetverbindung.

- **Eigenes Netzwerk Ihres Unternehmens** Die Qualität der Echtzeitmedien hängt stark von Ihrem eigenen Netzwerk ab: insbesondere vom WLAN-Netzwerk und der Qualität der Verbindung, die zum Erreichen der Cloud verwendet wird.

> [!NOTE]
> Weitere Informationen zur Leistungsoptimierung in Skype for Business Online finden Sie unter [Optimieren Skype for Business Onlineleistung.](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US) 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Voraussetzungen für die Verwendung von Telefonsystem mit lokaler PSTN-Anbindung

Bevor Sie Telefonsystem mit lokaler PSTN-Anbindung konfigurieren und Benutzer in Skype for Business Online verschieben können, müssen Sie sicherstellen, dass die folgenden Voraussetzungen erfüllt sind:

 **Lokale Serverversionen.** Die Versionen der Server in Ihrer lokalen Bereitstellung müssen in der folgenden Tabelle aufgeführt sein, um Telefonsystem mit lokaler PSTN-Anbindung zu unterstützen.


| **Serverrolle**                                       | **Unterstützte Versionen\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Partnerverbund-Edge\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Next Hop Federation Route Internal Pool Server  <br/> | Skype for Business Server 2015, kumulatives Update vom März 2016 6.0.9319.235 oder höher (Front-End oder Director)  <br/> |
| Front-End-Benutzerserver  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edgeserver  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Vermittlungsserver  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Unterstützte Mindestversionen sind:

- Skype for Business Server 2015, kumulatives Update 6.0.9319.235 vom März 2016

- Lync Server 2013 Kumulatives Update vom Juli 2015 5.0.8308.920

\*\*Die Partnerverbundroute für alle unterstützten SIP-Domänen muss über den Edgeserver Skype for Business Server 2015 geleitet werden, auf dem das kumulative Update vom März 2016 oder höher ausgeführt wird. Wenn sich der Benutzerpool in Lync Server 2013 befindet, verbleibt der Datenverkehr des externen Pools auf dem Lync Server 2013-Edgeserver. 

Darüber hinaus müssen Sie Folgendes sicherstellen:

- **Lokale Enterprise-VoIP für lokale Benutzer konfiguriert und getestet wird** Dies umfasst PSTN-Verbindungskomponenten. Weitere Informationen finden Sie in den folgenden Themen, wenn Sie Skype for Business Server 2015 verwenden, unter [Plan for Enterprise-VoIP in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) and Deploy Enterprise-VoIP in Skype for Business Server [2015.](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)

    Wenn Sie Lync Server 2013 verwenden, lesen Sie die Informationen unter [Planning for Enterprise-VoIP in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice) and [Deploying Enterprise-VoIP in Lync Server 2013.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-enterprise-voice)

- **Active Directory-Synchronisierung** Sie müssen die Active Directory-Synchronisierung mithilfe von Azure AD Verbinden konfigurieren. Weitere Informationen finden Sie unter [Verwalten von Azure AD Verbinden.](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)

    > [!NOTE]
    > Die von Ihnen verwendete Version von AAD Verbinden muss Version 1.0.9125.0 oder höher sein. Wenn Sie eine frühere Version von AAD Verbinden Tools oder DirSync verwenden, aktualisieren Sie bitte auf die unterstützte Version. Sie können ihre aktuelle Installation aktualisieren und alle benutzerdefinierten Regeln verwalten, die Sie in Ihrer Umgebung definiert haben. 

- **Konfigurieren Der Hybridbereitstellung** Unabhängig davon, ob alle Ihre Skype for Business-Benutzer derzeit online oder lokal verwaltet werden oder wenn Sie derzeit über eine Mischung verfügen, müssen Sie die Schritte zum Konfigurieren einer Hybridbereitstellung von Skype for Business Server oder Lync Server 2013 ausführen, wie unter [Bereitstellen der Hybridkonnektivität zwischen Skype for Business Server und Office 365](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)beschrieben. Weitere Hintergrundinformationen zu Hybridbereitstellungen finden Sie unter Planen der [Hybridkonnektivität zwischen Skype for Business Server und Office 365.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 

    Wenn Sie Lync Server 2013 verwenden, finden Sie weitere Informationen unter [Lync Server 2013 Hybrid.](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid)

- **(Empfohlen) Active Directory-Verbunddienste (AD FS).** Es wird empfohlen, AD FS zur Unterstützung des einmaligen Anmeldens bereitzustellen. Weitere Informationen finden Sie unter [Active Directory-Verbunddienste (AD FS).](/previous-versions/windows/it-pro/windows-server-2003/cc736690(v=ws.10))

Informationen zum Bereitstellen von Telefonsystem finden Sie unter [Aktivieren von Benutzern für Telefonsystem mit lokaler PSTN-Konnektivität in Skype for Business Server.](enable-users-for-phone-system.md)