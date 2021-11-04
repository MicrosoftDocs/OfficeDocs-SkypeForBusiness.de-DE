---
title: VoIP-Komponenten des Front-End-Servers für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Erfahren Sie mehr über die Enterprise-VoIP Komponenten, die sich auf Front-End-Servern in Skype for Business Server befinden, einschließlich Übersetzungsdienst und verschiedene Routingkomponenten.
ms.openlocfilehash: cb57e3c4d06ff77661453321a7b4f3254c780822
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751564"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>VoIP-Komponenten des Front-End-Servers für Skype for Business Server

Erfahren Sie mehr über die Enterprise-VoIP Komponenten, die sich auf Front-End-Servern in Skype for Business Server befinden, einschließlich Übersetzungsdienst und verschiedene Routingkomponenten.

Die VoIP-Komponenten, die sich auf Front-End-Servern befinden, sind wie folgt:

- Übersetzungsdienst

- Eingangsroutingkomponente

- Ausgangsroutingkomponente

- Routingkomponente für Exchange UM

- Komponente für das clusterübergreifende Routing

- [Vermittlungsserverkomponente in Skype for Business Server](mediation-server.md)

## <a name="translation-service"></a>Übersetzungsdienst

Der Übersetzungsdienst ist die Serverkomponente, die eine gewählte Nummer gemäß den vom Administrator definierten Normalisierungsregeln in das E.164-Format oder ein anderes Format übersetzt. Der Übersetzungsdienst kann in andere Formate als E.164 übersetzen, wenn in Ihrer Organisation ein privates Nummernsystem oder ein Gateway bzw. eine Nebenstellenanlage verwendet wird, das bzw. die E.164 nicht unterstützt.

## <a name="inbound-routing-component"></a>Eingangsroutingkomponente

Die eingehende Routingkomponente verarbeitet eingehende Anrufe im Wesentlichen gemäß den Einstellungen, die von Benutzern auf den Enterprise-VoIP-Clients festgelegt sind. Diese Komponente unterstützt außerdem das Delegieren von Anrufen und das gleichzeitige Klingeln, sofern vom Benutzer konfiguriert. Beispielsweise geben Benutzer an, ob unbeantwortete Anrufe weitergeleitet oder lediglich zur Benachrichtigung protokolliert werden sollen. Wenn die Anrufweiterleitung aktiviert ist, können Benutzer angeben, ob nicht beantwortete Anrufe an eine andere Nummer oder an einen Exchange UM-Server weitergeleitet werden sollen, der für die Anrufannahme konfiguriert wurde. Die Eingehende Routingkomponente wird standardmäßig auf allen Standard Edition- und Front-End-Servern installiert.

## <a name="outbound-routing-component"></a>Ausgangsroutingkomponente

Die Ausgangsroutingkomponente leitet Anrufe an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weiter. Sie wendet Anrufautorisierungsregeln gemäß der VoIP-Richtlinie des Benutzers auf Anrufer an und bestimmt das optimale PSTN-Gateway für die Weiterleitung jedes Anrufs. Die Komponente für das ausgehende Routing wird standardmäßig auf allen Standard Edition- und Front-End-Servern installiert.

Die Ausgangsroutingkomponente verwendet eine Routinglogik, die größtenteils von Netzwerk- oder Telefonieadministratoren gemäß den Anforderungen ihrer Organisationen konfiguriert wird.

## <a name="exchange-um-routing-component"></a>Routingkomponente für Exchange UM

Die Exchange UM-Routingkomponente übernimmt das Routing zwischen Skype for Business Server und Servern, auf denen Exchange Unified Messaging (UM) ausgeführt wird, um Skype for Business Server in Unified Messaging-Features zu integrieren.

Die Exchange UM-Routingkomponente übernimmt auch das Umleiten von Voicemail über das PSTN, wenn Exchange UM-Server nicht verfügbar sind. Wenn Sie über Enterprise-VoIP Benutzer an Zweigstellenstandorten verfügen, die keine ausfallsichere WAN-Verbindung mit einem zentralen Standort haben, bietet die Survivable Branch Appliance, die Sie am Zweigstellenstandort bereitstellen, Voicemail-Survivability für Zweigstellenbenutzer während eines WAN-Ausfalls. Wenn die WAN-Verbindung nicht verfügbar ist, führt die Survivable Branch Appliance folgende Aufgaben aus:

- Nicht beantwortete Anrufe werden über das Telefonfestnetz an den Exchange Unified Messaging-Server am zentralen Standort weitergeleitet

- Benutzer haben die Möglichkeit, Voicemailnachrichten über das Telefonfestnetz abzurufen

- Benachrichtigungen zu verpassten Anrufen werden in einer Warteschlange platziert und auf den Exchange UM-Server hochgeladen, wenn die WAN-Verbindung wieder verfügbar ist

Um voicemailumrouting zu aktivieren, empfehlen wir, dass Ihr Exchange-Administrator Exchange automatische UM-Telefonzentrale (AA) so konfiguriert, dass nur Nachrichten akzeptiert werden.

Ausführliche Informationen zu diesen Features finden Sie unter [On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) bzw. [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency).

## <a name="intercluster-routing-component"></a>Komponente für das clusterübergreifende Routing

Die Interclusterroutingkomponente ist für das Weiterleiten von Anrufen an den primären Registrierungsstellenpool des Angerufenen verantwortlich. Wenn dies nicht verfügbar ist, leitet die Komponente den Anruf an den Sicherungsregistrierungsstellenpool des Angerufenen weiter. Wenn die primären Und Sicherungsregistrierungsstellenpools des Angerufenen über das IP-Netzwerk nicht erreichbar sind, leitet die Komponente für das clusterübergreifende Routing den Anruf über das PSTN an die Telefonnummer des Benutzers um.

## <a name="other-front-end-server-components-required-for-voip"></a>Andere für VoIP erforderliche Front-End-Serverkomponenten

Andere Komponenten, die sich auf dem Front-End-Server oder Director befinden und grundlegende Unterstützung für VoIP bereitstellen, aber selbst keine VoIP-Komponenten sind, umfassen Folgendes:

- **Benutzerdienste.** Die Benutzerdienste führen eine umgekehrte Nummernsuche für die Zielrufnummer jedes eingehenden Anrufs durch und ordnen diese Nummer dem SIP-URI des Zielbenutzers zu. Anhand dieser Informationen verteilt die Eingehende Routingkomponente den Anruf an die registrierten SIP-Endpunkte dieses Benutzers. Benutzerdienste sind eine Zentrale Komponente auf allen Front-End-Servern und Directors.

- **Benutzerreplikationsdienst.** Extrahiert Benutzertelefonnummern aus Active Directory Domain Services und schreibt sie in Tabellen in der RTC-Datenbank, in denen sie für Benutzerdienste und Adressbuchserver verfügbar sind. Der Benutzerreplikationsdienst ist eine Kernkomponente auf allen Front-End-Servern.

- **Adressbuchserver.** Stellt informationen zu globalen Adresslisten von Active Directory Domain Services für Skype for Business Server Clients bereit. Außerdem werden Benutzer- und Kontaktinformationen aus der RTC-Datenbank abgerufen, die Informationen in die Adressbuchdateien geschrieben und die Dateien dann in einem freigegebenen Ordner gespeichert, in den sie von Skype for Business Clients heruntergeladen werden. Der Adressbuchserver schreibt die Informationen in die RTCAb-Datenbank, die vom Adressbuchwebabfragedienst verwendet wird, um auf Benutzersuchabfragen von Skype for Business Mobilen zu antworten. Sie normalisiert optional Telefonnummern von Unternehmensbenutzern, die in die RTC-Datenbank geschrieben werden, um Benutzerkontakte in Skype for Business bereitzustellen. Der Adressbuchdienst wird standardmäßig auf allen Front-End-Servern installiert. Der Adressbuchwebabfragedienst wird standardmäßig mit den Webdiensten auf jedem Front-End-Server installiert.