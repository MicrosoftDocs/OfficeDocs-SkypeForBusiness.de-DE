---
title: Direkte SIP-Verbindungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Direkte SIP-Verbindungen werden zwischen Skype for Business Server und sowohl PSTN-Gateways als auch IP-PBX in Enterprise-VoIP.
ms.openlocfilehash: 7a70a6f3afd303ef5847993240b26b47d1b4ceac
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096415"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Direkte SIP-Verbindungen in Skype for Business Server

Direkte SIP-Verbindungen werden zwischen Skype for Business Server und sowohl PSTN-Gateways als auch IP-PBX in Enterprise-VoIP.

Sie können direkte SIP-Verbindungen verwenden, um Skype for Business Server mit einer der folgenden Verbindungen zu verbinden:

- IP-Nebenstellenanlage

- PSTN-Gateway

Um eine direkte SIP-Verbindung zu implementieren, führen Sie im Wesentlichen die gleichen Bereitstellungsschritte aus wie beim Implementieren eines SIP-Trunks. In beiden Fällen implementieren Sie die Verbindung mithilfe der externen Schnittstelle eines Vermittlungsservers. Der einzige Unterschied besteht in der Verbindung von SIP-Trunks mit einer externen Entität, z. B. einem ITSP-Gateway, und sie verbinden direkte SIP-Verbindungen mit einer internen Entität innerhalb Ihres lokalen Netzwerks, z. B. einer IP-PBX oder einem PstN-Gateway (Public Switched Telephone Network).

## <a name="direct-sip-deployment-options"></a>Direkte SIP-Bereitstellungsoptionen

### <a name="skype-for-business-server-stand-alone"></a>Skype for Business Server Stand-Alone
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Wenn Ihre Organisation eine der in diesem Abschnitt beschriebenen Bereitstellungen verwendet, können Sie Skype for Business Server als einzige Telefonielösung für einen Teil oder die ganze Organisation verwenden. In diesem Abschnitt werden die folgenden Bereitstellungen ausführlich beschrieben:

- **Inkrementelle Bereitstellung:** Bei dieser Option wird davon ausgegangen, dass Sie über eine vorhandene Private Branch Exchange (PBX)-Infrastruktur verfügen und beabsichtigen, Enterprise-VoIP kleineren Gruppen oder Teams in Ihrer Organisation inkrementell einzuführen.

- **Nur-VoIP-Bereitstellung:** Bei dieser Option wird davon ausgegangen, dass Enterprise-VoIP an einem Standort ohne herkömmliche Telefonieinfrastruktur bereitgestellt werden.

#### <a name="incremental-deployment"></a>Inkrementelle Bereitstellung

In der inkrementellen Bereitstellung ist Skype for Business Server die einzige Telefonielösung für einzelne Teams oder Abteilungen, während die restlichen Benutzer in einer Organisation weiterhin eine Nebenstellenanlage verwenden. Diese inkrementelle Bereitstellungsstrategie bietet eine Möglichkeit, ip-Telefonie über kontrollierte Pilotprogramme in Ihr Unternehmen einzuführen. Arbeitsgruppen, deren Kommunikationsanforderungen von Microsoft Unified Communications am besten erfüllt werden, werden in Enterprise-VoIP verschoben, während andere Benutzer in der vorhandenen Nebenstellenanlage verbleiben. Zusätzliche Arbeitsgruppen können bei Bedarf zu Enterprise-VoIP migriert werden.

Die inkrementelle Option wird empfohlen, wenn Sie über klar definierte Benutzergruppen verfügen, die gemeinsame Kommunikationsanforderungen haben und sich für die zentrale Verwaltung n nen. Diese Option ist auch wirksam, wenn Sie über Teams oder Abteilungen verfügen, die sich über große geografische Bereiche verteilen, wobei die Einsparungen bei den Ferngebühren erheblich sein können. Tatsächlich ist diese Option nützlich, um virtuelle Teams zu erstellen, deren Mitglieder möglicherweise auf der ganzen Welt verteilt sind. Sie können solche Teams in reaktion auf sich ändernde Geschäftsanforderungen schnell erstellen, ändern oder auflösen.

Die folgende Abbildung zeigt die generische Topologie für die Bereitstellung von Enterprise-VoIP hinter einer Nebenstellenanlage. Dies ist die empfohlene Topologie für die inkrementelle Bereitstellung.

**Inkrementelle Bereitstellungsoption**

![Diagramm "Abteilungsmigrationsoption"](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Wenn Sie Ihre Skype for Business Server-Bereitstellung mit einem zertifizierten Direct SIP-Partner verbinden, ist kein PstN-Gateway (Public Switched Telephone Network) zwischen dem Vermittlungsserver und der Nebenstellenanlage erforderlich. Eine Liste der zertifizierten Direct SIP-Partner finden Sie im  [Microsoft Unified Communications Open Interoperability Program](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).

> [!NOTE]
> Für den in dieser Abbildung angezeigten Medienpfad ist die Medienumgehung aktiviert (empfohlene Konfiguration). Wenn Sie die Medienumgehung deaktivieren möchten, wird der Medienpfad über den Vermittlungsserver geroutet.

In dieser Topologie sind ausgewählte Abteilungen oder Arbeitsgruppen für die Enterprise-VoIP. Ein PSTN-Gateway verbindet die VoIP-aktivierte Arbeitsgruppe (Voice over Internet Protocol) mit der Nebenstellenanlage. Benutzer, die für Enterprise-VoIP aktiviert sind, einschließlich Remotemitarbeiter, kommunizieren über das IP-Netzwerk. Anrufe von Enterprise-VoIP an das PSTN und an Kollegen, die nicht für Enterprise-VoIP aktiviert sind, werden an das entsprechende PSTN-Gateway geroutet. Anrufe von Kollegen, die sich noch im Nebenstellensystem befinden, oder von Anrufern im PSTN werden an das PSTN-Gateway weitergeleitet, das die Anrufe zum Routing an Skype for Business Server weiterleite.

Es gibt zwei empfohlene Konfigurationen zum Verbinden von Enterprise-VoIP mit einer vorhandenen Nebenstellenanlageinfrastruktur für die Interoperabilität: Enterprise-VoIP hinter der Nebenstellenanlage und Enterprise-VoIP vor der Nebenstellenanlage.

#### <a name="enterprise-voice-behind-the-pbx"></a>Enterprise-VoIP hinter der Nebenstellenanlage

Wenn Enterprise-VoIP hinter der Nebenstellenanlage bereitgestellt wird, gelangen alle Anrufe aus dem PSTN an die Nebenstellenanlage, die Anrufe an Enterprise-VoIP-Benutzer an ein PSTN-Gateway weiter leitet, und Anrufe an Nebenstellenanlagenbenutzer an die Nebenstellenanlage.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise-VoIP vor der Nebenstellenanlage

Wenn Enterprise-VoIP vor der Nebenstellenanlage bereitgestellt wird, gelangen alle Anrufe an das PSTN-Gateway, das Anrufe von Enterprise-VoIP-Benutzern an Skype for Business Server und Anrufe für PbX-Benutzer an die Nebenstellenanlage weiter leitet. Anrufe von Benutzern von Enterprise-VoIP und Nebenstellenanlagen an das PSTN werden über das IP-Netzwerk an das kostengünstigste PSTN-Gateway geroutet. Die folgende Tabelle zeigt die Vor- und Nachteile dieser Konfiguration.

**Vor- und Nachteile der Bereitstellung Enterprise-VoIP Vor- und Nebenstellenanlage**

|**Vorteile**|**Nachteile**|
|:-----|:-----|
|Nebenstellenanlagen dienen weiterhin Benutzern, die nicht für die Enterprise-VoIP.  <br/> |Vorhandene Gateways unterstützen möglicherweise nicht die features oder kapazität, die Sie möchten.  <br/> |
|PbX verarbeitet alle früheren Geräte.  <br/> |Erfordert einen Trunk vom Gateway zur Nebenstellenanlage und vom Gateway zum Vermittlungsserver. Möglicherweise benötigen Sie weitere Trunks vom Dienstanbieter.  <br/> |
|Enterprise-VoIP benutzer behalten die gleichen Telefonnummern.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>VoIP-Only Bereitstellung

Enterprise-VoIP bietet neuen Unternehmen und auch neuen Bürostandorten für bestehende Unternehmen die Möglichkeit, eine umfassende VoIP-Lösung zu implementieren, ohne sich Gedanken über die PbX-Integration machen zu müssen oder die erheblichen Bereitstellungs- und Wartungskosten einer IP-PBX-Infrastruktur zu verursachen. Diese Lösung unterstützt sowohl Mitarbeiter vor Ort als auch Remotemitarbeiter.

In dieser Bereitstellung werden alle Anrufe über das IP-Netzwerk geroutet. Anrufe an das PSTN werden an das entsprechende PSTN-Gateway geroutet. Skype for Business oder Lync Phone Edition dient als Softphone. Die Remoteanrufsteuerung ist nicht verfügbar und nicht erforderlich, da benutzer keine Nebenstellentelefone steuern können. Voicemail- und automatische Telefoniedienste sind über die optionale Bereitstellung von Exchange Unified Messaging (UM) verfügbar.

> [!NOTE]
> Zusätzlich zur Netzwerkinfrastruktur, die für die Unterstützung von Skype for Business Server erforderlich ist, kann eine Nur-VoIP-Bereitstellung ein kleines, qualifiziertes Gateway verwenden, um Faxgeräte und analoge Geräte zu unterstützen.

Die folgende Abbildung zeigt eine typische Topologie für eine Nur-VoIP-Bereitstellung.

**Nur-VoIP-Bereitstellungsoption**

![Greenfidle-Bereitstellungsoption](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> Für den in dieser Abbildung angezeigten Medienpfad ist die Medienumgehung aktiviert (empfohlene Konfiguration). Wenn Sie die Medienumgehung deaktivieren möchten, wird der Medienpfad über den Vermittlungsserver geroutet.

## <a name="pstn-gateway-deployment-options"></a>Bereitstellungsoptionen für das PSTN-Gateway

### <a name="pstn-gateways"></a>PSTN-Gateways

PstN-Gateways (Public Switched Telephone Network) sind Hardwarekomponenten von Drittanbietern, die Signalisierung und Medien zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN entweder direkt oder über eine Verbindung mit SIP-Trunks übersetzen. In beiden Topologien stellt das Gateway den Endpunkt für das Telefonfestnetz dar. Das Gateway ist in einem eigenen Subnetz isoliert und über den Vermittlungsserver mit dem Unternehmensnetzwerk verbunden.

In einem Unternehmen mit mehreren Standorten wird üblicherweise mindestens ein Gateway pro Standort bereitgestellt. Zweigstellenstandorte können eine Verbindung mit dem PSTN entweder über ein Gateway oder über eine Survivable Branch Appliance herstellen, die Gateway und Server in einem einzigen Feld kombiniert. Wenn Zweigstellenstandorte ein Gateway verwenden, sind sowohl eine Registrierungsstelle als auch ein Vermittlungsserver vor Ort erforderlich, es sei denn, die WAN-Verbindung ist ausfallsicher. Mindestens ein Vermittlungsserver, der auf Front-End-Servern zusammengeknallt ist, kann Anrufe für die ein oder mehrere Gateways an jedem Standort routen. Es wird empfohlen, dass die registrierungs-, Vermittlungsserver- und Gateways, die vor Ort erforderlich sind, als Survivable Branch Appliance bereitgestellt werden.

Die Bestimmung der Anzahl, Größe und des Standorts von PSTN-Gateways ist möglicherweise die wichtigste und kostspieligste Entscheidung, die Sie beim Planen Ihrer Enterprise-VoIP treffen müssen.

Sie müssen folgende wichtige Fragen bedenken. Keine dieser Fragen kann unabhängig von den anderen beantwortet werden.

- Wie viele PSTN-Gateways sind erforderlich? Die Antwort richtet sich nach der Anzahl von Benutzern, der erwarteten Anzahl gleichzeitiger Anrufe (Datenverkehr) und der Anzahl von Standorten (jeder Standort benötigt ein Gateway).

- Wie groß sollen die Gateways sein? Die Antwort richtet sich nach der Anzahl von Benutzern am Standort und dem zu erwartenden Datenverkehr.

- Wo sollen sich die Gateways befinden? Die Antwort richtet sich zum Teil nach der Topologie und zum Teil nach der geografischen Verteilung Ihrer Organisation.

  Sie sollten auch die Optionen für die Gatewaytopologie berücksichtigen (weitere Informationen hierzu finden Sie im Abschnitt "Gatewaytopologien" weiter unten in diesem Thema).

#### <a name="mn-trunk-support"></a>M:N-Trunkunterstützung

Die Vermittlungsserver können Anrufe über mehrere Gateways, Von Internettelefoniedienstanbietern bereitgestellte Session Border Controller (SBCs) oder eine Kombination aus beiden routen. Darüber hinaus können mehrere Vermittlungsserver im Pool mit mehreren Gateways interagieren. Die logische Route, die zwischen einem Vermittlungsserver und einem Gateway definiert ist, wird als Trunk bezeichnet. Wenn ein interner Benutzer einen PSTN-Anruf abnimmt, wählt die ausgehende Routinglogik im Front-End-Pool aus allen möglichen Kombinationen, die für das Routing dieses bestimmten Anrufs verfügbar sein können, den Trunk aus, um ihn weiter zu routen. Wenn beim DNS-Lastenausgleich ein Anruf aufgrund eines Problems mit einem bestimmten Vermittlungsserver im Pool kein Gateway erreicht, wird der Anruf an einen alternativen Vermittlungsserver im Pool wiederholt.

Weitere Informationen zur Planung mehrerer Gateways finden Sie unter [M:N trunk in Skype for Business Server](m-n-trunk.md).

Ausführliche Informationen zu weiteren Verbesserungen beim Ausgangsrouting finden Sie unter [Call Routes](/previous-versions/office/lync-server-2013/lync-server-2013-voice-routes).

#### <a name="gateway-topologies"></a>Gatewaytopologien

Halten Sie sich bei Ihren Überlegungen zu den grundlegenden Fragen zur Gatewaybereitstellung an die folgenden Schritte:

1. Zählen Sie die Standorte, an denen Sie eine PSTN-Verbindung mithilfe von Enterprise-VoIP.

2. Schätzen Sie den zu erwartenden Datenverkehr für jeden Standort (Anzahl von Benutzern und durchschnittliche Anzahl von Anrufen pro Stunde und Benutzer).

3. Stellen Sie mindestens ein Gateway an jedem Standort bereit, um den zu erwartenden Datenverkehr zu verarbeiten.

In dieser Topologie werden alle Anrufe zwischen Mitarbeitern innerhalb jedes Standorts sowie zwischen den Standorten über Ihr Intranet weitergeleitet. Anrufe in das Telefonfestnetz werden über das IP-Unternehmensnetzwerk an die Gateways weitergeleitet, die dem Standort der Zielrufnummern am nächsten sind. Wie sollte die Bereitstellung jedoch aussehen, wenn Ihre Organisation Dutzende, Hunderte oder sogar Tausende von Standorten unterstützt, die über mehrere Kontinente verteilt sind – was beispielsweise bei vielen Finanzinstituten und anderen großen Unternehmen der Fall ist? In solchen Fällen ist es nicht empfehlenswert, an jedem Standort ein separates Gateway bereitzustellen.

Um dieses Problem zu beheben, bevorzugen viele große Unternehmen die Bereitstellung eines oder weniger großer Telefoniestandorte.

In dieser Topologie werden an jedem zentralen Standort mehrere große Gateways bereitgestellt, die für die erwartete Benutzerlast ausreichen. Alle Anrufe bei Benutzern im Unternehmen werden durch den Telefondienstanbieter des Unternehmens an einen zentralen Standort weitergeleitet. Die Routinglogik am zentralen Standort bestimmt, ob der Anruf über das Intranet oder an das PSTN weitergeleitet werden soll.

#### <a name="gateway-location"></a>Gatewaystandort

Auch der Gatewaystandort bestimmt möglicherweise, welche Typen von Gateways Sie auswählen und wie Sie diese konfigurieren können. Es gibt Dutzende von PSTN-Protokollen, von denen jedoch keines weltweiter Standard ist. Wenn sich all Ihre Gateways in einem einzigen Land bzw. einer einzigen Region befinden, stellt dies kein Problem dar. Wenn Sie jedoch Gateways in mehreren Ländern/Regionen platzieren, muss jedes Gateway gemäß den dort verwendeten PSTN-Standards konfiguriert werden. Außerdem sind die Gateways, die beispielsweise für den Betrieb in Kanada zugelassen sind, in Indien, Brasilien oder der Europäischen Union möglicherweise nicht zugelassen.

#### <a name="gateway-size-and-number"></a>Größe und Anzahl von Gateways

Die Größe der PSTN-Gateways, deren Bereitstellung für die meisten Organisationen in Betracht kommt, liegt im Bereich von 2 bis 960 Ports. (Es gibt sogar noch größere Gateways; diese werden jedoch hauptsächlich von Telefonanbietern verwendet.) Um zu schätzen, wie viele Ports in Ihrer Organisation benötigt werden, beachten Sie die folgenden Richtlinien:

- Wenn in Ihrer Organisation wenig telefoniert wird (ein PSTN-Anruf pro Benutzer und Stunde), sollten Sie einen Port für jeweils 15 Benutzer zuordnen. Wenn beispielsweise 20 Benutzer vorhanden sind, benötigen Sie ein Gateway mit zwei Ports.

- Wenn in Ihrer Organisation mäßig viel telefoniert wird (zwei PSTN-Anrufe pro Benutzer und Stunde), sollten Sie einen Port für jeweils 10 Benutzer zuordnen. Wenn beispielsweise 100 Benutzer vorhanden sind, benötigen Sie insgesamt 10 Ports, die Sie auf einem oder auf mehreren Gateways zuordnen können.

- Wenn in Ihrer Organisation viel telefoniert wird (mindestens drei PSTN-Anrufe pro Benutzer und Stunde), sollten Sie einen Port für jeweils 5 Benutzer zuordnen. Wenn beispielsweise 47.000 Benutzer vorhanden sind, benötigen Sie insgesamt 9.400 Ports, die Sie auf mindestens 10 großen Gateways zuordnen sollten.

- Zusätzliche Ports können erworben werden, wenn die Benutzeranzahl oder der Umfang des Datenverkehrs in Ihrer Organisation steigt.

Für jede zu unterstützende Benutzeranzahl können Sie entweder wenige größere Gateways oder mehrere kleine bereitstellen. Prinzipiell werden für jede Organisation mindestens zwei Gateways empfohlen, um die Verfügbarkeit sicherzustellen, falls ein Gateway ausfällt.

Jedes bereitgestellte PSTN-Gateway muss über mindestens einen entsprechenden Vermittlungsserver verfügen.