---
title: Planen der Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
ms.audience: ITPro
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
description: Informationen Sie zu den planungsüberlegungen für Telefonsystem in Office 365 (Cloud, PBX) mit lokalen PSTN-Anbindung.
ms.openlocfilehash: 4614b3fdc62d8a51323ee7c9f261bec3d6cea6c3
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531602"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planen der Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype Business Server

Informationen Sie zu den planungsüberlegungen für Telefonsystem in Office 365 (Cloud, PBX) mit lokalen PSTN-Anbindung.

Dieser Inhalt ist relevant, wenn Sie bereits Skype für Business Server oder Lync Server 2013 lokal bereitgestellt haben. Für andere Szenarien finden Sie unter [Planen von Ihrem Telefonsystem in Office 365 (PBX) zu Cloud-Lösung](plan-your-phone-system-cloud-pbx-solution.md).

 Telefonsystem in Office 365 mit lokalen PSTN-Anbindung können Sie Funktionen für Ihre Benutzer Telefonsystem (Cloud, PBX) nutzen. Das kann in folgenden Szenarien hilfreich sein:

- Stehen Ihnen einige Ihrer Skype für Business Benutzer lokal und andere Personen in Skype für Business Online verwaltet werden. Sie können jetzt Telefonsystem aktivieren, in Office 365-Funktionen und Features für Ihre Benutzer in Skype für Business Online verwaltet, aber weiterhin lokale PSTN-Anbindung zu verwenden.

- Sie haben eine lokale Bereitstellung, und Sie einige oder alle Benutzer in Skype für Business Online verschoben werden jedoch weiterhin lokale PSTN-Anbindung verwenden möchten.

    > [!IMPORTANT]
    > Um erfolgreich Benutzern für Telefonsystem in Office 365 mit lokalen PSTN-Anbindung zu ermöglichen, muss ihre SIP-Adresse in Ihrer eigenen Domäne sein. Die Verwendung der Standarddomäne für Office 365 (onmicrosoft.com) wird nicht unterstützt. 

Weitere Informationen zu Telefonsystem in Office 365-Pläne und Lizenzierung einschließlich finden, finden Sie unter [PSTN aufrufen Abonnements Skype für Unternehmen](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Vergleich der Features

Cloud-Nebenstellenanlage mit lokalen PSTN-Anbindung bietet keine dieselbe Features als vollständig lokalen Enterprise-VoIP-Lösung. Um besser entscheiden, ob die Cloud-Nebenstellenanlage mit lokalen PSTN-Anbindung die richtige Featuregruppe für Ihre Organisation bereitgestellt werden, finden Sie unter [Hier erhalten Sie mit der Cloud Nebenstellenanlage](https://go.microsoft.com/fwlink/?LinkId=715517).

## <a name="benefits-and-planning-considerations"></a>Vorteile und Planungsüberlegungen

> [!CAUTION]
> Lync Phone Edition-Geräte MÜSSEN in Ihrer lokalen Umgebung auf die minimal erforderliche Firmware aktualisiert werden, BEVOR nach Skype for Business Online umgezogen wird.
Wenn Sie Ihre Benutzer vor einer Aktualisierung der Firma von der lokalen Verwendung zur Onlinebereitstellung übertragen, können diese Benutzer mit ihren Telefonen keine Verbindung herstellen. Um dieses Problem zu beheben, müssen die Benutzer zur lokalen Umgebung zurückübertragen werden, damit ihre Telefone dort auf die minimal erforderliche Firmware aktualisiert werden. VERSUCHEN SIE NICHT; VOR DEM ZURÜCKÜBERTRAGEN DER BENUTZER ZU IHRER LOKALEN UMGEBUNG AUF DIE MINIMAL ERFORDERLICHE FIRMWARE ZU AKTUALISIEREN ODER EIN HARDRESET DER TELEFONE DURCHZUFÜHREN.
Wenn ein Hardreset durchgeführt wird, während das Gerät nicht mit der minimal erforderlichen Firmware ausgestattet ist, nutzt das Telefon standardmäßig die PIN-Authentifizierung, die in Skype for Business Online nicht unterstützt wird. Weitere Informationen finden Sie unter [Getting Telefone für Skype für Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Durch die Bereitstellung von Telefonsystem in Office 365 mit lokalen PSTN-Anbindung können Sie Ihre Benutzer in die Cloud über Skype für Business Online in Ihrem eigenen Tempo verschieben Beibehaltung von ihren lokalen PSTN-Anbindung. Wenn Sie über eine PBX verfügen, können Sie diese weiterhin für die PSTN-Anbindung der Benutzer verwenden, die Sie in die Cloud übertragen. Nachdem ein Benutzer in Skype für Business Online und Telefonsystem in Office 365 verschoben wurde, ihren legacy PBX-Telefon funktioniert nicht mehr, aber ihre Telefonnummer leitet an keines der Skype für Business-Clients für PCs oder Smartphones sowie Skype für Business-kompatiblen Telefonapparat s. Nachdem der Port, können Telefonsystem in Office 365-Benutzer und bestehende PBX-Benutzer miteinander normalerweise aufrufen sowie PSTN-Anrufe mithilfe ihrer normalen Telefonnummer müssen/empfangen.

Möglicherweise verfügen Sie über eine benutzerdefinierte Funktion oder ein wesentliches Add-On für Ihre ältere PBX, zum Beispiel ein Callcenter. Wenn die benutzerdefinierte Funktion nicht aktuell auf Telefonsystem in Office 365 verfügbar ist, sollten Sie diese Benutzer lassen, die erfordern, benutzerdefinierte Funktion mit dem vorhandene PBX und nur Port die Benutzer lokale, die nicht auf die benutzerdefinierte Funktion Telefonsystem in Office 365 zugreifen müssen mit lokalen PSTN-Anbindung.

Eine Liste der Vorversion Nebenstellenanlagen, die interagieren direkt mit Skype für Business Server 2015 finden Sie unter [Qualifizierten Infrastruktur für Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Ist der Nebenstellenanlage nicht in dieser Liste, können Sie ein Controller für die Verbindung der Nebenstellenanlage mit Telefonsystem in Office 365 in Skype für Business Online verwenden.

### <a name="network-considerations-for-quality-and-performance"></a>Überlegungen zum Netzwerk in Bezug auf Qualität und Leistung

Bei einen Wolke gehosteter Dienst wie Telefonsystem in Office 365 mit PSTN-Anbindung: lokal bereitstellen, müssen Sie Folgendes im Hinterkopf behalten. Befinden sich in einem rein lokalen Skype für Business Server 2015 Enterprise Voice-Bereitstellung die Infrastruktur und -Clients auf das Netzwerk des Unternehmens. Die Qualität und Leistung dieses Netzwerks, die für hochwertige Audio- und Video-Wiedergabe wesentlich sind, werden unmittelbar von Mitarbeitern Ihres Unternehmens kontrolliert. In das Telefonsystem in Office 365 mit lokalen PSTN-Anbindung gibt es drei Netze sind, zwei, von denen der Kunde für zuständig ist, aber nur über ein, die Enterprise-Mitarbeiter über direkte Kontrolle hat:

- **Microsofts globale Media Delivery Networks** Globale Cloud Netzwerk- und Infrastruktur von Microsoft. Office 365 und Telefonsystem in Office 365-Servern und Datenverkehr über dieses Netzwerk übertragen.

- **Enterprise/Cloud PSTN-Verbindung** Dies ist das Netzwerk, das Ihr Unternehmen in die Office 365-Cloud verbindet. Es ist nicht automatisch dasselbe wie bei Ihrer generischen Internetverbindung.

- **Ihr Netzwerk des Unternehmens** Die Qualität des Mediums in Echtzeit ist stark abhängig von Ihrem eigenen Netzwerk: vor allem das WLAN-Netzwerk und die Qualität der Interconnect verwendet, um die Office 365-Cloud zu erreichen.

> [!NOTE]
> Weitere Informationen zur Feinabstimmung Performance in Skype für Business Online finden Sie unter [Skype für Business Online Leistung zu optimieren](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Voraussetzung für die Verwendung von Telefonsystem in Office 365 mit lokalen PSTN-Anbindung

Bevor Sie Telefonsystem in Office 365 mit lokalen PSTN-Anbindung und Benutzer in Skype verschieben für Business Online konfigurieren können, müssen Sie bestätigen, dass Sie die folgenden Anforderungen erfüllt sein:

 **Lokale Serverversionen.** Die Versionen der Server in der lokalen Bereitstellung müssen in der folgenden Tabelle zur Unterstützung der Telefonsystem in Office 365 mit lokalen PSTN-Anbindung aufgeführt sein.


| **Serverrolle**                                       | **Unterstützte Versionen\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Verbund Edge\*\*  <br/>                            | Skype for Business Server 2015  <br/>                                                                              |
| Interner Poolserver für den nächsten Hop der Partnerverbundroute  <br/> | Skype for Business Server 2015, March 2016 Cumulative Update 6.0.9319.235 or higher (Front End or Director)   <br/> |
| Front-End-Benutzerserver  <br/>                          | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Edgeserver  <br/>                                    | Skype for Business Server 2015  <br/>                                                                              |
| Vermittlungsserver  <br/>                               | Skype for Business Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Minimale unterstützte Versionen sind:

- Skype for Business Server 2015, kumulatives Update 6.0.9319.235 vom März 2016

- Lync Server 2013, kumulatives Update 5.0.8308.920 vom Juli 2015

\*\*Der Verbund weiterleiten für alle unterstützte SIP-Domänen durch die Skype Business Server 2015 Edge-Server ausführen, geleitet werden müssen die März 2016 oder höher kumulative Update. Wenn sich der Benutzerpool in Lync Server 2013 befindet, bleibt der Datenverkehr des externen Pools auf dem Lync Server 2013-Edgeserver. 

Darüber hinaus müssen Sie Folgendes sicherstellen:

- **Lokale Enterprise-VoIP, konfiguriert und getestet, die für lokale Benutzer** Dies schließt PSTN Connectivity Komponenten. Weitere Informationen finden Sie unter den folgenden Themen, wenn Sie für die Business Server 2015 Skype verwenden, finden Sie unter [Enterprise-VoIP in Skype für Business Server 2015 planen](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) und [Bereitstellen von Enterprise-VoIP in Skype für Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Wenn Sie Lync Server 2013 verwenden, finden Sie unter [Planning for Enterprise-VoIP in Lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) und [Bereitstellen von Enterprise-VoIP in Lync Server 2013](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx).

- **Active Directory-Synchronisierung** Sie müssen Active Directory-Synchronisierung mit Azure Active Directory verbinden konfigurieren. Weitere Informationen finden Sie unter [Nächste Schritte und Verwalten von Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > Die von Ihnen verwendete Version von AAD Connect muss Version 1.0.9125.0 oder höher sein. Wenn Sie mit einer früheren Version der AAD Connect-Werkzeuge oder DirSync arbeiten, führen Sie ein Upgrade auf die unterstützte Version durch. Sie können aber auch ein Upgrade Ihrer aktuellen Installation durchführen und alle benutzerdefinierten Regeln beibehalten, die Sie in Ihrer Umgebung definiert haben. 

- **Konfigurieren einer hybridbereitstellung** Gibt an, ob alle Ihre Skype für Unternehmensbenutzer sind derzeit entweder online verwaltet oder lokal, oder wenn Sie derzeit eine Kombination haben, müssen Sie die Schritte zum Konfigurieren einer hybriden bereitstellungs von Skype für Business Server oder Lync Server 2013, wie beschrieben in [Deploy Hybrid Konnektivität zwischen Skype für Business Server und Skype für Online Business](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Weitere Informationen zu hybridbereitstellungen finden Sie unter [Planen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md). 

    Wenn Sie Lync Server 2013 verwenden, finden Sie unter [Lync Server 2013 Hybrid](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx).

- **Active Directory-Verbunddienste (AD FS) (empfohlen)** Wir empfehlen die Bereitstellung von AD FS für einmaliges Anmelden zu unterstützen. Weitere Informationen finden Sie unter [Active Directory-Verbunddienste (AD FS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx).

Informationen zum Bereitstellen von Telefonsystem in Office 365 finden Sie unter [Aktivieren von Benutzern für Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität in Skype für Business Server](enable-users-for-phone-system.md).


