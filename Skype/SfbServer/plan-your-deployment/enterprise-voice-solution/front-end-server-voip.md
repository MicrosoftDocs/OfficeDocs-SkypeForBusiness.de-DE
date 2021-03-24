---
title: Front-End-Server-VoIP-Komponenten für Skype for Business Server
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
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Erfahren Sie mehr Enterprise-VoIP Komponenten, die sich auf Front-End-Servern in Skype for Business Server befinden, einschließlich Übersetzungsdienst und verschiedenen Routingkomponenten.
ms.openlocfilehash: 830f54e59e0d2135e3748fd03474b19e22741136
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101491"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Front-End-Server-VoIP-Komponenten für Skype for Business Server

Erfahren Sie mehr Enterprise-VoIP Komponenten, die sich auf Front-End-Servern in Skype for Business Server befinden, einschließlich Übersetzungsdienst und verschiedenen Routingkomponenten.

Die VoIP-Komponenten auf Front-End-Servern sind wie folgt:

- Übersetzungsdienst

- Eingangsroutingkomponente

- Ausgangsroutingkomponente

- Routingkomponente für Exchange UM

- Komponente für das clusterübergreifende Routing

- [Vermittlungsserverkomponente in Skype for Business Server](mediation-server.md)

## <a name="translation-service"></a>Übersetzungsdienst

Der Übersetzungsdienst ist die Serverkomponente, die eine gewählte Nummer gemäß den vom Administrator definierten Normalisierungsregeln in das E.164-Format oder ein anderes Format übersetzt. Der Übersetzungsdienst kann in andere Formate als E.164 übersetzen, wenn in Ihrer Organisation ein privates Nummernsystem oder ein Gateway bzw. eine Nebenstellenanlage verwendet wird, das bzw. die E.164 nicht unterstützt.

## <a name="inbound-routing-component"></a>Eingangsroutingkomponente

Die eingehende Routingkomponente verarbeitet eingehende Anrufe im Wesentlichen gemäß den Einstellungen, die von Benutzern auf den Enterprise-VoIP-Clients festgelegt sind. Diese Komponente unterstützt außerdem das Delegieren von Anrufen und das gleichzeitige Klingeln, sofern vom Benutzer konfiguriert. Beispielsweise geben Benutzer an, ob unbeantwortete Anrufe weitergeleitet oder lediglich zur Benachrichtigung protokolliert werden sollen. Wenn die Anrufumleitungen aktiviert ist, können Benutzer angeben, ob nicht beantwortete Anrufe an eine andere Nummer oder an einen Exchange -UM-Server weitergeleitet werden sollen, der für die Bereitstellung von Anrufanrufen konfiguriert wurde. Die Eingehende Routingkomponente wird standardmäßig auf allen Standard Edition- und Front-End-Servern installiert.

## <a name="outbound-routing-component"></a>Ausgangsroutingkomponente

Die Ausgangsroutingkomponente leitet Anrufe an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weiter. Sie wendet Anrufautorisierungsregeln gemäß der Sprachrichtlinie des Benutzers auf Anrufer an und bestimmt das optimale PSTN-Gateway für das Routing jedes Anrufs. Die Komponente für ausgehendes Routing wird standardmäßig auf allen Standard Edition- und Front-End-Servern installiert.

Die Ausgangsroutingkomponente verwendet eine Routinglogik, die größtenteils von Netzwerk- oder Telefonieadministratoren gemäß den Anforderungen ihrer Organisationen konfiguriert wird.

## <a name="exchange-um-routing-component"></a>Routingkomponente für Exchange UM

Die Exchange UM-Routingkomponente übernimmt das Routing zwischen Skype for Business Server und Servern mit Exchange Unified Messaging (UM), um Skype for Business Server in Unified Messaging-Features zu integrieren.

Die Exchange UM-Routingkomponente übernimmt auch die Umleitung von Voicemail über das PSTN, wenn Exchange -UM-Server nicht verfügbar sind. Wenn Sie über Enterprise-VoIP an Zweigstellenstandorten verfügen, die über keine ausfallsichere WAN-Verbindung zu einem zentralen Standort verfügen, bietet die Survivable Branch Appliance, die Sie am Zweigstellenstandort bereitstellen, Voicemail-Survivabilität für Zweigstellenbenutzer während eines WAN-Ausfalls. Wenn die WAN-Verbindung nicht verfügbar ist, führt die Survivable Branch Appliance folgende Aufgaben aus:

- Nicht beantwortete Anrufe werden über das Telefonfestnetz an den Exchange Unified Messaging-Server am zentralen Standort weitergeleitet

- Benutzer haben die Möglichkeit, Voicemailnachrichten über das Telefonfestnetz abzurufen

- Benachrichtigungen zu verpassten Anrufen werden in einer Warteschlange platziert und auf den Exchange UM-Server hochgeladen, wenn die WAN-Verbindung wieder verfügbar ist

Um die Voicemailumleitung zu aktivieren, empfiehlt es sich, dass Ihr Exchange-Administrator Exchange UM automatische Telefonzentrale (AA) so konfiguriert, dass nur Nachrichten akzeptiert werden.

Ausführliche Informationen zu diesen Features finden Sie unter [On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) bzw. [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency).

## <a name="intercluster-routing-component"></a>Komponente für das clusterübergreifende Routing

Die Routingkomponente intercluster ist für das Routing von Anrufen an den primären Registrierungsstellenpool des Anrufers verantwortlich. Wenn dies nicht verfügbar ist, leitet die Komponente den Anruf an den Sicherungsregistrierungsstellenpool des Anrufers weiter. Wenn die primären Und Sicherungsregistrierungspools des Anrufers über das IP-Netzwerk nicht erreichbar sind, leitet die Routingkomponente intercluster den Anruf über das PSTN erneut an die Telefonnummer des Benutzers weiter.

## <a name="other-front-end-server-components-required-for-voip"></a>Andere für VoIP erforderliche Front-End-Serverkomponenten

Weitere Komponenten, die sich auf dem Front-End-Server oder Director befinden, die wesentliche Unterstützung für VoIP bereitstellen, aber nicht selbst VoIP-Komponenten sind, umfassen Folgendes:

- **Benutzerdienste.** Die Benutzerdienste führen eine umgekehrte Nummernsuche für die Zielrufnummer jedes eingehenden Anrufs durch und ordnen diese Nummer dem SIP-URI des Zielbenutzers zu. Mithilfe dieser Informationen verteilt die Eingehende Routingkomponente den Anruf an die registrierten SIP-Endpunkte dieses Benutzers. Benutzerdienste sind eine Kernkomponente auf allen Front-End-Servern und Directors.

- **Benutzerreplikatetor.** Extrahiert Benutzertelefonnummern aus Active Directory-Domänendiensten und schreibt sie in Tabellen in der RTC-Datenbank, wo sie für Benutzerdienste und Adressbuchserver verfügbar sind. Der Benutzerreplikatetor ist eine Kernkomponente auf allen Front-End-Servern.

- **Adressbuchserver.** Stellt globale Adresslisteninformationen von Active Directory-Domänendiensten für Skype for Business Server-Clients zur Verfügung. Außerdem werden Benutzer- und Kontaktinformationen aus der RTC-Datenbank abgerufen, die Informationen in die Adressbuchdateien geschrieben und dann in einem freigegebenen Ordner gespeichert, in dem sie von Skype for Business-Clients heruntergeladen werden. Der Adressbuchserver schreibt die Informationen in die RTCAb-Datenbank, die vom Adressbuchwebabfragedienst verwendet wird, um auf Benutzersuchabfragen von Skype for Business mobile zu reagieren. Optional normalisiert es Unternehmensbenutzertelefonnummern, die zur Bereitstellung von Benutzerkontakten in Skype for Business in die RTC-Datenbank geschrieben werden. Der Adressbuchdienst wird standardmäßig auf allen Front-End-Servern installiert. Der Adressbuchwebabfragedienst wird standardmäßig mit den Webdiensten auf jedem Front-End-Server installiert.