---
title: Direkte SIP-Verbindungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Direkte SIP-Verbindungen werden zwischen Skype for Business Server und sowohl PSTN-Gateways als auch IP-PBX in Enterprise-VoIP unterstützt.
ms.openlocfilehash: 1948e08d63aed9d49c70443a386adce6dc65f78e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803055"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Direkte SIP-Verbindungen in Skype for Business Server

Direkte SIP-Verbindungen werden zwischen Skype for Business Server und sowohl PSTN-Gateways als auch IP-PBX in Enterprise-VoIP unterstützt.

Sie können direkte SIP-Verbindungen verwenden, um Skype for Business Server mit einem der folgenden zu verbinden:

- An IP-PBX 

- A PSTN gateway

Um eine direkte SIP-Verbindung zu implementieren, führen Sie im wesentlichen dieselben Bereitstellungsschritte wie bei der Implementierung eines SIP-Trunks aus. In beiden Fällen implementieren Sie die Verbindung mithilfe der externen Schnittstelle eines Vermittlungsservers. Der einzige Unterschied besteht darin, dass Sie SIP-Trunks mit einer externen Entität wie einem ITSP-Gateway verbinden und direkte SIP-Verbindungen mit einer internen Entität in Ihrem lokalen Netzwerk verbinden, beispielsweise mit einer IP-Telefonanlage oder einem PSTN-Gateway (Public Switched Telephone Network).

## <a name="direct-sip-deployment-options"></a>Direct SIP deployment options

### <a name="skype-for-business-server-stand-alone"></a>Skype for Business Server Stand-Alone
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Wenn in Ihrer Organisation eine der in diesem Abschnitt beschriebenen Bereitstellungen verwendet wird, können Sie Skype for Business Server als einzige Telefonlösung für einen Teil oder eine ganze Organisation verwenden. In diesem Abschnitt werden die folgenden Bereitstellungen ausführlich beschrieben:

- **Inkrementelle Bereitstellung:** Bei dieser Option wird davon ausgegangen, dass Sie über eine vorhandene PBX-Infrastruktur (Private Branch Exchange) verfügen und beabsichtigen, Enterprise-VoIP inkrementell für kleinere Gruppen oder Teams innerhalb Ihrer Organisation einzuführen.

- **Nur-VoIP-Bereitstellung:** bei dieser Option wird davon ausgegangen, dass Sie die Bereitstellung von Enterprise-VoIP an einer Website erwägen, die keine herkömmliche Telefonie-Infrastruktur aufweist.

#### <a name="incremental-deployment"></a>Incremental Deployment

Bei der inkrementellen Bereitstellung ist Skype for Business Server die einzige Telefonlösung für einzelne Teams oder Abteilungen, während die restlichen Benutzer in einer Organisation weiterhin eine Telefonanlage verwenden. Diese inkrementelle Bereitstellungsstrategie bietet eine Möglichkeit, IP-Telefonie in Ihrem Unternehmen durch gesteuerte Pilotprogramme einzuführen. Arbeitsgruppen, deren Kommunikationsanforderungen am besten von Microsoft Unified Communications erfüllt werden, werden in Enterprise-VoIP verschoben, während andere Benutzer auf der vorhandenen Telefonanlage verbleiben. Zusätzliche Arbeitsgruppen können nach Bedarf in Enterprise-VoIP migriert werden.

Die Option "inkrementell" wird empfohlen, wenn Sie über klar definierte Benutzergruppen verfügen, die gemeinsame Kommunikationsanforderungen aufweisen und sich für eine zentralisierte Verwaltung eignen. Diese Option ist auch effektiv, wenn Sie über Teams oder Abteilungen verfügen, die sich über weite geografische Gebiete verteilen, wo die Einsparungen bei den Gebühren für Ferngespräche erheblich sein können. In der Tat ist diese Option für die Erstellung virtueller Teams hilfreich, deren Mitglieder auf der ganzen Welt verstreut sein können. Sie können solche Teams erstellen, ändern oder auflösen, indem Sie schnell auf wechselnde geschäftliche Anforderungen reagieren.

Die folgende Abbildung zeigt die generische Topologie für die Bereitstellung von Enterprise-VoIP hinter einer Telefonanlage. Dies ist die empfohlene Topologie für die inkrementelle Bereitstellung.

**Incremental deployment option**

![Abteilungsbezogene Migrationsoption (Diagramm)](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Wenn Sie die Bereitstellung von Skype for Business Server mit einem Certified Direct SIP-Partner verbinden, ist kein öffentliches PSTN-Gateway zwischen dem Vermittlungsserver und der Telefonanlage erforderlich. Eine Liste der zertifizierten Direct SIP-Partner finden Sie im [Microsoft Unified Communications Open Interoperability-Programm](https://go.microsoft.com/fwlink/p/?linkId=203309).

> [!NOTE]
> Der Medienpfad, der in dieser Abbildung dargestellt ist, hat die medienumgehung aktiviert (die empfohlene Konfiguration). Wenn Sie sich entscheiden, die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungs Server weitergeleitet.

In dieser Topologie sind ausgewählte Abteilungen oder Arbeitsgruppen für Enterprise-VoIP aktiviert. Ein PSTN-Gateway verknüpft die VoIP-fähige Arbeitsgruppe (Voice over Internet Protocol) mit der Telefonanlage. Benutzer, die für Enterprise-VoIP aktiviert sind, einschließlich Remotemitarbeitern, kommunizieren über das IP-Netzwerk. Anrufe von Enterprise-VoIP-Benutzern an das PSTN und an Kollegen, die nicht für Enterprise-VoIP aktiviert sind, werden an das entsprechende PSTN-Gateway weitergeleitet. Anrufe von Kollegen, die sich noch im PBX-System befinden, oder von Anrufern im PSTN, werden an das PSTN-Gateway weitergeleitet, das die Anrufe an den Skype for Business-Server für das Routing weiterleitet.

Es gibt zwei Empfohlene Konfigurationen für die Verbindung von Enterprise-VoIP zu einer vorhandenen PBX-Infrastruktur für die Interoperabilität: Enterprise-VoIP hinter der Telefonanlage und Enterprise-VoIP vor der Telefonanlage.

#### <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice Behind the PBX

Wenn Enterprise-VoIP hinter der Telefonanlage bereitgestellt wird, kommen alle Anrufe vom PSTN an die Telefonanlage, die Anrufe an Enterprise-VoIP-Benutzer an ein PSTN-Gateway weiterleitet, und Anrufe an PBX-Benutzer an die Telefonanlage.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice in Front of the PBX

Wenn Enterprise-VoIP vor der Telefonanlage bereitgestellt wird, gelangen alle Anrufe an das PSTN-Gateway, das Anrufe an Enterprise-VoIP-Benutzer an den Skype for Business-Server weiterleitet und Telefonanlagen Nutzer an die Telefonanlage anruft. Anrufe an das PSTN von Enterprise-VoIP-und PBX-Benutzern werden über das IP-Netzwerk an das kostengünstigste PSTN-Gateway weitergeleitet. Die folgende Tabelle zeigt die vor-und Nachteile dieser Konfiguration.

**Vor-und Nachteile der Bereitstellung von Enterprise-VoIP vor einer Telefonanlage**

|**Advantages**|**Disadvantages**|
|:-----|:-----|
|PBX bietet weiterhin Benutzern, die nicht für Enterprise-VoIP aktiviert sind.  <br/> |Vorhandene Gateways unterstützen möglicherweise nicht die gewünschten Features oder Kapazitäten.  <br/> |
|PBX handles all earlier devices.  <br/> |Erfordert einen trunk vom Gateway zur Telefonanlage und vom Gateway zum Vermittlungs Server. Möglicherweise benötigen Sie weitere Trunks des Dienstanbieters.  <br/> |
|Enterprise-VoIP-Benutzer behalten die gleichen Telefonnummern.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a> VoIP-Only Deployment

Enterprise-VoIP bietet neuen Unternehmen und auch neuen Office-Websites für vorhandene Unternehmen die Möglichkeit, eine vollständige VoIP-Lösung zu implementieren, ohne sich um die Integration von Telefonanlagen zu kümmern oder um eine beträchtliche Bereitstellung und Wartung zu vermeiden. Kosten einer IP-PBX-Infrastruktur. Diese Lösung unterstützt sowohl Website-als auch Remotemitarbeiter.

In dieser Bereitstellung werden alle Anrufe über das IP-Netzwerk weitergeleitet. Anrufe an das PSTN werden an das entsprechende PSTN-Gateway weitergeleitet. Skype for Business oder lync Phone Edition dient als Softphone. Die Remote Anrufsteuerung steht nicht zur Verfügung und ist nicht erforderlich, da es keine PBX-Telefone gibt, die von Benutzern gesteuert werden können. Voicemail-und automatische Telefonzentralendienste stehen über die optionale Bereitstellung von Exchange Unified Messaging (um) zur Verfügung.

> [!NOTE]
> Zusätzlich zur Netzwerkinfrastruktur, die für die Unterstützung von Skype for Business Server erforderlich ist, kann eine reine VoIP-Bereitstellung ein kleines, qualifiziertes Gateway zur Unterstützung von Faxgeräten und analogen Geräten verwenden.

Die folgende Abbildung zeigt eine typische Topologie für eine reine VoIP-Bereitstellung.

**VoIP-only deployment option**

![Greenfidle-Bereitstellungsoption](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> Der Medienpfad, der in dieser Abbildung dargestellt ist, hat die medienumgehung aktiviert (die empfohlene Konfiguration). Wenn Sie sich entscheiden, die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungs Server weitergeleitet.

## <a name="pstn-gateway-deployment-options"></a>PSTN Gateway deployment options

### <a name="pstn-gateways"></a>PSTN Gateways

PSTN-Gateways (Public Switched Telephone Network) sind Hardwarekomponenten von Drittanbietern, die Signale und Medien zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN übersetzen, entweder direkt oder über die Verbindung zu SIP-Stämmen. In beiden Topologien beendet das Gateway das PSTN. Das Gateway ist in seinem eigenen Subnetz isoliert und wird über den Vermittlungs Server mit dem Unternehmensnetzwerk verbunden.

In einem Unternehmen mit mehreren Websites werden in der Regel mindestens ein Gateway an jedem Standort bereitgestellt. Zweigstellenstandorte können eine Verbindung mit dem PSTN entweder über ein Gateway oder über eine Survivable Branch-Appliance herstellen, die Gateway und Server in einem einzigen Feld kombiniert. Wenn Verzweigungs Websites ein Gateway verwenden, sind auf der Website sowohl eine Registrierungsstelle als auch ein Vermittlungs Server erforderlich, es sei denn, die WAN-Verbindung ist widerstandsfähig. Auf einem oder mehreren Vermittlungsservern, die sich auf Front-End-Servern befinden, können Anrufe an die einen oder mehrere Gateways an jedem Standort weitergeleitet werden. Wir empfehlen, dass die auf der Website erforderliche Registrierungsstelle, der Vermittlungs Server und das Gateway als Survivable Branch Appliance bereitgestellt werden.

Die Ermittlung von Anzahl, Größe und Standort von PSTN-Gateways ist vielleicht die wichtigste und kostspieligste Entscheidung, die Sie bei der Planung Ihrer Enterprise-VoIP-Infrastruktur treffen müssen.

Here are the main questions to consider. Beachten Sie, dass die Antworten auf diese Fragen alle voneinander abhängig sind.

- How many PSTN gateways are needed? Die Antwort richtet sich nach der Anzahl der Benutzer, der voraussichtlichen Anzahl von gleichzeitigen anrufen (Traffic Load) und der Anzahl der Websites (jeder Standort benötigt einen).

- What size should the gateways be? Die Antwort hängt von der Anzahl der Benutzer auf der Website und von der Auslastung des Datenverkehrs ab.

- Where should the gateways be located? Die Antwort hängt teilweise von der Topologie und teilweise von der geografischen Verteilung Ihrer Organisation ab.

   You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).

#### <a name="mn-trunk-support"></a>M:N Trunk Support

Die Vermittlungsserver können Anrufe über mehrere Gateways (Session Border Controllers, SBCS), die von Internet-Telefoniedienst-Anbietern bereitgestellt werden, oder eine Kombination der beiden leiten. Darüber hinaus können mehrere Vermittlungsserver im Pool mit mehreren Gateways interagieren. Die logische Route, die zwischen einem Vermittlungs Server und einem Gateway definiert wird, wird als trunk bezeichnet. Wenn ein interner Benutzer einen PSTN-Anruf annimmt, wählt die ausgehende Routinglogik im Front-End-Pool aus, welcher trunk über alle möglichen Kombinationen weitergeleitet werden soll, die möglicherweise für das Routing dieses bestimmten Anrufs verfügbar sind. Wenn ein Anruf aufgrund eines Problems mit einem bestimmten Vermittlungsserver im Pool durch einen DNS-Lastenausgleich nicht erreicht wird, wird der Anruf an einen alternativen Vermittlungsserver im Pool wiederholt.

Details zur Planung mehrerer Gateways finden Sie unter [M:N trunk in Skype for Business Server](m-n-trunk.md).

Details zu weiteren Verbesserungen des ausgehenden Routings finden Sie unter [Anrufrouten](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).

#### <a name="gateway-topologies"></a>Gateway Topologies

Führen Sie die folgenden Schritte aus, wenn Sie die grundlegenden Fragen der Gateway-Bereitstellung beachten:

1. Zählen Sie die Websites, auf denen Sie PSTN-Konnektivität mithilfe von Enterprise-VoIP bereitstellen möchten.

2. Schätzen Sie den Datenverkehr an jeder Website (Anzahl der Benutzer und durchschnittliche Anzahl von Anrufen pro Stunde pro Benutzer).

3. Bereitstellen eines oder mehrerer Gateways an jedem Standort, um den erwarteten Datenverkehr zu verarbeiten

Bei dieser Topologie werden Anrufe zwischen Mitarbeitern an jedem Standort und zwischen Websites über Ihr Intranet weitergeleitet. Anrufe an das PSTN werden über das Enterprise IP-Netzwerk an die Gateways weitergeleitet, die dem Standort der Zielrufnummern am nächsten sind. Was aber, wenn Ihre Organisation Dutzende oder Hunderte oder sogar Tausende von Websites unterstützt, die sich über einen oder mehrere Kontinente verteilen, wie es viele Finanzinstitute und andere große Unternehmen tun? In solchen Fällen ist die Bereitstellungeines separaten Gateways an jedem Standort nicht praktikabel.

Um dieses Problem zu beheben, bevorzugen viele große Unternehmen die Bereitstellung von einem oder wenigen großen zentralen Telefonie-Websites.

In dieser Topologie sind mehrere große Gateways, die für die erwartete Benutzerauslastung ausreichend sind, an jedem zentralen Standort bereitgestellt. Alle Anrufe an Benutzer im Unternehmen werden vom Telefondienstanbieter des Unternehmens an einen zentralen Standort weitergeleitet. Die Routing Logik am zentralen Standort bestimmt, ob der Anruf über das Intranet oder das PSTN weitergeleitet werden soll.

#### <a name="gateway-location"></a>Gateway Location

Der Gateway-Speicherort kann auch die von Ihnen ausgewählten Typen von Gateways und Ihre Konfiguration ermitteln. Es gibt Dutzende von PSTN-Protokollen, von denen keiner weltweit Standard ist. Wenn sich alle Ihre Gateways in einem einzelnen Land/einer Region befinden, handelt es sich nicht um ein Problem, aber wenn Sie Gateways in verschiedenen Ländern/Regionen finden, müssen die einzelnen Gateways entsprechend den PSTN-Standards für dieses Land/diese Region konfiguriert werden. Darüber hinaus sind Gateways, die für den Einsatz in Kanada zertifiziert sind, möglicherweise nicht in Indien, Brasilien oder der Europäischen Union zertifiziert.

#### <a name="gateway-size-and-number"></a>Gateway Size and Number

Die PSTN-Gateways, die in den meisten Organisationen für die Bereitstellung von Bereichsgröße von 2 bis so viele 960-Ports in Frage kommen. (Es gibt sogar größere Gateways, die aber hauptsächlich von Telefondienstanbietern verwendet werden.) Verwenden Sie die folgenden Richtlinien, wenn Sie die Anzahl der von Ihrer Organisation benötigten Ports schätzen:

- Organisationen mit leichter Telefonie-Nutzung (ein PSTN-Anruf pro Benutzer pro Stunde) sollten für alle 15 Benutzer einen Port zuteilen. Wenn Sie beispielsweise 20 Benutzer haben, benötigen Sie ein Gateway mit zwei Anschlüssen.

- Organisationen mit mittlerer Telefonie-Nutzung (zwei PSTN-Anrufe pro Benutzer pro Stunde) sollten einem Port für alle 10 Nutzer zugeteilt werden. Wenn Sie beispielsweise über 100-Benutzer verfügen, benötigen Sie insgesamt 10 Ports, die einem oder mehreren Gateways zugewiesen sind.

- Organisationen mit hoher Telefonnutzung (drei oder mehr PSTN-Anrufe pro Benutzer pro Stunde) sollten für alle fünf Benutzer einen Port zuteilen. Wenn Sie beispielsweise über 47.000-Benutzer verfügen, benötigen Sie insgesamt 9.400-Ports, die unter mindestens 10 große Gateways zugeteilt sind.

- Zusätzliche Ports können abgerufen werden, wenn die Anzahl der Benutzer oder der Datenverkehr in Ihrer Organisation zunimmt.

Für eine bestimmte Anzahl von Benutzern, die Sie unterstützen müssen, haben Sie die Wahl, weniger, größere Gateways oder kleinere bereitzustellen. In der Regel werden mindestens zwei Gateways für eine Organisation empfohlen, um die Verfügbarkeit zu gewährleisten, wenn ein Gateway ausfällt.

Jedes von Ihnen bereitgestellte PSTN-Gateway muss mindestens über einen entsprechenden Vermittlungs Server verfügen.


