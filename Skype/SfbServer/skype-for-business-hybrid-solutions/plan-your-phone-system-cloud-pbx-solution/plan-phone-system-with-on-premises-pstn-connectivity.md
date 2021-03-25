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
description: Erfahren Sie mehr über die Planungsüberlegungen für Das Telefonsystem (Cloud PBX) mit einer lokalen PSTN-Verbindung.
ms.openlocfilehash: e0caed5560e7b7609adbfccf79e4ef63ee4eae09
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110541"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planen eines Telefonsystems mit lokaler Festnetzanbindung in Skype for Business Server

> [!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, nachdem der Zugriff auf den Dienst nicht mehr möglich ist.  Darüber hinaus wird die PSTN-Verbindung zwischen Ihrer lokalen Umgebung über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)

Erfahren Sie mehr über die Planungsüberlegungen für Das Telefonsystem (Cloud PBX) mit einer lokalen PSTN-Verbindung.

Dieser Inhalt ist relevant, wenn Skype for Business Server oder Lync Server 2013 bereits lokal bereitgestellt sind. Weitere Szenarien finden Sie unter [Microsoft telephony solutions](../../../SfbHybrid/hybrid/msft-telephony-solutions.md).

 Mit dem Telefonsystem mit einer lokalen PSTN-Verbindung können Sie die Funktionen des Telefonsystems (Cloud PBX) für Ihre Benutzer nutzen. Dies kann bei den folgenden Szenarien hilfreich sein:

- Einige Ihrer Skype for Business-Benutzer werden lokal und andere in Skype for Business Online heimgeheimst. Sie können jetzt die Funktionen und Features des Telefonsystems für Ihre Benutzer aktivieren, die in Skype for Business Online gespeichert sind, aber weiterhin lokale PSTN-Konnektivität verwenden.

- Sie verfügen über eine lokale Bereitstellung, und Sie möchten einige oder alle Ihrer Benutzer zu Skype for Business Online verschieben, aber weiterhin lokale PSTN-Konnektivität verwenden.

    > [!IMPORTANT]
    > Damit Benutzer für Das Telefonsystem erfolgreich mit einer lokalen PSTN-Verbindung aktiviert werden können, muss sich ihre SIP-Adresse in Ihrer eigenen Domäne befinden. Die Verwendung der Standarddomäne für Microsoft 365 oder Office 365, onmicrosoft.com, wird nicht unterstützt. 

Weitere Informationen zum Telefonsystem, einschließlich Lizenzierung und Plänen, finden Sie unter [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Featurevergleich

Cloud PBX mit lokalem PSTN Connectivity bietet nicht denselben Funktionssatz wie eine vollständig lokale Enterprise-VoIP Lösung. Informationen dazu, ob Cloud PBX mit lokalem PSTN Connectivity den richtigen Funktionssatz für Ihre Organisation bietet, finden Sie unter [Here's what you get with Cloud PBX](/microsoftteams/here-s-what-you-get-with-phone-system?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2ftoc.json).

## <a name="benefits-and-planning-considerations"></a>Vorteile und Planungsüberlegungen

> [!CAUTION]
> Lync Phone Edition-Geräte MÜSSEN vor dem Wechsel zu Skype for Business Online auf die mindestens erforderliche Firmware in Ihrer lokalen Umgebung aktualisiert werden.
Wenn Sie Ihre Benutzer vor dem Aktualisieren der Firmware von lokal auf online verschieben, können Benutzer keine Verbindung über ihre Telefone herstellen. Um dieses Problem zu beheben, müssen Benutzer wieder in die lokale Umgebung verschoben werden, damit ihre Telefone auf die Mindestfirmware aktualisiert werden. VERSUCHEN SIE NICHT, AUF DIE MINIMALE FIRMWARE ZU AKTUALISIEREN ODER DAS TELEFON FEST ZURÜCKZUSETZEN, BEVOR SIE DEN BENUTZER WIEDER IN IHRE LOKALE UMGEBUNG VERSCHIEBEN.
Wenn ein hard reset ausgeführt wird, während das Gerät nicht mindestens Firmware ist, wird standardmäßig die PIN-Authentifizierung verwendet, die in Skype for Business Online nicht unterstützt wird. Weitere Informationen finden Sie unter [Getting phones for Skype for Business Online](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Durch die Bereitstellung des Telefonsystems mit der lokalen PSTN-Konnektivität können Sie Ihre Benutzer über Skype for Business Online in Ihrem eigenen Tempo in die Cloud verschieben und gleichzeitig ihre lokale PSTN-Konnektivität beibehalten. Wenn Sie über eine Nebenstellenanlage verfügen, verwenden Sie sie weiterhin, um die PSTN-Konnektivität für die Benutzer zu ermöglichen, die Sie in die Cloud verschieben. Sobald ein Benutzer zu Skype for Business Online und Telefonsystem verschoben wurde, funktioniert sein altes Nebenstellentelefon nicht mehr, aber seine Telefonnummer wird an einen der Skype for Business-Clients für PCs oder Smartphones sowie skype for Business-kompatible Telefone umgeschaltet. Nach dem Portieren können Sich Benutzer des Telefonsystems und ältere PbX-Benutzer normal anrufen sowie PSTN-Anrufe über ihre normale Telefonnummer machen/empfangen.

Möglicherweise verfügen Sie über ein benutzerdefiniertes Feature oder ein großes Add-On zu Ihrer älteren Nebenstellenanlage, z. B. ein Call Center. Wenn das benutzerdefinierte Feature derzeit nicht im Telefonsystem verfügbar ist, sollten Sie die Benutzer, die dieses benutzerdefinierte Feature benötigen, lokal mit der älteren Nebenstellenanlage lassen und die Benutzer, die nicht auf das benutzerdefinierte Feature zugreifen müssen, mit einer lokalen PSTN-Verbindung an das Telefonsystem portieren.

Eine Liste der älteren Nebenstellenanlagen, die direkt mit Skype for Business Server 2015 zusammenarbeiten, finden Sie unter  [Infrastructure Qualified for Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md). Wenn Ihre Nebenstellenanlage nicht in dieser Liste aufgeführt ist, können Sie einen Session Border Controller verwenden, um Ihre Nebenstellenanlage mit dem Telefonsystem in Skype for Business Online zu verbinden.

### <a name="network-considerations-for-quality-and-performance"></a>Netzwerküberlegungen für Qualität und Leistung

Bei der Bereitstellung eines in der Cloud gehosteten Diensts wie dem Telefonsystem mit einer lokalen PSTN-Verbindung müssen Sie Folgendes beachten. In einer rein lokalen Skype for Business Server 2015 Enterprise-VoIP bereitstellung befinden sich alle Infrastruktur und Clients im eigenen Netzwerk des Unternehmens. Die Qualität und Leistung dieses Netzwerks, das für hochwertige Audio- und Videoqualität entscheidend ist, wird von den Mitarbeitern des Unternehmens direkt kontrolliert. Bei Telefonsystem mit lokalen PSTN-Verbindungen sind drei Netzwerke beteiligt, von denen zwei vom Kunden, aber nur von einem der Mitarbeiter des Unternehmens direkt kontrolliert werden:

- **Globales Medienzustellungsnetzwerk von Microsoft** Das globale Cloudnetzwerk und die Infrastruktur von Microsoft. Telefonsystemserver und Datenverkehr durchqueren dieses Netzwerk.

- **Enterprise/Cloud PSTN Interconnect** Dies ist das Netzwerk, das Ihr Unternehmen mit der Cloud verbindet. Dies ist nicht unbedingt identisch mit Ihrer generischen Internetverbindung.

- **Das eigene Netzwerk Ihres Unternehmens** Die Qualität der Echtzeitmedien hängt stark vom eigenen Netzwerk ab: insbesondere vom WLAN-Netzwerk und von der Qualität der Verbindung, die für die Cloud verwendet wird.

> [!NOTE]
> Weitere Informationen zum Optimieren der Leistung in Skype for Business Online finden Sie [unter Optimieren der Skype for Business Online-Leistung.](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US) 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Voraussetzungen für die Verwendung des Telefonsystems mit einer lokalen PSTN-Verbindung

Bevor Sie das Telefonsystem mit einer lokalen PSTN-Verbindung konfigurieren und Benutzer zu Skype for Business Online verschieben können, müssen Sie bestätigen, dass die folgenden Voraussetzungen erfüllt sind:

 **Lokale Serverversionen.** Die Versionen der Server in Ihrer lokalen Bereitstellung müssen in der folgenden Tabelle aufgeführt sein, um das Telefonsystem mit einer lokalen PSTN-Verbindung zu unterstützen.


| **Serverrolle**                                       | **Unterstützte Versionen\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Verbund-Edge\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Next Hop Federation Route Internal Pool Server  <br/> | Skype for Business Server 2015, März 2016 Kumulatives Update 6.0.9319.235 oder höher (Front-End oder Director)  <br/> |
| Front-End-Benutzerserver  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edgeserver  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Vermittlungsserver  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Die mindestens unterstützten Versionen sind:

- Skype for Business Server 2015, Kumulatives Update vom März 2016 6.0.9319.235

- Lync Server 2013 July 2015 Kumulatives Update 5.0.8308.920

\*\*Die Verbundroute für alle unterstützten SIP-Domänen muss über den Skype for Business Server 2015-Edgeserver mit dem kumulativen Update vom März 2016 oder höher geroutet werden. Wenn sich der Benutzerpool auf Lync Server 2013 befindet, verbleibt der externe Pooldatenverkehr auf Lync Server 2013 Edge Server. 

Darüber hinaus müssen Sie Folgendes sicherstellen:

- **Lokale Enterprise-VoIP für lokale** Benutzer konfiguriert und getestet Dies umfasst PSTN-Verbindungskomponenten. Weitere Informationen finden Sie in den folgenden Themen, wenn Sie Skype for Business Server 2015 verwenden, unter [Plan for Enterprise-VoIP in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) und Deploy Enterprise-VoIP in Skype for Business Server [2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Wenn Sie Lync Server 2013 verwenden, lesen Sie [Planning for Enterprise-VoIP in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice) und [Deploying Enterprise-VoIP in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-enterprise-voice).

- **Active Directory-Synchronisierung** Sie müssen die Active Directory-Synchronisierung mithilfe von Azure AD Connect konfigurieren. Weitere Informationen finden Sie unter [Managing Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > Die von Ihnen verwendete Version von AAD Connect muss Version 1.0.9125.0 oder höher sein. Wenn Sie eine frühere Version von AAD Connect-Tools oder DirSync verwenden, aktualisieren Sie bitte auf die unterstützte Version. Sie können Die aktuelle Installation aktualisieren und benutzerdefinierte Regeln verwalten, die Sie in Ihrer Umgebung definiert haben. 

- **Konfigurieren Der Hybridbereitstellung** Unabhängig davon, ob alle Skype for Business-Benutzer derzeit entweder online oder lokal oder über eine Mischung verfügen, müssen Sie die Schritte zum Konfigurieren einer Hybridbereitstellung von Skype for Business Server oder Lync Server 2013 ausführen, wie unter Bereitstellen von Hybridkonnektivität zwischen Skype for Business Server und [Office 365](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)beschrieben. Weitere Hintergrundinformationen zu Hybridbereitstellungen finden Sie unter [Plan hybrid connectivity between Skype for Business Server and Office 365](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json). 

    Wenn Sie Lync Server 2013 verwenden, finden Sie weitere Informationen unter [Lync Server 2013 hybrid](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-2013-hybrid).

- **(Empfohlen) Active Directory Federation Services (AD FS).** Es wird empfohlen, AD FS zur Unterstützung des einmaligen Anmeldens zu bereitstellen. Weitere Informationen finden Sie unter [Active Directory Federation Services (AD FS)](/previous-versions/windows/it-pro/windows-server-2003/cc736690(v=ws.10)).

Informationen zum Bereitstellen des Telefonsystems finden Sie unter Aktivieren von Benutzern für Telefonsystem mit einer lokalen [PSTN-Verbindung in Skype for Business Server](enable-users-for-phone-system.md).