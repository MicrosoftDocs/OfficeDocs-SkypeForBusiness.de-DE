---
title: Plan eines Telefonsystems mit lokaler Festnetzanbindung in Skype for Business Server
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
description: Erfahren Sie mehr über die Planungsüberlegungen für das Telefon System (Cloud PBX) mit lokaler PSTN-Konnektivität.
ms.openlocfilehash: f8baab67191f32013a9d7a01ddc12f1b04b62c03
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358811"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Plan eines Telefonsystems mit lokaler Festnetzanbindung in Skype for Business Server

> [!Important]
> Skype for Business Online werden am 31. Juli 2021 zurückgezogen, nach dem der Zugriff auf den Dienst nicht mehr möglich ist.  Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung unabhängig davon, ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Hier erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.

Erfahren Sie mehr über die Planungsüberlegungen für das Telefon System (Cloud PBX) mit lokaler PSTN-Konnektivität.

Dieser Inhalt ist relevant, wenn Sie bereits Skype for Business Server oder lokal bereitgestellt lync Server 2013. Weitere Szenarien finden Sie unter [Microsoft Telephony Solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions).

 Telefonsystem mit lokaler PSTN-Konnektivität ermöglicht Ihnen die Nutzung von Telefonsystem-Funktionen (Cloud PBX) für Ihre Benutzer. Dies kann bei den folgenden Szenarien hilfreich sein:

- Einige Ihrer Skype for Business-Benutzer sind lokal und andere in Skype for Business Online verwaltet. Sie können jetzt Telefon System Funktionen und-Features für die in Skype for Business Online verwalteten Benutzer aktivieren, aber weiterhin die lokale PSTN-Konnektivität verwenden.

- Sie verfügen über eine lokale Bereitstellung, und Sie möchten einige oder alle Ihre Benutzer auf Skype for Business Online umstellen, aber weiterhin lokale PSTN-Konnektivität verwenden.

    > [!IMPORTANT]
    > Damit Benutzer für das Telefon System mit lokaler PSTN-Konnektivität erfolgreich aktiviert werden können, muss sich Ihre SIP-Adresse in ihrer eigenen Domäne befinden. Die Verwendung der Standarddomäne für Microsoft 365 oder Office 365, onmicrosoft.com, wird nicht unterstützt. 

Weitere Informationen zum Telefon System einschließlich Lizenzierung und Plänen finden Sie unter [PSTN-Anrufpläne für Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Funktionsvergleich

Cloud-PBX mit lokaler PSTN-Konnektivität bietet nicht denselben Funktionsumfang wie eine vollständig lokale Enterprise-VoIP-Lösung. Um Sie bei der Entscheidung zu unterstützen, ob die Cloud-PBX-Anlage mit lokaler PSTN-Konnektivität das richtige Feature für Ihre Organisation bereitstellt, sehen Sie [sich die folgenden Funktionen mit Cloud-PBX](https://go.microsoft.com/fwlink/?LinkId=715517)an.

## <a name="benefits-and-planning-considerations"></a>Vorteile und Planungsüberlegungen

> [!CAUTION]
> Lync Phone Edition-Geräte müssen in Ihrer lokalen Umgebung auf die minimal erforderliche Firmware aktualisiert werden, bevor Sie zu Skype for Business Online wechseln.
Wenn Sie Ihre Benutzer vor dem Aktualisieren der Firmware von lokal in Online migrieren, können Benutzer keine Verbindung mit ihren Telefonen herstellen. Um dieses Problem zu beheben, müssen Benutzer wieder in die lokale Umgebung verschoben werden, damit ihre Telefone auf die minimale Firmware aktualisiert werden. versuchen Sie nicht, das Telefon vor dem Verschieben des Benutzers zurück in Ihre lokale Umgebung auf die minimale Firmware oder auf das Hard-Reset zu aktualisieren.
Wenn ein Hard Reset durchgeführt wird, während das Gerät nicht mit einer minimalen Firmware ausgestattet ist, wird standardmäßig die PIN-Authentifizierung verwendet, die in Skype for Business Online nicht unterstützt wird. Weitere Informationen finden Sie unter [Getting phones for Skype for Business Online](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Durch die Bereitstellungeines Telefonsystems mit lokaler PSTN-Konnektivität können Sie Ihre Benutzer in Ihrem eigenen Tempo über Skype for Business Online in die Cloud migrieren und dabei Ihre lokale PSTN-Konnektivität beibehalten. Wenn Sie über eine Nebenstellenanlage verfügen, wird Sie weiterhin verwendet, um die PSTN-Konnektivität für die Benutzer bereitzustellen, die Sie in die Cloud migrieren. Nachdem ein Benutzer in Skype for Business Online-und Telefon System verschoben wurde, funktioniert das PBX-Telefon der Vorversion nicht mehr, aber seine Telefonnummer wird an einen der Skype for Business-Clients für PCs oder Smartphones sowie an Skype for Business konforme Schreibgeräte weitergeleitet. Nach dem portieren können Benutzer von Telefonsystemen und älteren Nebenstellenanlagen sich gegenseitig normal aufrufen sowie PSTN-Anrufe über ihre normale Telefonnummer tätigen/empfangen.

Möglicherweise verfügen Sie über ein benutzerdefiniertes Feature oder ein Haupt-Add-on für Ihre Legacy-Nebenstellenanlage, beispielsweise ein Callcenter. Wenn das benutzerdefinierte Feature derzeit nicht im Telefonsystem verfügbar ist, sollten Sie die Benutzer, die diese benutzerdefinierte Funktion lokal mit der Legacy-PBX-Anlage benötigen, übertragen und die Benutzer, die nicht auf das benutzerdefinierte Feature zugreifen müssen, mit lokaler PSTN-Konnektivität direkt an das Telefonsystem anportieren.

Eine Liste der Legacy-PBX-Anlagen, die direkt mit Skype for Business Server 2015 zusammenarbeiten, finden Sie unter  [für Microsoft lync qualifizierte Infrastruktur](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Wenn sich Ihre Nebenstellenanlage nicht in dieser Liste befindet, können Sie einen Session Border Controller verwenden, um Ihre Nebenstellenanlage mit dem Telefon System in Skype for Business Online zu verbinden.

### <a name="network-considerations-for-quality-and-performance"></a>Überlegungen zu Netzwerkqualität und Leistung

Bei der Bereitstellungeines in der Cloud gehosteten Diensts wie Telefon System mit lokaler PSTN-Konnektivität müssen Sie Folgendes berücksichtigen. In einer reinen lokalen Skype for Business Server 2015 Enterprise-VoIP-Bereitstellung befinden sich alle Infrastrukturen und Clients im eigenen Netzwerk des Unternehmens. Die Qualität und Leistung dieses Netzwerks, das für hochwertige Audio-und Videoqualität entscheidend ist, unterliegen der direkten Kontrolle des Enterprise-Personals. Bei einem Telefon System mit lokaler PSTN-Konnektivität gibt es drei Netzwerke, von denen der Kunde zwei umfasst, von denen jedoch nur eines der Mitarbeiter des Unternehmens direkt die Kontrolle über Folgendes hat:

- **Das globale Medien Zustellungs Netzwerk von Microsoft** Das globale Cloud-Netzwerk und die Infrastruktur von Microsoft. Telefon System Server und Datenverkehr durchlaufen dieses Netzwerks.

- **Enterprise/Cloud-PSTN-Interconnect** Dies ist das Netzwerk, das Ihr Unternehmen mit der Cloud verbindet. Dies ist nicht unbedingt identisch mit ihrer generischen Internet Verbindung.

- **Das eigene Netzwerk Ihres Unternehmens** Die Qualität der Echt Zeit Medien hängt stark von Ihrem eigenen Netzwerk ab: vor allem das WLAN-Netzwerk und die Qualität der Interconnect-Netzwerke, die zum Erreichen der Cloud verwendet werden.

> [!NOTE]
> Weitere Informationen zum Optimieren der Leistung in Skype for Business Online finden Sie unter [Tune Skype for Business Online Performance](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Voraussetzungen für die Verwendung des Telefonsystems mit lokaler PSTN-Konnektivität

Bevor Sie das Telefon System mit lokaler PSTN-Konnektivität konfigurieren und Benutzer zu Skype for Business Online migrieren können, müssen Sie sicherstellen, dass die folgenden Voraussetzungen erfüllt sind:

 **Lokale Server Versionen.** Die Versionen der Server in Ihrer lokalen Bereitstellung müssen in der folgenden Tabelle aufgeführt sein, um das Telefon System mit lokaler PSTN-Konnektivität zu unterstützen.


| **Serverrolle**                                       | **Unterstützte Versionen\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Verbund Edge\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Nächster Hop Partnerverbund Route interner Pool Server  <br/> | Skype for Business Server 2015, März 2016 Kumulatives Update 6.0.9319.235 oder höher (Front-End oder Director)  <br/> |
| Front-End-Benutzer Server  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edgeserver  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Vermittlungsserver  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Mindestens unterstützte Versionen:

- Skype for Business Server 2015, März 2016 Kumulatives Update 6.0.9319.235

- Lync Server 2013 Juli 2015 Kumulatives Update 5.0.8308.920

\*\*Die Verbund Route für alle unterstützten SIP-Domänen muss durch die Skype for Business Server 2015 geleitet werden, Edgeserver das kumulative Update vom 2016. März oder höher ausführt. Wenn sich der Benutzerpool auf lync Server 2013 befindet, bleibt der externe Pool Datenverkehr auf lync Server 2013 Edgeserver. 

Außerdem müssen Sie Folgendes sicherstellen:

- **Lokale Enterprise-VoIP ist für lokale Benutzer konfiguriert und getestet** Dies umfasst Komponenten für die PSTN-Konnektivität. Weitere Informationen finden Sie in den folgenden Themen, wenn Sie Skype for Business Server 2015 verwenden, finden Sie unter [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) und [Deploy Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Wenn Sie lync Server 2013 verwenden, lesen Sie [Planen von Enterprise-VoIP in lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) und [Bereitstellen von Enterprise-VoIP in lync Server 2013](https://technet.microsoft.com/library/gg412876%28v=ocs.15%29.aspx).

- **Active Directory Synchronisierung** Sie müssen Active Directory Synchronisierung mit Azure AD Connect konfigurieren. Weitere Informationen finden Sie unter [Managing Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > Die Version von Aad Connect, die Sie verwenden, muss Version 1.0.9125.0 oder höher sein. Wenn Sie eine frühere Version von Aad Connect Tools oder Dirsync verwenden, führen Sie ein Upgrade auf die unterstützte Version durch. Sie können Ihre aktuelle Installation aktualisieren und alle benutzerdefinierten Regeln verwalten, die Sie in Ihrer Umgebung definiert haben. 

- **Konfigurieren der hybridbereitstellung** Unabhängig davon, ob alle Skype for Business Benutzer derzeit online oder lokal verwaltet werden oder wenn Sie derzeit über eine Mischung verfügen, müssen Sie die Schritte zum Konfigurieren einer hybridbereitstellung von Skype for Business Server oder lync Server 2013 ausführen, wie unter [Deploy Hybrid Connectivity zwischen Skype for Business Server und Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)beschrieben. Weitere Hintergrundinformationen zu hybridbereitstellungen finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). 

    Wenn Sie lync Server 2013 verwenden, finden Sie weitere Informationen unter [lync Server 2013 Hybrid](https://technet.microsoft.com/library/jj204805%28v=ocs.15%29.aspx).

- **Empfohlen Active Directory Verbunddienste (AD FS).** Wir empfehlen die Bereitstellung von AD FS zur Unterstützung von einmaligem Anmelden. Weitere Informationen finden Sie unter [Active Directory Federation Services (AD FS)](https://technet.microsoft.com/library/cc736690%28v=ws.10%29.aspx).

Informationen zum Bereitstellen des Telefonsystems finden Sie unter [enable users for Phone System with on-premises PSTN Connectivity in Skype for Business Server](enable-users-for-phone-system.md).


