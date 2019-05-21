---
title: Planen des Telefonsystems in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Informieren Sie sich über die Planungsüberlegungen für Telefonsysteme in Office 365 (Cloud PBX) mit lokalen PSTN-Konnektivität.
ms.openlocfilehash: 7b24c0de8eab663dea771948b066a0752fe943ca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287020"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planen des Telefonsystems in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server

Informieren Sie sich über die Planungsüberlegungen für Telefonsysteme in Office 365 (Cloud PBX) mit lokalen PSTN-Konnektivität.

Dieser Inhalt ist relevant, wenn Sie bereits über Skype for Business Server oder lync Server 2013 verfügen, das lokal bereitgestellt wird. Weitere Szenarien finden Sie unter [Microsoft-Telefonie-Lösungen](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

 Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität können Sie Telefonsystem Funktionen (Cloud PBX) für Ihre Benutzer nutzen. Das kann in folgenden Szenarien hilfreich sein:

- Sie verfügen über einige Ihrer Skype for Business-Benutzer, die lokal und andere in Skype for Business Online verwaltet werden. Sie können jetzt das Telefon System in den Office 365-Funktionen und-Features für Ihre in Skype for Business Online gehosteten Benutzer aktivieren, aber weiterhin die lokale PSTN-Konnektivität verwenden.

- Sie verfügen über eine lokale Bereitstellung, und Sie möchten einige oder alle Benutzer in Skype for Business Online verschieben, aber weiterhin lokale PSTN-Konnektivität verwenden.

    > [!IMPORTANT]
    > Damit Benutzer für Telefonsysteme in Office 365 mit lokalen PSTN-Verbindungen erfolgreich aktiviert werden können, muss sich Ihre SIP-Adresse in ihrer eigenen Domäne befinden. Die Verwendung der Standarddomäne für Office 365 (onmicrosoft.com) wird nicht unterstützt. 

Weitere Informationen zu Telefonsystemen in Office 365, einschließlich Lizenzierung und Pläne, finden Sie unter [PSTN-Anrufpläne für Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Vergleich der Features

Cloud PBX mit lokalen PSTN-Konnektivität bietet nicht den gleichen Funktionsumfang wie eine vollständige lokale Enterprise-VoIP-Lösung. Wenn Sie entscheiden möchten, ob Cloud PBX mit lokalen PSTN-Konnektivität die richtige Funktionsgruppe für Ihre Organisation bereitstellen soll, finden Sie hier Informationen dazu, [was Sie mit Cloud PBX erhalten](https://go.microsoft.com/fwlink/?LinkId=715517).

## <a name="benefits-and-planning-considerations"></a>Vorteile und Planungsüberlegungen

> [!CAUTION]
> Lync Phone Edition-Geräte MÜSSEN in Ihrer lokalen Umgebung auf die minimal erforderliche Firmware aktualisiert werden, BEVOR nach Skype for Business Online umgezogen wird.
Wenn Sie Ihre Benutzer vor einer Aktualisierung der Firma von der lokalen Verwendung zur Onlinebereitstellung übertragen, können diese Benutzer mit ihren Telefonen keine Verbindung herstellen. Um dieses Problem zu beheben, müssen die Benutzer zur lokalen Umgebung zurückübertragen werden, damit ihre Telefone dort auf die minimal erforderliche Firmware aktualisiert werden. VERSUCHEN SIE NICHT; VOR DEM ZURÜCKÜBERTRAGEN DER BENUTZER ZU IHRER LOKALEN UMGEBUNG AUF DIE MINIMAL ERFORDERLICHE FIRMWARE ZU AKTUALISIEREN ODER EIN HARDRESET DER TELEFONE DURCHZUFÜHREN.
Wenn ein Hardreset durchgeführt wird, während das Gerät nicht mit der minimal erforderlichen Firmware ausgestattet ist, nutzt das Telefon standardmäßig die PIN-Authentifizierung, die in Skype for Business Online nicht unterstützt wird. Weitere Informationen finden Sie unter [Abrufen von Telefonen für Skype for Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Durch die Bereitstellung von Telefon System in Office 365 mit lokalen PSTN-Konnektivität können Sie Ihre Benutzer in Ihrem eigenen Tempo über Skype for Business Online in die Cloud verschieben, während Sie Ihre lokale PSTN-Konnektivität beibehalten. Wenn Sie über eine PBX verfügen, können Sie diese weiterhin für die PSTN-Anbindung der Benutzer verwenden, die Sie in die Cloud übertragen. Wenn ein Benutzer nach Skype for Business Online und Telefon System in Office 365 verschoben wird, funktioniert sein herkömmliches PBX-Telefon nicht mehr, aber seine Telefonnummer wird an einen der Skype for Business-Clients für PCs oder Smartphones weitergeleitet, sowie an ein Skype for Business-kompatibles Tischtelefon s. Nach dem portieren können Telefon System in Office 365-Benutzern und Legacy-PBX-Nutzer sich gegenseitig in der Regel anrufen und PSTN-Anrufe über ihre normale Telefonnummer tätigen oder empfangen.

Möglicherweise verfügen Sie über eine benutzerdefinierte Funktion oder ein wesentliches Add-On für Ihre ältere PBX, zum Beispiel ein Callcenter. Wenn das benutzerdefinierte Feature derzeit nicht auf dem Telefonsystem in Office 365 zur Verfügung steht, sollten Sie die Benutzer, die das benutzerdefinierte Feature lokal mit der Legacy-Telefonanlage benötigen, belassen und die Benutzer, die nicht auf das benutzerdefinierte Feature zugreifen müssen, in Office 365 einfach an das Telefonsystem portieren. mit lokalen PSTN-Konnektivität.

Eine Liste der Legacy-PBX-Anlagen, die direkt mit Skype for Business Server 2015 interagieren, finden Sie unter [für Microsoft lync qualifizierte Infrastruktur](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Wenn Ihre Telefonanlage nicht in dieser Liste aufgeführt ist, können Sie einen Session Border Controller verwenden, um Ihre Telefonanlage mit dem Telefon System in Office 365 in Skype for Business Online zu verbinden.

### <a name="network-considerations-for-quality-and-performance"></a>Überlegungen zum Netzwerk in Bezug auf Qualität und Leistung

Beim Bereitstellen eines in der Cloud gehosteten Diensts wie Telefonsystems in Office 365 mit lokalen PSTN-Konnektivität müssen Sie die folgenden Punkte beachten. In einer rein lokalen Skype for Business Server 2015 Enterprise-VoIP-Bereitstellung befinden sich alle Infrastrukturen und Clients im eigenen Netzwerk des Unternehmens. Die Qualität und Leistung dieses Netzwerks, die für hochwertige Audio- und Video-Wiedergabe wesentlich sind, werden unmittelbar von Mitarbeitern Ihres Unternehmens kontrolliert. Mit dem Telefon System in Office 365 mit lokalen PSTN-Konnektivität sind drei Netzwerke beteiligt, von denen zwei der Kunde verantwortlich ist, aber nur eines, von dem die Mitarbeiter des Unternehmens direkt kontrollieren können:

- **Das globale Media Delivery-Netzwerk von Microsoft** Das globale Cloud-Netzwerk und die Infrastruktur von Microsoft. Office 365 und Telefon System in Office 365-Servern und-Datenverkehr durchlaufen dieses Netzwerks.

- **PSTN-Interconnect für Unternehmen/Cloud** Hierbei handelt es sich um das Netzwerk, das Ihr Unternehmen mit der Office 365-Cloud verbindet. Es ist nicht automatisch dasselbe wie bei Ihrer generischen Internetverbindung.

- **Das eigene Netzwerk Ihres Unternehmens** Die Qualität des Echt Zeit Mediums hängt stark von Ihrem eigenen Netzwerk ab: insbesondere vom WLAN-Netzwerk und der Qualität der Interconnect-Verbindung, um die Office 365-Cloud zu erreichen.

> [!NOTE]
> Weitere Informationen zum Optimieren der Leistung in Skype for Business Online finden Sie unter [Optimieren der Leistung von Skype for Business Online](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Voraussetzungen für die Verwendung des Telefonsystems in Office 365 mit lokalen PSTN-Konnektivität

Bevor Sie das Telefon System in Office 365 mit lokalem PSTN-Konnektivität konfigurieren und Benutzer in Skype for Business Online verschieben können, müssen Sie sicherstellen, dass Sie die folgenden Voraussetzungen erfüllt haben:

 **Lokale Serverversionen.** Die Versionen der Server in Ihrer lokalen Bereitstellung müssen in der folgenden Tabelle aufgeführt sein, um das Telefon System in Office 365 mit lokalen PSTN-Konnektivität zu unterstützen.


| **Serverrolle**                                       | **Unterstützte Versionen\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Föderations Kante\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Interner Poolserver für den nächsten Hop der Partnerverbundroute  <br/> | Skype for Business Server 2015, March 2016 Cumulative Update 6.0.9319.235 or higher (Front End or Director)   <br/> |
| Front-End-Benutzerserver  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edgeserver  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Vermittlungsserver  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Unterstützte Mindestversionen sind:

- Skype for Business Server 2015, kumulatives Update 6.0.9319.235 vom März 2016

- Lync Server 2013, kumulatives Update 5.0.8308.920 vom Juli 2015

\*\*Die Verbund Route für alle unterstützten SIP-Domänen muss über den Skype for Business Server 2015 Edge-Server weitergeleitet werden, auf dem das kumulative Update vom März 2016 oder höher ausgeführt wird. Wenn sich der Benutzerpool in Lync Server 2013 befindet, bleibt der Datenverkehr des externen Pools auf dem Lync Server 2013-Edgeserver. 

Darüber hinaus müssen Sie Folgendes sicherstellen:

- **Lokale Enterprise-VoIP wird für lokale Benutzer konfiguriert und getestet** Dazu gehören Komponenten für PSTN-Konnektivität. Weitere Informationen finden Sie in den folgenden Themen: Wenn Sie Skype for Business Server 2015 verwenden, lesen Sie [Planen von Enterprise-VoIP in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) und [Bereitstellen von Enterprise-VoIP in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Wenn Sie lync Server 2013 verwenden, lesen Sie [Planen der Enterprise-VoIP in lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) und [Bereitstellen von Enterprise-VoIP in lync Server 2013](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx).

- **Active Directory-Synchronisierung** Sie müssen die Active Directory-Synchronisierung mithilfe von Azure AD Connect konfigurieren. Weitere Informationen finden Sie unter [Verwalten von Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > Die von Ihnen verwendete Version von AAD Connect muss Version 1.0.9125.0 oder höher sein. Wenn Sie mit einer früheren Version der AAD Connect-Werkzeuge oder DirSync arbeiten, führen Sie ein Upgrade auf die unterstützte Version durch. Sie können aber auch ein Upgrade Ihrer aktuellen Installation durchführen und alle benutzerdefinierten Regeln beibehalten, die Sie in Ihrer Umgebung definiert haben. 

- **Konfigurieren der hybridbereitstellung** Ob alle Ihre Skype for Business-Benutzer derzeit entweder online oder lokal gehostet werden oder wenn Sie derzeit eine Mischung haben, müssen Sie die Schritte zum Konfigurieren einer hybridbereitstellung von Skype for Business Server oder lync Server 2013 ausführen, wie in [Deploy Hybrid beschrieben. Konnektivität zwischen Skype for Business Server und Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md) Weitere Hintergrundinformationen zu hybridbereitstellungen finden Sie unter [Planen der Hybrid Konnektivität zwischen Skype for Business Server und Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). 

    Wenn Sie lync Server 2013 verwenden, finden Sie weitere Informationen unter [lync Server 2013 Hybrid](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx).

- **(Empfohlen) Active Directory-Verbunddienste (AD FS)** Wir empfehlen die Bereitstellung von AD FS zur Unterstützung der einmaligen Registrierung. Weitere Informationen finden Sie unter [Active Directory-Verbunddienste (AD FS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx).

Informationen zum Bereitstellen von Telefonsystemen in Office 365 finden Sie unter [Aktivieren von Benutzern für Telefonsysteme in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server](enable-users-for-phone-system.md).


