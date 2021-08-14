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
description: Direkte SIP-Verbindungen werden zwischen Skype for Business Server und PSTN-Gateways und IP-Nebenstellenanlagen in Enterprise-VoIP unterstützt.
ms.openlocfilehash: cac0cf06843ed3bf623bd2d3bbe9e92cf6b32a091fd434ac4d422812cc59e60f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343369"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Direkte SIP-Verbindungen in Skype for Business Server

Direkte SIP-Verbindungen werden zwischen Skype for Business Server und PSTN-Gateways und IP-Nebenstellenanlagen in Enterprise-VoIP unterstützt.

Sie können direkte SIP-Verbindungen verwenden, um Skype for Business Server mit einer der folgenden Verbindungen zu verbinden:

- IP-Nebenstellenanlage

- PSTN-Gateway

Um eine direkte SIP-Verbindung zu implementieren, führen Sie im Wesentlichen die gleichen Bereitstellungsschritte wie zum Implementieren eines SIP-Trunks aus. In beiden Fällen implementieren Sie die Verbindung mithilfe der externen Schnittstelle eines Vermittlungsservers. Der einzige Unterschied besteht darin, dass Sie SIP-Trunks mit einer externen Entität wie z. B. einem ITSP-Gateway verbinden und direkte SIP-Verbindungen mit einer internen Entität in Ihrem lokalen Netzwerk verbinden, z. B. einer IP-Nebenstellenanlage oder einem PSTN-Gateway (Public Switched Telephone Network).

## <a name="direct-sip-deployment-options"></a>Optionen für die direkte SIP-Bereitstellung

### <a name="skype-for-business-server-stand-alone"></a>Skype for Business Server Stand-Alone
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Wenn Ihre Organisation eine der in diesem Abschnitt beschriebenen Bereitstellungen verwendet, können Sie Skype for Business Server als einzige Telefonielösung für einen Teil oder die gesamte Organisation verwenden. In diesem Abschnitt werden die folgenden Bereitstellungen ausführlich beschrieben:

- **Inkrementelle Bereitstellung:** Bei dieser Option wird davon ausgegangen, dass Sie über eine vorhandene PbX-Infrastruktur (Private Branch Exchange) verfügen und sie beabsichtigen, Enterprise-VoIP inkrementell für kleinere Gruppen oder Teams in Ihrer Organisation einzuführen.

- **Nur VoIP-Bereitstellung:** Bei dieser Option wird davon ausgegangen, dass Sie Enterprise-VoIP an einem Standort bereitstellen möchten, der nicht über eine herkömmliche Telefonieinfrastruktur verfügt.

#### <a name="incremental-deployment"></a>Inkrementelle Bereitstellung

Bei der inkrementellen Bereitstellung ist Skype for Business Server die einzige Telefonielösung für einzelne Teams oder Abteilungen, während die restlichen Benutzer in einer Organisation weiterhin eine Nebenstellenanlage verwenden. Diese inkrementelle Bereitstellungsstrategie bietet eine Möglichkeit, IP-Telefonie über kontrollierte Pilotprogramme in Ihr Unternehmen einzuführen. Arbeitsgruppen, deren Kommunikationsanforderungen am besten von Microsoft Unified Communications erfüllt werden, werden in Enterprise-VoIP verschoben, während andere Benutzer weiterhin auf der vorhandenen Nebenstellenanlage bleiben. Zusätzliche Arbeitsgruppen können nach Bedarf zu Enterprise-VoIP migriert werden.

Die inkrementelle Option wird empfohlen, wenn Sie klar definierte Benutzergruppen haben, die gemeinsame Kommunikationsanforderungen haben und sich für die zentrale Verwaltung eignen. Diese Option ist auch wirksam, wenn Sie über Teams oder Abteilungen verfügen, die sich über viele geografische Bereiche erstrecken, in denen die Einsparungen bei Ferngespräche erheblich sein können. Tatsächlich ist diese Option nützlich, um virtuelle Teams zu erstellen, deren Mitglieder möglicherweise auf der ganzen Welt verteilt sind. Sie können solche Teams erstellen, ändern oder auflösen, um schnell auf sich ändernde Geschäftsanforderungen zu reagieren.

Die folgende Abbildung zeigt die generische Topologie für die Bereitstellung von Enterprise-VoIP hinter einer Nebenstellenanlage. Dies ist die empfohlene Topologie für die inkrementelle Bereitstellung.

**Option für inkrementelle Bereitstellung**

![Diagramm "Abteilungsmigrationsoption"](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Wenn Sie Ihre Skype for Business Server Bereitstellung mit einem zertifizierten Direct SIP-Partner verbinden, ist kein PSTN-Gateway (Public Switched Telephone Network) zwischen dem Vermittlungsserver und der Nebenstellenanlage erforderlich. Eine Liste der zertifizierten Direct SIP-Partner finden Sie im [Microsoft Unified Communications Open Interoperability-Programm.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)

> [!NOTE]
> Für den in dieser Abbildung dargestellten Medienpfad ist die Medienumgehung aktiviert (die empfohlene Konfiguration). Wenn Sie die Medienumgehung deaktivieren, wird der Medienpfad über den Vermittlungsserver weitergeleitet.

In dieser Topologie sind ausgewählte Abteilungen oder Arbeitsgruppen für Enterprise-VoIP aktiviert. Ein PSTN-Gateway verbindet die VoIP-fähige Arbeitsgruppe (Voice over Internet Protocol) mit der Nebenstellenanlage. Benutzer, die für Enterprise-VoIP aktiviert sind, einschließlich Remotemitarbeiter, kommunizieren über das IP-Netzwerk. Anrufe von Enterprise-VoIP Benutzern an das PSTN und an Kollegen, die nicht für Enterprise-VoIP aktiviert sind, werden an das entsprechende PSTN-Gateway weitergeleitet. Anrufe von Kollegen, die sich noch im Nebenstellensystem befinden, oder von Anrufern im PSTN werden an das PSTN-Gateway weitergeleitet, das die Anrufe zum Weiterleiten an Skype for Business Server weiterleitet.

Es gibt zwei empfohlene Konfigurationen zum Verbinden von Enterprise-VoIP mit einer vorhandenen Pbx-Infrastruktur zur Interoperabilität: Enterprise-VoIP hinter der Nebenstellenanlage und Enterprise-VoIP vor der Nebenstellenanlage.

#### <a name="enterprise-voice-behind-the-pbx"></a>Enterprise-VoIP Hinter der Nebenstellenanlage

Wenn Enterprise-VoIP hinter der Nebenstellenanlage bereitgestellt wird, gelangen alle Anrufe aus dem Festnetz an die Nebenstellenanlage, die Anrufe an Enterprise-VoIP Benutzer an ein PSTN-Gateway und Anrufe an Nebenstellenanlagenbenutzer an die Nebenstellenanlage weitergibt.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise-VoIP vor der Nebenstellenanlage

Wenn Enterprise-VoIP vor der Nebenstellenanlage bereitgestellt wird, gelangen alle Anrufe an das PSTN-Gateway, das Anrufe für Enterprise-VoIP Benutzer an Skype for Business Server und Anrufe für PbX-Benutzer an die Nebenstellenanlage weitergibt. Anrufe an das PSTN von Enterprise-VoIP- und Nebenstellenanlagenbenutzern werden über das IP-Netzwerk an das kostengünstigste PSTN-Gateway weitergeleitet. Die folgende Tabelle zeigt die Vor- und Nachteile dieser Konfiguration.

**Vor- und Nachteile der Bereitstellung von Enterprise-VoIP vor Nebenstellenanlagen**

|**Vorteile**|**Nachteile**|
|:-----|:-----|
|PBX bedient weiterhin Benutzer, die nicht für Enterprise-VoIP aktiviert sind.  <br/> |Vorhandene Gateways unterstützen möglicherweise nicht die gewünschten Features oder Kapazität.  <br/> |
|PBX behandelt alle früheren Geräte.  <br/> |Erfordert einen Trunk vom Gateway zur Nebenstellenanlage und vom Gateway zum Vermittlungsserver. Möglicherweise benötigen Sie weitere Trunks vom Dienstanbieter.  <br/> |
|Enterprise-VoIP Benutzer behalten die gleichen Telefonnummern.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>VoIP-Only-Bereitstellung

Enterprise-VoIP bietet neue Unternehmen und auch neue Bürostandorte für bestehende Unternehmen, die die Möglichkeit haben, eine VoIP-Lösung mit vollem Funktionsumfang zu implementieren, ohne sich Gedanken über die PbX-Integration machen zu müssen oder die erheblichen Bereitstellungs- und Wartungskosten einer IP-Nebenstellenanlageinfrastruktur anfallen zu müssen. Diese Lösung unterstützt sowohl lokale als auch Remotemitarbeiter.

In dieser Bereitstellung werden alle Anrufe über das IP-Netzwerk weitergeleitet. Anrufe an das PSTN werden an das entsprechende PSTN-Gateway weitergeleitet. Skype for Business oder Lync Telefon Edition dient als Softphone. Die Remoteanrufsteuerung ist nicht verfügbar und unnötig, da es keine PBX-Telefone gibt, die Benutzer steuern können. Voicemail- und automatische Telefonzentralendienste sind über die optionale Bereitstellung von Exchange Unified Messaging (UM) verfügbar.

> [!NOTE]
> Zusätzlich zur Netzwerkinfrastruktur, die zur Unterstützung Skype for Business Server erforderlich ist, kann eine Nur-VoIP-Bereitstellung ein kleines, qualifiziertes Gateway verwenden, um Faxgeräte und analoge Geräte zu unterstützen.

Die folgende Abbildung zeigt eine typische Topologie für eine Nur-VoIP-Bereitstellung.

**Nur VoIP-Bereitstellungsoption**

![Greenfidle-Bereitstellungsoption](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> Für den in dieser Abbildung dargestellten Medienpfad ist die Medienumgehung aktiviert (die empfohlene Konfiguration). Wenn Sie die Medienumgehung deaktivieren, wird der Medienpfad über den Vermittlungsserver weitergeleitet.

## <a name="pstn-gateway-deployment-options"></a>Bereitstellungsoptionen für PSTN-Gateways

### <a name="pstn-gateways"></a>PSTN-Gateways

PSTN-Gateways (Public Switched Telephone Network) sind Hardwarekomponenten von Drittanbietern, die Signale und Medien zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN übersetzen, entweder direkt oder über eine Verbindung mit SIP-Trunks. In beiden Topologien stellt das Gateway den Endpunkt für das Telefonfestnetz dar. Das Gateway ist in seinem eigenen Subnetz isoliert und über den Vermittlungsserver mit dem Unternehmensnetzwerk verbunden.

In einem Unternehmen mit mehreren Standorten wird üblicherweise mindestens ein Gateway pro Standort bereitgestellt. Zweigstellen können eine Verbindung mit dem PSTN entweder über ein Gateway oder über eine Survivable Branch Appliance herstellen, die Gateway und Server in einem einzigen Feld kombiniert. Wenn Zweigstellen ein Gateway verwenden, sind sowohl eine Registrierungsstelle als auch ein Vermittlungsserver vor Ort erforderlich, es sei denn, die WAN-Verbindung ist ausfallsicher. Ein oder mehrere Vermittlungsserver, die auf Front-End-Servern verbunden sind, können Anrufe für ein oder mehrere Gateways an jedem Standort weiterleiten. Es wird empfohlen, dass die registrierungsstelle, der Vermittlungsserver und das Gateway, die vor Ort erforderlich sind, als Survivable Branch Appliance bereitgestellt werden.

Die Bestimmung der Anzahl, Größe und Desorts von PSTN-Gateways ist möglicherweise die wichtigste und teuerste Entscheidung, die Sie bei der Planung Ihrer Enterprise-VoIP Infrastruktur treffen müssen.

Sie müssen folgende wichtige Fragen bedenken. Keine dieser Fragen kann unabhängig von den anderen beantwortet werden.

- Wie viele PSTN-Gateways sind erforderlich? Die Antwort richtet sich nach der Anzahl von Benutzern, der erwarteten Anzahl gleichzeitiger Anrufe (Datenverkehr) und der Anzahl von Standorten (jeder Standort benötigt ein Gateway).

- Wie groß sollen die Gateways sein? Die Antwort richtet sich nach der Anzahl von Benutzern am Standort und dem zu erwartenden Datenverkehr.

- Wo sollen sich die Gateways befinden? Die Antwort richtet sich zum Teil nach der Topologie und zum Teil nach der geografischen Verteilung Ihrer Organisation.

  Sie sollten auch die Optionen für die Gatewaytopologie berücksichtigen (weitere Informationen hierzu finden Sie im Abschnitt "Gatewaytopologien" weiter unten in diesem Thema).

#### <a name="mn-trunk-support"></a>M:N-Trunkunterstützung

Die Vermittlungsserver können Anrufe über mehrere Gateways, Session Border Controller (SBCs) von Internettelefoniedienstanbietern oder eine Kombination der beiden weiterleiten. Darüber hinaus können mehrere Vermittlungsserver im Pool mit mehreren Gateways interagieren. Die logische Route, die zwischen einem Vermittlungsserver und einem Gateway definiert ist, wird als Trunk bezeichnet. Wenn ein interner Benutzer einen PSTN-Anruf abgibt, wählt die Logik für das ausgehende Routing im Front-End-Pool aus, welcher Trunk aus allen möglichen Kombinationen weitergeleitet werden soll, die für die Weiterleitung dieses bestimmten Anrufs verfügbar sein können. Wenn beim DNS-Lastenausgleich aufgrund eines Problems mit einem bestimmten Vermittlungsserver im Pool ein Gateway nicht erreicht wird, wird der Anruf an einen alternativen Vermittlungsserver im Pool wiederholt.

Ausführliche Informationen zur Planung mehrerer Gateways finden Sie unter [M:N-Trunk in Skype for Business Server.](m-n-trunk.md)

Ausführliche Informationen zu weiteren Verbesserungen beim Ausgangsrouting finden Sie unter [Call Routes](/previous-versions/office/lync-server-2013/lync-server-2013-voice-routes).

#### <a name="gateway-topologies"></a>Gatewaytopologien

Halten Sie sich bei Ihren Überlegungen zu den grundlegenden Fragen zur Gatewaybereitstellung an die folgenden Schritte:

1. Zählen Sie die Standorte, an denen Sie pstn-Konnektivität mithilfe von Enterprise-VoIP bereitstellen möchten.

2. Schätzen Sie den zu erwartenden Datenverkehr für jeden Standort (Anzahl von Benutzern und durchschnittliche Anzahl von Anrufen pro Stunde und Benutzer).

3. Stellen Sie mindestens ein Gateway an jedem Standort bereit, um den zu erwartenden Datenverkehr zu verarbeiten.

In dieser Topologie werden alle Anrufe zwischen Mitarbeitern innerhalb jedes Standorts sowie zwischen den Standorten über Ihr Intranet weitergeleitet. Anrufe in das Telefonfestnetz werden über das IP-Unternehmensnetzwerk an die Gateways weitergeleitet, die dem Standort der Zielrufnummern am nächsten sind. Wie sollte die Bereitstellung jedoch aussehen, wenn Ihre Organisation Dutzende, Hunderte oder sogar Tausende von Standorten unterstützt, die über mehrere Kontinente verteilt sind – was beispielsweise bei vielen Finanzinstituten und anderen großen Unternehmen der Fall ist? In solchen Fällen ist es nicht empfehlenswert, an jedem Standort ein separates Gateway bereitzustellen.

Um dieses Problem zu beheben, bevorzugen viele große Unternehmen die Bereitstellung eines oder einiger großer zentraler Telefoniestandorte.

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

Jedes PSTN-Gateway, das Sie bereitstellen, muss über mindestens einen entsprechenden Vermittlungsserver verfügen.